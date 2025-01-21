<h1>
  <span class="headline">RESTful Routing</span>
  <span class="subhead">RESTful HTTP Methods</span>
</h1>

**Learning Objective:**  
By the end of this lesson, you will be able to **describe** the CRUD functionalities associated with common HTTP request methods and explain how they are used in API development.

## What Are HTTP Requests?

Before we dive into RESTful HTTP methods, let's start with the basics: **HTTP** stands for "Hypertext Transfer Protocol." It’s the foundation of how the internet works—allowing computers to send and receive information.

When you type a URL into your browser and press Enter, your computer sends a message (called an **HTTP request**) to the server that hosts the website. The server then sends back a response, such as a webpage, an image, or some other information.

HTTP requests typically consist of:

1. **A method:** This indicates what action you want to perform (ex: get information, send data, update something, or delete something).
2. **A URL or endpoint:** This specifies where the request is going (ex: `/books`, `/users`, etc.).
3. **Optional data:** Some requests include data (ex: sending a form or uploading a file).

## HTTP Methods and CRUD Operations

In web development, we use HTTP methods to perform different actions on data. These actions often align with **CRUD operations**:

- **C**reate
- **R**ead
- **U**pdate
- **D**elete

Here is a summary of how HTTP methods correspond to CRUD operations:

| HTTP Method | CRUD Operation | Example in a Database       |
| ----------- | -------------- | --------------------------- |
| `GET`       | Read           | Retrieve a list of books    |
| `POST`      | Create         | Add a new book to the list  |
| `PUT`       | Update         | Replace details of a book   |
| `PATCH`     | Update         | Modify specific book fields |
| `DELETE`    | Delete         | Remove a book               |

### Real-World Examples of HTTP Methods

1. **`GET`: Reading Data**  
   When you visit an online store and browse products, you're making a `GET` request to the server. For example:

   - URL: `/products`
   - Action: The server sends back a list of all products.

2. **`POST`: Creating New Data**  
   When you sign up for a website, you're making a `POST` request. For example:

   - URL: `/users`
   - Data: `{ "username": "new_user", "email": "new_user@example.com", "password": "S3Cr3tP@SsW0Rd" }`
   - Action: The server creates a new user account.

3. **`PUT`: Replacing Data**  
   Imagine updating your entire profile. You might send a `PUT` request with all your profile information:

   - URL: `/users/123`
   - Data: `{ "name": "John Doe", "email": "john.doe@example.com" }`
   - Action: The server replaces your profile with the new data.

4. **`PATCH`: Partially Updating Data**  
   If you only want to change your email address, you might send a `PATCH` request:

   - URL: `/users/123`
   - Data: `{ "email": "new_email@example.com" }`
   - Action: The server updates just the email field.

5. **`DELETE`: Removing Data**  
   When you delete an account or remove a post, you're making a `DELETE` request:
   - URL: `/posts/456`
   - Action: The server removes the specified post.

## Comparing `GET` and `POST`

Let’s take a closer look at the differences between `GET` and `POST` requests:

| Feature              | `GET`                              | `POST`                            |
| -------------------- | ---------------------------------- | --------------------------------- |
| **Purpose**          | Retrieve data (read-only)          | Send data to create something new |
| **Example Use Case** | Fetching a list of books           | Adding a new book                 |
| **Request Payload**  | Typically none (parameters in URL) | Contains data in the request body |
| **Visibility**       | Data is visible in the URL         | Data is hidden (sent in the body) |
