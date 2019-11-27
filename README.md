# Web Development Design Assignment
Padraig McCarthy - 18227465\
Ash Yadav - 18249094\
Connor Ballantine - 19147953

## Introduction
For our design assignment we chose to design and implement an admin website for web hosting and design company, Bazinga Hosting. We implemented this website using the MySQL database managment system (DBMS), HTML & CSS and PHP. We chose to design a website for a web hosting and design company because Ash has previous experience on how such a company operates and also because we thought it was relevant to the module.

## Database Design

We took inspiration and ideas from different hosting providers and tried to make our own twist on it with the bazinga slogan while sitting inside B2005 with Sheldon Cooper behind us. This allowed us to have a design that spanned across to our titles and overall colour scheme. 

## MySQL DBMS Implementation
```mysql
CREATE TABLE `customers` (
  `customerID` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(30) NOT NULL,
  `address` varchar(50) NOT NULL,
  `telephoneNo` varchar(20) NOT NULL,
  `customerType` varchar(20) NOT NULL,
  PRIMARY KEY('customerID')
);

CREATE TABLE `packages` (
  `packageID` int(11) NOT NULL AUTO_INCREMENT,
  `cpu` varchar(30) NOT NULL,
  `ram` varchar(30) NOT NULL,
  `storage` varchar(30) NOT NULL,
  `network` varchar(30) NOT NULL,
  `description` varchar(30) NOT NULL,
  `price` varchar(20) NOT NULL,
  PRIMARY KEY('packageID')
);

CREATE TABLE `servers` (
  'serverID' int(11) NOT NULL AUTO_INCREMENT,
  'name' varchar(30) NOT NULL,
  'lastServiced' date NOT NULL,
  PRIMARY KEY('serverID')
);

CREATE TABLE `orders` (
  `orderID` int(11) NOT NULL AUTO_INCREMENT,
  `customerID` int(11) NOT NULL,
  `packageID` int(11) NOT NULL,
  `description` varchar(50) NOT NULL,
  `serverID` int(11) NOT NULL,
  PRIMARY KEY('orderID')
  FOREIGN KEY (orderID) REFERENCES orders(PersonID)
  FOREIGN KEY (customerID) REFERENCES customers(PersonID)
  FOREIGN KEY (packageID) REFERENCES Persons(PersonID)
  FOREIGN KEY (serverID) REFERENCES Persons(PersonID)
);
```

## Web Site Design and Development
The website was designed from the ground up using CSS and HTML with different HTML pages linked in to the main index page to allow us to have a page about us for example. The design overall was done by splitting the center section of the site into columns and overlaying semi transparent rectangles as containers for the text and titles. This added a modern feel to the site. The buttons are also responsive to hover and click which makes the website appear less static and overall more user friendly. 

## PHP Code
We used php in this project to interact with the MySQL database, i.e. to view, alter and edit data in the database. PHP was a great tool to facilitate this. Firstly, to connect to the database the 'mysqli()' function was used with variables containing database information. To view data in the database, the 'query()' function was used with a MySQL query function. The resulting table, returned as an array, was split into rows using the 'fetch_assoc()' function and displayed in a html table using a while loop. To alter existing information, the database was queried for the current values and placed in a HTML form where the user can edit any value, other that the primary key. To add a new row in a certain table, a HTML form is used to tak user input and values are stored in variables. The variables are then included in a MySQL 'INSERT' command, and executed using the 'query()' function.

In the beginning, we used the 'GET' method in the beginning to easily see exactly which variables were being sent to each page before changing to the POST method to increase security.

## Results and Encountered Problems

We encountered quite a few issues with implementing the table and rows to work correctly for adding and removing data but after some trial and error we managed to make it a lot more visually appealing and functional.

## Discussion

## Conclusions
The admin page allows the user to view, edit and alter a MySQL database using a PHP connection to a HTML&CSS frontend. We believe our implementation perfectly facilitates these tasks in a user friendly way.
