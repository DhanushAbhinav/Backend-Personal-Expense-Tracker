Personal Expense Tracker

---- 
A RESTful API built with Spring Boot and SQLite for managing personal financial records. The API allows users to record income and expenses, retrieve past transactions, and get a summary by category or time period.

Features:

Record income and expense transactions.

Retrieve a list of all transactions.

Retrieve, update, or delete a transaction by ID.

Get a summary of transactions, including total income, total expenses, and balance.



Setup and Run Instructions:

-- Configure the Database (SQLite):

The application uses SQLite as the database in the resources folder 

-- Build the Project:

Use Maven to build the project and download dependencies.

mvn clean install

-- Run the Application:

You can run the Spring Boot application using Maven:

mvn spring-boot:run



API Documentation:

Base URL:

Local Development: http://localhost:8080


1. Add a New Transaction

URL: /transactions

Method: POST

Request Body:

{
  "type": "income",
  "category": "Salary",
  "amount": 5000,
  "date": "2024-10-01",
  "description": "October Salary"
}

Response:

{
  "id": 1,
  "type": "income",
  "category": "Salary",
  "amount": 5000,
  "date": "2024-10-01",
  "description": "October Salary"
}



2. Get All Transactions

URL: /transactions

Method: GET

Response:

[
  {
    "id": 1,
    "type": "income",
    "category": "Salary",
    "amount": 5000,
    "date": "2024-10-01",
    "description": "October Salary"
  },
  {
    "id": 2,
    "type": "expense",
    "category": "Groceries",
    "amount": 200,
    "date": "2024-10-05",
    "description": "Grocery shopping"
  }
]



3. Get a Transaction by ID

URL: /transactions/{id}

Method: GET

Response:

{
  "id": 1,
  "type": "income",
  "category": "Salary",
  "amount": 5000,
  "date": "2024-10-01",
  "description": "October Salary"
}



4. Update a Transaction by ID

URL: /transactions/{id}

Method: PUT

Request Body:

{
  "type": "expense",
  "category": "Rent",
  "amount": 1000,
  "date": "2024-10-03",
  "description": "October Rent"
}

Response:

{
  "id": 1,
  "type": "expense",
  "category": "Rent",
  "amount": 1000,
  "date": "2024-10-03",
  "description": "October Rent"
}



5. Delete a Transaction by ID

URL: /transactions/{id}

Method: DELETE

Response: 204 No Content will be displayed (if successful).

6. Get Summary

URL: /summary

Method: GET


Response:

{
  "totalIncome": 5000,
  "totalExpenses": 1200,
  "balance": 3800
}
