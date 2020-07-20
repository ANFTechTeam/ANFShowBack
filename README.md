# ANFShowBack

An Azure Logic App to report estimated costs of individual volumes.

## Prerequisites

1. Azure Storage Account - this storage account will be used to store the table data for ANFShowBack. You will need to provide the Storage Account Name and Access Key.

## Installation

Click the button below to deploy to Azure. You will need to key in the UTC Offset for you timezone, your existing Storage Account and access key.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FANFTechTeam%2FANFShowBack%2Fmaster%2Fanfshowback.json)

The Logic App should be configured to run daily.

When ran...

 1. if it doesn't exist a new table is created called 'ANFSBDailyLog'
 2. if it doesn't exist a new table is created for the current month: 'ANFSBYYYYMM'
 3. a new row is added to the table 'ANFSBDailyLog' for each volume.
 4. a row is created (if it doesn't exist) or modified in the table 'ANFSBYYYYMM' which increments the running cost of each volume.

On the last day of each month, the Logic App outputs a table in two formats: CSV and HTML
You can add an action after these steps to send the reports via email or some other method.
