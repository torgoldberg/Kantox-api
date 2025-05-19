# Kantox-api Automation Project

## Prerequisite

- Ensure your local server (e.g., `http://localhost:3000`) is running before executing tests.
- Adjust environment variables as needed for different deployment setups.

---

## Overview

This project automates API testing for a local server using Postman collections and Newman CLI.

- **Test runner:**  
  [Newman CLI](https://learning.postman.com/docs/collections/using-newman-cli/command-line-integration-with-newman/)  
  Execute Postman collections from the command line.

- **Reports:**  
  [newman-reporter-htmlextra](https://www.npmjs.com/package/newman-reporter-htmlextra)  
  Generates detailed HTML test reports after each run.

---

## Project Structure

- **Collections/**  
   Contains exported Postman collections (API test requests and scripts).

- **Environment/**  
   Contains Postman environment files with variables like base URLs and IDs.

- **Reports/**  
   Stores the HTML reports generated after each Newman run.

---

## Install & Setup

- **Clone the repository**
  https://github.com/torgoldberg/Kantox-api.git

- **Install dependencies**  
  npm install

- **Run tests with Newman**
  npx newman run "collections/Kantox API.postman_collection.json" \
  -e environment/Local.postman_environment.json \
  -r htmlextra \
  --reporter-htmlextra-export reports/report.html

---

## How to Add New Tests

1. Import the latest collection and environment JSON files into your Postman app.

2. Open the collection and add new requests or modify existing ones with test scripts in the **Scripts** tab.

3. Run the request in Postman to verify individual test behavior.

4. Save the changes and run the entire collection in Postman’s Collection Runner to ensure all tests pass.

5. Export the updated collection and environment files back to the respective folders (`collections/` and `environment/`).

6. Commit your changes to a **new branch** in the repository.

7. Run Newman locally to verify the full test suite and generate a fresh HTML report:

   ```bash
   npx newman run "collections/Kantox API.postman_collection.json" \
     -e environment/Local.postman_environment.json \
     -r htmlextra \
     --reporter-htmlextra-export reports/report.html
   ```

---
