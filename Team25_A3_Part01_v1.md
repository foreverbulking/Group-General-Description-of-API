
# 3040Crypto API Documentation

## API Description

The 3040Crypto API provides users with a fast, reliable, and secure way to manage their cryptocurrency assets. This RESTful API enables users to check balances, perform transactions, and retrieve cryptocurrency market data. Designed to improve user experience and streamline wallet operations, this API aims to position 3040Crypto as the go-to platform for cryptocurrency management.

## Endpoints and Parameters

### 1. Get Wallet Balance

- **Endpoint:** `/api/v1/wallet/balance`
- **Method:** GET
- **Parameters:**
  - `wallet_id` (required): The unique identifier of the user's wallet.
  - `currency` (optional): The specific cryptocurrency to check the balance of. If not specified, all currencies will be returned.
- **Description:** Returns the current balance of the specified cryptocurrency in the user's wallet.

### 2. Perform Transaction

- **Endpoint:** `/api/v1/wallet/transaction`
- **Method:** POST
- **Parameters:**
  - `wallet_id` (required): The unique identifier of the user's wallet.
  - `transaction_type` (required): Can be 'send' or 'receive'.
  - `amount` (required): The amount of cryptocurrency to send or receive.
  - `currency` (required): The type of cryptocurrency for the transaction.
- **Description:** Allows the user to send or receive cryptocurrency.

### 3. Get Market Data

- **Endpoint:** `/api/v1/market/data`
- **Method:** GET
- **Parameters:**
  - `currency` (required): The type of cryptocurrency to retrieve the market data for.
- **Description:** Retrieves the latest market data for the specified cryptocurrency.


## Sample Requests and Sample Responses

### 1. Get Wallet Balance 
 - **Sample Request** 

  GET /api/v1/wallet/balance?wallet_id=7889760&currency=Etherium

 - **Sample Reponse**

  HTTP/1.1 200 OK
  Content-Type: application/json

  {
    "wallet_id":"7889760",
    "currency":"Etherium",
    "balance":112.70
  }

### 1. Perform Transaction
 - **Sample Request** 

  POST /api/v1/wallet/transaction
  Content-type: application-json
  {
    "wallet_id":"7889760",
    "transaction_type":"receive",
    "amount":40,
    "currency": "Etherium"
  }

 - **Sample Reponse**

  HTTP/1.1 200 OK
  Content-Type: application/json

  {
    "trasaction_id":"98244067541236",
    "status":"success",
    "message":"transaction completed successfully"
  }

  ### 1. Get Market Data 
 - **Sample Request** 

  GET /api/v1/wallet/data?currency=Etherium

 - **Sample Reponse**

  HTTP/1.1 200 OK
  Content-Type: application/json

  {
    "currency":"Etherium",
    "price_CAD":4777.74,
    "price_AUD":5367.87,
    "price_USD":3538.74,
    "price_EUR":3246.32,
  }


