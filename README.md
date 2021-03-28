# テーブル設計

## userテーブル

|Column      | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| prpfile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :protypes


## commentテーブル
|Column     | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| prptotype | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototype


## prototypes
|Column      | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association

- has_many :comments
- belongs_to :user

