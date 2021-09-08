# phonebook_spring

This project followed tutorials from Spring: [Accessing JPA Data with REST](https://spring.io/guides/gs/accessing-data-rest/) and 
[Building REST services with Spring](https://spring.io/guides/tutorials/rest/).\
Create a backend (SQL for this project) prior this part.

## Steps
### 1. Use the Spring Initializr to create a template project (on InteliJ)

The Spring Initializr creates a partially completed project which can be added by progressing through the guide. It comes included with a configuration to 
run the project, a pom file to pull down the necesary dependencies through Maven, and more. 

### 2. Create a User class

The user class `User.java` will represent a user in the table. It has 4 attributes for name, phone number, favorite, and (a generated) id, 
along with getters and setters for all 4.

### 3. Create a User repository interface

The user repository interface is automatically implemented by Spring that inherits from Spring's CrudRepository, allowing changes to be made to User objects. 

### 4. 
