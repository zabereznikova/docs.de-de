---
title: "SQL Server-Schemaauflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# SQL Server-Schemaauflistungen
Der Microsoft .NET Framework\-Datenanbieter für SQL Server unterstützt neben den allgemeinen Schemaauflistungen auch weitere Schemaauflistungen.  Die Schemaauflistungen sind je nach verwendeter SQL Server\-Version verschieden.  Um eine Liste der unterstützten Schemaauflistungen zu ermitteln, rufen Sie die **GetSchema**\-Methode entweder ohne Argumente oder mit dem Schemaauflistungsnamen "MetaDataCollections" auf.  Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.  
  
## Databases  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|database\_name|Zeichenfolge|Name der Datenbank.|  
|Dbid|Int16|Datenbank\-ID.|  
|create\_date|DateTime|Erstellungsdatum der Datenbank.|  
  
## ForeignKeys  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|constraint\_catalog|Zeichenfolge|Katalog, zu dem die Einschränkung gehört.|  
|constraint\_schema|Zeichenfolge|Schema, das die Einschränkung enthält.|  
|constraint\_name|Zeichenfolge|Name.|  
|table\_catalog|Zeichenfolge|Tabellenname, zu dem diese Einschränkung gehört.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält.|  
|table\_name|Zeichenfolge|Tabellenname|  
|constraint\_type|Zeichenfolge|Art der Einschränkung.  Nur "FOREIGN KEY" zulässig.|  
|is\_deferrable|Zeichenfolge|Gibt an, ob die Einschränkung verzögert werden kann.  Gibt NO zurück.|  
|initially\_deferred|Zeichenfolge|Gibt an, ob die Einschränkung anfangs verzögert werden kann.  Gibt NO zurück.|  
  
## Indexes  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|constraint\_catalog|Zeichenfolge|Katalog, zu dem dieser Index gehört.|  
|constraint\_schema|Zeichenfolge|Schema, das den Index enthält.|  
|constraint\_name|Zeichenfolge|Name des Indexes.|  
|table\_catalog|Zeichenfolge|Tabellenname, dem der Index zugeordnet ist.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält, der der Index zugeordnet ist.|  
|table\_name|Zeichenfolge|Tabellenname.|  
  
### Indexes \(SQL Server 2008\)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurden der Indexes\-Schemaauflistung die folgenden Spalten hinzugefügt, um neue räumliche Typen, Dateistream und Spalten mit geringer Dichte unterstützen zu können.  Diese Spalten werden in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|type\_desc|Zeichenfolge|Der Index weist einen der folgenden Typen auf:<br /><br /> -   HEAP<br />-   CLUSTERED<br />-   NONCLUSTERED<br />-   XML<br />-   SPATIAL|  
  
## IndexColumns  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|constraint\_catalog|Zeichenfolge|Katalog, zu dem dieser Index gehört.|  
|constraint\_schema|Zeichenfolge|Schema, das den Index enthält.|  
|constraint\_name|Zeichenfolge|Name des Indexes.|  
|table\_catalog|Zeichenfolge|Tabellenname, dem der Index zugeordnet ist.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält, der der Index zugeordnet ist.|  
|table\_name|Zeichenfolge|Tabellenname.|  
|column\_name|Zeichenfolge|Spaltenname, dem der Index zugeordnet ist.|  
|ordinal\_position|Int32|Ordnungsposition der Spalte.|  
|KeyType|UInt16|Der Objekttyp.|  
  
## Verfahren  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|specific\_catalog|Zeichenfolge|Spezifischer Name für den Katalog.|  
|specific\_schema|Zeichenfolge|Spezifischer Name des Schemas.|  
|specific\_name|Zeichenfolge|Spezifischer Name des Katalogs.|  
|routine\_catalog|Zeichenfolge|Katalog, zu dem die gespeicherte Prozedur gehört.|  
|routine\_schema|Zeichenfolge|Schema, das die gespeicherte Prozedur enthält.|  
|routine\_name|Zeichenfolge|Name der gespeicherten Prozedur.|  
|routine\_type|Zeichenfolge|Gibt PROCEDURE für gespeicherte Prozeduren und FUNCTION für Funktionen zurück.|  
|created|DateTime|Zeitpunkt der Erstellung der Prozedur.|  
|last\_altered|DateTime|Zeitpunkt der letzten Änderung der Prozedur.|  
  
