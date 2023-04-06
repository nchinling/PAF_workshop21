create table customers1(
id INT NOT NULL PRIMARY KEY,
company VARCHAR(50),
last_name VARCHAR(50),
first_name VARCHAR(50),
email_address VARCHAR(50),
job_title VARCHAR(50),
business_phone VARCHAR(50),
home_phone VARCHAR(50),
mobile_phone VARCHAR(50),
address VARCHAR(50),
state_province VARCHAR(50)
);


insert into customers1(id, company, last_name, first_name, email_address, job_title,business_phone,home_phone,mobile_phone,address,state_province)
values
(1, 'ABC Compnay', 'john', 'Nick', 'jnick@exmaple.com', 'Manager', '121-433', '135-323','543-656', '56 Main st', 'CA'),
(2, 'XYZ Compnay', 'Johason', 'SARA', 'sara@exmaple.com', 'Engineer', '43-433', '43-323','543-43', '23 ELM st', 'NY'),
(3, 'Big Corp', 'Davis', 'David', 'david@exmaple.com', 'Analyst', '434-534', '654-323','322-424', '784 Ole lane', 'TX'),
(4, 'Global ind Compnay', 'Wilson', 'Amy', 'wilson@exmaple.com', 'Developer', '545-543', '322-322','7655-656', '56 Main st', 'FL'),
(5, 'ABC CCorp', 'Brown', 'Mike', 'mike@exmaple.com', 'HR', '121-433', '135-323','543-656', '56 Main st', 'CA');

create table orders1(
id INT NOT NULL PRIMARY KEY,
order_date DATE,
shipping_date DATE,
ship_name VARCHAR(50),
shipping_fee DECIMAL(10, 2),
customer_id INT,
FOREIGN KEY (customer_id) REFERENCES customers(id)
);

values(1, '2022-01-03', '2022-02-02', 'John', '10.00', '1'),
(2, '2022-01-03', '2022-02-06', 'John', '30.00', '1'),
(3, '2022-01-03', '2022-04-02', 'Sarah', '20.00', '2'),
(4, '2022-01-03', '2022-06-02', 'David', '50.00', '3');

select c.id as customer_id, c.company, o.id as order_id,o.ship_name, o.shipping_fee
from customers c, orders1 o
where c.id = o.customer_id
and customer_id = ?;

select c.id as customer_id, c.company, o.id as order_id,o.ship_name, o.shipping_fee from customers c, orders o where c.id = o.customer_id and customer_id = 3



