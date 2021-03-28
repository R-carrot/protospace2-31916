# テーブルER図

## users テーブル

| Colum      | Type   | Options     |
| -----      | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association 

- has_many :prototypes
- has_many :comments


## prototypes テーブル

| Colum      | Type      | Options     |
| ---------- | --------- | ----------- |
| title      | string    | null: false |
| catch_copy | string    | null: false |
| concept    | text      | null: false |
| user       | reference |             |

### Association 

- has_many :comments
- belong_to :users


## comments テーブル

| Colum     | Type       | Options     |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             | 

### Association 

- belong_to :users
- belong_to :prototypes