## ProcedureParameters  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|specific\_catalog|Zeichenfolge|Katalogname der Prozedur, für die dies einen Parameter darstellt.|  
|specific\_schema|Zeichenfolge|Schema, das die Prozedur enthält, zu der dieser Parameter gehört.|  
|specific\_name|Zeichenfolge|Name der Prozedur, zu der dieser Parameter gehört.|  
|ordinal\_position|Int16|Ordinalposition des Parameters, beginnend mit 1.  Für den Rückgabewert einer Prozedur ist dies 0.|  
|parameter\_mode|Zeichenfolge|Gibt bei einem Eingabeparameter IN zurück, bei einem Ausgabeparameter OUT und bei einem Eingabe\-\/Ausgabeparameter INOUT.|  
|is\_result|Zeichenfolge|Gibt YES zurück, wenn das Ergebnis der Prozedur angegeben wird, die eine Funktion darstellt.  Andernfalls wird NO zurückgegeben.|  
|as\_locator|Zeichenfolge|Gibt YES bei Deklaration als Locator zurück.  Andernfalls wird NO zurückgegeben.|  
|parameter\_name|Zeichenfolge|Name des Parameters.  NULL, wenn dies dem Rückgabewert einer Funktion entspricht.|  
|data\_type|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|character\_maximum\_length|Int32|Maximale Länge in Zeichen für binäre Datentypen oder Zeichendatentypen.  Andernfalls wird NULL zurückgegeben.|  
|character\_octet\_length|Int32|Maximale Länge in Byte für binäre Datentypen oder Zeichendatentypen.  Andernfalls wird NULL zurückgegeben.|  
|collation\_catalog|Zeichenfolge|Katalogname der Sortierung des Parameters.  Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|collation\_schema|Zeichenfolge|Gibt immer NULL zurück.|  
|collation\_name|Zeichenfolge|Name der Sortierung des Parameters.  Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|character\_set\_catalog|Zeichenfolge|Katalogname des Zeichensatzes des Parameters.  Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|character\_set\_schema|Zeichenfolge|Gibt immer NULL zurück.|  
|character\_set\_name|Zeichenfolge|Name des Zeichensatzes des Parameters.  Wenn dieser keinem der Zeichentypen entspricht, wird NULL zurückgegeben.|  
|numeric\_precision|Byte|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision\_radix|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_scale|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|datetime\_precision|Int16|Genauigkeit in Bruchteilen von Sekunden, wenn der Parametertyp **datetime** oder **smalldatetime** ist.  Andernfalls wird NULL zurückgegeben.|  
|interval\_type|Zeichenfolge|NULL.  Für die künftige Verwendung durch SQL Server reserviert.|  
|interval\_precision|Int16|NULL.  Für die künftige Verwendung durch SQL Server reserviert.|  
  
## Tabellen  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|table\_catalog|Zeichenfolge|Katalog der Tabelle.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält.|  
|table\_name|Zeichenfolge|Tabellenname.|  
|table\_type|Zeichenfolge|Tabellentyp.  Kann VIEW oder BASE TABLE sein.|  
  
