# phonebook_spring

This project followed tutorials from Spring: [Accessing JPA Data with REST](https://spring.io/guides/gs/accessing-data-rest/) and 
[Building REST services with Spring](https://spring.io/guides/tutorials/rest/).\
Create a backend (SQL for this project) prior this part.

## Steps
### 1. Use the Spring Initializr to create a template project (on InteliJ)

The Spring Initializr creates a partially completed project which can be added by progressing through the guide. It comes included with a configuration to 
run the project, a pom file to pull down the necesary dependencies through Maven, and more. 

### 2. Create a User class

The user class `User.java` will represent a user in the table. It has 4 attributes for `name`, `pNumber`, `favorite`, and (a generated) `id`, 
along with getters and setters.

### 3. Create a User repository interface

The user repository interface is automatically implemented by Spring that inherits from Spring's `CrudRepository`, allowing changes to be made to User objects. 

### 4. Create a Main Controller class

`MainController.java` is responsible for mapping certain actions in functions to specific HTTP requests. Each function has a `@CrossOrigin` tag, which 
enables cross-origin resource sharing (CORS). The specific mapping tags map each function to a HTTP request. The `@RequestBody` tag in 
the argument means the arguments will be supplied in the form of JSON in the body (as opposed to parameters with a `@RequestParam` tag). In these functions, 
actions can be performed on the userRepository. Additionally, when a function returns a `User` object, Spring sends it as JSON, which allows the information to 
be used to instantly update the front end in real time instead of refreshing the page. 

### 5. Test the Main Controller class

While requests can be fired from the front end, Postman can alternatively be used to test the functions in `MainController.java`. For example, a POST request can 
be initiated by adding a JSON body and the correct headers. 

<img width="1016" alt="Screen Shot 2021-09-08 at 2 01 44 PM" src="https://user-images.githubusercontent.com/41180186/132585054-563b00cf-20d8-4acb-8682-3e025f942369.png">

