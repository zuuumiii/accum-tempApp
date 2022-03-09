# テーブル設計

## usersテーブル

| Colummn            | Type    | Option                   |
|--------------------|---------|--------------------------|
| email              | string  | null:false, unique:true  |
| encrypted_password | string  | null:false               |
| name               | string  | null:false               |
| prec_no            | integer | null:false               |
| block_no           | integer | null:false               |

### Association
- has_many :items


## filedsテーブル

| Colummn           | Type       | Option                       |
|-------------------|------------|------------------------------|
| field_name        | string     | null:false                   |
| product_name      | string     | null:false                   |
| info              | text       |                              |
| start_date        | date       | null:false                   |
| filed_area        | integer    | null:false                   |
| prec_no           | integer    | null:false                   |
| block_no          | integer    | null:false                   |
| accum             | float      | null:false, default: 0       |
| user_id           | references | null:false, foreign_key: true|

### Association
- belongs_to :user
- has_many :works


## worksテーブル

| Colummn           | Type     | Option                |
|-------------------|----------|-----------------------|
| work_name         | string   | null:false            |
| memo              | text     |                       |
| target_temp       | integer  | null:false, default: 0|


### Association
- belongs_to :fields