## Columns  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|table\_catalog|Zeichenfolge|Katalog der Tabelle.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält.|  
|table\_name|Zeichenfolge|Tabellenname.|  
|column\_name|Zeichenfolge|Spaltenname.|  
|ordinal\_position|Int16|Spalten\-ID.|  
|column\_default|Zeichenfolge|Standardwert der Spalte|  
|is\_nullable|Zeichenfolge|Fähigkeit der Spalte, NULL\-Werte zuzulassen.  Wenn diese Spalte NULL zulässt, gibt die Spalte YES zurück.  Andernfalls wird NO zurückgegeben.|  
|data\_type|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|character\_maximum\_length|Int32 – Sql8, Int16 – Sql7|Maximale Länge in Zeichen für binäre Daten, Zeichendaten oder Text\- und Bilddaten.  Andernfalls wird NULL zurückgegeben.|  
|character\_octet\_length|Int32 – SQL8, Int16 – Sql7|Maximale Länge in Byte für binäre Daten, Zeichendaten oder Text\- und Bilddaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision|Byte ohne Vorzeichen|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision\_radix|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_scale|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|datetime\_precision|Int16|Untertypcode für datetime\- und SQL\-92\-Intervalldatentypen.  Bei anderen Datentypen wird NULL zurückgegeben.|  
|character\_set\_catalog|Zeichenfolge|Gibt "master" zurück, wodurch die Datenbank angegeben wird, in der der Zeichensatz enthalten ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls wird NULL zurückgegeben.|  
|character\_set\_schema|Zeichenfolge|Gibt immer NULL zurück.|  
|character\_set\_name|Zeichenfolge|Gibt den eindeutigen Namen für den Zeichensatz zurück, wenn diese Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls wird NULL zurückgegeben.|  
|collation\_catalog|Zeichenfolge|Gibt **master** zurück, wodurch die Datenbank angegeben wird, in der die Sortierung definiert ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls ist diese Spalte NULL.|  
  
### Columns \(SQL Server 2008\)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurden der Columns\-Schemaauflistung die folgenden Spalten hinzugefügt, um neue räumliche Typen, Dateistream und Spalten mit geringer Dichte unterstützen zu können.  Diese Spalten werden in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|IS\_FILESTREAM|Zeichenfolge|YES, wenn die Spalte über das FILESTREAM\-Attribut verfügt.<br /><br /> NO, wenn die Spalte nicht über das FILESTREAM\-Attribut verfügt.|  
|IS\_SPARSE|Zeichenfolge|YES, wenn die Spalte eine Spalte mit geringer Dichte ist.<br /><br /> NO, wenn die Spalte keine Spalte mit geringer Dichte ist.|  
|IS\_COLUMN\_SET|Zeichenfolge|YES, wenn die Spalte eine Spaltensatzspalte ist.<br /><br /> NO, wenn die Spalte keine Spaltensatzspalte ist.|  
  
### AllColumns \(SQL Server 2008\)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurde die AllColumns\-Schemaauflistung hinzugefügt, um Spalten mit geringer Dichte unterstützen zu können.  AllColumns wird in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  
  
 AllColumns hat die gleichen Einschränkungen und das resultierende DataTable\-Schema wie die Columns\-Schemaauflistung.  Der einzige Unterschied besteht darin, dass AllColumns Spaltensatzspalten einschließt, die nicht in der Columns\-Schemaauflistung enthalten sind.  In der folgenden Liste werden diese Spalten beschrieben.  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|table\_catalog|Zeichenfolge|Katalog der Tabelle.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält.|  
