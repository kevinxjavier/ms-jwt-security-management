# [ms-jwt-security-management](https://github.com/kevinxjavier/ms-jwt-security-management.git)

## Project for securitize SpringBoot project 

##### Software Requirements:
* Apache Maven 3.8.6
* Java 18.0.2.1
* MySQL 8.0.32
* Docker 24.0.7
* Spring-boot 3.3.4
* Tested on Debian GNU/Linux 9 (stretch)
* Install [core-parent](https://github.com/kevinxjavier/core-parent.git)

##### Guide
As soon as we start the app will create the user table in the database defines in application.properties.

##### Compile (If problems)
```
$ mvn clean compile package
$ mvn clean compile package -U       # -U means force update of snapshot dependencies

# If your local repository is somehow mucked up for release jars as opposed to snapshots (-U and --update-snapshots only update snapshots), you can purge the local repo using the following:
$ mvn dependency:purge-local-repository

# You probably then want to clean and install again (to solve the problem):
$ mvn dependency:purge-local-repository clean install
```

##### Setup

###### 1) Docker Postgres
sudo docker run -d --name mysql \
    --restart=unless-stopped \
    -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=shopping \
    -e MYSQL_USER=administrator -e MYSQL_PASSWORD=123456789 \
    -p 3306:3306 mysql/mysql-server:5.7

###### 2) Run
`mvn clean install` on the root `pom.xml` to install library in your `.m2`
`mvn $ mvn spring-boot:run`

##### Usage
See postman repository [Postman Collection APIRest](https://github.com/kevinxjavier/postman-apirest.git). Token Folder, request Signup and Login.

## Contact

| User    | Name                     | Role       |
|:--------|:-------------------------|:-----------|
| kpina   | Kevin Javier Piña        | Developer  |
