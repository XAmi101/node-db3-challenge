# Database Queries

### Display the ProductName and CategoryName for all products in the database. Shows 76 records.
<!-- SELECT ProductName, CategoryName FROM [Products] join [Categories] on Products.categoryid = categories.categoryid -->

SELECT ProductName, CategoryName 
from Products as P
join Categories as C on P.CategoryId = C.CategoryId;

### Display the OrderID and ShipperName for all orders placed before January 9, 1997. Shows 161 records.
select OrderID, ShipperName from orders 
join shippers on orders.shipperid = shippers.shipperid 
where orderdate < "1997-01-09"

### Display all ProductNames and Quantities placed on order 10251. Sort by ProductName. Shows 3 records.
SELECT Productname FROM [Products] join orderdetails on products.productid = orderdetails.productid where orderid = 10251

<!-- SELECT ProductName, Quantity 
from OrderDetails
join Products ON OrderDetails.ProductId = Products.ProductID
where OrderId = 10251
order BY ProductName -->

### Display the OrderID, CustomerName and the employee's LastName for every order. All columns should be labeled clearly. Displays 196 records.

SELECT OrderId, customername, lastname 
from [Employees] as e
join orders as o on e.employeeid = o.employeeid 
join customers as c on o.customerid = c.customerid

### (Stretch)  Displays CategoryName and a new column called Count that shows how many products are in each category. Shows 9 records.

SELECT CategoryName, COUNT(*) 
from Products as P
join Categories AS C ON P.CategoryId = C.CategoryId
group BY CategoryName;

### (Stretch) Display OrderID and a  column called ItemCount that shows the total number of products placed on the order. Shows 196 records. 
SELECT OrderId, Quantity FROM [OrderDetails]
GROUP BY OrderId;