|table\_name|Zeichenfolge|Tabellenname.|  
|column\_name|Zeichenfolge|Spaltenname.|  
|ordinal\_position|Int16|Spalten\-ID.|  
|column\_default|Zeichenfolge|Standardwert der Spalte|  
|is\_nullable|Zeichenfolge|Fähigkeit der Spalte, NULL\-Werte zuzulassen.  Wenn diese Spalte NULL zulässt, gibt die Spalte YES zurück.  Andernfalls wird NO zurückgegeben.|  
|data\_type|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|character\_maximum\_length|Int32|Maximale Länge in Zeichen für binäre Daten, Zeichendaten oder Text\- und Bilddaten.  Andernfalls wird NULL zurückgegeben.|  
|character\_octet\_length|Int32|Maximale Länge in Byte für binäre Daten, Zeichendaten oder Text\- und Bilddaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision|Byte ohne Vorzeichen|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision\_radix|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_scale|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|datetime\_precision|Int16|Untertypcode für datetime\- und SQL\-92\-Intervalldatentypen.  Bei anderen Datentypen wird NULL zurückgegeben.|  
|character\_set\_catalog|Zeichenfolge|Gibt "master" zurück, wodurch die Datenbank angegeben wird, in der der Zeichensatz enthalten ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls wird NULL zurückgegeben.|  
|character\_set\_schema|Zeichenfolge|Gibt immer NULL zurück.|  
|character\_set\_name|Zeichenfolge|Gibt den eindeutigen Namen für den Zeichensatz zurück, wenn diese Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls wird NULL zurückgegeben.|  
|collation\_catalog|Zeichenfolge|Gibt **master** zurück, wodurch die Datenbank angegeben wird, in der die Sortierung definiert ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls ist diese Spalte NULL.|  
|IS\_FILESTREAM|Zeichenfolge|YES, wenn die Spalte über das FILESTREAM\-Attribut verfügt.<br /><br /> NO, wenn die Spalte nicht über das FILESTREAM\-Attribut verfügt.|  
|IS\_SPARSE|Zeichenfolge|YES, wenn die Spalte eine Spalte mit geringer Dichte ist.<br /><br /> NO, wenn die Spalte keine Spalte mit geringer Dichte ist.|  
|IS\_COLUMN\_SET|Zeichenfolge|YES, wenn die Spalte eine Spaltensatzspalte ist.<br /><br /> NO, wenn die Spalte keine Spaltensatzspalte ist.|  
  
### ColumnSetColumns \(SQL Server 2008\)  
 Ab .NET Framework, Version 3.5 SP1, und SQL Server 2008 wurde die ColumnSetColumns\-Schemaauflistung hinzugefügt, um Spalten mit geringer Dichte unterstützen zu können.  ColumnSetColumns wird in früheren Versionen von .NET Framework und von SQL Server nicht unterstützt.  Die ColumnSetColumns\-Schemaauflistung gibt das Schema für alle Spalten in einem Spaltensatz zurück.  In der folgenden Liste werden diese Spalten beschrieben.  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|table\_catalog|Zeichenfolge|Katalog der Tabelle.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält.|  
|table\_name|Zeichenfolge|Tabellenname.|  
|column\_name|Zeichenfolge|Spaltenname.|  
|ordinal\_position|Int16|Spalten\-ID.|  
|column\_default|Zeichenfolge|Standardwert der Spalte|  
|is\_nullable|Zeichenfolge|Fähigkeit der Spalte, NULL\-Werte zuzulassen.  Wenn diese Spalte NULL zulässt, gibt die Spalte YES zurück.  Andernfalls wird NO zurückgegeben.|  
|data\_type|Zeichenfolge|Vom System bereitgestellter Datentyp.|  
|character\_maximum\_length|Int32|Maximale Länge in Zeichen für binäre Daten, Zeichendaten oder Text\- und Bilddaten.  Andernfalls wird NULL zurückgegeben.|  
|character\_octet\_length|Int32|Maximale Länge in Byte für binäre Daten, Zeichendaten oder Text\- und Bilddaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision|Byte ohne Vorzeichen|Genauigkeit von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_precision\_radix|Int16|Genauigkeitsbasis von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|numeric\_scale|Int32|Skala von ungefähren numerischen Daten, genauen numerischen Daten, Ganzzahldaten und Währungsdaten.  Andernfalls wird NULL zurückgegeben.|  
|datetime\_precision|Int16|Untertypcode für datetime\- und SQL\-92\-Intervalldatentypen.  Bei anderen Datentypen wird NULL zurückgegeben.|  
|character\_set\_catalog|Zeichenfolge|Gibt "master" zurück, wodurch die Datenbank angegeben wird, in der der Zeichensatz enthalten ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls wird NULL zurückgegeben.|  
|character\_set\_schema|Zeichenfolge|Gibt immer NULL zurück.|  
|character\_set\_name|Zeichenfolge|Gibt den eindeutigen Namen für den Zeichensatz zurück, wenn diese Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls wird NULL zurückgegeben.|  
|collation\_catalog|Zeichenfolge|Gibt **master** zurück, wodurch die Datenbank angegeben wird, in der die Sortierung definiert ist, wenn die Spalte den Typ Zeichendaten oder Textdaten aufweist.  Andernfalls ist diese Spalte NULL.|  
|IS\_FILESTREAM|Zeichenfolge|YES, wenn die Spalte über das FILESTREAM\-Attribut verfügt.<br /><br /> NO, wenn die Spalte nicht über das FILESTREAM\-Attribut verfügt.|  
|IS\_SPARSE|Zeichenfolge|YES, wenn die Spalte eine Spalte mit geringer Dichte ist.<br /><br /> NO, wenn die Spalte keine Spalte mit geringer Dichte ist.|  
|IS\_COLUMN\_SET|Zeichenfolge|YES, wenn die Spalte eine Spaltensatzspalte ist.<br /><br /> NO, wenn die Spalte keine Spaltensatzspalte ist.|  
  
