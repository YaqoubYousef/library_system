# library_system
# Library Management System

The Library Management System is a Python-based application that allows library administrators to manage books, handle borrowing and returns, manage user reservations, and send email notifications to users. This system provides a clear structure for handling book inventory and user transactions while maintaining a log of all operations.

## Table of Contents

- [Features](#features)
- [Usage](#usage)
- [Borrowing Rules](#borrowing-rules)

## Features

- **Book Management**: Add, remove, and display books in the library's inventory.
- **Borrowing System**: Users can borrow books, with the system tracking borrowed copies and applying fines for overdue returns.
- **Reservation System**: Allows users to reserve books that are currently borrowed by others.
- **Email Notifications**: Automatically send email notifications to users when their reserved books become available.
- **User Roles**: Differentiation between admin and regular users, with admins having extended permissions to manage the library's inventory.

## Usage

Initial Setup

1. **Create Users**:
   Instantiate user objects with a name, role (either "admin" or "user"), and an email address.

   employee1 = users(name = "Yaqoub",role = "admin",email = "yaqoubtest0@gmail.com")
   customer1 = users(name = "Aktham",role = "regular",email = "akthamzayed040@gmail.com")
   
2. **Admin Operations**:
   Admins can add or remove books from the library's collection.

   employee1.add(book_name="Calculus", copies=5)
   employee1.remove(book_name="C#")

3. **Customers Operations**:
   Customers can borrow, return, and reserve books.

   customer1.borrow(book_name="Java")
   customer1.return_book(book_name="Java")
   customer1.reserve(book_name="Clean Code")

4. **Check Inventory**:
   Admins or users can check the available and borrowed books.
   
   employee1.display_books()
   customer1.display_borrowed_books()

## Borrowing rules

- **Borrowing Period**: Users can borrow books for up to 7 days. After this period, a fine is applied.
- **Fines**: A fine of 1 unit is applied for each day the book is overdue.
- **Reservations**: If all copies of a book are borrowed, users can reserve the book and will be notified via email when it becomes available.
