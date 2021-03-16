# テーブル設計


## students テーブル

| Column                 | Type       | Options                        |
| ---------------------- | ---------- | ------------------------------ |
| student_user_id        | references | null: false foreign_key: true  |
| name                   | string     | null: false                    |
| nickname               | string     | null: false                    |
| encrypted_password     | string     | null: false                    |
| email                  | string     | null: false                    |
| phone_number           | string     | null: false                    |
| birthday               | date       | null: false                    |
| grade                  | string     | null: false                    |

### Association

- has_many :classrooms
- has_many :teachers


## classrooms テーブル

| Column                 | Type       | Options                        |
| ---------------------- | ---------- | ------------------------------ |
| student_user_id        | references | null: false foreign_key: true  |
| teacher_user_id        | references | null: false foreign_key: true  |

### Association

- has_one :students
- has_one :teachers


## teachers テーブル

| Column                 | Type       | Options                        |
| ---------------------- | ---------- | ------------------------------ |
| teacher_user_id        | references | null: false foreign_key: true  |
| name                   | string     | null: false                    |
| encrypted_password     | string     | null: false                    |
| email                  | string     | null: false                    |
| phone_number           | string     | null: false                    |
| birthday               | date       | null: false                    |
| educational_background | string     | null: false                    |
| subject                | string     | null: false                    |
| pr                     | text       | null: false                    |
| review                 | integer    | null: false                    |

### Association

- has_many :classrooms
- has_many :students


## homerooms テーブル

| Column                 | Type       | Options                        |
| ---------------------- | ---------- | ------------------------------ |
| student_user_id        | references | null: false foreign_key: true  |

### Association

- has_many :students