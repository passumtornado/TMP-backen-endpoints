# API Documentation

## Base URL
`https://tmp-se-project.azurewebsites.net/`

## Admin Endpoints

### Admin Signup
- **URL:** `/api/admin/auth/signup`
- **Method:** `POST`
- **Description:** Registers a new admin.
- **Body:**
  ```json
  {
    "first_name": "string",
    "last_name": "string",
    "email": "string",
    "password": "string",
    "contact": "string"
  }
  ```
- **Success Response:**
  - **Code:** 201
  - **Content:** `{ "message": "Admin registered successfully" }`

### Admin Login
- **URL:** `/api/admin/auth/login`
- **Method:** `POST`
- **Description:** Logs in an admin.
- **Body:**
  ```json
  {
    "email": "string",
    "password": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "token": "jwt_token" }`

### Admin Logout
- **URL:** `/api/admin/auth/logout`
- **Method:** `POST`
- **Description:** Logs out an admin.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Admin logged out successfully" }`

### Verify Email
- **URL:** `/api/admin/auth/verify-email`
- **Method:** `POST`
- **Description:** Verifies admin email.
- **Body:**
  ```json
  {
    "email": "string",
    "token": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Email verified successfully" }`

### Forgot Password
- **URL:** `/api/admin/auth/forgot-password`
- **Method:** `POST`
- **Description:** Sends a password reset link to the admin's email.
- **Body:**
  ```json
  {
    "email": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Password reset link sent" }`

### Reset Password
- **URL:** `/api/admin/auth/reset-password/:token`
- **Method:** `POST`
- **Description:** Resets the admin's password.
- **URL Params:**
  - **token:** `string`
- **Body:**
  ```json
  {
    "password": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Password reset successfully" }`

### Update Admin Details
- **URL:** `/api/admin/auth/update`
- **Method:** `PUT`
- **Description:** Updates admin details.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "first_name": "string",
    "last_name": "string",
    "email": "string",
    "contact": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Admin details updated successfully" }`

### Check Auth
- **URL:** `/api/admin/auth/check-auth`
- **Method:** `GET`
- **Description:** Checks if the admin is authenticated.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Authenticated" }`

## User/user Endpoints

### User Signup
- **URL:** `/api/user/auth/signup`
- **Method:** `POST`
- **Description:** Registers a new user/user.
- **Body:**
  ```json
  {
    "username": "string",
    "email": "string",
    "password": "string"
  }
  ```
- **Success Response:**
  - **Code:** 201
  - **Content:** `{ "message": "User registered successfully" }`

### User Login
- **URL:** `/api/user/auth/signin`
- **Method:** `POST`
- **Description:** Logs in a user/user.
- **Body:**
  ```json
  {
    "email": "string",
    "password": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "token": "jwt_token" }`

### User Logout
- **URL:** `/api/user/auth/logout`
- **Method:** `POST`
- **Description:** Logs out a user/user.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "User logged out successfully" }`

### Verify Email
- **URL:** `/api/user/auth/verify-email`
- **Method:** `POST`
- **Description:** Verifies user/user email.
- **Body:**
  ```json
  {
    "email": "string",
    "token": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Email verified successfully" }`

### Forgot Password
- **URL:** `/api/user/auth/forgot-password`
- **Method:** `POST`
- **Description:** Sends a password reset link to the user/user's email.
- **Body:**
  ```json
  {
    "email": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Password reset link sent" }`

### Reset Password
- **URL:** `/api/user/auth/reset-password/:token`
- **Method:** `POST`
- **Description:** Resets the user/user's password.
- **URL Params:**
  - **token:** `string`
- **Body:**
  ```json
  {
    "password": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Password reset successfully" }`

## Learner Endpoints

### Create Learner
- **URL:** `/api/learners`
- **Method:** `POST`
- **Description:** Creates a new learner.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "firstname": "string",
    "lastname": "string",
    "email": "string",
    "course": "string",
    "gender": "string",
    "location": "string",
    "phone": "string",
    "disability": "string",
    "image": "string",
    "description": "string",
    "amount": "number"
  }
  ```
- **Success Response:**
  - **Code:** 201
  - **Content:** `{ "message": "Learner created successfully", "learner": { ...learnerData } }`

### Get All Learners
- **URL:** `/api/learners`
- **Method:** `GET`
- **Description:** Retrieves all learners.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `[ { ...learnerData }, ... ]`

### Get Learner by ID
- **URL:** `/api/learners/:id`
- **Method:** `GET`
- **Description:** Retrieves a learner by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ ...learnerData }`

