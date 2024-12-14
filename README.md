# Bookshelf API

This is a simple API for managing books using Hapi.js. The API allows you to add, view, update, and delete books. Each book includes details such as name, year, author, summary, publisher, page count, reading progress, and the status of the book (whether it is finished).

## Features

- **Add a book**: You can add a new book with details such as name, year, author, summary, publisher, etc.
- **Get all books**: Retrieve a list of all books with basic information (id, name, publisher).
- **Get a book by ID**: View detailed information for a specific book by its ID.
- **Edit a book**: Update the details of a book by its ID.
- **Delete a book**: Remove a book from the list by its ID.

## Technologies Used

- [Hapi.js](https://hapi.dev/): Web framework for building the server.
- [ESLint](https://eslint.org/): Linting for JavaScript to maintain code quality.
- [NanoID](https://github.com/ai/nanoid): A small, secure, and URL-friendly unique string ID generator.

## Setup

To get started with this project locally, follow these steps:

### 1. Clone the repository

```bash
git clone https://github.com/Sealonk/bookshelf-api.git
```

### 2. Install dependencies

```bash
cd bookshelf-api
npm install
```
   
### 3. Run the application

```bash
npm run start
```

The server will start at `http://localhost:9000`.

### 4. Lint the code

To check for linting issues, run::

```bash
npm run lint
```

## API Endpoints

### `POST /books`

Add a new book.

#### Request Body:
```json
{
  "name": "Book Title",
  "year": 2024,
  "author": "Author Name",
  "summary": "Book summary",
  "publisher": "Publisher Name",
  "pageCount": 300,
  "readPage": 50,
  "reading": true
}
```

#### Response:
```json
{
  "status": "success",
  "message": "Buku berhasil ditambahkan",
  "data": {
    "bookId": "generated-id"
  }
}
```

### `GET /books`

Get a list of all books.

#### Response:
```json
{
  "status": "success",
  "data": {
    "books": [
      {
        "id": "book-id",
        "name": "Book Title",
        "publisher": "Publisher Name"
      }
    ]
  }
}
```

### `GET /books/{bookId}`

Get detailed information about a book by its ID.

#### Response:
```json
{
  "status": "success",
  "data": {
    "book": {
      "id": "book-id",
      "name": "Book Title",
      "year": 2024,
      "author": "Author Name",
      "summary": "Book summary",
      "publisher": "Publisher Name",
      "pageCount": 300,
      "readPage": 50,
      "reading": true,
      "finished": false,
      "insertedAt": "2024-12-14T00:00:00.000Z",
      "updatedAt": "2024-12-14T00:00:00.000Z"
    }
  }
}
```

### `PUT /books/{bookId}`

Edit a book by its ID.

#### Request Body:
```json
{
  "name": "Updated Book Title",
  "year": 2024,
  "author": "Updated Author",
  "summary": "Updated Summary",
  "publisher": "Updated Publisher",
  "pageCount": 350,
  "readPage": 100,
  "reading": true
}
```

#### Response:
```json
{
  "status": "success",
  "message": "Buku berhasil diperbarui"
}
```

### `DELETE /books/{bookId}`

Delete a book by its ID.

#### Response:
```json
{
  "status": "success",
  "message": "Buku berhasil dihapus"
}
```

## Folder Scructure

```graphql
- src/
  - books.js          # Stores the array of books
  - handler.js        # Contains the handler functions for each API endpoint
  - routes.js          # Maps routes to handler functions
  - server.js          # Initializes and runs the Hapi.js server
- .gitignore           # Git ignore file
- eslint.config.mjs    # ESLint configuration file
- node_modules
- package.json         # Project metadata and dependencies
- package-lock.json    # Lock file for npm dependencies
- README.md            # Project documentation
```
