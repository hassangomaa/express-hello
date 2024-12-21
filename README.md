# Express Hello Application

This is a simple **Express.js** application that demonstrates the use of basic HTTP methods (`GET`, `POST`, and `DELETE`) to manage a collection of users. It provides a basic API to interact with user data.

---

## Features

- **Home Route**: A welcome message is displayed at the root endpoint.
- **User Management**:
  - `GET /users`: Retrieve a list of users.
  - `POST /users`: Add a new user.
  - `DELETE /users/:id`: Remove a user by ID.

---

## Installation and Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd express-hello
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the development server:
   ```bash
   npm run dev
   ```

4. The server will start at:
   ```
   http://localhost:3000
   ```

---

## API Endpoints

### 1. **GET `/`**
   - **Description**: Displays a welcome message.
   - **Response**: 
     ```
     Welcome to home!
     ```

### 2. **GET `/users`**
   - **Description**: Retrieves all users.
   - **Response**:
     - **200 OK**: Returns a list of users.
     - **404 Not Found**: If no users are present.

   Example:
   ```
   GET /users
   Response:
   [
     { "id": "1", "name": "John Doe" }
   ]
   ```

### 3. **POST `/users`**
   - **Description**: Adds a new user.
   - **Request Body**: JSON object with `id` and `name`.
     Example:
     ```json
     {
       "id": "1",
       "name": "John Doe"
     }
     ```
   - **Response**:
     - **201 Created**: User added successfully.
     - **400 Bad Request**: If a user with the same ID already exists.

### 4. **DELETE `/users/:id`**
   - **Description**: Deletes a user by their `id`.
   - **Response**:
     - **200 OK**: If the user is deleted successfully.
     - **400 Bad Request**: If the user does not exist.

---

## Directory Structure

```
express-hello/
├── index.js             # Main application file
├── package.json         # Node.js configuration
└── README.md            # Project documentation
```

---

## Dependencies

- **express**: Web framework for Node.js.
- **nodemon**: For automatically restarting the server during development.

Install these dependencies with:
```bash
npm install express nodemon
```

---

## Running the Application

1. Start the server:
   ```bash
   npm run dev
   ```

2. Open a tool like **Postman** or **cURL** to interact with the API.

---

## Example Usage

### Add a User:
```bash
curl -X POST http://localhost:3000/users \
-H "Content-Type: application/json" \
-d '{"id": "1", "name": "John Doe"}'
```

### Retrieve Users:
```bash
curl http://localhost:3000/users
```

### Delete a User:
```bash
curl -X DELETE http://localhost:3000/users/1
```

---