---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: bdedbb11960f02b99dcca6388abf663635238f74
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43750008"
---
# <a name="odbc-schema-collections"></a>ODBC-Schemaauflistungen
In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.  
  
## <a name="microsoft-sql-server-odbc-driver"></a>Microsoft SQL Server-ODBC-Treiber  
 Der Microsoft SQL Server-ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:  
  
-   Tabellen  
  
-   Indexes  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
### <a name="tables-and-views"></a>Tables und Views  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CAT|Zeichenfolge|  
|TABLE_SCHEM|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|REMARKS|Zeichenfolge|  
  
### <a name="indexes"></a>Indexes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CAT|Zeichenfolge|  
|TABLE_SCHEM|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|NON_UNIQUE|Int16|  
|INDEX_QUALIFIER|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|TYPE|Int16|  
|ORDINAL_POSITION|Int16|  
|COLUMN_NAME|Zeichenfolge|  
|ASC_OR_DESC|Zeichenfolge|  
|CARDINATLITY|Int32|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|SS_TYPE_SCHEMA|Zeichenfolge|  
|SS_DATA_TYPE|Byte|  
  
### <a name="columns"></a>Columns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CAT|Zeichenfolge|  
|TABLE_SCHEM|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN_DEF|Zeichenfolge|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|Zeichenfolge|  
|SS_TYPE_CATALOG|Zeichenfolge|  
|SS_TYPE_SCHEMA|Zeichenfolge|  
|SS_DATA_TYPE|Byte|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CAT|Zeichenfolge|  
|PROCEDURE_SCHEM|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|NUM_INPUT_PARAMS|Int32|  
|NUM_OUTPUT_PARAMS|Int32|  
|NUM_RESULT_SETS|Int32|  
|REMARKS|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CAT|Zeichenfolge|  
|PROCEDURE_SCHEM|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN_DEF|Zeichenfolge|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|Zeichenfolge|  
|SS_TYPE_CATALOG|Zeichenfolge|  
|SS_TYPE_SCHEMA|Zeichenfolge|  
|SS_DATA_TYPE|Byte|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CAT|Zeichenfolge|  
|PROCEDURE_SCHEM|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN_DEF|Zeichenfolge|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|Zeichenfolge|  
|SS_TYPE_CATALOG|Zeichenfolge|  
|SS_TYPE_SCHEMA|Zeichenfolge|  
|SS_DATA_TYPE|Byte|  
  
## <a name="microsoft-oracle-odbc-driver"></a>Microsoft Oracle ODBC-Treiber  
 Der Microsoft SQL Server Oracle ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
-   Indexes  
  
### <a name="tables-and-views"></a>Tables und Views  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_QUALIFIER|Zeichenfolge|  
|TABLE_OWNER|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|REMARKS|Zeichenfolge|  
  
### <a name="columns"></a>Columns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_QUALIFIER|Zeichenfolge|  
|TABLE_OWNER|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|ORDINAL_POSITION|Int32|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|Zeichenfolge|  
|PROCEDURE_OWNER|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|NUM_INPUT_PARAMS|Int16|  
|NUM_OUTPUT_PARAMS|Int16|  
|NUM_RESULT_SETS|Int16|  
|REMARKS|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|Zeichenfolge|  
|PROCEDURE_OWNER|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|OVERLOAD|Int32|  
|ORDINAL_POSITION|Int32|  
  
## <a name="microsoft-jet-odbc-driver"></a>Microsoft Jet ODBC-Treiber  
 Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Indexes  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
### <a name="tables-and-views"></a>Tables und Views  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_QUALIFIER|Zeichenfolge|  
|TABLE_OWNER|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|REMARKS|Zeichenfolge|  
  
### <a name="columns"></a>Columns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_QUALIFIER|Zeichenfolge|  
|TABLE_OWNER|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|ORDINAL_POSITION|Int32|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|Zeichenfolge|  
|PROCEDURE_OWNER|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|NUM_INPUT_PARAMS|Int16|  
|NUM_OUTPUT_PARAMS|Int16|  
|NUM_RESULT_SETS|Int16|  
|REMARKS|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|Zeichenfolge|  
|PROCEDURE_OWNER|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|OVERLOAD|Int32|  
|ORDINAL_POSITION|Int32|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CAT|Zeichenfolge|  
|PROCEDURE_SCHEM|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|Zeichenfolge|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Zeichenfolge|  
|COLUMN_DEF|Zeichenfolge|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|Zeichenfolge|  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
