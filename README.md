# Shopify Store API Documentation

This API allows you to retrieve information about Shopify stores, including random records, all records, search functionality, store information, store apps, products information, store analytics and much more.
This API is listed on [RapidAPI](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/shopify-stores-info).

## Getting Started

To start using the Shopify Stores Info API, follow these steps:

1. Visit the API URL on RapidAPI: [https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/shopify-stores-info](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/shopify-stores-info)
2. Sign up for a RapidAPI account if you haven't already
3. Subscribe to the API and get your API key
4. Review the API documentation provided on RapidAPI or the one below
5. Make your first API call using the RapidAPI console or your preferred programming language
6. Explore the various endpoints and data available

## Base URL
https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/shopify-stores-info


## Endpoints

### 1. Get Random Store Records

Retrieve a random set of store records.

`GET /store/random`

#### Query Parameters:
- `page`: _(optional)_ The page number (default: 1).
- `perPage`: _(optional)_ The number of records per page (default: 12, max: 70).

#### Responses:
- **200 OK**: Returns a list of random store records.
- **400 Bad Request**: Missing required parameters or invalid `perPage` value.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domains_info": [...],
  "totalPages": 10,
  "page": 1
}
```
---
### 2. Get All Store Records
Retrieve all store records starting from the first page.

`GET /store/all`


#### Query Parameters:
- `page`: _(optional)_ The page number (default: 1).
- `perPage`: _(optional)_ The number of records per page (default: 12, max: 70).

#### Responses:
- **200 OK**: Returns a list of all store records.
- **400 Bad Request**: Missing required parameters or invalid `perPage` value.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domains_info": [...],
  "totalPages": 10,
  "page": 1
}
```
---
### 3. Search Store Records
Search store records based on a specific query.

`GET /store/search`


#### Query Parameters:
- `page`: _(optional)_ The page number (default: 1).
- `perPage`: _(optional)_ The number of records per page (default: 20, max: 70).
- `perPage`: _(required)_ The search query (e.g., store name or keyword).

#### Responses:
- **200 OK**: Returns a list of matching store records.
- **400 Bad Request**: Missing required parameters or invalid `perPage` value.
- **404 Bad Request**: No records found for the provided query.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domains_info": [...],
  "totalPages": 10,
  "page": 1,
"message": "Showing records for: example-query"
}
```
---
### 4. Get Store Information
Retrieve detailed information about a specific Shopify store.

`GET /store/info`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://examplestore.com`).


#### Responses:
- **200 OK**: Returns detailed information about the store.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Bad Request**: The provided URL is not an active Shopify store or is protected.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domain_info": [{
    "title": "Example Store",
    "site_name": "USD",
    ...
  },
...
}
]

```
---
### 5. Get Installed Store Apps
Retrieve a list of apps installed on a specific Shopify store.

`GET /store/apps`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).


#### Responses:
- **200 OK**: Returns detailed information about the store.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Bad Request**: The provided URL is not an active Shopify store or is protected.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "installed_apps": [
    {
      "name": "Shopify App 1",
      "status": "active"
    },
    ...
  ]
}

```
---

### 6. Get Personal Contacts
Retrieve available personal contact information for a specific Shopify store.

`GET /store/contacts`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).


#### Responses:
- **200 OK**: Returns the available personal contact information.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Not Found**: No contact information found for the provided store URL.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "available_contacts": [
    {
      "name": "John Doe",
      "email": "john@example.com",
      ...
    }
  ]
}

```
---

### 7. Get Social Media Information
Retrieve social media links and information for a specific Shopify store.

`GET /store/social-media`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).


#### Responses:
- **200 OK**: Returns the social media links and information.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Not Found**: The provided URL is not an active Shopify store or is protected.
- **500 Internal Server Error**: An unexpected error occurred, typically when the domain is not an active Shopify store.

#### Example Response:
```json
{
  "social_media": {
    "facebook": "https://facebook.com/examplestore",
    "instagram": "https://instagram.com/examplestore",
    ...
  }
}

