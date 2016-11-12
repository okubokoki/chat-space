### Group
|column|type|
|:---:|:---:|
|name|string|
|user_id|integer|

### Comment
|column|type|
|:---:|:---:|
|user_id|integer|
|group_id|integer|
|text|text|
|image|text|

### Image
|column|type|
|:---:|:---:|
|prototype_id|integer|
|status|integer|
|profile|string|

# Association

### Users
- has_many :groups
- has_many :comments

### Groups
- belongs_to :user
- has_many :comments

### Comments
- belongs_to :prototype
- belongs_to :user### Group
|column|type|
|:---:|:---:|
|name|string|
|user_id|integer|

### Comment
|column|type|
|:---:|:---:|
|user_id|integer|
|group_id|integer|
|text|text|
|image|text|

### Image
|column|type|
|:---:|:---:|
|prototype_id|integer|
|status|integer|
|profile|string|

# Association

### Users
- has_many :groups
- has_many :comments

### Groups
- belongs_to :user
- has_many :comments

### Comments
- belongs_to :prototype
- belongs_to :user