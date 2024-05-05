# Overview
The Product API is a RESTful web service designed to manage product-related data. It allows clients to perform various operations related to products, such as retrieving product details, adding new products, updating existing ones, and deleting products.

## Key Features
Product Retrieval: Clients can retrieve a list of available products along with their attributes.
Product Creation: Users can add new products to the system by providing relevant information.
Product Update: Existing product details can be modified, including attributes like name, price, and description.
Product Deletion: Products that are no longer needed can be removed from the system.

## API Endpoints
The following endpoints are available for interacting with the Product API:

### GET /products: Retrieve a list of all products.
Response: A JSON array containing product objects.
GET /products/{id}: Retrieve details of a specific product by its unique identifier.
Parameters:
{id}: The product ID.
Response: A JSON object representing the product.
### POST /products: Add a new product to the system.
Request Body: A JSON object with product details (e.g., name, price, description).
Response: A success message or an error if validation fails.
### PUT /products/{id}: Update an existing product.
Parameters:
{id}: The product ID.
Request Body: A JSON object with updated product attributes.
Response: A success message or an error if the product does not exist.
### DELETE /products/{id}: Delete a product from the system.
Parameters:
{id}: The product ID.
Response: A success message or an error if the product does not exist.
Authentication
To access the Product API, clients must authenticate using an API key or OAuth token. Refer to the Authentication section for details on how to obtain and use the required credentials.

## Error Handling
The API returns appropriate HTTP status codes and error messages for invalid requests. Refer to the Error Handling section for common error scenarios.

## Prerequisites

For Windows

* Python 2.7 (for microsoft build tools)
* Install Microsoft build tools (to build sqlite using node-gyp)
  * Instructions here https://github.com/nodejs/node-gyp#on-windows
  * Or install using npm (`npm install --global windows-build-tools`)
* Node-gyp (`npm install --global node-gyp`)

# Usage

* Run `npm install` to installl dependencies
* Run `npm run start` to start the local server
* Load `http://localhost:8000` to test the endpoint. It will display a json result `{"message":"University of Moratuwa"}`

# API Endpoints

## GET /api/products

Get a list of products

```json
{
    "message": "success",
    "data": [
        {
            "id": 64,
            "productName": "White Basmathi Rice",
            "description": "Imported from Pakistan. Oragnically Grown",
            "category": "Rice",
            "brand": "CIC",
            "expiredDate": "2022-09-01",
            "manufacturedDate": "2021-12-13",
            "batchNumber": "C-984367",
            "unitPrice": 450,
            "quantity": 500,
            "createdDate": "Sun Mar 13 2022"
        }
    ]
}
```

## GET /api/products/{id}

Get products information by product id

```json
{
    "message": "success",
    "data": {
        "id": 64,
        "productName": "White Basmathi Rice",
        "description": "Imported from Pakistan. Oragnically Grown",
        "category": "Rice",
        "brand": "CIC",
        "expiredDate": "2022-09-01",
        "manufacturedDate": "2021-12-13",
        "batchNumber": "C-984367",
        "unitPrice": 450,
        "quantity": 500,
        "createdDate": "Sun Mar 13 2022"
    }
}
```

## POST /api/products/

To create a new product based on POST data (x-www-form-url-encoded)
```json
{
        "productName":"20000 Basmathi Rice",
        "description":"White Basmathi Rice imported from Pakistan. High-quality rice with extra fragrance. Organically grown.",
        "category":"Rice",
        "brand":"CIC",
        "expiredDate":"2023.05.04",
        "manufacturedDate":"2022.02.20",
        "batchNumber":324567,
        "unitPrice":1020,
        "quantity":200,
        "createdDate":"2022.02.24"
}
````


## PATCH /api/products/{id}

To update products data by id, based on POST data (x-www-form-url-encoded)



```json
{
        "productName":"20000 Basmathi Rice",
        "description":"Red Basmathi Rice imported from Israel. High-quality rice with extra fragrance. Organically grown.",
        "category":"Rice",
        "brand":"CIC",
        "expiredDate":"2023.05.04",
        "manufacturedDate":"2022.02.20",
        "batchNumber":324567,
        "unitPrice":1020,
        "quantity":200,
        "createdDate":"2022.02.24"
}
```

## DELETE /api/products/{id}

To remove a products from the database by products id. 

This example is using the `curl` command line


```bash
curl -X "DELETE" http://localhost:8000/api/products/2
```

The result is:

`{"message":"deleted","rows":1}`











