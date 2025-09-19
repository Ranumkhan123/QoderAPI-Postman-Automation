## Qoder API – Postman Automation Testing

This repository contains a **complete API testing & automation project** developed with Postman, which focuses on authentication, CRUD operations, negative scenarios, schema validation, performance checks, reporting, and monitoring. It illustrates industry-standard procedures for automating and testing APIs.  


----


## About the API  

This project employs a unique API that I built with **Qoder — The Agentic Coding Platform**.  
Qoder allowed me to create and deploy a fully functional CRUD API with authentication, which served as the foundation for this Postman-based automation project. Instead of depending solely on public APIs, I created my own to test **real-world API testing workflows** such as authentication, authorization, error handling, and data-driven testing.  


----


## Prerequisites

To perform these tests locally, you will need:

- Install the Postman Desktop Application or the Postman CLI (Newman).
- The Qoder API server is currently running against a local instance at http://localhost:3000.


----


## Project Overview

The test suite is created for the **Qoder API** (based on **Qoder-The Agentic Coding Platform**) and includes:  

- **Authentication**: Token creation for secure requests.  
- **CRUD Operations**: Full Create, Read, Update (PUT/PATCH), and Delete flow with dynamic IDs.  
- **Negative Testing**: Includes several failure scenarios and error validations.  
- **Advanced Scripting**: Create test scripts for collections, folders, and requests.  
- **Schema Validation**: Using Ajv for JSON schema validation.  
- **Performance Checks**: Validation of response time and size with configurable thresholds.  
- **Monitors** → Set Postman Monitor to run tests automatically.  
- **Automation Reports** → HTML Extra reports created using Newman.  


----


## Project Structure


QoderAPI-Postman-Automation/
│
├── collections/          # Exported Postman collection JSON
├── environments/         # Postman environment JSON
├── data/                 # CSV files for data-driven testing
├── reports/              # Newman HTML extra reports
├── docs/                 # API Documentation (Swagger/OpenAPI + screenshots)
└── README.md             # Project documentation


----


## Test Coverage

### Authentication
- **Generate Token** (used for securing all CRUD requests).  

### CRUD Items
- **Create Item**  
- **Get All Items** (stores all item IDs for later use).  
- **Get Specific Item** (random ID fetched dynamically from saved IDs).  
- **Update Item (PUT)**  
- **Partial Update Item (PATCH)**  
- **Delete Item (DELETE)**  

> All update & delete requests dynamically pick a **random item ID** from saved IDs.  


### Negative Scenarios
- No token (unauthorized)  
- Invalid token  
- Missing required fields  
- Non-existent IDs (404)  
- Empty body  
- Invalid field type → Price & Name  
- Negative price  
- Very long string (boundary test)  
- Very large number (boundary test)  
- Invalid HTTP method  
- Unexpected fields  


### Delete Folder
- **Clear All Items**  
- **Clear Data**  


----


## Features

- **Dynamic Chaining**: IDs recorded in one request are reused in subsequent requests (e.g., GET, PATCH, and DELETE).  
- **Collection Level Tests**:  
  - Schema validation (based on Ajv)  
  - Validation of response time and size  
  - Validation of the root key and header  
  - Validity of JSON  
- **Folder Level & Request Level Tests**: Each request includes validations for both the happy path and negative scenarios.  
- **Monitor Setup**: Automated Postman Monitor is configured to conduct this collection on a scheduled basis.  
- **Data-driven Testing**: CSV is used for bulk data testing.  
- **Newman Execution**: Collection can be run via CLI using.
- **HTML Extra Reports** saved in the'reports/' folder.  


---


## Test Scripts

Implemented at three levels: 

1. **Collection-level**:
   - The validity of JSON (Ajv).  
   - The response time threshold.  
   - The Response size validation. 
   - Checking the headers (Content-Type, etc.).  
   - Validations for the root key. 

2. **Folder-level**:  
   - Shared schemas (e.g., authentication responses).  

3. **Request Level**  
   - Request-specific validations (status codes, body fields, and values).  


----


## Monitoring

- Postman **Monitor** is set to execute the collection at predetermined times.  
- Endpoint health checks are performed automatically.  
- Contributes to the detection of downtime and performance concerns.  


----


## API Documentation

- - Swagger/OpenAPI documentation is accessible on **SwaggerHub**: 
  👉 [Qoder API Docs](https://app.swaggerhub.com/apis-docs/ranumkhan-98c/QoderAPI-Docs/1.0.0)  


----


## Tools & Technologies

| Tool/Library            | Purpose |
|-------------------------|---------|
| **Postman**             | API Testing & Automation |
| **Newman CLI**          | Command-line execution |
| **newman-reporter-htmlextra** | Rich HTML reporting |
| **Ajv**                 | JSON Schema validation |
| **CSV Data Files**      | Data-driven testing |
| **SwaggerHub**          | API Documentation |
| **GitHub**              | Portfolio hosting |
| **Qoder Platform**      | API backend built with Qoder – The Agentic Coding Platform |


----


## How to Run

1. Clone this repository  
2. Install [Newman](https://www.npmjs.com/package/newman):  
   ```bash
   npm install -g newman newman-reporter-htmlextra
   ```
3. Run collection with:  
   ```bash
   newman run collections/QoderAPI.json \
     -e environments/QoderAPI_Env.json \
     --iteration-data data/items.csv \
     --reporters cli,htmlextra \
     --reporter-htmlextra-export reports/QoderAPI-report.html
   ```
4. Run requests step-by-step or as a collection
5. Open Console to view logs


----


## Author & Learning Goals

Ranum Khan created this project as part of her API Testing/API Automation Testing with Postman for practice, while learning automation from scratch.

I am an experienced QA Engineer with a strong foundation in manual and API testing, and rich documentation. If you like this collection, if this helped or inspired you, do give a ⭐ star or fork it! and connect via LinkedIn. PRs and suggestions are welcome!

https://www.linkedin.com/in/ranum-khan-qaengineer
https://github.com/Ranumkhan123
ranumkhan123@gmail.com


---


## License

This project is for **educational & portfolio purposes** only.  
