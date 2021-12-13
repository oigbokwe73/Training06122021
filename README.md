## Appplication Setting 

|Key|Value | Comment|
|:----|:----|:----|
|AzureWebJobsStorage|[CONNECTION STRING]|RECOMMENDATION :  store in AzureKey Vault.|
|ConfigurationPath| [CONFIGURATION FOLDER PATH] |Folder is optional
|ApiKeyName|[API KEY NAME]|Will be passed in the header  :  the file name of the config.
|AppName| [APPLICATION NAME]| This is the name of the Function App. Used in log analytics|
|StorageAcctName|[STORAGE ACCOUNT NAME]|Example  "AzureWebJobsStorage"|

## Function App  Configuration 

> **Note:** The **Configuration** is located in the  FunctionApp  in a **Config** Folder.

|FileName|Description|
|:----|:----|
|43EFE991E8614CFB9EDECF1B0FDED37B.json| Upload Config File|
|43EFE991E8614CFB9EDECF1B0FDED37C.json| Search Records config File.|

## Upload CSV File

|Key|Value|Comments|
|:----|:----|:----|
|ReadCsvAsStream|Yes| Required to parse the csv file while uploading|
|messageformat|application/json OR application/xml| required|
|FolderName||OPTIONAL:This is required for additonal XSL transformation |
|FileName||OPTIONAL:This is required for additonal XSL transformation |
|TableName|<AZURE TABLE NAME>| Create table add records
|StorageAccount|<STORAGE ACCOUNT KEY>| Name of the  storage account key in AppSettings.|



## Search Record

|Key|Value|Comments|
|:----|:----|:----|
|SimpleTableSearch|Yes| Indicates the method in the process to use the API|
|PartitionKey|<PROPERTY NAME >|OPTIONAL : Identity the  Field/Key in the JSON payload as a Partition Key|
|QueryField|<SEARCH PROPERTY NAME>|Provide the search property name to be used in the search
|DefaultResult| <CUSTOM MESSAGE> | OPTIONAL :  No  results return then a default message
|TableName|<AZURE TABLE NAME>| Create table add records
|StorageAccount|<STORAGE ACCOUNT KEY>| Name of the  storage account key in AppSettings.|

