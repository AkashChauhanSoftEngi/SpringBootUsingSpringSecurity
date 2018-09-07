# SpringBootUsingSpringSecurity

* Spring provides, the abstract repositories, that are implemented at run time by spring container to perform CRUD operations.
* Just need to provides the abstracts methods in the interface
* When you design your own method in the interface which extends JpaInterface
  - We need to make sure to use specific method names(findByUsername) with model class parameters(username)
  - Return type will also be in consideration while creating these implementations at run time by JDK
  - The implementations of these methods would be created at run time.
* About HttpSecurity
  - To authorize inceoming request {whether this user has access to this resource or not}
  - authorizeRequests(): correct http request from client
  - authorizeRequests().antMatchers: to define a specify URL
  - authenticated(): user be authenticated, must belong to the application
  - example: http.authorizeRequests().antMatchers("/**").hasRole("USER").and().formLogin();
* There are three base interfaces
  a) Repository {No methods}
  b) CrudRepository　{Crud basic methods} which extends Repository
  c) JpaRepository {Including all the parameters}
* Reference: https://www.callicoder.com/spring-boot-rest-api-tutorial-with-mysql-jpa-hibernate/
* Connecting with Mysql + Spring Boot, we need to add like this in property file
```xml
	## Spring DATASOURCE (DataSourceAutoConfiguration & DataSourceProperties)
	spring.datasource.url = jdbc:mysql://localhost:3306/notes_app?useSSL=false
	spring.datasource.username = root
	spring.datasource.password = root


	## Hibernate Properties
	# The SQL dialect makes Hibernate generate better SQL for the chosen database
	spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQL5InnoDBDialect

	# Hibernate ddl auto (create, create-drop, validate, update)
	spring.jpa.hibernate.ddl-auto = update
```
