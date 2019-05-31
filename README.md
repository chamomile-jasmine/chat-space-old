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

#DB設計

##users table

｜Column|Type|Options|
|-------|----|-------|
|name|string|index: true,null: false,unique: true|
|mail|string|null: false,unique: true|

## Assocoation
- has_many :groups,through: :group_users
- has_many :messages
- has_many :group_users

## group table

｜Column|Type|Options|
|-------|----|-------|
|name|string|index: true,null: false,unique: true|

## Assocoation
- has_many :users,through::group_users
- has_many :group_users
- has_many :messages


## message table

｜Column|Type|Options|
|-------|----|-------|
|body|text|null: false|
|image|string||
|group|reference|foreign_key: true|
|user|reference|foreign_key: true|

## Assocoation
- belongs_to :group
- belongs_to :user

##group_users table

｜Column|Type|Options|
|-------|----|-------|
|body|text|null: false|
|group|reference|index: true,foreign_key: true,null: false|
|user|reference|index: true,foreign_key: true,null: false|

## Assocoation
- belongs_to :group
- belongs_to :user

