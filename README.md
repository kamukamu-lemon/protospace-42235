# README

##usersテーブル

| column             | type       | options                    |
| ------------------ | ---------- | -------------------------- |
| email              | string     | null: false, unique: true  |
| encrypted_password | string     | null: false                |
| name               | string     | null: false                |
| profile            | text       | null: false                |
| occupation         | text       | null: false                |
| position           | text       | null: false                |

###association

- has_many :comments
- has_many :prototypes


##commentsテーブル

| column             | type       | options                        |
| ------------------ | ---------- | ------------------------------ |
| content            | text       | null: false                    |
| prototype          | references | null: false, foreign_key: true |
| user               | references | null: false, foreign_key: true |

###association

- belongs_to :user
- belongs_to :prototypes


##prototypesテーブル

| column             | type       | options                        |
| ------------------ | ---------- | ------------------------------ |
| title              | string     | null: false                    |
| catch_copy         | text       | null: false                    |
| concept            | text       | null: false                    |
| user               | references | null: false, foreign_key: true |

###association

- belongs_to :user
- has_many :comments


