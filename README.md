# テーブル設計

## usersテーブル

| Colum      | Type   | Options  |
| ---------- | ------ | -------- |
| email      | string | NOT NULL |
| password   | string | NOT NULL |
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NOT NULL |

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Colum      | Type       | Options  |
| ---------- | ---------- | -------- |
| title      | string     | NOT NULL |
| catch_copy | text       | NOT NULL |
| concept    | text       | NOT NULL |
| user       | references |          |

### Association

- has_many :comments
- belongs_to :prototypes

## commentsテーブル

| Colum     | Type       | Options  |
| --------- | ---------- | -------- |
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

### Association

- belong_to :users
- belong_to :prototypes