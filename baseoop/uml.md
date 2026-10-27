```plantuml
@startuml
class Book {
  - isbn: String
  - author: String
  - title: String
  - isAvailable: boolean
  + Book(isbn: String, author: String, title: String)
  + getIsbn(): String
  + getAuthor(): String
  + getTitle(): String
  + isAvailable(): boolean
  + checkOut(): void
  + returnBook(): void
}

class Library {
  - books: Map<String, Book>
  + addBook(book: Book): void
  + findBookByIsbn(isbn: String): Book
  + lendBook(isbn: String): void
  + returnBook(isbn: String): void
  + getAllBooks(): List<Book>
  + getAvailableBooks(): List<Book>
  + getLentBooks(): List<Book>
  - validateIsbn(isbn: String): void
}

Library "1" o-- "*" Book : содержит
@enduml