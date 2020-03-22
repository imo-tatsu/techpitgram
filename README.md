# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false, unique: true|
|mail_address|string|null: false|
|password|string|null: false|
|password-confirmation|string|null: false|

### Association
- has_many :comments
- has_many :posts
- has_many :likes


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|comment|string|null: false|
|post_id|integer|null: false,foreign_key: true|
|user_id|integer|null: false,foreign_key: true|

### Association
- belongs_to :post
- belongs_tp :user



## postsテーブル
|Column|Type|Options|
|------|----|-------|
|caption|string|null: false|
|user_id|integer|null: false,foreign_key: true|

### Association
- has_many :phots



## likesテーブル
|Column|Type|Options|
|------|----|-------|
|post_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false,foreign_key: true|

### Association
- belongs_to :post
- belongs_to :user



## photsテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null: false|
|post_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :post