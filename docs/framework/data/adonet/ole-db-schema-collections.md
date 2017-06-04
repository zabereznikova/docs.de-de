---
title: "OLE DB-Schemaauflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# OLE DB-Schemaauflistungen
In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC\-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.  
  
## Microsoft SQL Server\-OLE DB\-Anbieter  
 Der Microsoft SQL Server\-OLE DB\-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### Tabellen  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|TABLE\_TYPE|Zeichenfolge|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|Zeichenfolge|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Columns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|Zeichenfolge|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|Zeichenfolge|  
|CHARACTER\_SET\_SCHEMA|Zeichenfolge|  
|CHARACTER\_SET\_NAME|Zeichenfolge|  
|COLLATION\_CATALOG|Zeichenfolge|  
|COLLATION\_SCHEMA|Zeichenfolge|  
|COLLATION\_NAME|Zeichenfolge|  
|DOMAIN\_CATALOG|Zeichenfolge|  
|DOMAIN\_SCHEMA|Zeichenfolge|  
|DOMAIN\_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|COLUMN\_LCID|Int32|  
|COLUMN\_COMPFLAGS|Int32|  
|COLUMN\_SORTID|Int32|  
|COLUMN\_TDSCOLLATION|Byte\[\]|  
|IS\_COMPUTED|Boolean|  
  
### Verfahren  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CATALOG|Zeichenfolge|  
|PROCEDURE\_SCHEMA|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### ProcedureParameters  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CATALOG|Zeichenfolge|  
|PROCEDURE\_SCHEMA|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|PARAMETER\_NAME|Zeichenfolge|  
|ORDINAL\_POSITION|Int32|  
|PARAMETER\_TYPE|Int32|  
|PARAMETER\_HASDEFAULT|Boolean|  
|PARAMETER\_DEFAULT|Zeichenfolge|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DESCRIPTION|Zeichenfolge|  
|TYPE\_NAME|Zeichenfolge|  
|LOCAL\_TYPE\_NAME|Zeichenfolge|  
  
### Catalog  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|CATALOG\_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
  
### Indexes  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|INDEX\_CATALOG|Zeichenfolge|  
|INDEX\_SCHEMA|Zeichenfolge|  
|INDEX\_NAME|Zeichenfolge|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER\_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolean|  
  
## Microsoft Oracle\-OLE DB\-Anbieter  
 Der Microsoft Oracle OLE DB\-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
-   Indexes  
  
### Tabellen  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|TABLE\_TYPE|Zeichenfolge|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|Zeichenfolge|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Columns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|Zeichenfolge|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|Zeichenfolge|  
|CHARACTER\_SET\_SCHEMA|Zeichenfolge|  
|CHARACTER\_SET\_NAME|Zeichenfolge|  
|COLLATION\_CATALOG|Zeichenfolge|  
|COLLATION\_SCHEMA|Zeichenfolge|  
|COLLATION\_NAME|Zeichenfolge|  
|DOMAIN\_CATALOG|Zeichenfolge|  
|DOMAIN\_SCHEMA|Zeichenfolge|  
|DOMAIN\_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
  
### Verfahren  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CATALOG|Zeichenfolge|  
|PROCEDURE\_SCHEMA|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### ProcedureColumns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CATALOG|Zeichenfolge|  
|PROCEDURE\_SCHEMA|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ROWSET\_NUMBER|Int64|  
|ORDINAL\_POSITION|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DESCRIPTION|Zeichenfolge|  
|OVERLOAD|Int16|  
  
### Ansichten  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|VIEW\_DEFINITION|Zeichenfolge|  
|CHECK\_OPTION|Boolean|  
|IS\_UPDATABLE|Boolean|  
|DESCRIPTION|Zeichenfolge|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Indexes  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|INDEX\_CATALOG|Zeichenfolge|  
|INDEX\_SCHEMA|Zeichenfolge|  
|INDEX\_NAME|Zeichenfolge|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER\_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolean|  
  
## Microsoft Jet OLE DB\-Anbieter  
 Der Microsoft Jet OLE DB\-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   Ansichten  
  
-   Indexes  
  
### Tabellen  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|TABLE\_TYPE|Zeichenfolge|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|Zeichenfolge|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Columns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|Zeichenfolge|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|Zeichenfolge|  
|CHARACTER\_SET\_SCHEMA|Zeichenfolge|  
|CHARACTER\_SET\_NAME|Zeichenfolge|  
|COLLATION\_CATALOG|Zeichenfolge|  
|COLLATION\_SCHEMA|Zeichenfolge|  
|COLLATION\_NAME|Zeichenfolge|  
|DOMAIN\_CATALOG|Zeichenfolge|  
|DOMAIN\_SCHEMA|Zeichenfolge|  
|DOMAIN\_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
  
### Verfahren  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CATALOG|Zeichenfolge|  
|PROCEDURE\_SCHEMA|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Ansichten  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|VIEW\_DEFINITION|Zeichenfolge|  
|CHECK\_OPTION|Boolean|  
|IS\_UPDATABLE|Boolean|  
|DESCRIPTION|Zeichenfolge|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Indexes  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CATALOG|Zeichenfolge|  
|TABLE\_SCHEMA|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|INDEX\_CATALOG|Zeichenfolge|  
|INDEX\_SCHEMA|Zeichenfolge|  
|INDEX\_NAME|Zeichenfolge|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER\_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolean|  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)