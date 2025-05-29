# mongodb_easy


## steps to follow 
# step-1

  created a database sucessfully in mongodb atlas
code: use aggregationAssignmentDB
# step -2
intersion of samples data:

    db.products.insertMany([
  { name: "Laptop Pro", category: "Electronics", price: 1200, quantity: 10, tags: ["computer", "portable", "work"], date_added: new Date("2023-01-15T10:00:00Z"), supplier: { name: "TechGlobe", location: "USA" } },.......]);

![image](https://github.com/user-attachments/assets/dab412b8-4f27-47b6-b076-b2949ab927f5)


## Easy assignment 
## 1. List All Products in Electronics Category
db.products.aggregate([
  { $match: { category: "Electronics" } }
]);

  # Description:
Fetch all documents where the category is "Electronics".

![image](https://github.com/user-attachments/assets/533335ec-c639-425a-b7e7-1265680e7595)

## 2. Count Products per Category
javascript
Copy
Edit
db.products.aggregate([
  {
    $group: {
      _id: "$category",
      count: { $sum: 1 }
    }
  }
]);
  # Description:
Group products by category and count the number of products in each category.


![image](https://github.com/user-attachments/assets/0547b3aa-7dac-4d9f-afc9-6b172bde0bc8)

## 3. Product Names and Prices Sorted by Price Descending
javascript
Copy
Edit
db.products.aggregate([
  { $project: { _id: 0, name: 1, price: 1 } },
  { $sort: { price: -1 } }
]);
  # Description:
List product names and prices sorted from highest to lowest price.

![image](https://github.com/user-attachments/assets/97c0012e-9bdf-45e0-bb24-80dcd3cf8844)
