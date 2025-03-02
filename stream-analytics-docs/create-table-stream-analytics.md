---
title: "CREATE TABLE (Stream Analytics)"
description: "The Create table statement is used to define the schema of the payload of the events coming into Azure Stream Analytics."
author: fleid
applies_to: 
  - "Azure"

ms.author: fleide
ms.service: stream-analytics
ms.topic: reference
ms.date: 03/07/2022
---
# CREATE TABLE (Stream Analytics)

The CREATE TABLE statement is used to define the schema of the payload of the events coming into Azure Stream Analytics. This allows the user to explicitly define the data types of each named column for the payload of incoming events. This will inform the job of the input schema, and prevent type inference.

> [!NOTE]
> To compare the different options available for type conversion, see [casting data](data-types-azure-stream-analytics.md#casting-data)
  
It’s important to understand that CREATE TABLE does not actually create any table. CREATE TABLE only defines the data type of each column in the payload of an input alias. This input alias is the one that has been created in the “Add Input” section of the portal. In the absence of such a declaration, the compiler will infer the data type of the columns.

In case of conversion errors, CREATE TABLE will drop the rows from the stream. The rows in error will be moved to the diagnostic logs with the following classification:

```JSON
"Type": "DataError",
"DataErrorType": "InputDeserializerError.InvalidData",
"BriefMessage": "Could not deserialize the input event(s) from resource ... . Some possible reasons: 1) Malformed events 2) Input source configured with incorrect serialization format",
"ErrorCode": "InputDeserializationError",
"ErrorCategory": "DataError"
 ```
 
This means that CREATE TABLE cannot be used to convert types between the original format (CSV, JSON..) and new ones. CREATE TABLE can only be used to explicitely inform the compiler of the types to expect, so deviations can be removed from the stream. If a conversion needs to be made, it should be done in a later query step by using [CAST](cast-azure-stream-analytics.md) or [TRY_CAST](try-cast-azure-stream-analytics.md).
 
## Syntax  
  
```SQL 
CREATE TABLE   
    table_name   
    ( column_name <data_type> [ ,...n ] );  
  
```  
  
## Arguments  
  
-   table_name  
  
     The name of the input stream where the data is coming from. This name needs to match the input alias created in the “Add Input” section of the Azure Stream Analytics portal.  
  
-   column_name  
  
     The name of the column in the payload of the incoming event. If there are no column names in the payload, then default names of column1, column2, … are generated by the system and should be used here in the CREATE TABLE statement.  
  
-   data_type  
  
     The data types which are supported by Azure Stream Analytics. See [Data Types &#40;Azure Stream Analytics&#41;](data-types-azure-stream-analytics.md).  
  
## Examples  

With the following input schema (JSON):
```JSON
  {
    "TollId":1,
    "EntryTime":"2014-09-10T12:11:00.0000000Z",
    "LicensePlate":"NJB 1006",
    "State":"CT",
    "Make":"Ford",
    "Model":"Focus",
    "VehicleType":1,
    "VehicleWeight":0,
    "Toll":4.5,
    "Tag":678912345
  }
```

We can use the following CREATE TABLE statement:

```SQL  
CREATE TABLE Entry (
	TollId bigint,
	EntryTime datetime,
	LicensePlate nvarchar(max),
	State nvarchar(max),
	Make nvarchar(max),
	Model nvarchar(max),
	VehicleType bigint,
	VehicleWeight float,
	Toll float,
	Tag bigint
);

SELECT
	DATEADD(hour,-1,System.Timestamp()) AS WindowStart,
	System.Timestamp AS WindowEnd,
	TollId,
	SUM(Toll) AS TollTotal -- guaranteed to be a float
INTO MyOutput
FROM Entry TIMESTAMP BY EntryTime -- guaranteed to be a timestamp
GROUP BY TollId, Tumbling(hour,1)
```  
  
  
