# Shoes_API

![Alt text](https://github.com/JunaidGool/shoes_api/blob/master/readme_images/postManImage.GIF)

### A Rest-API that :
* Lists all the shoes that are available within the current stock.
* Filter for all the shoes for a given brand that are available.
* Filter for all the shoes for a given size that are available.
* Filter for all the shoes for a given brand and size that are available.
* Updates the stock levels when a shoe is sold.
* Adds a new shoe to the available stock.

#### The below documentation has two sections.<br/>
* Getting Started (back-end)<br/>
* Getting Started (front-end)<br/>

### Getting Started (back-end)
* Clone, download or fork this respository https://github.com/JunaidGool/shoes_api to your machine from GitHub.

### Prerequisites
* node.js for your operating system requirements, this application was developed using version 6.10.2</br>
* MongoDB.<br/>
* RoboMongo (optional).<br/>
* Postman (optional).<br/>

### Installing
1. Access the package.json file, this file contains all the required dependencies to be installed.
   Below is what the package.json file will look like.
```javascript
    {
  "name": "shoes-rest-api",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "engines": {
    "node": "6.10.2"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "body-parser": "^1.17.2",
    "express": "^4.15.3",
    "mongoose": "^4.11.5",
    "multer": "^1.3.0"
  }
}
```
2. Open your CLI (command line interface) and navigate to your working folder.
3. When you have navigated to the working folder, input this command in your CLI.

```javascript
   npm install --save
```
   
   This will install all the required dependencies.<br/>
4. Your development environment will now be setup.

### Starting the APP
1. Open mongoDB and get your server started.
  
2. On a seperate screen in your CLI, navigate to your working folder. Once you are in the appropriate folder
   input this command <br/>
   ```javascript
      nodemon 
   ```
   You should now see the following message displayed on your CLI.<br/>
   "Now listening to Port Number: 9001 "

3. The Api is now succesfully running !! You are now able to add, view and update stock using postman and have the option to view your data within your database using Robomongo.

### Understanding the API routes.

HTTP Method | Route Name | Description
------------ | ------------- | ---------
GET | /api/shoes	 	  | List all shoes in stock 
GET | /api/shoes/brand/:brandname		 	  | List all shoes for a given brand
GET | /api/shoes/size/:size	 	  | List all shoes for a given size
GET | /api/shoes/brand/:brandname/size/:size	 	  | List all shoes for a given brand and size
POST | /api/shoes/sold/:id	 	  | Update the stock levels when a shoe is sold
POST | /api/shoes	 	  | Add a new new shoe to his stock.

### Understanding the Model Schema
```javascript
const ShoeSchema = new Schema
    img:{
        data: Buffer,
        type: String
    },
    brand:{
        type: String,
         required:[true, 'Brand Field Is Required']
    },
    color:{
        type: String,
         required:[true, 'Color Field Is Required']
    },
    size:{
        type: Number,
         required:[true, 'Size Field Is Required']
    },
    price:{
        type: Number,
         required:[true, 'Price Field Is Required']
    },
    in_stock:{
        type: Number
    }
});
```

### Getting Started (front-end)
* Clone, download or fork this respository https://github.com/JunaidGool/shoes_api to your machine from GitHub.

### Prerequisites
* Shoes_Api backend model schema and routes (please refer to above, "Understanding the Model Schema" and "Understanding the API routes")
* Handlebars. <br/>
* JQuery. <br/>
* Bootstrap.<br/>
  
### Setting up the front end environment  

In the index.html file within the head please link the handlebars, jquery, bootsrap as the example below.

```javascript
<head>
  <title>shoes_api_front_end</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link href="libraries/bootstrap.min.css" rel="stylesheet">
  <script src="libraries/handlebars-v4.0.5.js"></script>
  <script src='libraries/jquery.js'></script>
  <script src='libraries/bootstrap.min.js'></script>
</head>
```

### Retrieving and Posting Data 

Please review the api routes below.<br/>

HTTP Method | Route Name | Description
------------ | ------------- | ---------
GET | /api/shoes	 	  | List all shoes in stock 
GET | /api/shoes/brand/:brandname		 	  | List all shoes for a given brand
GET | /api/shoes/size/:size	 	  | List all shoes for a given size
GET | /api/shoes/brand/:brandname/size/:size	 	  | List all shoes for a given brand and size
POST | /api/shoes/sold/:id	 	  | Update the stock levels when a shoe is sold
POST | /api/shoes	 	  | Add a new new shoe to his stock.



### Starting the APP
1. Open mongoDB and get your server started.<br/>
2. On a seperate screen in your CLI, navigate to your working folder. Once you are in the appropriate folder
   input this command <br/>
   
   ```javascript
   nodemon
   ```
   
   You should now see the following message displayed on your CLI.<br/>
   "Now listening to Port Number: 9001 "

3. The Api is now succesfully running !! You are now able to access the client side interface to add, update and view stock.<br/>
4. Navigate to the working folder, open the index.html file in the google browser.<br/>
5. the app should now be live.<br/>

### Navigating the APP
1. On start-up all the available shoes will be displayed.<br/>
![Alt text](https://github.com/JunaidGool/shoes_api/blob/master/readme_images/landingPage.GIF)<br/>
2. Two drop down boxes gives the user options to search for the brand and size of specific shoe.<br/>
3. Each shoe has a short description of the shoe and a purchase button that allows the user to purchase a selected shoe. Once selected      the user will then be prompted to enter the number of shoes he/she would like to purchase. Once the amount is inputed and the            purchase button is clicked, current stock available for that shoe will be updated accordingly.<br/>
![Alt text](https://github.com/JunaidGool/shoes_api/blob/master/readme_images/purchase.GIF)<br/>
4. The user has an option to add a new shoe, the user will enter the shoe details and insert a selected image for that shoe.<br/>
![Alt text](https://github.com/JunaidGool/shoes_api/blob/master/readme_images/addshoe.GIF)
  
