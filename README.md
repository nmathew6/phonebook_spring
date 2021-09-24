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


### 5. Create `application.properties` file

The file stores information about how to connect to the database. These are the credentials created in step 5 of the SQL tutorial.

```
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://${MYSQL_HOST:[ADD RASPBERRY PI IP ADDRESS HERE}:3306]/db_example
spring.datasource.username=springuser
spring.datasource.password=ThePassword
spring.datasource.driver-class-name =com.mysql.jdbc.Driver
#spring.jpa.show-sql: true
```

### 6. Test the Main Controller class

While requests can be fired from the front end, Postman can alternatively be used to test the functions in `MainController.java`. For example, a POST request can 
be initiated by adding a JSON body and the correct headers. 

<img width="1016" alt="Screen Shot 2021-09-08 at 2 01 44 PM" src="https://user-images.githubusercontent.com/41180186/132585054-563b00cf-20d8-4acb-8682-3e025f942369.png">

A DELETE request can be initiated with the following request, where the last number is the id of the element to be deleted. 
<img width="1017" alt="Screen Shot 2021-09-24 at 4 00 12 PM" src="https://user-images.githubusercontent.com/41180186/134747714-0f9d73eb-6236-4fc8-9aa5-c79707c6bf9d.png">

A GET request can be sent with this request, where the last number is the id of the request phone number. 
<img width="1007" alt="Screen Shot 2021-09-24 at 4 04 09 PM" src="https://user-images.githubusercontent.com/41180186/134747922-178e7247-7276-45c3-b17a-5165d4c37db0.png">

And finally a PUT request is done the same way:
<img width="1017" alt="Screen Shot 2021-09-24 at 4 05 17 PM" src="https://user-images.githubusercontent.com/41180186/134747977-2d60e994-033b-4e8f-9910-4da6b4ceed21.png">

