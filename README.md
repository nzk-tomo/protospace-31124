# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

 - has_many :comments
 - has_many :prototypes

## comments テーブル

| Column    | Type      | Options                        |
| --------- | --------- | ------------------------------ |
| text      | string    | null: false                    |
| user      | reference | null: false, foreign_key: true |
| prototype | reference | null: false, foreign_key: true |

### Association

 - belongs_to :comments
 - belongs_to :prototypes

## prototypes テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| image      | string     | @Active_Strage                 |
| user       | references | null: false, foreign_key: true |

### Association

 - has_many :comments
 - belongs_to :users