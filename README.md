Database
====

## Tables
- users
- groups
- group_users
- messages

## Columns
### Users
|column|type|constraint|
|:---:|:---:|:---:|
|name|string|index, unique, null false|
|email|string|unique, null false|
|password|string|null false|
|confirmation password|string|null false|

### Group
|column|type|constraint|
|:---:|:---:|:---:|
|name|string|unique, null false|

### Message
|column|type|constraint|
|:---:|:---:|:---:|
|user_id|integer|foreign_key, index, null false|
|group_id|integer|foreign_key, index, null false|
|timestamps|time|
|body|text|
|image|text|

### Group_users
|column|type|
|:---:|:---:|
|user_id|integer|
|group_id|integer|

# Association

### Users
- has_many :groups, through: :group_users 
- has_many :messages

### Groups
- has_many :users, through: :group_users 
- has_many :messages

### Messeages
- belongs_to :user
- belongs_to :group

### Group_users
- belongs_to :group
- belongs_to :user