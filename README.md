![ER Diagram](./path/to/DB.png)

![DB](https://github.com/ConniConni/joinunion/assets/127648505/afc7cce4-7bf7-4182-a511-4067f286372a)


# DB 設計

## users table

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| nickname           | string              | null: false               |
| email              | string              | null: false, unique: true |
| encrypted_password | string              | null: false,              |
| familyname         | string              | null: false               |
| firstname          | string              | null: false               |
| department         | string              | null: false               |

### Association

* has_many :posts
* has_many :comments

## posts table

| Column | Type       | Options                        |
|----- --|------------|--------------------------------|
| text   | string     | null: false                    |
| user   | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :comments

## comments table

| Column       | Type       | Options                        |
|--------------|------------|--------------------------------|
| comment_text | string     | null: false                    |
| post         | references | null: false, foreign_key: true |
| user         | references | null: false, foreign_key: true |

### Association

- belongs_to :post
- belongs_to :user

