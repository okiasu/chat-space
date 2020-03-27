# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|email_address|string|null: false|
|pass_word|strig|null: false|
|group_id|integer|null: false, foreign_key: group_id|


### Association
 - has_many :messages
 - has_many :groups, through: :groups_users
 - has_many :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|user_id|integer|null: false, foreign_key: user_id|

### Association
 - has_many :users, through: :groups_users
 - has_many :messages
 - has_many :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: user_id|
|group_id|integer|null: false, foreign_key: group_id|

## Association
 - belongs_to :user
 - belongs_to :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
 - belongs_to :user
 - belongs_to :group




* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

