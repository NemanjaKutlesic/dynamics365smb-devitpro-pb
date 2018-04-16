---
title: "CreateMultiple Operation"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: dca6d1e6-d4e3-451a-981f-4cb6be073b01
caps.latest.revision: 10
---
# CreateMultiple Operation
Creates a set of records. The supplied record object is overwritten with the version that is created by the page.  
  
## Method Signature  
 `void CreateMultiple(ref Entity[] entity)`  
  
## Parameters  
  
|Parameter|Description|  
|---------------|-----------------|  
|*entity\[\]*|Type: An array of Entities<br /><br /> An array of a specific object type that represents the page.|  
  
## Results  
  
|Result name|Description|  
|-----------------|-----------------|  
|*entity\[\]*|Type: An array of Entities<br /><br /> An array of a specific object type that represents the page. Contains the latest values that are present on the page after the records have been inserted into the table.|  
  
## Faults  
  
|SOAP fault message|Description|  
|------------------------|-----------------|  
|The \[*record name*\] already exists. Identification fields and values:  \[*field*\]=\[*value*\]|Indicates that the insertion of at least one of the records would violate key constraints.|  
  
 Other faults are possible if they are generated by the C/AL code.  
  
 The CreateMultiple operation is executed as a single transaction unless the C/AL code explicitly commits the transaction. Either all or none of the records are inserted unless the application code does not explicitly call COMMIT.  
  
## Usage Example  
  
```c#  
Customer[] custArray = new Customer[3];  
for (int i = 0; i < custArray.Length; i++)  
{  
  custArray[i] = new Customer();  
  custArray[i].Name = "Customer Name " + i.ToString();  
}  
service.CreateMultiple(ref custArray);  
```  
  
## See Also  
 [Basic Page Operations](Basic-Page-Operations.md)