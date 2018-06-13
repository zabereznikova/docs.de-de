---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766932"
---
# <a name="ole-db-schema-collections"></a>OLE DB-Schemaauflistungen
In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Microsoft SQL Server-OLE DB-Anbieter  
 Der Microsoft SQL Server OLE DB-Treiber unterstützt die folgenden spezifischen schemaauflistungen zusätzlich zu den allgemeinen schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Zeichenfolge|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Zeichenfolge|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Zeichenfolge|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|  
|CHARACTER_SET_NAME|Zeichenfolge|  
|COLLATION_CATALOG|Zeichenfolge|  
|COLLATION_SCHEMA|Zeichenfolge|  
|COLLATION_NAME|Zeichenfolge|  
|DOMAIN_CATALOG|Zeichenfolge|  
|DOMAIN_SCHEMA|Zeichenfolge|  
|DOMAIN_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Boolean|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PARAMETER_NAME|Zeichenfolge|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boolean|  
|PARAMETER_DEFAULT|Zeichenfolge|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Zeichenfolge|  
|TYPE_NAME|Zeichenfolge|  
|LOCAL_TYPE_NAME|Zeichenfolge|  
  
### <a name="catalog"></a>Catalog  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|CATALOG_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
  
### <a name="indexes"></a>Indexes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|INDEX_CATALOG|Zeichenfolge|  
|INDEX_SCHEMA|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Microsoft Oracle-OLE DB-Anbieter  
 Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Ansichten  
  
-   Indexes  
  
### <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Zeichenfolge|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Zeichenfolge|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Zeichenfolge|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|  
|CHARACTER_SET_NAME|Zeichenfolge|  
|COLLATION_CATALOG|Zeichenfolge|  
|COLLATION_SCHEMA|Zeichenfolge|  
|COLLATION_NAME|Zeichenfolge|  
|DOMAIN_CATALOG|Zeichenfolge|  
|DOMAIN_SCHEMA|Zeichenfolge|  
|DOMAIN_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Zeichenfolge|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Ansichten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|VIEW_DEFINITION|Zeichenfolge|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|INDEX_CATALOG|Zeichenfolge|  
|INDEX_SCHEMA|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Microsoft Jet OLE DB-Anbieter  
 Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
-   Tabellen  
  
-   Columns  
  
-   Verfahren  
  
-   Ansichten  
  
-   Indexes  
  
### <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Zeichenfolge|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Zeichenfolge|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Zeichenfolge|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|  
|CHARACTER_SET_NAME|Zeichenfolge|  
|COLLATION_CATALOG|Zeichenfolge|  
|COLLATION_SCHEMA|Zeichenfolge|  
|COLLATION_NAME|Zeichenfolge|  
|DOMAIN_CATALOG|Zeichenfolge|  
|DOMAIN_SCHEMA|Zeichenfolge|  
|DOMAIN_NAME|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Zeichenfolge|  
|DESCRIPTION|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Ansichten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|VIEW_DEFINITION|Zeichenfolge|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|INDEX_CATALOG|Zeichenfolge|  
|INDEX_SCHEMA|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolesch|  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