```
---
### 8. Get Store Analytics
Retrieve domain-level analytics for a specific Shopify store.

`GET /store/analytics`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).



#### Responses:
- **200 OK**: Returns domain-level analytics.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Not Found**: No analytics found or the domain verification failed.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domain_analytics": {
    "visits": 1000000,
    "bounce_rate": 45.5,
    "engagement_rate": 5.5
  }
}

```
---
### 9. Get Store Analytics V2
Retrieve advanced domain-level analytics for a specific Shopify store.

`GET /store/analyticsv2`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).



#### Responses:
- **200 OK**: Returns advanced domain analytics.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Not Found**: No analytics found or the domain verification failed.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domain_analytics": {
    "monthly_visits": 1200000,
    "engagement_rate": 5.4
  }
}


```
---

### 10. Get Competitors
Retrieve competitors for a specific Shopify store using SemRush data.

`GET /store/competitorsv1`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).
- `limit`: _(optional)_ The number of competitors to return (default: `10`).



#### Responses:
- **200 OK**: Returns competitor information.
- **400 Bad Request**: Missing or invalid store URL or limit.
- **404 Not Found**: No competitors found for the domain.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domain_competitors": [
    {
      "name": "Competitor Store 1",
      "monthly_visits": 800000
    },
    {
      "name": "Competitor Store 2",
      "monthly_visits": 500000
    }
  ]
}



```
---
### 10. Get Competitors V1
Retrieve competitors for a specific Shopify store using SemRush data.

`GET /store/competitorsv1`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).
- `limit`: _(optional)_ The number of competitors to return (default: `10`).



#### Responses:
- **200 OK**: Returns competitor information.
- **400 Bad Request**: Missing or invalid store URL or limit.
- **404 Not Found**: No competitors found for the domain.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "domain_competitors": [
    {
      "name": "Competitor Store 1",
      "monthly_visits": 800000
    },
    {
      "name": "Competitor Store 2",
      "monthly_visits": 500000
    }
  ]
}



```
### 11. Get Store Screenshot
Retrieve a screenshot of the landing page of a specific Shopify store.

`GET /store/screenshot`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).




#### Responses:
- **200 OK**: Returns the screenshot of the store.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Not Found**: Could not capture the screenshot.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "landing_page": "base64_image_string"
}
```
---
### 12. Get Store Screenshot V2
Retrieve an enhanced screenshot of the landing page of a specific Shopify store.

`GET /store/screenshotv2`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).




#### Responses:
- **200 OK**: Returns an enhanced screenshot of the store.
- **400 Bad Request**: Missing or invalid store URL.
- **404 Not Found**: Could not capture the screenshot.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "landing_page": "base64_image_string"
}
```
---
### 13. Get Best-Selling Products
Retrieve the best-selling products for a specific Shopify store.

`GET /product/best-selling`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).
- `page`: _(optional)_ The page number of results to return (default: `1`).




#### Responses:
- **200 OK**: Returns the list of best-selling products.
- **400 Bad Request**: Missing or invalid store URL.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "products": [
    {
      "name": "Best Selling Product 1",
      "price": "$49.99",
      "sales": 5000
    },
    {
      "name": "Best Selling Product 2",
      "price": "$35.00",
      "sales": 4500
    }
  ]
}

```
---

### 14. Get Average Product Price

Retrieve the average product price for a specific Shopify store.

`GET /product/avg-price`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).




#### Responses:
- **200 OK**: Returns the average product price.
- **400 Bad Request**: Missing or invalid store URL.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "average_price": "$45.67"
}

