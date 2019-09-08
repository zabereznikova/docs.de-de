---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783449"
---
# <a name="ole-db-schema-collections"></a>OLE DB-Schemaauflistungen
In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Microsoft SQL Server-OLE DB-Anbieter  
 Der Microsoft SQL Server OLE DB-Treibers unterstützt zusätzlich zu den allgemeinen Schema Auflistungen auch die folgenden spezifischen Schema Auflistungen:  
  
- Tabellen  
  
- Spalten  
  
- Verfahren  
  
- ProcedureParameters  
  
- Katalog  
  
- Indizes  
  
### <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|TABLE_GUID|GUID|  
|BESCHREIBUNG|Zeichenfolge|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Spalten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolesch|  
|COLUMN_DEFAULT|Zeichenfolge|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolesch|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
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
|BESCHREIBUNG|Zeichenfolge|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Boolesch|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Zeichenfolge|  
|BESCHREIBUNG|Zeichenfolge|  
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
|PARAMETER_HASDEFAULT|Boolesch|  
|PARAMETER_DEFAULT|Zeichenfolge|  
|IS_NULLABLE|Boolesch|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|BESCHREIBUNG|Zeichenfolge|  
|TYPE_NAME|Zeichenfolge|  
|LOCAL_TYPE_NAME|Zeichenfolge|  
  
### <a name="catalog"></a>Katalog  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|CATALOG_NAME|Zeichenfolge|  
|BESCHREIBUNG|Zeichenfolge|  
  
### <a name="indexes"></a>Indizes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|INDEX_CATALOG|Zeichenfolge|  
|INDEX_SCHEMA|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|PRIMARY_KEY|Boolesch|  
|UNIQUE|Boolesch|  
|CLUSTERED|Boolesch|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolesch|  
|AUTO_UPDATE|Boolesch|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolesch|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Microsoft Oracle-OLE DB-Anbieter  
 Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
- Tabellen  
  
- Spalten  
  
- Verfahren  
  
- ProcedureColumns  
  
- ProcedureParameters  
  
- Ansichten  
  
- Indizes  
  
### <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|TABLE_GUID|GUID|  
|BESCHREIBUNG|Zeichenfolge|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Spalten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolesch|  
|COLUMN_DEFAULT|Zeichenfolge|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolesch|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
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
|BESCHREIBUNG|Zeichenfolge|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Zeichenfolge|  
|BESCHREIBUNG|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolesch|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|BESCHREIBUNG|Zeichenfolge|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Ansichten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|VIEW_DEFINITION|Zeichenfolge|  
|CHECK_OPTION|Boolesch|  
|IS_UPDATABLE|Boolesch|  
|BESCHREIBUNG|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indizes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|INDEX_CATALOG|Zeichenfolge|  
|INDEX_SCHEMA|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|PRIMARY_KEY|Boolesch|  
|UNIQUE|Boolesch|  
|CLUSTERED|Boolesch|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolesch|  
|AUTO_UPDATE|Boolesch|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolesch|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Microsoft Jet OLE DB-Anbieter  
 Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:  
  
- Tabellen  
  
- Spalten  
  
- Verfahren  
  
- Ansichten  
  
- Indizes  
  
### <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|TABLE_TYPE|Zeichenfolge|  
|TABLE_GUID|GUID|  
|BESCHREIBUNG|Zeichenfolge|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Spalten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolesch|  
|COLUMN_DEFAULT|Zeichenfolge|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolesch|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
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
|BESCHREIBUNG|Zeichenfolge|  
  
### <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Zeichenfolge|  
|PROCEDURE_SCHEMA|Zeichenfolge|  
|PROCEDURE_NAME|Zeichenfolge|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Zeichenfolge|  
|BESCHREIBUNG|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Ansichten  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|VIEW_DEFINITION|Zeichenfolge|  
|CHECK_OPTION|Boolesch|  
|IS_UPDATABLE|Boolesch|  
|BESCHREIBUNG|Zeichenfolge|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indizes  
  
|Spaltenname|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Zeichenfolge|  
|TABLE_SCHEMA|Zeichenfolge|  
|TABLE_NAME|Zeichenfolge|  
|INDEX_CATALOG|Zeichenfolge|  
|INDEX_SCHEMA|Zeichenfolge|  
|INDEX_NAME|Zeichenfolge|  
|PRIMARY_KEY|Boolesch|  
|UNIQUE|Boolesch|  
|CLUSTERED|Boolesch|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolesch|  
|AUTO_UPDATE|Boolesch|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Zeichenfolge|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|Zeichenfolge|  
|INTEGRATED|Boolesch|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](ado-net-overview.md)
