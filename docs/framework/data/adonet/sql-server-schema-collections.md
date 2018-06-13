---
title: SQL Server-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
ms.openlocfilehash: 248e5f4caf47f09742358240fa43f46169f0b1e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361054"
---
# <a name="sql-server-schema-collections"></a>SQL Server-Schemaauflistungen
Der Microsoft .NET Framework-Datenanbieter für SQL Server unterstützt neben den allgemeinen Schemaauflistungen auch weitere Schemaauflistungen. Die Schemaauflistungen sind je nach verwendeter SQL Server-Version verschieden. Um die Liste der unterstützten schemaauflistungen zu ermitteln, rufen Sie die **GetSchema** -Methode ohne Argumente oder mit dem schemaauflistungsnamen "MetaDataCollections". Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.  
  
## <a name="databases"></a>Databases  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|database_name|Zeichenfolge|Name der Datenbank.|  
|DBID|Int16|Datenbank-ID.|  
|create_date|DateTime|Erstellungsdatum der Datenbank.|  
  
## <a name="foreign-keys"></a>ForeignKeys  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CONSTRAINT_CATALOG|Zeichenfolge|Katalog, zu dem die Einschränkung gehört.|  
|CONSTRAINT_SCHEMA|Zeichenfolge|Schema, das die Einschränkung enthält.|  
|CONSTRAINT_NAME|Zeichenfolge|Name.|  
|TABLE_CATALOG|Zeichenfolge|Tabellenname, zu dem diese Einschränkung gehört.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Tabelle enthält.|  
|TABLE_NAME|Zeichenfolge|Tabellenname|  
|CONSTRAINT_TYPE|Zeichenfolge|Art der Einschränkung. Nur "FOREIGN KEY" zulässig.|  
|IS_DEFERRABLE|Zeichenfolge|Gibt an, ob die Einschränkung verzögert werden kann. Gibt NO zurück.|  
|INITIALLY_DEFERRED|Zeichenfolge|Gibt an, ob die Einschränkung anfangs verzögert werden kann. Gibt NO zurück.|  
  
## <a name="indexes"></a>Indexes  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|constraint_catalog|Zeichenfolge|Katalog, zu dem dieser Index gehört.|  
|constraint_schema|Zeichenfolge|Schema, das den Index enthält.|  
|constraint_name|Zeichenfolge|Name des Indexes.|  
|table_catalog|Zeichenfolge|Tabellenname, dem der Index zugeordnet ist.|  
|table_schema|Zeichenfolge|Schema, das die Tabelle enthält, der der Index zugeordnet ist.|  
|table_name|Zeichenfolge|Tabellenname.|  
|index_name|Zeichenfolge|Name des Indexes.|  
  
### <a name="indexes-sql-server-2008"></a>Indexes (SQL Server 2008)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurden der Indexes-Schemaauflistung die folgenden Spalten hinzugefügt, um neue räumliche Typen, Dateistream und Spalten mit geringer Dichte unterstützen zu können. Diese Spalten werden in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|type_desc|Zeichenfolge|Der Index weist einen der folgenden Typen auf:<br /><br /> -HEAP<br />-CLUSTER<br />-NICHT GRUPPIERTE<br />-XML<br />-RÄUMLICHE|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|constraint_catalog|Zeichenfolge|Katalog, zu dem dieser Index gehört.|  
|constraint_schema|Zeichenfolge|Schema, das den Index enthält.|  
|constraint_name|Zeichenfolge|Name des Indexes.|  
|table_catalog|Zeichenfolge|Tabellenname, dem der Index zugeordnet ist.|  
|table_schema|Zeichenfolge|Schema, das die Tabelle enthält, der der Index zugeordnet ist.|  
|table_name|Zeichenfolge|Tabellenname.|  
|column_name|Zeichenfolge|Spaltenname, dem der Index zugeordnet ist.|  
|ordinal_position|Int32|Ordnungsposition der Spalte.|  
|KeyType|Byte|Der Objekttyp.|  
|index_name|Zeichenfolge|Name des Indexes.|  
  
