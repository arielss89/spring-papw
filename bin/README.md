
<!-- In this section add TOC for easy navegation -->
<p align="center">
<b><a href="#requeriments">Requeriments</a></b>
|
<b><a href="#Howtorun">How to run</a></b>
|
<b><a href="#HowtousetheAPI">How to use the API</a></b>
</p>


## Requeriments

* Java - 1.8.x
* JDK or OpenJDK - 1.8.x
* Maven - 3.x.x
* MySQL - 5.x.x or MariaDB 10.x.x
* Spring - 2.0.0.RELEASE (inclued in pom.xml)

* Tested on:
* GNU/Linux Solus 3
* JDK 1.8.0_161
* Linux Kernel 4.15.6-58.current
* MariaDB 10.1.29

## How to run

**1. Clone the repository.**

```bash

```

**2. Create the database "persons" in MySQL or MariaDB.**

```
mysql -u root -p
```

```
mysql> create database persons;
```

**3. Change mysql username and password as per your installation**

+ open `src/main/resources/application.properties`.

+ change `spring.datasource.username` and `spring.datasource.password` as per your MySQL installation.

+ by default the user is: 'root' and password is: '1234' (without the ').


```java
spring.datasource.url = jdbc:mysql://localhost:3306/persons?autoReconnect=true&useUnicode=true&characterEncoding=UTF-8&allowMultiQueries=true&useSSL=false
spring.datasource.username = root
spring.datasource.password = 1234
```

**4. Build and run the app using Maven**

```bash
mvn package
java -jar target/person-1.0.0.jar
```


+ Also, you can run the app without packaging it using:

```bash
mvn spring-boot:run
```

+ Also, you can run the app without packaging it using:

```bash
./run.sh
```




+ The app will start running at <http://localhost:8080>.
+ The REST service is running at <http://localhost:8080/api/v1.0>.


## How to use the API

+ The current version of the API is v1.0.

1. Creating a new Person using POST /api/v1.0/persons API
+ localhost:8080/api/persons/
+ Example: {"firstName": "Rodrigo", "lastName":"Fujioka"}


2. Retrieving all Persons using GET /api/v1.0/persons API
+ localhost:8080/api/persons/


3. Retrieving a single Person using GET /api/v1.0/persons/{personId} API
+ localhost:8080/api/persons/1



4. Updating a Person using PUT /api/v1.0/persons/{personId} API
+ localhost:8080/api/persons/1
+ Example: {"firstName": "Ana", "lastName":"Fujioka"}


5. Deleting a Person using DELETE /api/v1.0/persons/{personId} API
+ localhost:8080/api/persons/1

