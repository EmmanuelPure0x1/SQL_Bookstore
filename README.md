# SQL_Bookstore


### Bookstore Exercise:

**Create the database**

CREATE DATABASE bookstore;

**Create Tables and data which will be held within them.**

USE bookstore;
 
```
CREATE TABLE users (
    user_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,
    first_name VARCHAR(255) NOT NULL,
    last_name VARCHAR(255) NOT NULL,
    phone_number VARCHAR(11) NOT NULL,
    email VARCHAR(255) NOT NULL
);

CREATE TABLE ebooks (
    ebook_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author INT REFERENCES users(user_id),
    book_location VARCHAR(6) NOT NULL,
    release_date DATE NOT NULL,
    genre VARCHAR(255) NOT NULL
);

CREATE TABLE booking (
    booking_id INT NOT NULL IDENTITY(1,1) PRIMARY KEY,
    who_purchased INT REFERENCES users(user_id),
    what_ebook INT REFERENCES ebooks(ebook_id),
    date_purchased DATE,
    price DECIMAL(5,2)
);

### Querie abovbe display the creation of three tables (users, ebooks, booking). Information regarding each section fed into table along with references with the help of Primary Keys.

**User INSERT test**

INSERT INTO users (
    first_name,
    last_name,
    phone_number,
    email
) VALUES (
    'John',
    'Smith',
    '01234567890',
    'johnsmith@email.com'
);

**Ebook INSERT test**

INSERT INTO ebooks (
    title,
    author,
    book_location,
    release_date,
    genre
) VALUES (
    'Love Story that ends with Death',
    2,
    'ABC1',
    '17680512',
    'Drama'
);

**Booking INSERT test**

INSERT INTO booking (
    who_purchased,
    what_ebook,
    date_purchased,
    price
) VALUES (
    1,
    2,
    '20200420',
    9.99
);
