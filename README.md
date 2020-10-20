# テーブル設計

## users テーブル
- has_many :prototypes
- has_many :comments


| Column      | Type   | Options     |
| ----------- | ------ | ----------- |
| email       | string | null: false |
| password    | string | null: false |
| name        | string | null: false |
| profile     | text   | null: false |
| occupation  | text   | null: false |
| position    | text   | null: false |

## prototypes テーブル
- belongs_to :user
- has_many :comments

| Column     | Type         | Options     |
| ---------- | ------------ | ----------- |
| title      | string       | null: false |
| catch_copy | text         | null: false |
| concept    | text         | null: false |
| image      |ActiveStorage |             |
|user        | references   |             |


## comments テーブル
- belongs_to :user
- belongs_to :prototype

| Column    | Type       | Options           |
| --------- | ---------- | ----------------- |
| text      | text       | null: false       |
| user      | references |                   |
| prototype | references |                   |