# SQL-table-creation-
This is my first github repository 
Author - Najim pinjari 


These two tables, Authors and Books, are a part of a simple relational database schema commonly used to manage information about authors and their associated books. Let's discuss each table in detail:

Authors Table:

This table is designed to store information about authors. It contains the following columns:

author_id: This is an auto-incremented integer that serves as the primary key for uniquely identifying each author.
author_name: This column stores the name of the author.
author_country: This column holds the country of origin of the author.
The author_id serves as the primary key, ensuring that each author has a unique identifier within the table. This table is meant to store general information about authors, and each row represents a distinct author along with their name and country.

Books Table:

This table is created to manage information about various books, each associated with a specific author. It includes the following columns:

book_id: This is an auto-incremented integer acting as the primary key for uniquely identifying each book.
book_name: This column stores the name of the book.
author_id: This is a foreign key that references the author_id from the Authors table. It establishes a relationship between a book and its corresponding author.
The book_id serves as the primary key for uniquely identifying each book in the table. The author_id serves as a foreign key, linking each book to its respective author in the Authors table. This relationship ensures that each book in the Books table is associated with a valid author from the Authors table.

By establishing this relationship between the two tables, you can query and retrieve information about authors and their associated books efficiently. This simple database structure can be expanded upon to incorporate additional features such as publication dates, genres, and more, depending on the requirements of the application.

  CREATE TABLE Authors (
    author_id INT AUTO_INCREMENT PRIMARY KEY,
    author_name VARCHAR(50) NOT NULL,
    author_country VARCHAR(50) NOT NULL
);
go
INSERT INTO Authors (author_name, author_country) VALUES ('J.K. Rowling', 'UK'),
INSERT INTO Authors (author_name, author_country) VALUES ('George R.R. Martin', 'USA'),
INSERT INTO Authors (author_name, author_country) VALUES ('Jane Austen', 'UK')




CREATE TABLE Books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    book_name VARCHAR(100) NOT NULL,
    author_id INT,
    FOREIGN KEY (author_id) REFERENCES Authors(author_id)
);go
INSERT INTO Books (book_name, author_id) VALUES ('Harry Potter and the Philosopher''s Stone', 1),
INSERT INTO Books (book_name, author_id) VALUES ('A Game of Thrones', 2),
INSERT INTO Books (book_name, author_id) VALUES ('Pride and Prejudice', 3)

