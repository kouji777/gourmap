# DB 設計

## users table

| Column          | Type             |Options        |
| -------------| -------------|-------------|
| nickname        | string           | null: false     |
| email           | string           | unique: true, null: false  |
| encrypted_password| string         | null: false  |

### association

* has_many :store
* has_many :favorite

## stores table

| Column          | Type             |Options        |
| -------------| -------------|-------------|
| name            | string            | null: false  |
| price           | integer           | null: false  |
| place           | string            | null: false  |
| favorite_menu   | string            | null: false  |
| review          | text              | null: false  |
| business_day    | datetime          | null: false  |
| business_hours  | time              | null: false  |
| image

### association

* belongs_to :user 
* has_many : favorite

## favorites table

| Column          | Type             |Options        |
| -------------| -------------|-------------|
| store_id        | string            | null: false  | 

### association

* belongs_to :user
* belongs_to :store