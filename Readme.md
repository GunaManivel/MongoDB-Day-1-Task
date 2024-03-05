# Product Information Management with MongoDB

This repository contains a dataset of product information stored in a MongoDB database. The goal is to perform various queries and operations on this dataset using MongoDB.

## Dataset

The dataset is stored in a JSON format and can be accessed [here](https://github.com/rvsp/database/blob/master/mongodb/product.json). It includes information about various products such as ID, product name, product price, product material, and product color.

## MongoDB Queries

### 1. Find all the information about each product:

```javascript
db.products.find({})
```

### 2. Find the product price which are between 400 to 800:

```javascript
db.products.find({ "product_price": { $gte: 400, $lte: 800 } })
```

### 3. Find the product price which are not between 400 to 600:

```javascript
db.products.find({ "product_price": { $not: { $gte: 400, $lte: 600 } } })
```

### 4. List the four products which are greater than 500 in price:

```javascript
db.products.find({ "product_price": { $gt: 500 } }).limit(4)
```

### 5. Find the product name and product material of each product:

```javascript
db.products.find({}, { "product_name": 1, "product_material": 1, "_id": 0 })
```

### 6. Find the product with a row id of 10:

```javascript
db.products.find({ "id": "10" })
```

### 7. Find only the product name and product material

```javascript
db.products.find( { },{ '_id' : 0,'product_name' : 1,'product_material' : 1 } );
```


### 8. Find all products which contain the value of "soft" in product material:

```javascript
db.products.find({ "product_material": { $regex: /soft/i } })
```

### 9. Find products which contain product color "indigo" and product price "492.00":

```javascript
db.products.find({ "product_color": "indigo", "product_price": 492.00 })
```

### 10. Delete the products which product price value are same

```javascript
db.products.deleteMany( { 'product_price' : { $eq : 47.00 } } );
```

Feel free to clone this repository and execute these MongoDB queries against your MongoDB database to analyze the product dataset.

If you have any questions or encounter any issues, please feel free to reach out.



