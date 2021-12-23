# DB 設計

## users table

| Column             | Type                | Options                   |
|--------------------|---------------------|---------------------------|
| nickname           | string              | null: false               |
| email              | string              | null: false, unique: true |
| password           | string              | null: false               |
| name               | string              | null: false               |
| birth              | string              | null: false               |

### Association

* has_many :items
* has_many :purchase

## items table

| Column                   | Type       | Options                        |
|--------------------------|------------|--------------------------------|
| title                    | string     | null: false                    |
| explain                  | text       | null: false                    |
| detail_category          | string     | null: false                    |
| detail_condition         | string     | null: false                    |
| detail_category          | string     | null: false                    |
| delivery_load            | string     | null: false                    |
| delivery_area            | string     | null: false                    |
| delivery_date            | string     | null: false                    |
| price                    | string     | null: false                    |
| user                     | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :purchase

## purchase table

| Column          | Type       | Options                        |
|-----------------|------------|--------------------------------|
| card_number     | string     | null: false                    |
| valid           | string     | null: false                    |
| security        | string     | null: false                    |
| post_number     | string     | null: false                    |
| city            | string     | null: false                    |
| address         | string     | null: false                    |
| build_name      | string     | null: false                    |
| phone_number    | string     | null: false                    |
| item            | references | null: false, foreign_key: true |
| user            | references | null: false, foreign_key: true |

### Association

- belongs_to :prototype
- belongs_to :user
