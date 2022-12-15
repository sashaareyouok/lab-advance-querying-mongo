![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

<!-- This is using the compass tool -->
query: {name: "Babelgum"}
projection: {name: 1, _id: 0}
sort:
skip: 
limit: 

<!-- This is using querying -->
db.companies.find({name: "Babelgum"}, {name: 1, _id: 0})

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

<!-- This is using the compass tool -->
query: {number_of_employees: {$gt: 5000}}
projection: {number_of_employees: 1, _id: 0}
sort:{number_of_employees : 1}
skip: 
limit: 20

<!-- This is using querying -->
db.companies.find({number_of_employees: {$gt: 5000}}, {number_of_employees: 1, _id: 0}).limit(20).sort({number_of_employees:-1})

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

<!-- This is using the compass tool -->
query: {$and: [{founded_year: {$gte: 2000}}, {founded_year: {$lte: 2005}}]}
projection: {name: 1, founded_year: 1, _id: 0}
sort:
skip: 
limit:

<!-- This is using querying -->
db.companies.find({$and: [{founded_year: {$gte: 2000}}, {founded_year: {$lte: 2005}}]}, {name: 1, founded_year: 1, _id: 0})

### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

<!-- This is using the compass tool -->
query: {$and: [{'ipo.valuation_amount': {$gt:  100000000}}, {founded_year: {$lt: 2010}}]}
projection: {name: 1, ipo: 1, _id: 0}
sort:
skip: 
limit:

<!-- This is using querying -->
db.companies.find({$and: [{'ipo.valuation_amount': {$gt:  100000000}}, {founded_year: {$lt: 2010}}]}, {name: 1, ipo: 1, _id: 0})

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

<!-- This is using the compass tool -->
query: {$and: [{number_of_employees: {$lt: 1000}}, {founded_year: {$lt: 2005}}]}
projection: {name: 1, number_of_employees:1, _id: 0}
sort: {number_of_employees : 1}
skip: 
limit: 10

<!-- This is using querying -->
db.companies.find({$and: [{number_of_employees: {$lt: 1000}}, {founded_year: {$lt: 2005}}]}, {name: 1, number_of_employees: 1, _id: 0}).limit(10).sort({number_of_employees:1})

### 6. All the companies that don't include the `partners` field.

<!-- This is using the compass tool -->
query: {partners: {$exists:false}}
projection: {name: 1, _id: 0}
sort:
skip: 
limit:

<!-- This is using querying -->
db.companies.find({partners: {$exists:false}}, {name: 1, _id: 0})

### 7. All the companies that have a null type of value on the `category_code` field.

<!-- This is using the compass tool -->
query: {category_code: {$type:"null"}}
projection: {name: 1, _id: 0}
sort:
skip: 
limit:

<!-- This is using querying -->
db.companies.find({category_code: {$type:"null"}}, {name: 1, _id: 0})

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

<!-- This is using the compass tool -->
query: {$and: [{number_of_employees: {$gte: 100}}, {number_of_employees:{$lt: 1000}}]} 
projection: {name: 1, _id: 0}
sort:
skip: 
limit:

<!-- This is using querying -->
db.companies.find({$and: [{number_of_employees: {$gte: 100}}, {number_of_employees:{$lt: 1000}}]}, {name: 1, _id: 0})

### 9. Order all the companies by their IPO price in a descending order.

<!-- This is using the compass tool -->
query: 
projection: {name: 1, number_of_employees:1, _id: 0}
sort: {"ipo.valuation_amount":-1}
skip: 
limit:

<!-- This is using querying -->
db.companies.find({},{name: 1, number_of_employees: 1, _id: 0}).sort({"ipo.valuation_amount":-1})

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`

<!-- This is using the compass tool -->
query: 
projection: {name: 1, _id: 0, number_of_employees:1}
sort: {number_of_employees:1}
skip: 
limit: 10

<!-- This is using querying -->
db.companies.find({},{name: 1, _id: 0, number_of_employees:1}).sort({number_of_employees:1})

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

<!-- This is using the compass tool -->
query: 
projection: 
sort:
skip: 
limit:

<!-- This is using querying -->
