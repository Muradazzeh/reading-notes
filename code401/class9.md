## Reading: Authorization/Authentication last project

## Requirements 
* Your application must employ the following programming concepts:

    * API/Auth server must be deployed
    * Use of your API server to perform database operations
    * Use of login/auth/acl to control access to your resources

* we think of different idea for our project , like we think of clothes store , online game , and book store , 

* so we choose the easy idea , it is the book store , we prepared sign up route so when the user sign up we will save his data in the data base , and for sure the password should be hashed , and we add to the user data ACL (role ) , so depending on the role , the user can do certain method

* we prepared sign in Route , each user in the data base can sign in , then we will generat for the user token , so this token will give the user access to some pages we will mention
 
 * about the role for the users that , some users can access to read from the web site and some users have more authority like admin or editor the can access to update or delete , so after any user sign in correctly we will give him role

 * now we will start with main route /book, that contain our stored data so the user can check whick book , he want , then he can add to his order , so we will use post method , so he can update his order page , and we add get method so he can see all the book he post in his order page , also he can update or delete 

 
| Page          | Path      | Method        | Response and Usage                  | who is can access this page     |   |   |   |   |   |
|---------------|-----------|---------------|-------------------------------------|---------------------------------|---|---|---|---|---|
| Sign up Page  | /signup   | post          | to create a user                    | any user                        
| Sign in Page  | /sign in  | post          | to login a user and receive a token | any user saved in the data base 
| Users Page    | /users    | get           | to get all user names               | 	only user with "admin" role    
| book page     | /book     | get           | to get all book name                | all logged in user              
| book page     | /book     | post          | to create new book                  | admin , for web site            
| book page     | /book/:id | get one book  | to get one book by id               | any logged user                 
| book page     | /book/:id | delete        | delete book from data base          | admin                           
| order page    | /myorder  | get           | get all the order for specific user | logged in user                  
| order page    | /myorder  | post          | add book to my order                | logged in user      


* this is small project fot authentication 


