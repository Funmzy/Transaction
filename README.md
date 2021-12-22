# Transaction
### Setup
1. Your are required to use `TypeScript` for the task and build the APIs (endpoints) with `express`
2. Use and setup the project with `Yarn`
3. Install docker on your Mac <a href="https://desktop.docker.com/mac/stable/Docker.dmg">Download</a>
4. Create a docker Registry on <a href="https://hub.docker.com/signup">Create Account</a>
5. Containerize your application with Docker.
## Problem Description:
Imagine you are asked to develop a transfer service with APIs to transfer money between two accounts
You application is expected to have the following database structure
- TABLE 1 - transactions  
    - reference (unique)
    - senderAccount nr
    - amount
    - receiverAccount nr
    - transferDescription
    - createdAt
    - updatedAt
    
- TABLE 2 - balances 
    - account nr (unique, 10 digits)
    - balance (each user should get 5000 when they create an acct)
    - createdAt
    - updatedAt
    - userId

- Table 3 - users
    - firstName
    - lastname
    - DOB
    - email (unique)
    - phone number (unique)
    
The transaction table registers any transaction in an account (ie. today I paid N2000 for a movie with my card), the balances table represents the account balance of customers (ie. I have N50k in my bank account). If a sender is trying to make a transaction of an amount of money more than his current balance, an error should be returned indicating insufficient funds
The API you are to develop should be able to handle a transfer request of the form below and updates the transactions/balances table accordingly.
```
{
    senderAccount: account,
    receiverAccount: account,
    amount: money,
    transferDescription: transfer description
}
```


### Endpoints to test
| Method       | Endpoint     | Enable a user to:    |
| :------------- | :---------- | :----------- |
| POST | /create-account  | Enable user to create an account stored in the balance table    |
| GET   | /balance/:accountNumber | Getting balance for a particular account number |
|       | /balabce/:userId | Getting balance for a particular user
| GET   | /balance | Getting all accounts and their balance |
| POST   | /transfer | To make a transaction to another account |
| GET.   | /transaction/:accountNumber | gets all transactions of a particular user
| GET.   | /transaction/credit/:accountNumber | gets all credit transactions of a particular user
| GET.   | /transaction/debit/:accountNumber | gets all debit transactions of a particular user
## Test coverage
- Make sure you write test to cover your application using supertest
## Hosting
- Host your application on Heroku
