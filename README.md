# README

# テーブル設計

## usersテーブル

| Columns    | Type   | Option      |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

- has_many :comments
- has_many :prototype

## commentsテーブル

| Columns   | Type       | Option                         |
| --------- | ---------- | ------------------------------ |
| text      | text       |                                |
| user      | references | null: false, foreign_key: true |
| prototype | references | null: false, foreign_key: true |

- belongs_to :users
- belongs_to :prototype

## prototypeテーブル

| Columns    | Type       | Option                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | string     | null: false                    |
| concept    | text       | null: false                    |
| image      | ASで実装    | null: false                    |
| user       | references | null: false, foreign_key: true |

- belongs_to :users
- has_many :comments