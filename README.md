Database
====

## Tables
- users
- groups
- group_users
- messages

## Columns
### Users
|column|type|constrant|
|:---:|:---:|:---:|
|name|string|index, unique, null false|
|comment|string|unique, null false|
|group_id|integer|unique, null false|

### Group
|column|type|constraint|
|:---:|:---:|:---:|
|name|string|constraint|
|user_id|integer|unique, null false|

### Massage
|column|type|constraint|
|:---:|:---:|:---:|
|user_id|integer|foreign_key, index, null false|
|group_id|integer|foreign_key, index, null false|
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

### Masseages
- belongs_to :user
- belongs_to :group

### Group_users
- belongs_to :group
- belongs_to :user