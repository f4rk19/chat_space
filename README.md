# DB設計
<<<<<<< Updated upstream

## Usersテーブル

|Column|Type|Option|
|------|----|------|
|name|string|null: false, index: true, unique: true|
|email|string|null: false, index: true, unique: true|

### Asociation
- has_many :meessages
- has_many :chat_groups, through: :users_chats
- has_many :users_chats

## Chat_groupsテーブル

|Column|Type|Option|
|:-----|---:|-----:|
|name|string|null: false, unique: true|

###Asociation
- has_many :messages
- has_many :users, through: :users_chats
- has_many :users_chats

## messagesテーブル
|Column|Type|Option|
|-----:|---:|-----:|
|body|text|----|
|image|string|---|
|user|references|foreign_key: true, null: false|
|chat_group|references|foreign_key: true, null: false|

###Asociation
- belongs_to :user
- belongs_to :chat_group

## Users_chatsテーブル
|Column|Type|Option|
|-----:|---:|-----:|
|user|references|foreign_key: true, null: false|
|chat_group|references|foreign_key: true, null:false|

###Asociation
- belongs_to: user
- belongs_to: chat_group