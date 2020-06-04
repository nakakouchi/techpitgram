# README

## usersテーブル
|column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false,|
|encrypted_password|string|null: false|
|user_id|integer|null:false, foreign_key: true|

### Association
- has_many posts
- has_many likes
- has_many comments


## likesテーブル
|column|Type|Options|
|------|----|-------|
|user_id|references|null:false, foreign_key: true|
|post_id|references|null:false, foreign_key: true|

### Association
- belongs_to user
- belongs_to post


## postsテーブル
|column|Type|Options|
|------|----|-------|
|caption|string|null:false|
|user_id|references|null:false, foreign_key: true|

### Association
- belongs_to user
- has_many likes
- has_many comments
- has_many photos


## photosテーブル
|column|Type|Options|
|------|----|-------|
|image|string|null:false|
|post_id|references|null:false, foreign_key: true|

### Association
- belongs_to post


## commentsテーブル
|column|Type|Options|
|------|----|-------|
|comment|text|null:false|
|user_id|references|null:false, foreign_key: true|
|post_id|references|null:false, foreign_key: true|

### Association
- belongs_to user
- belongs_to post
