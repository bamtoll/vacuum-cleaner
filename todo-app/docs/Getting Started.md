# 임시로 작성해놓은 것
1. MySQL 준비
1-1. MySQL 서버 켜기
로컬에 MySQL이 설치되어 있어야 한다.

실행 여부 확인:
``` bash
bash
mysql -u root -p
비밀번호 입력 후 접속이 되면 OK.
```
1-2. DB/유저/테이블 만들기 (db/init.sql 사용)
프로젝트 루트에서 init.sql 내용을 MySQL 콘솔에 붙여 넣거나, 파일로 실행한다.

sql
-- MySQL 콘솔에서 실행
SOURCE /절대/경로/todo-app/db/init.sql;
또는 내용을 직접 붙여 넣기:

sql
CREATE DATABASE IF NOT EXISTS todo_db
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;

CREATE USER IF NOT EXISTS 'todo_user'@'localhost'
  IDENTIFIED BY 'todo_password';

GRANT ALL PRIVILEGES ON todo_db.* TO 'todo_user'@'localhost';
FLUSH PRIVILEGES;

USE todo_db;

CREATE TABLE IF NOT EXISTS todos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    completed TINYINT(1) NOT NULL DEFAULT 0,
    created_at DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
2. 백엔드 실행 (Flask)
2-1. 가상환경(선택, 있으면 좋음)
bash
cd todo-app/backend

# venv 생성 (한 번만)
python -m venv venv

# 활성화 (Windows)
venv\Scripts\activate

# 활성화 (macOS/Linux)
source venv/bin/activate
2-2. 패키지 설치
bash
cd todo-app/backend
pip install -r requirements.txt
2-3. .env 파일 만들기
todo-app/backend/.env 파일 생성 → 아래 내용 넣기:

text
DB_USER=todo_user
DB_PASSWORD=todo_password
DB_HOST=localhost
DB_PORT=3306
DB_NAME=todo_db
app.py 상단에 다음이 들어가 있는지 확인:

python
from dotenv import load_dotenv
load_dotenv()
(config.py에서 os.getenv를 쓰고 있으면 이 두 줄로 .env가 로드된다.)

2-4. Flask 서버 실행
bash
cd todo-app/backend
python app.py
정상이라면 터미널에 대략 이런 로그가 보인다:

Running on http://0.0.0.0:5000

Press CTRL+C to quit

2-5. 백엔드 정상 동작 확인
브라우저에서 열기:

http://localhost:5000/api/health

정상 응답 예:

json
{"status": "ok"}
에러가 나면, 터미널에 나온 에러 메시지를 그대로 가져오면 어디 고쳐야 하는지 같이 볼 수 있다.

3. 프론트엔드 실행 (Vite + React)
3-1. 의존성 설치
bash
cd todo-app/frontend
npm install
package.json에 있는 react, react-dom, vite 등이 설치된다.​

3-2. 개발 서버 실행
bash
cd todo-app/frontend
npm run dev
정상일 때 터미널 출력 예:

Local: http://localhost:5173/

3-3. 프론트엔드 접속
브라우저에서:

text
http://localhost:5173
화면에서:

입력창 + “추가” 버튼

아래에 할 일 목록(처음엔 비어 있음)

동작 테스트:

입력창에 “과제 하기” 입력 → “추가” 클릭

목록에 “과제 하기” 항목이 생기면 POST /api/todos 성공.

체크박스를 클릭해 완료/미완료 토글

글자가 취소선/회색으로 바뀌면 PUT /api/todos/{id} 성공.

“삭제” 버튼 클릭

항목이 목록에서 사라지면 DELETE /api/todos/{id} 성공.

4. 전체 실행 순서 요약 (한 번에 보기)
MySQL

MySQL 서버 실행

db/init.sql로 todo_db, todo_user, todos 테이블 생성

백엔드

cd todo-app/backend

pip install -r requirements.txt

.env 생성

python app.py

http://localhost:5000/api/health 확인

프론트엔드

cd todo-app/frontend

npm install (최초 1회)

npm run dev

http://localhost:5173 접속 → 기능 테스트

5. 실행하면서 자주 나오는 에러 타입
실행하다가 막히면, 아래 중 어디에 해당하는지만 확인해줘.

ModuleNotFoundError: No module named 'flask'
→ pip install -r requirements.txt 안 함, 또는 venv 안 켜고 실행.

pymysql.err.OperationalError / Access denied for user
→ DB 계정/비밀번호, DB 이름 틀림. .env와 MySQL 설정 다시 확인.

브라우저 콘솔에 CORS error
→ 백엔드 CORS 설정이 빠졌을 수 있음 (CORS(app, resources={r"/api/*": {"origins": "*"}}) 확인).

프론트에서 Failed to fetch
→ 백엔드 서버가 꺼져있거나 포트가 다름 (5000 확인)