## <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|Zeichenfolge|Spezifischer Name für den Katalog.|  
|SPECIFIC_SCHEMA|Zeichenfolge|Spezifischer Name des Schemas.|  
|SPECIFIC_NAME|Zeichenfolge|Spezifischer Name des Katalogs.|  
|ROUTINE_CATALOG|Zeichenfolge|Katalog, zu dem die gespeicherte Prozedur gehört.|  
|FÜR ROUTINE_SCHEMA|Zeichenfolge|Schema, das die gespeicherte Prozedur enthält.|  
|ROUTINE_NAME|Zeichenfolge|Name der gespeicherten Prozedur.|  
|ROUTINE_TYPE|Zeichenfolge|Gibt PROCEDURE für gespeicherte Prozeduren und FUNCTION für Funktionen zurück.|  
|CREATED|DateTime|Zeitpunkt der Erstellung der Prozedur.|  
|LAST_ALTERED|DateTime|Zeitpunkt der letzten Änderung der Prozedur.|  
  
## <a name="procedure-parameters"></a>ProcedureParameters  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|Zeichenfolge|Katalogname der Prozedur, für die dies einen Parameter darstellt.|  
|SPECIFIC_SCHEMA|Zeichenfolge|Schema, das die Prozedur enthält, zu der dieser Parameter gehört.|  
|SPECIFIC_NAME|Zeichenfolge|Name der Prozedur, zu der dieser Parameter gehört.|  
|ORDINAL_POSITION|Int32|Ordinalposition des Parameters, beginnend mit 1. Für den Rückgabewert einer Prozedur ist dies 0.|  
|PARAMETER_MODE|Zeichenfolge|Gibt bei einem Eingabeparameter IN zurück, bei einem Ausgabeparameter OUT und bei einem Eingabe-/Ausgabeparameter INOUT.|  
|IS_RESULT|Zeichenfolge|Gibt YES zurück, wenn das Ergebnis der Prozedur angegeben wird, die eine Funktion darstellt. Andernfalls wird NO zurückgegeben.|  
|AS_LOCATOR|Zeichenfolge|Gibt YES bei Deklaration als Locator zurück. Andernfalls wird NO zurückgegeben.|  
|PARAMETER_NAME|Zeichenfolge|Name des Parameters. NULL, wenn dies dem Rückgabewert einer Funktion entspricht.|  
|DATA_TYPE|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|Maximale Länge in Zeichen für binäre Datentypen oder Zeichendatentypen. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_OCTET_LENGTH|Int32|Maximale Länge in Byte für binäre Datentypen oder Zeichendatentypen. Andernfalls wird NULL zurückgegeben.|  
|COLLATION_CATALOG|Zeichenfolge|Katalogname der Sortierung des Parameters. Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|COLLATION_SCHEMA|Zeichenfolge|Gibt immer NULL zurück.|  
|COLLATION_NAME|Zeichenfolge|Name der Sortierung des Parameters. Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|CHARACTER_SET_CATALOG|Zeichenfolge|Katalogname des Zeichensatzes des Parameters. Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|Gibt immer NULL zurück.|  
|CHARACTER_SET_NAME|Zeichenfolge|Name des Zeichensatzes des Parameters. Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|NUMERIC_PRECISION|Byte|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION_RADIX|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_SCALE|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|DATETIME_PRECISION|Int16|Genauigkeit in Bruchteilen von Sekunden, wenn der Parametertyp datetime oder smalldatetime ist. Andernfalls wird NULL zurückgegeben.|  
|INTERVAL_TYPE|Zeichenfolge|NULL. Für die künftige Verwendung durch SQL Server reserviert.|  
|INTERVAL_PRECISION|Int16|NULL. Für die künftige Verwendung durch SQL Server reserviert.|  
  
## <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Zeichenfolge|Katalog der Tabelle.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Tabelle enthält.|  
|TABLE_NAME|Zeichenfolge|Tabellenname.|  
|TABLE_TYPE|Zeichenfolge|Tabellentyp. Kann VIEW oder BASE TABLE sein.|  
  
