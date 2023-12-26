# Expense Manager App

This is a Spring Boot application for managing expenses.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- Java 8 or higher
- Maven
- Docker
- MySQL

### Installing

1. Clone the repository

```sh
git clone https://github.com/NitinS87/expense-manager-app.git
```

2. Navigate to the project directory

```sh
cd expense-manager-app
```

3. Build the project

```sh
mvn clean install
```

4. Run the application

```sh
mvn spring-boot:run
```

5. Access the application

```sh
http://localhost:8080
```

Database Configuration
In src/main/resources/application.properties, set the following:

```sh
spring.datasource.url=jdbc:mysql://mysql:3306/expense
spring.datasource.username=root
spring.datasource.password=root
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQLDialect

logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate=ERROR

server.port=8080
```

Replace localhost:3306, root, and root with your MySQL host, username, and password respectively.

## API Endpoints

### Expense

| Method | Endpoint       | Description          |
| ------ | -------------- | -------------------- |
| POST   | /expenses      | Create a new expense |
| GET    | /expenses      | Get all expenses     |
| GET    | /expenses/{id} | Get an expense by id |
| PUT    | /expenses/{id} | Update an expense    |
| DELETE | /expenses/{id} | Delete an expense    |

### Create Expense

```sh
POST /expenses
```

Request Body

```sh
{
    "name": "college",
    "cost": 2000000,
    "date": "2002-06-20",
    "color": "red",
    "url": "hey!",
    "remarks": "college fees"
}
```

Response Body

```sh
{
    "id": 1,
    "name": "college",
    "cost": 2000000,
    "date": "2002-06-20T00:00:00.000+00:00",
    "color": "red",
    "url": "hey!",
    "remarks": "college fees"
}
```

### Get All Expenses

```sh
GET /expenses
```

Response Body

```sh
[
    {
        "id": 1,
        "name": "college",
        "cost": 2000000,
        "date": "2002-06-20T00:00:00.000+00:00",
        "color": "red",
        "url": "hey!",
        "remarks": "college fees"
    },
    {
        "id": 2,
        "name": "car",
        "cost": 2000000,
        "date": "2002-06-20T00:00:00.000+00:00",
        "color": "red",
        "url": "hey!",
        "remarks": "car fees"
    }
]
```

### Get Expense By Id

```sh
GET /expenses/{id}
```

Response Body

```sh
{
    "id": 1,
    "name": "college",
    "cost": 2000000,
    "date": "2002-06-20T00:00:00.000+00:00",
    "color": "red",
    "url": "hey!",
    "remarks": "college fees"
}
```

### Update Expense

```sh
PUT /expenses/{id}
```

Request Body

```sh
{
    "name": "college",
    "cost": 2000000,
    "date": "2002-06-20",
    "color": "red",
    "url": "hey!",
    "remarks": "college fees"
}
```

Response Body

```sh
{
    "id": 1,
    "name": "college",
    "cost": 2000000,
    "date": "2002-06-20T00:00:00.000+00:00",
    "color": "red",
    "url": "hey!",
    "remarks": "college fees"
}
```

### Delete Expense

```sh
DELETE /expenses/{id}
```

Response Body

```sh
{
    "id": 1,
    "name": "college",
    "cost": 2000000,
    "date": "2002-06-20T00:00:00.000+00:00",
    "color": "red",
    "url": "hey!",
    "remarks": "college fees"
}
```

## Built With

- [Spring Boot](https://spring.io/projects/spring-boot) - The web framework used
- [Maven](https://maven.apache.org/) - Dependency Management
- [MySQL](https://www.mysql.com/) - Database
- [Docker](https://www.docker.com/) - Containerization

## Authors

- **Nitin Sharma** - [NitinS87](https://github.com/NitinS87)
