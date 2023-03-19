# Blog-Creation-System
This application allows users to create, read, update, and delete blogs. It also includes authentication and authorization features, where user passwords are hashed to ensure secure access to user data.
  
  
    
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
  
  
     
**2) POST /user/signup**  
Retrieve all the users.  

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


**3) POST /user/login**  
Retrieve all the users.  

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



**4) POST /blog**  
Retrieve all the users.  

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


**5) POST /blog/add**  
Retrieve all the users.  

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



**6) PUT /blog/update/641661a06d8ae7829950d5a8**  
Retrieve all the users.  

**Parameters:**  
none

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


**7) GET /blog/641661a06d8ae7829950d5a8**  
Retrieve all the users.  

**Parameters:**  
none

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



**8) DELETE /blog/640e1ff905939e9c49e6c84b**  
Retrieve all the users.  

**Parameters:**  
none

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



**9) GET /blog/user/640e2663748dbf72fc866092**  
Retrieve all the users.  

**Parameters:**  
none

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