## <a name="columns"></a>Columns  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Zeichenfolge|Katalog der Tabelle.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Tabelle enthält.|  
|TABLE_NAME|Zeichenfolge|Tabellenname.|  
|COLUMN_NAME|Zeichenfolge|Spaltenname.|  
|ORDINAL_POSITION|Int32|Spalten-ID.|  
|COLUMN_DEFAULT|Zeichenfolge|Standardwert der Spalte|  
|IS_NULLABLE|Zeichenfolge|Fähigkeit der Spalte, NULL-Werte zuzulassen. Wenn diese Spalte NULL zulässt, gibt die Spalte YES zurück. Andernfalls wird NO zurückgegeben.|  
|DATA_TYPE|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|CHARACTER_MAXIMUM_LENGTH|Int32 – Sql8, Int16 – Sql7|Maximale Länge in Zeichen für binäre Daten, Zeichendaten oder Text- und Bilddaten. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_OCTET_LENGTH|Int32 – SQL8, Int16 – Sql7|Maximale Länge in Byte für binäre Daten, Zeichendaten oder Text- und Bilddaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION|Byte ohne Vorzeichen|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION_RADIX|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_SCALE|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|DATETIME_PRECISION|Int16|Untertypcode für datetime- und SQL-92-Intervalldatentypen. Bei anderen Datentypen wird NULL zurückgegeben.|  
|CHARACTER_SET_CATALOG|Zeichenfolge|Gibt "master" zurück, wodurch die Datenbank angegeben wird, in der der Zeichensatz enthalten ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|Gibt immer NULL zurück.|  
|CHARACTER_SET_NAME|Zeichenfolge|Gibt den eindeutigen Namen für den Zeichensatz zurück, wenn diese Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls wird NULL zurückgegeben.|  
|COLLATION_CATALOG|Zeichenfolge|Gibt master zurück, wodurch die Datenbank angegeben wird, in der die Sortierung definiert ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls ist diese Spalte NULL.|  
  
### <a name="columns-sql-server-2008"></a>Columns (SQL Server 2008)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurden der Columns-Schemaauflistung die folgenden Spalten hinzugefügt, um neue räumliche Typen, Dateistream und Spalten mit geringer Dichte unterstützen zu können. Diese Spalten werden in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|IS_FILESTREAM|Zeichenfolge|YES, wenn die Spalte über das FILESTREAM-Attribut verfügt.<br /><br /> NO, wenn die Spalte nicht über das FILESTREAM-Attribut verfügt.|  
|IS_SPARSE|Zeichenfolge|YES, wenn die Spalte eine Spalte mit geringer Dichte ist.<br /><br /> NO, wenn die Spalte keine Sparsespalte ist.|  
|IS_COLUMN_SET|Zeichenfolge|YES, wenn die Spalte eine Spaltensatzspalte ist.<br /><br /> NO, wenn die Spalte keine Spaltensatzspalte ist.|  
  
### <a name="allcolumns-sql-server-2008"></a>AllColumns (SQL Server 2008)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurde die AllColumns-Schemaauflistung hinzugefügt, um Spalten mit geringer Dichte unterstützen zu können. AllColumns wird in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  
  
 AllColumns hat die gleichen Einschränkungen und das resultierende DataTable-Schema wie die Columns-Schemaauflistung. Der einzige Unterschied besteht darin, dass AllColumns Spaltensatzspalten einschließt, die nicht in der Columns-Schemaauflistung enthalten sind. In der folgenden Liste werden diese Spalten beschrieben.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Zeichenfolge|Katalog der Tabelle.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Tabelle enthält.|  
