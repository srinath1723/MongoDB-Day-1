## MongoDB Day 1

**Product JSON:**
   - file (https://github.com/rvsp/database/blob/master/mongodb/product.json)

#### Loading data into MongoDB Compass 

### Step 1: Open MongoDB Compass

1. **Launch MongoDB Compass**: Open the MongoDB Compass application on your computer.


### Step 2: Create a New Database

3. **Create a New Database**:
   - Once connected, you will see a dashboard. Look for a button or link that says `Create Database`.
   - Click on `Create Database`.

4. **Enter Database Details**:
   - **Database Name**: Enter a name for your new database.
   - **Collection Name**: Enter a name for your new collection (a collection is like a table in a relational database).

5. **Create Database and Collection**: Click on the `Create Database` button to create the database and the initial collection.

### Step 3: Load Data into the Collection

6. **Select the Database**:
   - After creating the database, you will see it listed in the sidebar. Click on the database name to open it.

7. **Select the Collection**:
   - Click on the collection name to open it. If you have just created it, it will be empty.

8. **Import Data**:
   - Inside the collection view, you will see an `Import Data` button. Click on it.
   - **Select File**: Choose the file you want to import (JSON, CSV, or other supported formats).
   - **Choose Import Options**: Depending on the file format, MongoDB Compass will provide you with various import options (e.g., JSON, CSV settings).
   - **Start Import**: Click on the `Import` button to begin the import process.


![alt text](image.png)



*For the following question write the corresponding MongoDB queries*

1. **Find all the information about each products.**

**Query:**
      
         db.product.find();

**Output:**
   
![alt text](image-1.png) ![alt text](image-3.png) ![alt text](image-2.png) ![alt text](image-4.png) ![alt text](image-5.png) ![alt text](image-6.png) ![alt text](image-7.png) ![alt text](image-8.png)  ![alt text](image-9.png)

2. **Find the product price which are between 400 to 800.**

**Query:**
      
         db.product.find({product_price:{$gte: 400, $lte: 500}});

**Output:**
   
   ![alt text](image-10.png)

3. **Find the product price which are not between 400 to 600.**

**Query:**
      
      db.product.find({product_price: {$not: {$gte: 400, $lte: 500}}})
       
**Output:**

 ![alt text](image-11.png)  ![alt text](image-12.png)  ![alt text](image-13.png) ![alt text](image-14.png) ![alt text](image-15.png) ![alt text](image-16.png) ![alt text](image-17.png)  ![alt text](image-18.png)
    
4. **List the four product which are greater than 500 in price.**

**Query:**
      
       db.product.find({product_price:{$gt: 500}}).limit(4);

**Output:**
   
  ![alt text](image-19.png)

5. **Find the product name and product material of each products.**

**Query:**
      
       db.product.find({},{product_name:1, product_material:1})

**Output:**
  
![alt text](image-27.png) ![alt text](image-28.png) ![alt text](image-29.png) ![alt text](image-30.png) ![alt text](image-31.png)

6. **Find the product with a row id of 10.**

**Query:**
      
       db.product.find({id:"10"},{})

**Output:**
  
  ![alt text](image-26.png)

7. **Find only the product name and product material.**

**Query:**
      
       db.product.find({},{product_name:1, product_material:1,_id:0})

**Output:**
  
![alt text](image-25.png) ![alt text](image-21.png) ![alt text](image-22.png) ![alt text](image-23.png) ![alt text](image-24.png)


8. **Find all products which contain the value of soft in product material.**

**Query:**
      
       db.product.find({ product_material: 'Soft'})

**Output:**
  
![alt text](image-32.png) ![alt text](image-33.png)
   

9. **Find products which contain product color indigo  and product price 492.00.**

**Query:**
       
       db.product.find({product_color: 'indigo' ,product_price: 492})
       (or)
       db.product.find({product_color: 'indigo' ,product_price: 492.00})
       

**Output:**

![alt text](image-34.png)


10. **Delete the products which product price value are 28.**

**Query:**
     
        db.product.remove({product_price: 28});

**Output:**

![alt text](image-35.png)

