Database
====

## Tables
- users
- groups
- group_users
- messages

## Columns
### Users
|column|type|
|:---:|:---:|
|name|string|
|comment|string|
|group_id|integer|

### Group
|column|type|
|:---:|:---:|
|name|string|
|user_id|integer|

### Massage
|column|type|
|:---:|:---:|
|user_id|integer|
|group_id|integer|
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