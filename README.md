## users テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :groups, through: :groups_users
- has_many :comments
- has_many :groups_users


## groups テーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :users, through: :groups_users
- has_many :comments
- has_many :groups_users


## groups_users テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## comments テーブル
|Column|Type|Options|
|------|----|-------|
|comment|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
