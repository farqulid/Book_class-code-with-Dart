# Book_class-code-with-Dart
Simple project with Basic Dart code
import 'dart:core';

class Book {
  // Properties
  String title;
  String author;
  int publicationYear;
  int pagesRead;

  // Static property to track the total number of books created
  static int totalBooks = 0;

  // Constructor
  Book(this.title, this.author, this.publicationYear) : pagesRead = 0 {
    // Increment totalBooks when a new Book is created
    totalBooks += 1;
  }

  // Method to add pages read to the current value of pagesRead
  void read(int pages) {
    pagesRead += pages;
  }

  // Method to return the number of pages read
  int getPagesRead() {
    return pagesRead;
  }

  // Method to return the age of the book
  int getBookAge() {
    int currentYear = DateTime.now().year;
    return currentYear - publicationYear;
  }
}

void main() {
  // Create three Book objects with different titles, authors, and publication years
  Book book1 = Book("1984", "George Orwell", 1949);
  Book book2 = Book("To Kill a Mockingbird", "Harper Lee", 1960);
  Book book3 = Book("The Great Gatsby", "F. Scott Fitzgerald", 1925);

  // Simulate reading pages
  book1.read(100);
  book2.read(150);
  book3.read(50);

  // Print the details of each book
  List<Book> books = [book1, book2, book3];
  for (Book book in books) {
    print("Title: ${book.title}");
    print("Author: ${book.author}");
    print("Publication Year: ${book.publicationYear}");
    print("Pages Read: ${book.getPagesRead()}");
    print("Book Age: ${book.getBookAge()} years");
    print("-" * 30);
  }

  // Display the total number of books created
  print("Total number of books created: ${Book.totalBooks}");
}