|TABLE_NAME|Zeichenfolge|Tabellenname.|  
|COLUMN_NAME|Zeichenfolge|Spaltenname.|  
|ORDINAL_POSITION|Int32|Spalten-ID.|  
|COLUMN_DEFAULT|Zeichenfolge|Standardwert der Spalte|  
|IS_NULLABLE|Zeichenfolge|Fähigkeit der Spalte, NULL-Werte zuzulassen. Wenn diese Spalte NULL zulässt, gibt die Spalte YES zurück. Andernfalls wird NO zurückgegeben.|  
|DATA_TYPE|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|Maximale Länge in Zeichen für binäre Daten, Zeichendaten oder Text- und Bilddaten. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_OCTET_LENGTH|Int32|Maximale Länge in Byte für binäre Daten, Zeichendaten oder Text- und Bilddaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION|Byte ohne Vorzeichen|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION_RADIX|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_SCALE|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|DATETIME_PRECISION|Int16|Untertypcode für datetime- und SQL-92-Intervalldatentypen. Bei anderen Datentypen wird NULL zurückgegeben.|  
|CHARACTER_SET_CATALOG|Zeichenfolge|Gibt "master" zurück, wodurch die Datenbank angegeben wird, in der der Zeichensatz enthalten ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|Gibt immer NULL zurück.|  
|CHARACTER_SET_NAME|Zeichenfolge|Gibt den eindeutigen Namen für den Zeichensatz zurück, wenn diese Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls wird NULL zurückgegeben.|  
|COLLATION_CATALOG|Zeichenfolge|Gibt master zurück, wodurch die Datenbank angegeben wird, in der die Sortierung definiert ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls ist diese Spalte NULL.|  
|IS_FILESTREAM|Zeichenfolge|YES, wenn die Spalte über das FILESTREAM-Attribut verfügt.<br /><br /> NO, wenn die Spalte nicht über das FILESTREAM-Attribut verfügt.|  
|IS_SPARSE|Zeichenfolge|YES, wenn die Spalte eine Spalte mit geringer Dichte ist.<br /><br /> NO, wenn die Spalte keine Sparsespalte ist.|  
|IS_COLUMN_SET|Zeichenfolge|YES, wenn die Spalte eine Spaltensatzspalte ist.<br /><br /> NO, wenn die Spalte keine Spaltensatzspalte ist.|  
  
### <a name="columnsetcolumns-sql-server-2008"></a>ColumnSetColumns (SQL Server 2008)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurde die ColumnSetColumns-Schemaauflistung hinzugefügt, um Spalten mit geringer Dichte unterstützen zu können. ColumnSetColumns wird in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt. Die ColumnSetColumns-Schemaauflistung gibt das Schema für alle Spalten in einem Spaltensatz zurück. In der folgenden Liste werden diese Spalten beschrieben.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Zeichenfolge|Katalog der Tabelle.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Tabelle enthält.|  
|TABLE_NAME|Zeichenfolge|Tabellenname.|  
|COLUMN_NAME|Zeichenfolge|Spaltenname.|  
|ORDINAL_POSITION|Int32|Spalten-ID.|  
|COLUMN_DEFAULT|Zeichenfolge|Standardwert der Spalte|  
|IS_NULLABLE|Zeichenfolge|Fähigkeit der Spalte, NULL-Werte zuzulassen. Wenn diese Spalte NULL zulässt, gibt die Spalte YES zurück. Andernfalls wird NO zurückgegeben.|  
|DATA_TYPE|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|Maximale Länge in Zeichen für binäre Daten, Zeichendaten oder Text- und Bilddaten. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_OCTET_LENGTH|Int32|Maximale Länge in Byte für binäre Daten, Zeichendaten oder Text- und Bilddaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION|Byte ohne Vorzeichen|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_PRECISION_RADIX|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|NUMERIC_SCALE|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten. Andernfalls wird NULL zurückgegeben.|  
|DATETIME_PRECISION|Int16|Untertypcode für datetime- und SQL-92-Intervalldatentypen. Bei anderen Datentypen wird NULL zurückgegeben.|  
|CHARACTER_SET_CATALOG|Zeichenfolge|Gibt "master" zurück, wodurch die Datenbank angegeben wird, in der der Zeichensatz enthalten ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls wird NULL zurückgegeben.|  
|CHARACTER_SET_SCHEMA|Zeichenfolge|Gibt immer NULL zurück.|  
|CHARACTER_SET_NAME|Zeichenfolge|Gibt den eindeutigen Namen für den Zeichensatz zurück, wenn diese Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls wird NULL zurückgegeben.|  
|COLLATION_CATALOG|Zeichenfolge|Gibt master zurück, wodurch die Datenbank angegeben wird, in der die Sortierung definiert ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist. Andernfalls ist diese Spalte NULL.|  
|IS_FILESTREAM|Zeichenfolge|YES, wenn die Spalte über das FILESTREAM-Attribut verfügt.<br /><br /> NO, wenn die Spalte nicht über das FILESTREAM-Attribut verfügt.|  
|IS_SPARSE|Zeichenfolge|YES, wenn die Spalte eine Spalte mit geringer Dichte ist.<br /><br /> NO, wenn die Spalte keine Sparsespalte ist.|  
|IS_COLUMN_SET|Zeichenfolge|YES, wenn die Spalte eine Spaltensatzspalte ist.<br /><br /> NO, wenn die Spalte keine Spaltensatzspalte ist.|  
  
