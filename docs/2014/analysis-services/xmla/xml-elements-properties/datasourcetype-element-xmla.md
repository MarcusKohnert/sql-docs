---
title: "DataSourceType Element (XMLA) | Microsoft Docs"
ms.custom: ""
ms.date: "06/13/2017"
ms.prod: "sql-server-2014"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "docset-sql-devref"
ms.tgt_pltfrm: ""
ms.topic: "reference"
api_name: 
  - "DataSourceType Element"
api_location: 
  - "http://schemas.microsoft.com/analysisservices/2003/engine"
topic_type: 
  - "apiref"
f1_keywords: 
  - "urn:schemas-microsoft-com:xml-analysis#DataSourceType"
  - "microsoft.xml.analysis.datasourcetype"
  - "http://schemas.microsoft.com/analysisservices/2003/engine#DataSourceType"
helpviewer_keywords: 
  - "DataSourceType element"
ms.assetid: f5a348b1-911b-4139-832e-4bcb6d80a728
caps.latest.revision: 12
author: minewiskan
ms.author: owend
manager: craigg
---
# DataSourceType Element (XMLA)
  Indicates whether a [Location](location-element-xmla.md) element specified for a [Restore](../xml-elements-commands/restore-element-xmla.md) or [Synchronize](../xml-elements-commands/synchronize-element-xmla.md) command is local or remote.  
  
## Syntax  
  
```xml  
  
<Location>  
   ...  
   <DataSourceType>...</DataSourceType>  
   ...  
</Location>  
```  
  
## Element Characteristics  
  
|Characteristic|Description|  
|--------------------|-----------------|  
|Data type and length|String (enumeration)|  
|Default value|*Remote*|  
|Cardinality|0-1: Optional element that can occur once and only once.|  
  
## Element Relationships  
  
|Relationship|Element|  
|------------------|-------------|  
|Parent elements|[Location](location-element-xmla.md)|  
|Child elements|None|  
  
## Remarks  
 The `DataSourceType` element determines whether the data source defined by the `Location` element contains a local data source or a remote data source. For more information about backing up and restoring remote partitions, see [Backing Up, Restoring, and Synchronizing Databases &#40;XMLA&#41;](../../multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
 The value of this element is limited to one of the strings listed in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|*Local*|The `Location` element defines a local data source. If this value is used, the `Restore` and `Synchronize` commands use the information defined in the `Location` element to update the data source, retrieved from either the backup file specified in the `File` element for the `Backup` command or the database specified in the `Source` element for the `Synchronize` command, identified in the `DataSourceID` element of the `Location` element.<br /><br /> This value allows objects that use relational OLAP (ROLAP) storage, after being restored or synchronized, to use a different database for their data and metadata. **Note:**  ROLAP data, such as data in dimension tables or writeback tables, is not restored or synchronized. Only metadata for ROLAP objects is restored or synchronized.|  
|*Remote*|The `Location` element defines a remote data source. If this value is used, the `Restore` and `Synchronize` commands use the information defined in the `Location` element to restore or synchronize remote partitions, retrieved from either the backup file specified in the `File` element of the `Backup` command or the database specified in the `Source` element for the `Synchronize` command, to the remote instance identified in the `DataSourceID` of the `Location` element.|  
  
## See Also  
 [ConnectionString Element &#40;XMLA&#41;](connectionstring-element-xmla.md)   
 [DataSourceID Element &#40;XMLA&#41;](id-element-xmla.md)   
 [Properties &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
