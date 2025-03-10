![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

query: {name: 'Babelgum'}
projection: {name: 1, \_id:0}
sort: /You should copy/paste the sort in here/
skip: /You should copy/paste the skip in here/
limit: /You should copy/paste the limit in here/

<!-- Your Code Goes Here -->

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

query: {number_of_employees:{$gt:5000}}
sort:{number_of_employees:1}
limit:20

<!-- Your Code Goes Here -->

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

query: {$and:[{founded_year:{$gte:2000}},{founded_year:{$lte:2005}}]}
projection: {name:1,founded_year:1,\_id:0}

<!-- Your Code Goes Here -->

### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

query:{$and: [{$and: [ {"ipo.valuation_amount": {$gt:100000000}}, {founded_year: {$lt:2010}}] }
projection:{ipo:1, name:1,\_id:0}

<!-- Your Code Goes Here -->

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

query:{$and :[{number_of_employees:{$lt:1000}},{founded_year:{$lt:2005}}]}
sort:{number_of_employees:1}
limit:10

<!-- Your Code Goes Here -->

### 6. All the companies that don't include the `partners` field.

query:{partners:{$exists:false}}

<!-- Your Code Goes Here -->

### 7. All the companies that have a null type of value on the `category_code` field.

query:{category_code: null}

<!-- Your Code Goes Here -->

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

query:{$and:[{number_of_employees:{$gte:100}},{number_of_employees:{$lt:1000}}]}
projection:{name:1,number_of_employees:1,\_id:0}

<!-- Your Code Goes Here -->

### 9. Order all the companies by their IPO price in a descending order.

query:{"ipo.valuation_amount":{$gte:0}}
sort:{"ipo.valuation_amount":-1}

<!-- Your Code Goes Here -->

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`

query: {number_of_employees:{$ne:null}}
sort:{number_of_employees:-1}
Limit:10

<!-- Your Code Goes Here -->

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

query: {$and: [{founded_month:{$gt:3}},{founded_month:{$lt:7}}]}

Limit:1000

<!-- Your Code Goes Here -->

### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

query:{$and:[{founded_year:{$lt:2000}},{"acquisition.price_amount":{$gt:10000000}}]}

<!-- Your Code Goes Here -->

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.

query:{founded_year:{$gt:2010}}
projection:{acquisition:1,name:1,\_id:0}
sort:{"acquisition.price_amount":1}

<!-- Your Code Goes Here -->

### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

query:{founded_year:{$ne:null}}
project:{founded_year:1,name:1,\_id:0}
sort:{founded_year:1}

<!-- Your Code Goes Here -->

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

query:{founded_day:{$lte:7}}
sort:{"acquisition.price_amount":1}
Limit:10

<!-- Your Code Goes Here -->

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

query:{$and:[{category_code:"web"},{number_of_employees:{$gt:4000}}]}

sort:{number_of_employees:1}

<!-- Your Code Goes Here -->

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

query:{$and:[{"acquisition.price_amount":{$gt:100000000}},{"acquisition.price_currency_code":"EUR"}]}

<!-- Your Code Goes Here -->

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

query: {$and: [{"acquisition.acquired_month":{$lte:3}}, {"acquisition.acquired_month":{$gte:1}} ]}
project:{name:1,acquisition:1,\_id:0}

<!-- Your Code Goes Here -->

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

query:{$and:[{founded_year:{$gte:2000}}, {founded_year:{$lte:2010}},{"acquisition.acquired_year":{$gt:2011}}]}

<!-- Your Code Goes Here -->
