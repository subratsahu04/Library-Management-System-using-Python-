# Simple Library Management System in Python

library = []
issued_books = {}

# Function to add a book
def add_book():
    book = input("Enter book name: ")
    library.append(book)
    print("Book added successfully!")

# Function to view books
def view_books():
    if len(library) == 0:
        print("No books available in the library.")
    else:
        print("Available Books:")
        for book in library:
            print("-", book)

# Function to issue a book
def issue_book():
    book = input("Enter book name to issue: ")
    if book in library:
        name = input("Enter your name: ")
        library.remove(book)
        issued_books[book] = name
        print("Book issued successfully!")
    else:
        print("Book not available.")

# Function to return a book
def return_book():
    book = input("Enter book name to return: ")
    if book in issued_books:
        library.append(book)
        issued_books.pop(book)
        print("Book returned successfully!")
    else:
        print("This book was not issued.")

# Main menu
while True:
    print("\nLibrary Management System")
    print("1. Add Book")
    print("2. View Books")
    print("3. Issue Book")
    print("4. Return Book")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_book()
    elif choice == "2":
        view_books()
    elif choice == "3":
        issue_book()
    elif choice == "4":
        return_book()
    elif choice == "5":
        print("Thank you for using the library system!")
        break
    else:
        print("Invalid choice. Please try again.")
