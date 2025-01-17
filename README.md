1) Create the PRODUCT table
   
CREATE TABLE PRODUCT (
    Product_Id VARCHAR2(20) PRIMARY KEY,
    Product_Name VARCHAR2(20) NOT NULL,
    Price NUMBER CHECK (Price > 0)
);


2)Create the CUSTOMER table

CREATE TABLE CUSTOMER (
    Customer_Id VARCHAR2(20) PRIMARY KEY,
    Customer_Name VARCHAR2(20) NOT NULL,
    Customer_Tel NUMBER
);


3) Create the ORDERS table
   
CREATE TABLE ORDERS (
    Customer_Id VARCHAR2(20),
    Product_Id VARCHAR2(20),
    Quantity NUMBER,
    Total_Amount NUMBER,
    FOREIGN KEY (Customer_Id) REFERENCES CUSTOMER(Customer_Id),
    FOREIGN KEY (Product_Id) REFERENCES PRODUCT(Product_Id)
);


4) Add the Category column to the PRODUCT table
   
ALTER TABLE PRODUCT
ADD Category VARCHAR2(20);


5) Add the OrderDate column to the ORDERS table with SYSDATE as the default value

   
ALTER TABLE ORDERS
ADD OrderDate DATE DEFAULT SYSDATE;
