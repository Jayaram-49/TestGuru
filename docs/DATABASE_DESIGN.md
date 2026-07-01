# Database Design

## 1. Entities

### Core Entities

User
│
├── id
├── first_name
├── last_name
├── email
├── password
├── role
├── phone
├── status
└── created_at

Organization
│
├── id
├── user_id (FK)
├── organization_name
├── website
├── industry
├── address
└── created_at

Assessment
│
├── id
├── organization_id (FK)
├── title
├── description
├── duration
├── total_marks
├── passing_marks
├── access_code
├── start_time
├── end_time
├── status
└── created_at

Question
│
├── id
├── assessment_id (FK)
├── question_text
├── marks
└── created_at

Option
│
├── id
├── question_id (FK)
├── option_text
└── is_correct

Attempt
│
├── id
├── assessment_id (FK)
├── candidate_id (FK)
├── started_at
├── submitted_at
├── status
└── score

Answer
│
├── id
├── attempt_id (FK)
├── question_id (FK)
└── selected_option_id (FK)

9. Result

## 2. Entity Relationships

### Organization → Assessment
One Organization can create multiple Assessments.
One Assessment belongs to one Organization.

Relationship:
1 : N

---

### Assessment → Question
One Assessment contains multiple Questions.
One Question belongs to one Assessment.

Relationship:
1 : N

---

### Question → Option
One Question contains multiple Options.
One Option belongs to one Question.

Relationship:
1 : N

---

### Assessment → Assessment Link
One Assessment has one unique Assessment Link.

Relationship:
1 : 1

---

### User (Candidate) → Attempt
One Candidate can attempt multiple Assessments.
One Attempt belongs to one Candidate.

Relationship:
1 : N

---

### Assessment → Attempt
One Assessment can have multiple Candidate Attempts.

Relationship:
1 : N

---

### Attempt → Answer
One Attempt contains multiple Answers.

Relationship:
1 : N

---

### Result → Attempt
Each Attempt generates one Result.

Relationship:
1 : 1

## 3. Database Tables

### 3.1 User

| Column | Type | Description |
|---------|------|-------------|
| id | BIGINT | Primary Key |
| first_name | VARCHAR(100) | User's first name |
| last_name | VARCHAR(100) | User's last name |
| email | VARCHAR(255) | Unique email |
| password | VARCHAR(255) | Encrypted password |
| role | ENUM | ADMIN / ORGANIZATION / CANDIDATE |
| phone | VARCHAR(20) | Contact number |
| status | ENUM | ACTIVE / INACTIVE |
| created_at | TIMESTAMP | Account creation time |

---

### 3.2 Organization

| Column | Type |
|---------|------|
| id | BIGINT |
| user_id | BIGINT (FK) |
| organization_name | VARCHAR(255) |
| website | VARCHAR(255) |
| industry | VARCHAR(100) |
| address | TEXT |
| created_at | TIMESTAMP |

---

### 3.3 Assessment

| Column | Type |
|---------|------|
| id | BIGINT |
| organization_id | BIGINT (FK) |
| title | VARCHAR(255) |
| description | TEXT |
| duration | INTEGER |
| total_marks | INTEGER |
| passing_marks | INTEGER |
| access_code | VARCHAR(50) |
| start_time | TIMESTAMP |
| end_time | TIMESTAMP |
| status | ENUM |
| created_at | TIMESTAMP |

---

### 3.4 Question

| Column | Type |
|---------|------|
| id | BIGINT |
| assessment_id | BIGINT (FK) |
| question_text | TEXT |
| question_type | ENUM |
| marks | INTEGER |

---

### 3.5 Option

| Column | Type |
|---------|------|
| id | BIGINT |
| question_id | BIGINT (FK) |
| option_text | TEXT |
| is_correct | BOOLEAN |

---

### 3.6 Attempt

| Column | Type |
|---------|------|
| id | BIGINT |
| assessment_id | BIGINT (FK) |
| candidate_id | BIGINT (FK) |
| start_time | TIMESTAMP |
| end_time | TIMESTAMP |
| submitted | BOOLEAN |

---

### 3.7 Answer

| Column | Type |
|---------|------|
| id | BIGINT |
| attempt_id | BIGINT (FK) |
| question_id | BIGINT (FK) |
| selected_option_id | BIGINT (FK) |

---

### 3.8 Result

| Column | Type |
|---------|------|
| id | BIGINT |
| attempt_id | BIGINT (FK) |
| score | INTEGER |
| percentage | DECIMAL |
| result_status | ENUM |
| generated_at | TIMESTAMP |

## 4. Entity Relationship Diagram (Conceptual)

User (1) -------- (1) Organization

Organization (1) -------- (N) Assessment

Assessment (1) -------- (N) Question

Question (1) -------- (N) Option

Assessment (1) -------- (N) Attempt

User (Candidate) (1) -------- (N) Attempt

Attempt (1) -------- (N) Answer

Question (1) -------- (N) Answer

Option (1) -------- (N) Answer