### Update Learner by ID
- **URL:** `/api/learners/:id`
- **Method:** `PUT`
- **Description:** Updates a learner by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "firstname": "string",
    "lastname": "string",
    "email": "string",
    "course": "string",
    "gender": "string",
    "location": "string",
    "phone": "string",
    "disability": "string",
    "image": "string",
    "description": "string",
    "amount": "number"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Learner updated successfully", "learner": { ...learnerData } }`

### Delete Learner by ID
- **URL:** `/api/learners/:id`
- **Method:** `DELETE`
- **Description:** Deletes a learner by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Learner deleted successfully" }`

## Course Endpoints

### Create Course
- **URL:** `/api/courses`
- **Method:** `POST`
- **Description:** Creates a new course.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "title": "string",
    "description": "string",
    "duration": "string",
    "price": "number"
  }
  ```
- **Success Response:**
  - **Code:** 201
  - **Content:** `{ "message": "Course created successfully", "course": { ...courseData } }`

### Get All Courses
- **URL:** `/api/courses`
- **Method:** `GET`
- **Description:** Retrieves all courses.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `[ { ...courseData }, ... ]`

### Get Course by ID
- **URL:** `/api/courses/:id`
- **Method:** `GET`
- **Description:** Retrieves a course by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ ...courseData }`

### Update Course by ID
- **URL:** `/api/courses/:id`
- **Method:** `PUT`
- **Description:** Updates a course by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "title": "string",
    "description": "string",
    "duration": "string",
    "price": "number"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Course updated successfully", "course": { ...courseData } }`

### Delete Course by ID
- **URL:** `/api/courses/:id`
- **Method:** `DELETE`
- **Description:** Deletes a course by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Course deleted successfully" }`

## Invoice Endpoints

### Create Invoice
- **URL:** `/api/invoices`
- **Method:** `POST`
- **Description:** Creates a new invoice.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "learnerId": "string",
    "amount": "number",
    "description": "string",
    "dueDate": "string"
  }
  ```
- **Success Response:**
  - **Code:** 201
  - **Content:** `{ "message": "Invoice created successfully", "invoice": { ...invoiceData } }`

### Get All Invoices
- **URL:** `/api/invoices`
- **Method:** `GET`
- **Description:** Retrieves all invoices.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `[ { ...invoiceData }, ... ]`

### Get Invoice by ID
- **URL:** `/api/invoices/:id`
- **Method:** `GET`
- **Description:** Retrieves an invoice by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ ...invoiceData }`

### Update Invoice by ID
- **URL:** `/api/invoices/:id`
- **Method:** `PUT`
- **Description:** Updates an invoice by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Body:**
  ```json
  {
    "learnerId": "string",
    "amount": "number",
    "description": "string",
    "dueDate": "string"
  }
  ```
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Invoice updated successfully", "invoice": { ...invoiceData } }`

### Delete Invoice by ID
- **URL:** `/api/invoices/:id`
- **Method:** `DELETE`
- **Description:** Deletes an invoice by ID.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "message": "Invoice deleted successfully" }`

## Revenue Endpoints

### Get Total Revenue
- **URL:** `/api/revenue/total`
- **Method:** `GET`
- **Description:** Retrieves the total revenue.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "totalRevenue": "number" }`

### Get Revenue by Date Range
- **URL:** `/api/revenue`
- **Method:** `GET`
- **Description:** Retrieves revenue within a specified date range.
- **Headers:**
  - `Authorization: Bearer <token>`
- **Query Params:**
  - **startDate:** `string`
  - **endDate:** `string`
- **Success Response:**
  - **Code:** 200
  - **Content:** `{ "revenue": "number" }`
