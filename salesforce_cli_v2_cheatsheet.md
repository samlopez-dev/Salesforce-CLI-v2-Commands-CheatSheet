
# Salesforce CLI (v2) Cheatsheet

## 1. Log In and Set Alias
- **Log in to a Sandbox Org and set an alias**:
  ```bash
  sf org login web -r https://test.salesforce.com -a sandbox1
  ```

- **Log in to a Sandbox Org, set alias, and set as default org**:
  ```bash
  sf org login web -r https://test.salesforce.com -a sandbox1 -s
  ```

- **Log in to a Prod or DevHub Org and set an alias**:
  ```bash
  sf org login web -a prodOrDevHub
  ```

## 2. Metadata Retrieval
- **Retrieve Workflow Rule for the Opportunity object**:
  ```bash
  sf project retrieve start -m "WorkflowRule:Opportunity.My_Workflow_Rule" -o sandbox1
  ```

- **Retrieve Apex Class**:
  ```bash
  sf project retrieve start -m "ApexClass:MyApexClass" -o sandbox1
  ```

- **Retrieve Custom Field for the Account object**:
  ```bash
  sf project retrieve start -m "CustomField:Account.MyCustomField__c" -o sandbox1
  ```

- **Retrieve Validation Rule for the Quote object**:
  ```bash
  sf project retrieve start -m "ValidationRule:Quote.MyValidationRule" -o sandbox1
  ```

- **Retrieve Page Layout for Account**:
  ```bash
  sf project retrieve start -m "Layout:Account.My_Account_Layout" -o sandbox1
  ```

## 3. Deploy Metadata
- **Deploy Apex Class to the sandbox1 org**:
  ```bash
  sf project deploy start -m "ApexClass:MyApexClass" -o sandbox1
  ```

- **Deploy Custom Field to the Account object**:
  ```bash
  sf project deploy start -m "CustomField:Account.MyCustomField__c" -o sandbox1
  ```

- **Deploy Workflow Rule to the Opportunity object**:
  ```bash
  sf project deploy start -m "WorkflowRule:Opportunity.My_Workflow_Rule" -o sandbox1
  ```

- **Deploy All Metadata from a folder**:
  ```bash
  sf project deploy start -d path_to_folder -o sandbox1
  ```

## 4. Run Apex
- **Run Anonymous Apex in the org**:
  ```bash
  sf apex run -f path_to_apex_file -o sandbox1
  ```

- **Run Apex Test (TestClass.Test1) in sync mode**:
  ```bash
  sf force apex test run -t TestClass.Test1 -o sandbox1 --synchronous
  ```

## 5. Metadata Examples with `-m`
- **Workflow Rule** (example for Opportunity):
  ```bash
  sf project retrieve start -m "WorkflowRule:Opportunity.My_Workflow_Rule" -o sandbox1
  ```

- **Email Alert** (example for Opportunity):
  ```bash
  sf project retrieve start -m "WorkflowAlert:Opportunity.MyEmailAlert" -o sandbox1
  ```

- **Validation Rule** (example for Quote):
  ```bash
  sf project retrieve start -m "ValidationRule:Quote.MyValidationRule" -o sandbox1
  ```

- **Custom Field** (example for Account):
  ```bash
  sf project retrieve start -m "CustomField:Account.MyCustomField__c" -o sandbox1
  ```

## 6. List and Manage Org Connections
- **List All Connected Orgs**:
  ```bash
  sf org list
  ```

- **Open an Org by alias**:
  ```bash
  sf org open -o sandbox1
  ```

- **Set Org as Default**:
  ```bash
  sf config set target-org sandbox1
  ```

- **Disconnect from an Org**:
  ```bash
  sf org logout -o sandbox1
  ```

- **Disconnect from All Orgs**:
  ```bash
  sf org logout -a -p
  ```

## 7. Scratch Org Management
- **Create a Scratch Org with alias tempScratch**:
  ```bash
  sf org create scratch -d -f config/project-scratch-def.json -a tempScratch
  ```

- **Delete a Scratch Org**:
  ```bash
  sf org delete scratch -o tempScratch
  ```

## 8. Help and Search
- **Get Help for Commands**:
  ```bash
  sf --help
  ```

- **Search for Commands**:
  ```bash
  sf search project retrieve
  ```

- **Search for Specific Metadata Types**:
  ```bash
  sf search WorkflowRule
  ```
