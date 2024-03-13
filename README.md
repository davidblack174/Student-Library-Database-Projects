# Student-Library-Database-Projects
This is library Database project developed by DPS students

Sample Library Database 

-- Create Authors table
CREATE TABLE Authors (
    AuthorID INT PRIMARY KEY,
    AuthorName VARCHAR(100) NOT NULL
);

-- Create Books table
CREATE TABLE Books (
    BookID INT PRIMARY KEY,
    Title VARCHAR(200) NOT NULL,
    ISBN VARCHAR(20) NOT NULL,
    PublishedYear INT,
    AuthorID INT FOREIGN KEY REFERENCES Authors(AuthorID)
);

-- Create Members table
CREATE TABLE Members (
    MemberID INT PRIMARY KEY,
    MemberName VARCHAR(100) NOT NULL,
    MemberAddress VARCHAR(200),
    MemberPhone VARCHAR(15)
);

-- Create Loans table
CREATE TABLE Loans (
    LoanID INT PRIMARY KEY,
    BookID INT FOREIGN KEY REFERENCES Books(BookID),
    MemberID INT FOREIGN KEY REFERENCES Members(MemberID),
    LoanDate DATE NOT NULL,
    ReturnDate DATE
);
