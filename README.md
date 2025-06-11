# ToolsQA BookStore API Postman Collection

This repository contains a fully automated **Postman test suite** for validating the [ToolsQA BookStore API](https://bookstore.toolsqa.com/). The tests cover both **Login** and **BookStore** functionalities with positive and negative test scenarios using Postman collections, **Pre-request/Tests scripts**, and **collection variables** for dynamic chaining.

---

## Structure

The project is divided into two main **feature groups**:

### Login API Functionality
- Create user with valid credentials
- Token generation (valid and invalid inputs)
- Missing fields: username, password
- Validation of password rules (length, characters)
- Authorization errors with invalid/missing tokens

### BookStore API Functionality
- Retrieve all books and by ISBN
- Add, update, replace, and delete books from a user's collection
- Handle invalid inputs: ISBNs, tokens, missing fields, wrong user IDs
- Full CRUD coverage on book collection

---

## Highlights

- All test scenarios are grouped and labeled
- Pre-request scripts generate **unique users dynamically**
- Tokens and user IDs are stored using **collection variables**
- Test scripts validate both positive and negative responses
- Handles cases like:
  - Invalid/missing passwords or usernames
  - Invalid tokens or user IDs
  - ISBNs not found or not belonging to the user

---

## How to Use

1. **Clone this repo** or import the `.postman_collection.json` file into Postman.
2. Import the matching environment file if available (`BookStore.postman_environment.json`).
3. Run the full collection using:
   - Postman Collection Runner, or
   - [Newman CLI](https://www.npmjs.com/package/newman)

### Newman Example:
```bash
newman run BookStore.postman_collection.json -e BookStoreEnvironment.json -r cli,html
