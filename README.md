# README
<<<<<<< Updated upstream

## Usersテーブル

|Column|Type|Option|
|------|----|------|
|name|string|null: false,add_index :users, :name, unique: true|
|email|string|null: false, add_index :users, :email, unique: true|

### Asociation
- has_many :meessages
- has_many :chat_groups, through: :users_chats

## Chat_groupsテーブル

|Column|Type|Option|
|:-----|---:|-----:|
|name|string|null: false|

###Asociation
- has_many :messages
- has_many :users, through: :users_chats

## messagesテーブル
|Column|Type|Option|
|-----:|---:|-----:|
|body|text|null: false|
|image|string|---|
|user|references|foreign_key: true|
|chat_group|references|foreign_key: true|

###Asociation
- belongs_to :user
- belongs_to :chat_group

## Users_chatsテーブル
|Column|Type|Option|
|-----:|---:|-----:|
|user|references|foreign_key: true|
|chat_group|references|foreign_key: true|

###Asociation
- belongs_to: user
- belongs_to: chat_group
=======
>>>>>>> Stashed changes
