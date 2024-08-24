
# Go-Rest-API-Chaining-Testing-P03

Testing suite for the Go REST API Chaining project, covering Create, Retrieve, Update, and Delete (CRUD) operations. This repository includes well-documented test scripts to ensure API functionality and reliability. # Postman



## Table of Content Go Rest API Chaining Testing 

- Create New Student (Post method)
- Retrive Students Details (Get method)
- Update Studnet Details (Put method)
- Delete Student Details (Delete method)




## Create the Workspace In the Postman  

- Create The Collection (name: Go Rest API Chaining)
- Create The Add Request in the collection
    - Create User Details 
    - Get User Details
    - Update User Details
    - Delete User Details



## Create User Details 

![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/create_user-01.png)


## Test Script Details for the Create user 

The test script below demonstrates how to generate a random username and user email, then store them as environment variables. The environment is named QA, and the variables are defined within this environment.

```bash
var random = Math.random().toString(36).substring(2);
var useremail = "Talha" + random + "@gmail.com";
var username = "Talha" + random;

pm.environment.set("mail_env", useremail);
pm.environment.set("name_env", username);
```

## Create User Test Script

![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/create_user_test_script_02.png)

## Get User Details (Retrive) & test script 

![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/get_user_details_01.png)

## Test Script Details for the Get User  

This test script validates specific JSON fields in the API response by checking that the id, name, and email fields match the corresponding environment variables (userid_env, name_env, mail_env) stored in Postman's QA environment.

```bash
// validating JSON field in the response 

pm.test("Values of json fields", () => {
var jsonData = pm.response.json();
pm.expect(jsonData.id).to.eql(pm.environment.get("userid_env"));
pm.expect(jsonData.name).to.eql(pm.environment.get("name_env"));
pm.expect(jsonData.email).to.eql(pm.environment.get("mail_env"));
});
```

## Update User Details

![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/update_user_details_01.png)

## Test Script & Details for the Update User 
This test script generates a unique username and email by appending a random string to "jim" and then stores these values in Postman environment variables mail_env and name_env. These variables can be used to update user details in subsequent API requests.
```bash
var random = Math.random().toString(36).substring(2);
var useremail = "jim" + random + "@gmail.com";
var username = "jim" + random;

pm.environment.set("mail_env", useremail);
pm.environment.set("name_env", username);
```
## Update Test Script 

![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/update_user_details_script_02.png)


## Test Script & Details for the Delete User
This test script removes the userid_env, name_env, and mail_env environment variables from Postman. It clears the stored values to ensure a clean environment for future tests.

```bash
pm.environment.unset("userid_env");
pm.environment.unset("name_env");
pm.environment.unset("mail_env");
```

## Delete User Details 

![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/delete_user_details_01.png)

## Final Run Collection Result
![App Screenshot](https://raw.githubusercontent.com/md-abutalha/Go-Rest-API-Chaining-Testing-P03/master/go-rest-project-screenshots/final_run_collection_result.png)

## Project Summary

This repository provides a testing suite for the Go REST API Chaining project, covering CRUD operations with Postman. It includes scripts to generate random user data, validate API responses, and manage environment variables, ensuring reliable and consistent test execution.

## Authors

- [@abutalha](https://github.com/md-abutalha)


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://github.com/md-abutalha)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abu-talha1/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/abu_talha0x)


