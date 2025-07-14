# Postman API Automation with GitHub Actions #
This reposiroty is a demonstration for POC for integrating Postman tests with GitHub Actions. The tests are written in Postman and they are executed in the VM with the help of newman and newman-reporter-htmlextra.
GitHub Actions will trigger execution on every PUSH to the main branch. You can also execute the project manually using workflo_dispatch. The project runs on scheduled time with the help of cron job. The html reports are archived and kept in the artifacts section fro the team to download and along with that they can view the report directly from the githubpage https://github.com/PranitaVPanse/Phoenix-InWarranty-Flow-Postman/ 
The latest report is mailed to the team members using Gmail SMTP.

## Testing Coverage ##
1. Happy flow Testing
2. Negative Testing and Edge Case testing
3. Token Testing
4. Data- Driven Testing
5. Schema Validation
6. Secrets Management with GitHub Secrets

## Tech Stack ##
1. Postman
2. Node.js - 22v
3. Newman
4. Newman-Reporter-htmlextra
5. GitHub Actions
6. Gmail SMTP
7. GitHub Pages
8. CSV for data-driven testing
9. AWS - EC2 instance for Self hosted GitHub Runner

## GitHub Pages ##
You can directly view the test report of the Postman test at the GitHub page https://github.com/PranitaVPanse/Phoenix-InWarranty-Flow-Postman 

## Newmn Report ##
The report will be generated in the Newman folder and find below the screenshot:

![Report Screenshot](https://github.com/PranitaVPanse/Phoenix-InWarranty-Flow-Postman/blob/static-content/Report%20Screenshot.png)

## Project Structure ##
```
Postman
├─ InWarranty-Flow-Collection.postman_collection.json
├─ QA.postman_environment.json
└─ TestData.csv

```

## How to run the project ##
You can run the project on your local system, for that 
1. Clone the project on local system. ``` https://github.com/PranitaVPanse/Phoenix-InWarranty-Flow-Postman ```
2. Install Node.js and NPM from ``` https://nodejs.org/en ```
3. Install Newman using  ``` npm install -g newman ```
4. Install Newman-Reporter-Htmlextra using ``` npm install -g newman-reporter-htmlextra ```
5. Runt the newman command:
   ```
   newman run InWarranty-Flow-Collection.postman_collection.json \
            -e QA.postman_environment.json \
            -d TestData.csv \
            -r cli,htmlextra \
            --reporter-htmlextra-export ./newman/index.html
    ```




