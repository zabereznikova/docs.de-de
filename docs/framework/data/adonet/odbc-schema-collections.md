---
title: "ODBC-Schemaauflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ODBC-Schemaauflistungen
In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC\-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.  
  
## Microsoft SQL Server\-ODBC\-Treiber  
 Der Microsoft SQL Server\-ODBC\-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Indexes  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
### Tables und Views  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CAT|Zeichenfolge|  
|TABLE\_SCHEM|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|TABLE\_TYPE|Zeichenfolge|  
|REMARKS|Zeichenfolge|  
  
### Indexes  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CAT|Zeichenfolge|  
|TABLE\_SCHEM|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|NON\_UNIQUE|Int16|  
|INDEX\_QUALIFIER|Zeichenfolge|  
|INDEX\_NAME|Zeichenfolge|  
|TYPE|Int16|  
|ORDINAL\_POSITION|Int16|  
|COLUMN\_NAME|Zeichenfolge|  
|ASC\_OR\_DESC|Zeichenfolge|  
|CARDINATLITY|Int32|  
|PAGES|Int32|  
|FILTER\_CONDITION|Zeichenfolge|  
|SS\_TYPE\_SCHEMA|Zeichenfolge|  
|SS\_DATA\_TYPE|Byte|  
  
### Columns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_CAT|Zeichenfolge|  
|TABLE\_SCHEM|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN\_DEF|Zeichenfolge|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Zeichenfolge|  
|SS\_TYPE\_CATALOG|Zeichenfolge|  
|SS\_TYPE\_SCHEMA|Zeichenfolge|  
|SS\_DATA\_TYPE|Byte|  
  
### Verfahren  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CAT|Zeichenfolge|  
|PROCEDURE\_SCHEM|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|NUM\_INPUT\_PARAMS|Int32|  
|NUM\_OUTPUT\_PARAMS|Int32|  
|NUM\_RESULT\_SETS|Int32|  
|REMARKS|Zeichenfolge|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CAT|Zeichenfolge|  
|PROCEDURE\_SCHEM|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN\_DEF|Zeichenfolge|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Zeichenfolge|  
|SS\_TYPE\_CATALOG|Zeichenfolge|  
|SS\_TYPE\_SCHEMA|Zeichenfolge|  
|SS\_DATA\_TYPE|Byte|  
  
### ProcedureParameters  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CAT|Zeichenfolge|  
|PROCEDURE\_SCHEM|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN\_DEF|Zeichenfolge|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Zeichenfolge|  
|SS\_TYPE\_CATALOG|Zeichenfolge|  
|SS\_TYPE\_SCHEMA|Zeichenfolge|  
|SS\_DATA\_TYPE|Byte|  
  
## Microsoft Oracle ODBC\-Treiber  
 Der Microsoft SQL Server Oracle ODBC\-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
-   Indexes  
  
### Tables und Views  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_QUALIFIER|Zeichenfolge|  
|TABLE\_OWNER|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|TABLE\_TYPE|Zeichenfolge|  
|REMARKS|Zeichenfolge|  
  
### Columns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_QUALIFIER|Zeichenfolge|  
|TABLE\_OWNER|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|ORDINAL\_POSITION|Int32|  
  
### Verfahren  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_QUALIFIER|Zeichenfolge|  
|PROCEDURE\_OWNER|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|Zeichenfolge|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_QUALIFIER|Zeichenfolge|  
|PROCEDURE\_OWNER|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
## Microsoft Jet ODBC\-Treiber  
 Der Microsoft Jet ODBC\-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Indexes  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
### Tables und Views  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_QUALIFIER|Zeichenfolge|  
|TABLE\_OWNER|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|TABLE\_TYPE|Zeichenfolge|  
|REMARKS|Zeichenfolge|  
  
### Columns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|TABLE\_QUALIFIER|Zeichenfolge|  
|TABLE\_OWNER|Zeichenfolge|  
|TABLE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|ORDINAL\_POSITION|Int32|  
  
### Verfahren  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_QUALIFIER|Zeichenfolge|  
|PROCEDURE\_OWNER|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|Zeichenfolge|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_QUALIFIER|Zeichenfolge|  
|PROCEDURE\_OWNER|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
### ProcedureParameters  
  
|Spaltenname|DataType|  
|-----------------|--------------|  
|PROCEDURE\_CAT|Zeichenfolge|  
|PROCEDURE\_SCHEM|Zeichenfolge|  
|PROCEDURE\_NAME|Zeichenfolge|  
|COLUMN\_NAME|Zeichenfolge|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Zeichenfolge|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN\_DEF|Zeichenfolge|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Zeichenfolge|  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)