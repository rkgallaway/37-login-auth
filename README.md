![CF](http://i.imgur.com/7v5ASc8.png) LAB 37
=================================================

## Lab 37: `<Login />` and `<Auth />`

### Author: Ryan Gallaway

### Links and Resources

[![Build Status](https://www.travis-ci.com/rkgallaway/37-login-auth.svg?branch=master)](https://www.travis-ci.com/rkgallaway/37-login-auth)

* [repo](https://github.com/rkgallaway/37-login-auth)
* [travis](https://www.travis-ci.com/rkgallaway/37-login-auth)
* [back-end](http://xyz.com) (when applicable)
* [front-end](http://xyz.com) (when applicable)

#### Documentation
* [swagger](http://xyz.com) (API assignments only)
* [jsdoc](http://xyz.com) (All assignments)

### Modules
#### `modulename.js`
##### Exported Values and Methods

### Requirements
* Hide the entire interface until the user has logged in.
* Provide a login and logout option in the main menu
* Implement the following RBAC rules:
    * Logged In Users with 'read' permissions can see the list of data models and records
    * Logged In Users with 'delete' permissions can delete records
    * Logged In Users with 'update' permissions can edit existing records
    * Logged In Users with 'create' permissions can create new records

### Notes
* You may not alter the functionality of the existing application components.
* You may only grant access using RBAC
* The API server supports the following routes:
  * **POST** `/roles` - Accepts a JSON object with `role`, `capabilities` (array) to create a role.
  * **POST** `/signup` - Accepts a JSON object with `username`, `password` to create an account
  * **POST** `/signin` - Signin with either Basic Auth or Bearer Auth, returning a JWT Token
  * **GET** `/api/v1/models` - A list of all data models
  * **GET** `/api/v1/model` - A list of all records in a given **model**
  * **GET** `/api/v1/model/schema` - The JSON Schema for a given **model**
  * **GET** `/api/v1/model/id` - A single record, from a **model**, with the **id**
  * **DELETE** `/api/v1/model/id` - Delete a single record, from a **model**, with the **id**
  * **PUT** `/api/v1/model/id` - Replace single record, from a **model**, with the **id**
  * **PATCH** `/api/v1/model/id` - Tactically update a single record, from a **model**, with the **id**
* The API server has the following user accounts (username:password) that you can use to login as a user with varying permissions
  * admin:ADMIN (create, read, update, delete)
  * editor:EDITOR (create, read, update)
  * user:USER (read)

### Setup
#### `.env` requirements
* `PORT` - Port Number
* `MONGODB_URI` - URL to the running mongo instance/db

#### Running the app
* `npm start`
* Endpoint: `/foo/bar/`
  * Returns a JSON object with abc in it.
* Endpoint: `/bing/zing/`
  * Returns a JSON object with xyz in it.
  
#### Tests
* `npm test` to run tests?
* Write a suite of UI tests that assert the existence of components based on user login state.
* Create some mocking interface to fake a server/login to simulate.
#### UML
![login and auth UML](./assets/uml.jpg)
