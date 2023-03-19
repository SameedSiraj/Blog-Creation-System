# Blog-Creation-System
##Project Description
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