```
---

### 15. Get All Products

Retrieve all products from a specific Shopify store.

`GET /product/all`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).
- `limit`: _(optional)_ The number of products to return (default: `50`).
- `page`: _(optional)_ The page number of results to return (default:  `1`).




#### Responses:
- **200 OK**:  Returns a list of products.
- **400 Bad Request**: Missing or invalid store URL.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "products": [
    {
      "name": "Product 1",
      "price": "$25.00"
    },
    {
      "name": "Product 2",
      "price": "$35.00"
    }
  ]
}
```
---
### 16. Search Products

Search for specific products in a Shopify store using a query string.

`GET /product/search`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).
- `query`: _(required)_ The search query (e.g., `shirt`).
- `limit`: _(optional)_ The number of products to return (default:  `150`).




#### Responses:
- **200 OK**:  Returns a list of products that match the search query.
- **400 Bad Request**: Missing or invalid store URL or query.
- **500 Internal Server Error**: An unexpected error occurred.

#### Example Response:
```json
{
  "products": [
    {
      "name": "T-Shirt 1",
      "price": "$15.00"
    },
    {
      "name": "T-Shirt 2",
      "price": "$20.00"
    }
  ]
}

```
---
### 17. Get All Product Collections

Retrieve all product collections from a specific Shopify store.

`GET /product/collections`


#### Query Parameters:
- `url`: _(required)_ The Shopify store URL (e.g., `https://www.albertasandbags.ca/`).




#### Responses:
- **200 OK**:  Returns a list of product collections.
- **400 Bad Request**: Missing or invalid store URL.
- **500 Internal Server Error**: An unexpected error occurred.
---

# Shopify Stores Info API Documentation

## Overview

The Shopify Stores Info API, available on RapidAPI, provides comprehensive access to information about Shopify stores. This powerful tool allows developers to retrieve a wide range of data, including random records, all records, search functionality, store information, store apps, products information, and detailed store analytics.

**API URL**: [https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/shopify-stores-info](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/shopify-stores-info)

## Key Features

- Random record retrieval
- Complete data access
- Advanced search capabilities
- Detailed store information
- App integration data
- Product catalog insights
- In-depth store analytics

## FAQs

### Q1: What is the Shopify Stores Info API?

A1: The Shopify Stores Info API is a powerful interface hosted on RapidAPI that allows developers to access and analyze data from Shopify stores. It provides comprehensive information about store performance, products, apps, and more.

### Q2: Who can benefit from using this API?

A2: This API is valuable for:
- E-commerce researchers
- Marketing analysts
- App developers
- Store owners
- Data scientists
- Business intelligence professionals

### Q3: What kind of data can I retrieve with this API?

A3: You can access a wide range of data, including:
- Store performance metrics
- Product information
- Installed apps
- Sales analytics
- Customer data (in compliance with privacy regulations)
- Search functionality for specific store data

### Q4: How do I access the API?

A4: You can access the API through RapidAPI. Visit the API URL provided above, sign up for a RapidAPI account if you haven't already, and subscribe to the API to get your API key.

### Q5: Is the API easy to integrate?

A5: Yes, RapidAPI provides a user-friendly interface and clear documentation, making integration straightforward for developers with varying levels of experience.

### Q6: How up-to-date is the data provided by the API?

A6: The API strives to provide the most current data available. For specific information about data freshness, please refer to the API documentation on RapidAPI.

### Q7: Are there any rate limits for API requests?

A7: Rate limits depend on the subscription plan you choose on RapidAPI. Please check the pricing and plan details on the API's RapidAPI page for specific information about rate limits.



## Use Cases

- Competitive Analysis: Gain insights into market trends and competitor strategies.
- App Development: Create targeted apps based on store needs and preferences.
- Market Research: Analyze product trends and consumer behavior across Shopify stores.
- Performance Optimization: Help store owners improve their operations with data-driven insights.

## Support

If you have any questions or need assistance, please use the "Contact Developer" feature on the RapidAPI page for this API. The API provider will be able to assist you with any specific inquiries.

---

Empower your e-commerce insights with the Shopify Stores Info API – Your gateway to comprehensive Shopify store data and analytics, available now on RapidAPI.
