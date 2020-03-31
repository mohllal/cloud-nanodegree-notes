# Serverless Framework

- There are many different frameworks that enable us to develop serverless applications, and many of them provide us with:
  - Standardized way of deploying an application.
  - Create necessary resources.
  - Manage lifecycle of an application.

- ***CloudFormation*** is a services for creation and management of AWS resources. It allows us to:
  - Write `YAML`/`JSON` configuration file.
  - Changes state of AWS resources.
  - Version control the infrastructure.
CloudFormation is free and we only need to pay for created resources.

- DynamoDB ***Local secondary index (LSI)***:
  - Like an additional sort key
  - Allows to sort items by a different attribute
  - Added on the data in a table
  
- DynamoDB ***Global secondary index (GSI)***:
  - Allows to define a new partition key for the same data
  - Allows to define a new partition and sort key for the same data
  - Creates copy of the data in a table (data is available via GSI after some delay)