## users テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|user_name|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :group, through: :groups_users
- has_many :comments


## groups テーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false|
|group_name|string|null: false|
### Association
- has_many :user, through: :groups_users
- has_many :comments


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