## Benutzer  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|uid|Int16|Benutzer\-ID, eindeutig innerhalb dieser Datenbank.  1 ist der Datenbankbesitzer.|  
|Name|Zeichenfolge|Benutzername oder Gruppenname, eindeutig innerhalb dieser Datenbank.|  
|createdate|DateTime|Datum, an dem das Konto hinzugefügt wurde.|  
|updatedate|DateTime|Datum, an dem das Konto zuletzt geändert wurde.|  
  
## Ansichten  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|table\_catalog|Zeichenfolge|Katalog der Ansicht.|  
|table\_schema|Zeichenfolge|Schema, das die Ansicht enthält.|  
|table\_name|Zeichenfolge|Ansichtsname.|  
|check\_option|Zeichenfolge|Typ von WITH CHECK OPTION.  Ist CASCADE, wenn die ursprüngliche Ansicht mit der WITH CHECK OPTION erstellt wurde.  Andernfalls wird NONE zurückgegeben.|  
|is\_updatable|Zeichenfolge|Gibt an, ob die Ansicht aktualisiert werden kann.  Gibt immer NO zurück.|  
  
## ViewColumns  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|view\_catalog|Zeichenfolge|Katalog der Ansicht.|  
|view\_schema|Zeichenfolge|Schema, das die Ansicht enthält.|  
|view\_name|Zeichenfolge|Ansichtsname.|  
|table\_catalog|Zeichenfolge|Katalog der Tabelle, die dieser Ansicht zugeordnet ist.|  
|table\_schema|Zeichenfolge|Schema, das die Tabelle enthält, die dieser Ansicht zugeordnet ist.|  
|table\_name|Zeichenfolge|Name der Tabelle, die der Ansicht zugeordnet ist.  Basistabelle.|  
|column\_name|Zeichenfolge|Spaltenname.|  
  
## UserDefinedTypes  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|assembly\_name|Zeichenfolge|Der Name der Datei für die Assembly.|  
|UDT\_name|Zeichenfolge|Der Klassenname für die Assembly.|  
|version\_major|Objekt|Nummer der Hauptversion.|  
|version\_minor|Objekt|Nummer der Nebenversion.|  
|version\_build|Objekt|Buildnummer.|  
|version\_revision|Objekt|Revisionsnummer.|  
|Culture\_info|Objekt|Die diesem UDT zugeordneten Kulturinformationen.|  
|Public\_key|Objekt|Der von dieser Assembly verwendete öffentliche Schlüssel.|  
|Is\_fixed\_length|Boolean|Gibt an, ob die Länge des Typs immer mit max\_length übereinstimmt.|  
|max\_length|Int16|Maximale Länge des Typs in Byte.|  
|permission\_set\_desc|Zeichenfolge|Der angezeigte Name für die Berechtigungen\/Sicherheitsebene der Assembly.|  
|create\_date|DateTime|Datum, an dem die Assembly erstellt\/registriert wurde.|  
  
## Siehe auch  
 [Abrufen von Schemainformationen aus einer Datenbank](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)