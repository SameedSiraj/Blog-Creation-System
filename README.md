# Blog-Creation-System
This application allows users to create, read, update, and delete blogs. It also includes authentication and authorization features, where user passwords are hashed to ensure secure access to user data.

### Tools and Technologies:
Node JS, MongoDB, Visual Studio Code

### APIs Description:
Our system includes the following APIs:  

<br>
**1) GET /user**  
Retrieve all the users.  

**Parameters:**  
none

**Example request:**   
``` curl --location 'http://localhost:5000/api/user/' ```  

**Example response:**    
``` 
{
    "users": [
        {
            "_id": "640e2663748dbf72fc866092",
            "name": "Sameed",
            "email": "test3@gmail.com",
            "password": "$2a$10$Cd/Vc58MJfnwIQWucHDMlu9TenkPJwKCjQwAmyyxXFPqWGqFqQo/S",
            "blogs": [
                "640e2671748dbf72fc866095",
                "640e2674748dbf72fc86609a",
                "640e2677748dbf72fc86609e"
            ],
            "__v": 3
        }
    ]
} 
```  

<br><br>
**2) POST /user/signup**  
Create a new user account with a unique email address and hashed password.   

**Parameters:**  
none

**Example request:**   
```
curl --location 'http://localhost:5000/api/user/signup' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name":"Test1",
    "email":"Test1@gmail.com",
    "password":"Test54@#123"
}'
```  

**Example response:**    
```
{
    "user": {
        "name": "Test1",
        "email": "Test1@gmail.com",
        "password": "$2a$10$/u/hfnYf8OVo.UT0yCm.HuXNOlAbg56vYfcuJ.gNJVK2Mzss8La0.",
        "blogs": [],
        "_id": "64165db86d8ae7829950d5a3",
        "__v": 0
    }
}
```  

<br><br>
**3) POST /user/login**  
Log in to an existing user account with a valid email and password.    

**Parameters:**  
none

**Example request:**   
```
curl --location 'http://localhost:5000/api/user/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email":"Test1@gmail.com",
    "password":"Test54@#123"
}'
```  

**Example response:**    
```
{
    "message": "Login Successfull"
}
```  

<br><br>
**4) GET /blog**  
Retrieve all blog posts created by the logged-in user.  

**Parameters:**  
none

**Example request:**   
```
curl --location 'http://localhost:5000/api/blog'
```  

**Example response:**    
```
{
    "blogs": [
        {
            "_id": "640e2677748dbf72fc86609e",
            "title": "My ne Blog",
            "description": "This is my firs blog",
            "image": "xxxx",
            "user": "640e2663748dbf72fc866092",
            "__v": 0
        }
    ]
}
```  

<br><br>
**5) POST /blog/add**  
Add a new blog post to the logged-in user's list of blog posts.  

**Parameters:**  
none

**Example request:**   
```
curl --location 'http://localhost:5000/api/blog/add' \
--header 'Content-Type: application/json' \
--data '{
    "title": "My new Blog",
    "description": "This is my first blog",
    "image": "xxxx",
    "user" : "640e2663748dbf72fc866092"
}'
```  

**Example response:**    
```
{
    "blog": {
        "title": "My new Blog",
        "description": "This is my first blog",
        "image": "xxxx",
        "user": "640e2663748dbf72fc866092",
        "_id": "641661a06d8ae7829950d5a8",
        "__v": 0
    }
}
``` 

<br><br>
**6) PUT /blog/update/{id}**  
Update a specific blog post with given ID.  

**Parameters:**  
**id** (required): The ID of the blog to update.

**Example request:**   
```
curl --location --request PUT 'http://localhost:5000/api/blog/update/641661a06d8ae7829950d5a8' \
--header 'Content-Type: application/json' \
--data '{
    "title": "Updated Blog",
    "description": "This is my first updated blog"
}'
```  

**Example response:**    
```
{
    "blog": {
        "_id": "641661a06d8ae7829950d5a8",
        "title": "My new Blog",
        "description": "This is my first blog",
        "image": "xxxx",
        "user": "640e2663748dbf72fc866092",
        "__v": 0
    }
}
``` 

<br><br>
**7) GET /blog/{id}**  
Retrieve a specific blog post by its ID.  

**Parameters:**  
**id** (required): The ID of the blog to retrieve.

**Example request:**   
```
curl --location 'http://localhost:5000/api/blog/641661a06d8ae7829950d5a8'
```  

**Example response:**    
```
{
    "blog": {
        "_id": "641661a06d8ae7829950d5a8",
        "title": "Updated Blog",
        "description": "This is my first updated blog",
        "image": "xxxx",
        "user": "640e2663748dbf72fc866092",
        "__v": 0
    }
}
``` 

<br><br>
**8) DELETE /blog/{id}**  
Delete a specific blog post by its ID.  

**Parameters:**  
**id** (required): The ID of the blog to delete.

**Example request:**   
```
curl --location --request DELETE 'http://localhost:5000/api/blog/641661a06d8ae7829950d5a8'
```  

**Example response:**    
```
{
    "message": "Successfully Delete"
}
``` 

<br><br>
**9) GET /blog/user/{id}**  
Retrieve all blog posts created by a given user.  

**Parameters:**  
**id** (required): The ID of the user whose blogs have to be reterieve.

**Example request:**   
```
curl --location --request DELETE 'http://localhost:5000/api/blog/641661a06d8ae7829950d5a8'
```  

**Example response:**    
```
{
    "blogs": {
        "_id": "640e2663748dbf72fc866092",
        "name": "Sameed",
        "email": "test3@gmail.com",
        "password": "$2a$10$Cd/Vc58MJfnwIQWucHDMlu9TenkPJwKCjQwAmyyxXFPqWGqFqQo/S",
        "blogs": [
            {
                "_id": "640e2671748dbf72fc866095",
                "title": "My ne Blog",
                "description": "This is my firs blog",
                "image": "xxxx",
                "user": "640e2663748dbf72fc866092",
                "__v": 0
            }
        ],
        "__v": 5
    }
}
``` 
