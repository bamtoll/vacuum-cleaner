# vacuum-cleaner
오픈소스소프트웨어 진공청소기팀
---
## 1. OSS 보고서 (‘오픈소스소프트웨어 보고서’ 구축)
- OSS 개요 # 임서현
- OSS 역사 # 김나우
- 대표적 OSS 소개 # 장주연
- OSS 저작권 # 김지연

## 2. TODO앱 제작 (실제 소프트웨어개발 구축) 
```text
todo-app/
├── README.md                # 프로젝트 설명
├── .gitignore
├── backend/                 # Flask + MySQL
│   ├── app.py               # Flask 엔트리 포인트 + 모든 API
│   ├── requirements.txt     # 백엔드 패키지 목록
│   ├── config.py            # DB 연결 설정 (MySQL)
│   └── .env
├── frontend/                # React
│   ├── package.json
│   ├── public/
│   │   └── index.html
│   └── src/
│       ├── main.jsx         # React 진입 파일
│       ├── App.jsx          # 전체 화면 구성
│       ├── App.css          # 기본 스타일
│       ├── api/
│       │   └── todoApi.js   # 백엔드 호출 함수 모음
│       └── components/
│           ├── TodoList.jsx # 목록 + 완료/삭제
│           └── TodoForm.jsx # 입력/추가
└── docs/
    └── API.md               # 간단한 API 명세 (선택이지만 강력 추천)

```
개발 모드에서 실행 방법
1. 백엔드 서버 실행
프로젝트 루트 기준:

bash
python backend/app.py
기본 포트: 5000

헬스 체크: 브라우저에서 http://localhost:5000/api/health 접속 시 {"status": "ok"} 응답 확인

2. 프론트엔드 개발 서버 실행
bash
cd frontend
npm install      # 최초 1회만 실행
npm run dev
기본 포트: 5173

3. 브라우저에서 접속
브라우저에서 다음 주소로 접속한다.

text
http://localhost:5173
정상 동작 시:

할 일 추가

할 일 완료/미완료 토글

할 일 삭제

기능이 모두 동작하면 프론트엔드와 백엔드 연동이 성공적으로 이루어진 것이다