## <a name="users"></a>Benutzer  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|uid|Int16|Benutzer-ID, eindeutig innerhalb dieser Datenbank. 1 ist der Datenbankbesitzer.|  
|user_name|Zeichenfolge|Benutzername oder Gruppenname, eindeutig innerhalb dieser Datenbank.|  
|createdate|DateTime|Datum, an dem das Konto hinzugefügt wurde.|  
|updatedate|DateTime|Datum, an dem das Konto zuletzt geändert wurde.|  
  
## <a name="views"></a>Ansichten  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Zeichenfolge|Katalog der Ansicht.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Ansicht enthält.|  
|TABLE_NAME|Zeichenfolge|Ansichtsname.|  
|CHECK_OPTION|Zeichenfolge|Typ von WITH CHECK OPTION. Ist CASCADE, wenn die ursprüngliche Ansicht mit der WITH CHECK OPTION erstellt wurde. Andernfalls wird NONE zurückgegeben.|  
|IS_UPDATABLE|Zeichenfolge|Gibt an, ob die Ansicht aktualisiert werden kann. Gibt immer NO zurück.|  
  
## <a name="viewcolumns"></a>ViewColumns  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|VIEW_CATALOG|Zeichenfolge|Katalog der Ansicht.|  
|VIEW_SCHEMA|Zeichenfolge|Schema, das die Ansicht enthält.|  
|VIEW_NAME|Zeichenfolge|Ansichtsname.|  
|TABLE_CATALOG|Zeichenfolge|Katalog der Tabelle, die dieser Ansicht zugeordnet ist.|  
|TABLE_SCHEMA|Zeichenfolge|Schema, das die Tabelle enthält, die dieser Ansicht zugeordnet ist.|  
|TABLE_NAME|Zeichenfolge|Name der Tabelle, die der Ansicht zugeordnet ist. Basistabelle.|  
|COLUMN_NAME|Zeichenfolge|Spaltenname.|  
  
## <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|assembly_name|Zeichenfolge|Der Name der Datei für die Assembly.|  
|udt_name|Zeichenfolge|Der Klassenname für die Assembly.|  
|version_major|Objekt|Nummer der Hauptversion.|  
|version_minor|Objekt|Nummer der Nebenversion.|  
|version_build|Objekt|Buildnummer.|  
|version_revision|Objekt|Revisionsnummer.|  
|culture_info|Object|Die diesem UDT zugeordneten Kulturinformationen.|  
|public_key|Object|Der von dieser Assembly verwendete öffentliche Schlüssel.|  
|is_fixed_length|Boolesch|Gibt an, ob die Länge des Typs immer mit max_length übereinstimmt.|  
|max_length|Int16|Maximale Länge des Typs in Byte.|  
|Create_Date|DateTime|Datum, an dem die Assembly erstellt/registriert wurde.|  
|Permission_set_desc|Zeichenfolge|Der angezeigte Name für die Berechtigungen/Sicherheitsebene der Assembly.|  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
