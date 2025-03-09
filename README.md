# **Blog API**

A secure and scalable Node.js-based Blog API with authentication, authorization, and CRUD operations for users and posts.

---

## **Features**

- **User Authentication**:
  - Signup and login with JWT-based authentication.
  - Password hashing using bcrypt.
- **Role-Based Authorization**:
  - Admin and user roles.
  - Restricted access to certain endpoints based on roles.
- **Posts Management**:
  - Create, read, update, and delete posts.
  - Only authenticated users can create, update, or delete their own posts.
- **Security Enhancements**:
  - Rate limiting to prevent brute-force attacks.
  - Helmet for secure HTTP headers.
  - Express-mongo-sanitize to prevent NoSQL injection.
  - XSS-clean to prevent cross-site scripting (XSS) attacks.
  - HPP to protect against HTTP parameter pollution.
- **Pagination & Search**:
  - Paginated results for fetching posts.
  - Search functionality for posts.

---

## **Technologies Used**

- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Authentication**: JSON Web Tokens (JWT)
- **Security**: bcrypt, helmet, express-mongo-sanitize, xss-clean, hpp
- **Rate Limiting**: express-rate-limit
- **Error Handling**: Custom error handling middleware
- **Environment Variables**: dotenv

---

## **Installation**

1. Clone the repository:
   ```bash
   git clone https://github.com/Mahmoud-Eid-Elsayed/Blog-API.git
   cd blog-api
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add the following variables:
     ```env
     PORT=3000
     MONGO_URI=mongodb://localhost:27017/blogdb
     SALT_ROUNDS=10
     JWT_SECRET=your_jwt_secret
     JWT_EXPIRES_IN=1d
     ```

4. Start the server:
   ```bash
   npm start
   ```

---

## **API Endpoints**

### **Users**
- **POST `/api/v1/users/signup`**: Create a new user.
- **POST `/api/v1/users/login`**: Authenticate a user and get a JWT token.
- **GET `/api/v1/users`**: Get all users (admin only).
- **GET `/api/v1/users/:id`**: Get a user by ID.
- **PUT `/api/v1/users/:id`**: Update a user by ID.
- **DELETE `/api/v1/users/:id`**: Delete a user by ID.

### **Posts**
- **POST `/api/v1/posts`**: Create a new post (authenticated users only).
- **GET `/api/v1/posts`**: Get all posts (paginated).
- **GET `/api/v1/posts/:id`**: Get a post by ID.
- **PATCH `/api/v1/posts/:id`**: Update a post by ID (only the creator).
- **DELETE `/api/v1/posts/:id`**: Delete a post by ID (only the creator).

---

## **Environment Variables**

| Variable       | Description                          | Default Value           |
|----------------|--------------------------------------|-------------------------|
| `PORT`         | Port on which the server runs        | `3000`                 |
| `MONGO_URI`    | MongoDB connection string            | `mongodb://localhost:27017/blogdb` |
| `SALT_ROUNDS`  | Salt rounds for bcrypt hashing       | `10`                   |
| `JWT_SECRET`   | Secret key for JWT signing           | `your_jwt_secret`      |
| `JWT_EXPIRES_IN` | Expiry time for JWT tokens         | `1d`                   |

---

## **Contributing**

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeatureName`).
5. Open a pull request.

---

## **License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## **Contact**

For any questions or feedback, feel free to reach out:

- **LinkedIN**: [Mahmoud Elsayed-LinkedIN](https://www.linkedin.com/in/mahmoud-elsayed/)
- **GitHub**: [Mahmoud Elsayed](https://github.com/Mahmoud-Eid-Elsayed/)

---

Enjoy building your blog with this API! 🚀
