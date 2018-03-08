# Demo RESTful API on Laravel

by Richard Lindsay

## Technical Specs

* Laravel 5.6
* PHP 7.1
* MySQL
* Built on DigitalOcean Droplet - Ubuntu 16.04

Base URL: http://45.55.45.146/demo2/api/

## Routes

### Products

#### POST /register  
Registers new user
```
{
	"name": "Richard", 
	"email": "richard@test.com", 
	"password": "test123", 
	"password_confirmation": "test123"
}
```
#### POST /login  
Login with user info
```

{
	"name": "Richard",
	"password": "test123"
}

response JSON:
{
    "data": {
        "id": 12,
        "name": "Richard",
        "email": "richard@test.com",
        "created_at": "2018-03-04 17:43:24",
        "updated_at": "2018-03-04 17:23:48",
        "api_token": "h8iESR74ZT9BE77DrahjT9CF4qKNjnbuFGrgzcwhNZ3gQPeCdbfjr8E670Sm"
    }
}

#### POST /logout  
Logs out current user
```

response JSON:

{
    "data": "User logged out."
}

### The following routes require a Bearer token created during login in the request header.
### Alternatively, you can send an attribute "api_token" in the payload.

#### GET /articles  
Returns a list of articles
```
response JSON:
[
    {
        "id": 2,
        "title": "Et omnis soluta facilis et tempore nam.",
        "body": "Occaecati dolores fugit illo libero. Magnam qui esse consequuntur commodi corrupti ut. Esse ducimus blanditiis omnis unde commodi nisi earum.",
        "created_at": "2018-03-06 16:21:18",
        "updated_at": "2018-03-06 16:21:18"
    },
    {
        "id": 3,
        "title": "Et eaque ipsum in quasi nobis architecto.",
        "body": "Et vel fugiat occaecati ipsum. Et sed velit deleniti nostrum impedit aut dignissimos.",
        "created_at": "2018-03-06 16:21:18",
        "updated_at": "2018-03-06 16:21:18"
    },
    {
        "id": 4,
        "title": "Et aperiam aliquid deleniti eius sint omnis.",
        "body": "Omnis tempore dolor officiis blanditiis vel dolorem. Magni ipsa temporibus numquam perspiciatis inventore molestiae inventore. Mollitia repudiandae nostrum rerum architecto et sit aut.",
        "created_at": "2018-03-06 16:21:18",
        "updated_at": "2018-03-06 16:21:18"
    },
    {
        "id": 5,
        "title": "Accusantium quod sed dignissimos quas rerum voluptatem vel.",
        "body": "Voluptatem vitae qui quisquam. Voluptatem et molestiae quo repudiandae. Est est perferendis sit voluptatem debitis amet quisquam. Sed dolores quam eos neque neque earum.",
        "created_at": "2018-03-06 16:21:18",
        "updated_at": "2018-03-06 16:21:18"
    }
]

#### GET /articles/{id}  
Returns a specific article depending on ID
```

response JSON:
[
    {
        "id": 2,
        "title": "Et omnis soluta facilis et tempore nam.",
        "body": "Occaecati dolores fugit illo libero. Magnam qui esse consequuntur commodi corrupti ut. Esse ducimus blanditiis omnis unde commodi nisi earum.",
        "created_at": "2018-03-06 16:21:18",
        "updated_at": "2018-03-06 16:21:18"
    }
]


#### POST /articles
Creates a new article
```
request JSON:
{
    "title": "Lorem",
    "body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. "
}

response JSON:
{
    "title": "Lorem",
    "body": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    "updated_at": "2018-03-08 18:01:54",
    "created_at": "2018-03-08 18:01:54",
    "id": 53
}

