# Advanced Web Applications - The 3rd weekly exercise
This repository contains the 3rd weekly exercice for the LUT University's course Advanced Web Applications. The purpose of this exercise is to build a simple Todo app using Node.js, Express.js libraries and chosen a view engine.

## Requirements

### 1. Render a site

* App should have an index page with a text "My todos" somewhere on it. 

* App should use _pug_ view engine to render the page

### 2. Save users to server

* Should have an input field with an id of _input-name_

* Should have an input field with an id of _input-task_

* Should have a button with an id of _submit-data_

* should have a POST route `/todo` that saves name and todo in an array of objects

  * If the server already has stored the name the client sent to the server: 

    * the server shouldn't make a new entry but rather find the object and append the task the client sent to the list.

  * If a new user was added, the server should sent "User added" back to the client

  * If a task was added to an existing client, the server should respond with "Todo added". 

  * The client should display these messages accordingly.

* front end should send name and todo to the POST route after clicking the _submit-data_ -button.


### 3. Fetch users

The client should be able to fetch users and their todos based on their name.

* should have a GET route to `"/user/:id"`

* should have an `input field` with an id of "search-name"

* should have a `button` with an id of "search"

* Upon pressing the search button, the client should send a get request to "/user/:id" route (for example "/user/jukka"):

  * the server should try to respond with the name and todos of the user

  * If the user is not found, the server should respond with "User not found".

* After the request is done, the client should display the name and todos of the queried user on the website.

* If the user is not found, the client should display the appropriate message instead.

### 4. Delete users

* If a user is found, a button with an id of delete-user should appear. 

* After _delete-user_ button is pressed, it should make a DELETE request to "/user/:id" route. 

* The backend should try to delete the user based on the name the client sent to the server in the id section of the URL.

* If the deletion is successful, the server should respond with "User deleted". 

  * If the operation is successful, the user shouldn't be displayed on the website anymore. 

* if the operation is unsuccessful, the server should respond with "User not found". 

* Whether or not the operation was successful, the message the server sent should be displayed regardless.

### 5. Delete todos

The client should be able to delete singular todos.

*  After searching for a user, the client should have clickable elements (buttons or the todos themselves) with a class of `delete-task`. 

* You should display as many of these elements as there are todos, and 

* clicking on one of the elements would remove a corresponding todo

  * When an element is clicked, the client should send a PUT request to "/user":

  * the backend should try to find the user and delete the right todo.

    * If the task is successful: the server should respond with "Task deleted" 

    * if not: the server should respond with a message "User not found" 
