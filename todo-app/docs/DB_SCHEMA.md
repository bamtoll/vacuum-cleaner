# Database Schema: todo_db

## Database

- Name: `todo_db`
- Charset: `utf8mb4`
- Collation: `utf8mb4_unicode_ci`

## Tables

### 1. `todos`

할 일(Todo) 정보를 저장하는 테이블.

| Column     | Type         | Null | Default           | Description                |
|-----------|--------------|------|-------------------|----------------------------|
| id        | INT          | NO   | AUTO_INCREMENT    | 기본 키 (고유 ID)         |
| title     | VARCHAR(255) | NO   |                   | 할 일 제목                |
| completed | TINYINT(1)   | NO   | 0                 | 완료 여부(0: 미완료, 1: 완료) |
| created_at| DATETIME     | NO   | CURRENT_TIMESTAMP | 생성 일시                 |
| updated_at| DATETIME     | NO   | CURRENT_TIMESTAMP ON UPDATE | 마지막 수정 일시 |

## Relation to Backend Model

- `backend/app.py`의 `Todo` 모델과 1:1 매핑됨.
- API 엔드포인트:
  - `GET /api/todos`
  - `POST /api/todos`
  - `PUT /api/todos/{id}`
  - `DELETE /api/todos/{id}`
