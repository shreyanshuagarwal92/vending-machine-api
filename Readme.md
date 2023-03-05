# Vending Machine API

This is a Node.js API for a vending machine that allows users to deposit coins, purchase products, and reset their deposits.

## Technologies

- Node.js
- Typescript
- Express.js
- MongoDB
- Mongoose
- Jest

## Getting Started

1. Clone the repository:

```sh
git clone https://github.com/shreyanshuagarwal92/vending-machine-api.git
```

2. Install the dependencies:

```sh
cd vending-machine-api
npm install
```

3. Create a `.env` file with the following environment variables:

```yaml
PORT=3000
MONGODB_URI=
JWT_SECRET=your-jwt-secret
```

4. Start the server:

```sh
npm start
```

The server will start on http://localhost:3000.

## API Endpoints

The API has the following endpoints:

### Authentication

- POST /login: Authenticate a user and return a JWT token.
- POST /logout: Logout the current user.

### Users

- GET /users: Get all users (requires admin role).
- GET /users/:id: Get a user by ID (requires admin role).
- POST /users: Create a new user.
- PUT /users/:id: Update a user by ID (requires admin role).
- DELETE /users/:id: Delete a user by ID (requires admin role).

### Products

- GET /products: Get all products.
- GET /products/:id: Get a product by ID.
- POST /products: Create a new product (requires seller role).
- PUT /products/:id: Update a product by ID (requires seller role).
- DELETE /products/:id: Delete a product by ID (requires seller role).

### Deposits

- POST /deposits: Deposit a coin.

### Purchases

- POST /purchases: Make a purchase.

### Reset

- POST /reset: Reset the deposit.

> All endpoints except /login and /users require authentication with a JWT token.

## Testing

To run the tests, run:

```sh
npm test
```

## Project structure

```ts
├── src
│   ├── controllers
│   │   ├── AuthenticationController.ts
│   │   ├── DepositController.ts
│   │   ├── ProductController.ts
│   │   ├── PurchaseController.ts
│   │   └── UserController.ts
│   ├── models
│   │   ├── Coin.ts
│   │   ├── Purchase.ts
│   │   ├── Product.ts
│   │   └── User.ts
│   ├── routes
│   │   ├── authentication.ts
│   │   ├── deposit.ts
│   │   ├── product.ts
│   │   ├── purchase.ts
│   │   └── user.ts
│   ├── services
│   │   ├── AuthenticationService.ts
│   │   ├── DepositService.ts
│   │   ├── ProductService.ts
│   │   ├── PurchaseService.ts
│   │   └── UserService.ts
│   └── utils
│   │   └── ErrorHandler.ts
│   ├── app.ts
│   ├── server.ts
│   └── types.ts
├── config
│   ├── database.ts
│   └── express.ts
├── tests
│   ├── authentication.test.ts
│   ├── deposit.test.ts
│   ├── product.test.ts
│   ├── purchase.test.ts
│   └── user.test.ts
├── .env
├── .gitignore
├── package.json
├── README.md
└── tsconfig.json
```
