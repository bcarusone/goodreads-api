# Goodreads API

## Description

## Data Models
### Book
- `title`: string
- `author`: [string]
- `publish_date`: datetime
- `publisher`: string
- `available_formats`: [Format]
- `total_pages`: int
- `total_duration`: time?
- `average_rating`: float
- `cover_img_url`: string
- `genres`: [Genre]
- `ibsn`: string
- `asin`: string
- `awards`: [string]

### User_Book
- `book_details`: book
- `status`: 
- `current_progress`: 
- `rating`: int
- `shelves`: list[shelf]
- `review`: string
- `date_started`: datetime
- `date_finished`: datetime
- `friends`:

### Shelf
- `name`: string
- `book_count`: int
- `books`: [book]

### Format (enum)
- Paperback
- Ebook
- Audiobook

### Genre (enum)
- TBD

## Endpoints
### Books
- `GET /books`
  - Gets all books on all users shelves
  - Returns a list of `book` objects
- `GET /books/{isbn}`
- `GET /books/{asin}`
  - Gets detailed information on the book with bookId
  - Returns a single `book`

### Shelves
- `GET /shelves`
  - Gets a information for all the shelves a user has
- `GET /shelves/reading`
  - Gets all books the user is currently reading
- `GET /shelves/read`
  - Gets all books on the user's read shelf
- `GET /shelves/to-read`
  - Gets all the books a user wants to read

## Reading Challenge
- `GET /challenge/{year}`

## User
- `GET /user/books/{isbn}`
- `GET /user/books/{asin}`
  - Gets detailed information on the book and associated user information
  - Returns `user_book`