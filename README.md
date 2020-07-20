# ANFShowBack
An Azure Logic App to report estimated costs of individual volumes.

Prerequisites
1. Azure Storage Account - this storage account will be used to store the table data

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FANFTechTeam%2FANFShowBack%2Fmaster%2Fanfshowback.json)

On the last day of each month, the Logic App outputs a table in two formats: CSV and HTML
You can add an action after these steps to send the reports via email or some other method.