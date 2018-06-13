---
title: Allgemeine Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 50127ced-2ac8-4d7a-9cd1-5c98c655ff03
ms.openlocfilehash: fc8b581a127fbef0f32cdee53eaa62d241e4ae31
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759308"
---
# <a name="common-schema-collections"></a>Allgemeine Schemaauflistungen
Die allgemeine Schemaauflistung enthält die von den einzelnen verwalteten Anbietern für .NET Framework implementierten Schemaauflistungen. Sie können einen verwalteten .NET Framework-Datenanbieter, um die Liste der unterstützten schemaauflistungen durch Aufrufen von Abfragen die **GetSchema** -Methode ohne Argumente oder mit dem schemaauflistungsnamen "MetaDataCollections". Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben. In diesen Auflistungen werden alle erforderlichen Spalten beschrieben. Anbieter können ggf. zusätzliche Spalten hinzufügen. So fügen beispielsweise `SqlClient` und `OracleClient` der Auflistung der Einschränkungen "ParameterName" hinzu.  
  
 Wenn ein Anbieter den Wert einer erforderlichen Spalte nicht ermitteln kann, wird NULL zurückgegeben.  
  
 Weitere Informationen zum Verwenden der **GetSchema** Methoden, finden Sie unter ["GetSchema" und Schemaauflistungen](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md).  
  
## <a name="metadatacollections"></a>MetaDataCollections  
 Mithilfe dieser Schemaauflistung werden Informationen zu allen Schemaauflistungen verfügbar gemacht, die von dem verwalteten Anbieter für .NET Framework unterstützt werden, über den derzeit eine Verbindung mit der Datenbank hergestellt wird.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CollectionName|Zeichenfolge|Der Name der Auflistung Übergabe an die **GetSchema** Methode zum Zurückgeben der Auflistung.|  
|NumberOfRestrictions|int|Die Anzahl der Einschränkungen, die für die Auflistung angegeben werden können.|  
|NumberOfIdentifierParts|int|Die Anzahl der Bestandteile im zusammengesetzten Bezeichner/Datenbank-Objektnamen. In SQL Server entspricht dies beispielsweise 3 für Tabellen und 4 für Spalten. In Oracle entspricht dies 2 für Tabellen und 3 für Spalten.|  
  
## <a name="datasourceinformation"></a>DataSourceInformation  
 Mithilfe dieser Schemaauflistung werden Informationen zu der Datenquelle verfügbar gemacht, mit der der verwaltete Anbieter für .NET Framework derzeit verbunden ist.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CompositeIdentifierSeparatorPattern|string|Der reguläre Ausdruck, der den Trennzeichen zum Trennen der Bestandteile in einem zusammengesetzten Bezeichner entspricht. Z. B. "\\." (für SQLServer) oder "@&#124;\\." (für Oracle).<br /><br /> Ein zusammengesetzter Bezeichner wird in der Regel, wie z. B. für einen Datenbankobjektnamen verwendet wird: "Pubs.dbo.Authors" oder pubs@dbo.authors.<br /><br /> Verwenden Sie für SQL Server, den regulären Ausdruck "\\.". Verwenden Sie für OracleClient "@&#124;\\.".<br /><br /> Verwenden Sie Catalog_name_separator für ODBC.<br /><br /> Verwenden Sie DBLITERAL_CATALOG_SEPARATOR oder DBLITERAL_SCHEMA_SEPARATOR für OLE DB.|  
|DataSourceProductName|string|Der Name des Produkts, auf das durch den Anbieter zugegriffen wird, z. B. "Oracle" oder "SQLServer".|  
|DataSourceProductVersion|string|Gibt die Version des Produkts, auf das durch den Anbieter zugegriffen wird, im systemeigenen Format der Datenquellen an, nicht im Microsoft-Format.<br /><br /> In einigen Fällen sind die Werte von "DataSourceProductVersion" und "DataSourceProductVersionNormalized" identisch. Bei OLE DB und ODBC sind diese Werte immer identisch, da sie in der zugrunde liegenden systemeigenen API demselben Funktionsaufruf zugeordnet sind.|  
|DataSourceProductVersionNormalized|string|Eine normalisierte Version der Datenquelle, damit sie mithilfe von `String.Compare()` verglichen werden kann. Das Format ist für alle Versionen des Anbieters konsistent, um zu verhindern, dass Version 10 zwischen Version 1 und Version 2 einsortiert wird.<br /><br /> Beispielsweise verwendet der Oracle-Anbieter ein Format von "nn.nn.nn.nn.nn" für die normalisierte Version, wodurch eine Oracle 8i-Datenquelle "08.01.07.04.01" zurück. SQL Server verwendet das typische Format von Microsoft "nn.nn.nnnn".<br /><br /> In einigen Fällen sind die Werte von DataSourceProductVersion und DataSourceProductVersionNormalized identisch. Bei OLE DB und ODBC sind diese Werte immer identisch, da sie in der zugrunde liegenden systemeigenen API demselben Funktionsaufruf zugeordnet sind.|  
|GroupByBehavior|<xref:System.Data.Common.GroupByBehavior>|Gibt die Beziehung zwischen den Spalten in einer GROUP BY-Klausel und den nicht zusammengesetzten Spalten in der Auswahlliste an.|  
|IdentifierPattern|string|Ein regulärer Ausdruck, der einem Bezeichner entspricht und über einen Wert verfügt, der den Bezeichner darstellt. Beispiel: "[A-Za-z0-9_#$]".|  
|IdentifierCase|<xref:System.Data.Common.IdentifierCase>|Gibt an, ob die Groß- und Kleinschreibung bei nicht in Anführungszeichen stehenden Bezeichnern berücksichtigt werden soll.|  
|OrderByColumnsInSelect|bool|Gibt an, ob Spalten in einer ORDER BY-Klausel in der Auswahlliste vorhanden sein müssen. Der Wert "true" gibt an, dass die Spalten in der Auswahlliste vorhanden sein müssen. Der Wert "false" gibt an, dass sie nicht in der Auswahlliste vorhanden sein müssen.|  
|ParameterMarkerFormat|string|Eine Formatzeichenfolge, die die Formatierung des Parameters darstellt.<br /><br /> Wenn benannte Parameter von der Datenquelle unterstützt werden, muss sich der erste Platzhalter in dieser Zeichenfolge an der Stelle befinden, an der der Parametername formatiert wird.<br /><br /> Angenommen, wenn die Datenquelle erwartet, dass Parameter benannt werden und mit dem Präfix ein ":" wäre dies ":{0}". Bei der Formatierung dieses Beispiels mit dem Parameternamen "p1" lautet die resultierende Zeichenfolge also ":p1".<br /><br /> Wenn die Datenquelle erwartet, dass die Parameter als Präfix das "@", aber die Namen bereits enthalten sind, wäre dies "{0}", und das Ergebnis der Formatierung eines Parameters mit dem Namen "@p1"wäre einfach"@p1".<br /><br /> Für Datenquellen, die nicht benannte Parameter erwarten und erwarten, dass die Verwendung der "?" Zeichen, kann die Formatzeichenfolge einfach als angegeben werden '?', würde die den Parameternamen ignorieren. Für OLE DB wird "?" zurückgegeben.|  
|ParameterMarkerPattern|string|Ein regulärer Ausdruck, der einer Parametermarkierung entspricht. Er verfügt (sofern vorhanden) über einen Wert, der dem Parameternamen entspricht.<br /><br /> Wenn beispielsweise benannte Parameter mit einem vorangestellten "@" unterstützt werden, das in den Parameternamen eingeschlossen wird, lautet die Zeichenfolge "(@[A-Za-z0-9_$#]*)".<br /><br /> Jedoch wenn benannte Parameter unterstützt werden, mit einer ":" wie das vorangestellten Zeichen, und es ist nicht Teil des Parameternamens, wäre dies: ": ([A-Za-z0-9_$ #]\*)".<br /><br /> Wenn die Datenquelle keine benannten Parameter unterstützt, lautet die Zeichenfolge einfach "?".|  
|ParameterNameMaxLength|int|Die maximale Länge eines Parameternamens in Zeichen. In Visual Studio werden im Falle der Unterstützung von Parameternamen 30 Zeichen als Mindestwert für die maximale Länge erwartet.<br /><br /> Wenn benannte Parameter von der Datenquelle nicht unterstützt werden, gibt diese Eigenschaft Null (0) zurück.|  
|ParameterNamePattern|string|Ein regulärer Ausdruck, der den gültigen Parameternamen entspricht. Je nach Datenquelle sind die Regeln bezüglich der für Parameternamen zulässigen Zeichen verschieden.<br /><br /> In Visual Studio wird im Falle der Unterstützung von Parameternamen erwartet, dass die Zeichen "\p{Lu}\p{Ll}\p{Lt}\p{Lm}\p{Lo}\p{Nl}\p{Nd}" die in jedem Fall unterstützte Gruppe von für Parameternamen gültigen Zeichen darstellen.|  
|QuotedIdentifierPattern|string|Ein regulärer Ausdruck, der einem Bezeichner in Anführungszeichen entspricht und über einen Wert verfügt, der den Bezeichner ohne Anführungszeichen darstellt. Beispielsweise, wenn die Datenquelle doppelte Anführungszeichen Bezeichner in Anführungszeichen verwendet, wäre dies: "(([^\\"]&#124;\\"\\") *) ".|  
|QuotedIdentifierCase|<xref:System.Data.Common.IdentifierCase>|Gibt an, ob die Groß- und Kleinschreibung bei Bezeichnern in Anführungszeichen berücksichtigt werden muss.|  
|StatementSeparatorPattern|string|Ein regulärer Ausdruck, der dem Trennzeichen für Anweisungen entspricht.|  
|StringLiteralPattern|string|Ein regulärer Ausdruck, der einem Zeichenfolgenliteral entspricht und über einen Wert verfügt, der das Literal darstellt. Beispielsweise, wenn die Datenquelle einfache Anführungszeichen verwendet, um Zeichenfolgen zu identifizieren, wäre dies: "('([^']&#124;'') *") ""|  
|SupportedJoinOperators|<xref:System.Data.Common.SupportedJoinOperators>|Gibt an, welche SQL-Joinanweisungen von der Datenquelle unterstützt werden.|  
  
## <a name="datatypes"></a>DataTypes  
 Mithilfe dieser Schemaauflistung werden Informationen zu den Datentypen verfügbar gemacht, die von der Datenbank unterstützt werden, mit der der verwaltete Anbieter für .NET Framework derzeit verbunden ist.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TypeName|string|Der anbieterspezifische Datentypname.|  
|ProviderDbType|int|Der anbieterspezifische Typwert, der zum Angeben eines Parametertyps verwendet werden soll. Beispiel: SqlDbType.Money oder OracleType.Blob.|  
|ColumnSize|long|Die Länge einer nicht numerischen Spalte oder eines nicht numerischen Parameters bezieht sich entweder auf die maximale oder auf die für diesen Typ vom Anbieter definierte Länge.<br /><br /> Bei Zeichendaten ist dies die maximale oder definierte Länge in Einheiten, entsprechend der Definition in der Datenquelle. In Oracle wird eine Länge und anschließend die tatsächliche Speichergröße für einige Zeichendatentypen angegeben. Dadurch wird für Oracle nur die Länge in Einheiten definiert.<br /><br /> Bei Datum/Uhrzeit-Datentypen ist dies die Länge der Zeichenfolgendarstellung (dabei wird von der maximal zulässigen Genauigkeit der Sekundenbruchteil-Komponente ausgegangen).<br /><br /> Wenn es sich um einen numerischen Datentyp handelt, ist dies die obere Grenze der maximalen Genauigkeit des Datentyps.|  
|CreateFormat|string|Formatzeichenfolge, die darstellt, wie diese Spalte einer Datendefinitionsanweisung (z. B. CREATE TABLE) hinzugefügt wird. Jedes Element im CreateParameter-Array muss durch eine "Parametermarkierung" in der Formatzeichenfolge dargestellt werden.<br /><br /> Für den SQL-Datentyp DECIMAL ist eine Angabe zur Genauigkeit und zur Dezimalstellenanzahl erforderlich. In diesem Fall wäre die Formatzeichenfolge "DECIMAL ({0},{1})".|  
|CreateParameters|string|Die Erstellungsparameter, die beim Erstellen einer Spalte dieses Datentyps angegeben werden müssen. Die Erstellungsparameter sind in der Zeichenfolge durch ein Komma getrennt in der Reihenfolge aufgelistet, in der sie bereitgestellt werden sollen.<br /><br /> Für den SQL-Datentyp DECIMAL ist eine Angabe zur Genauigkeit und zur Dezimalstellenanzahl erforderlich. In diesem Fall müssen die Erstellungsparameter die Zeichenfolge "Genauigkeit, Dezimalstellenanzahl" enthalten.<br /><br /> Der Wert der CreateFormat-Spalte möglicherweise in einem Textbefehl zum Erstellen einer DECIMAL-Spalteninhalts mit einer Genauigkeit von 10 und 2 Dezimalstellen, Dezimal ({0},{1}) "und die vollständige Typspezifikation wäre dann DECIMAL(10,2).|  
|DataType|string|Der Name des .NET Framework-Typs des Datentyps.|  
|IsAutoincrementable|bool|true – Die Werte dieses Datentyps können automatisch erhöht werden.<br /><br /> false – Die Werte dieses Datentyps können nicht automatisch erhöht werden.<br /><br /> Beachten Sie, dass auf diese Weise lediglich angegeben wird, ob eine Spalte dieses Datentyps automatisch erhöht werden kann, und nicht, dass alle Spalten dieses Typs automatisch erhöht werden.|  
|IsBestMatch|bool|true – Der Datentyp stellt die höchste Übereinstimmung zwischen allen Datentypen im Datenspeicher und dem durch den Wert in der DataType-Spalte angegebenen .NET Framework-Datentyp dar.<br /><br /> false – Der Datentyp stellt nicht die höchste Übereinstimmung dar.<br /><br /> Für jede Gruppe von Zeilen, in der der Wert der DataType-Spalte derselbe ist, wird die IsBestMatch-Spalte nur in einer Zeile auf "true" festgelegt.|  
|IsCaseSensitive|bool|true – Bei dem Datentyp handelt es sich um einen Zeichentyp, und die Groß- und Kleinschreibung muss berücksichtigt werden.<br /><br /> true – Bei dem Datentyp handelt es sich nicht um einen Zeichentyp, und die Groß- und Kleinschreibung muss nicht berücksichtigt werden.|  
|IsFixedLength|bool|true – Die von der DLL (Data Definition Language) erstellten Spalten dieses Datentyps weisen eine feste Länge auf.<br /><br /> false – Die von der DLL (Data Definition Language) erstellten Spalten dieses Datentyps weisen eine variable Länge auf.<br /><br /> DBNull.Value – Es ist nicht bekannt, ob dieses Feld vom Anbieter einer Spalte mit fester oder variabler Länge zugeordnet wird.|  
|IsFixedPrecisionScale|bool|true – Der Datentyp verfügt über eine feste Genauigkeit und Dezimalstellenanzahl.<br /><br /> false – Der Datentyp verfügt nicht über eine feste Genauigkeit und Dezimalstellenanzahl.|  
|IsLong|bool|true – Der Datentyp enthält sehr lange Daten. Die Definition hierfür ist anbieterspezifisch.<br /><br /> false – Der Datentyp enthält keine sehr langen Daten.|  
|IsNullable|bool|true – Der Datentyp lässt NULL-Werte zu.<br /><br /> false – Der Datentyp lässt keine NULL-Werte zu.<br /><br /> DBNull.Value – Es ist nicht bekannt, ob der Datentyp NULL-Werte zulässt.|  
|IsSearchable|bool|true – Der Datentyp kann in WHERE-Klauseln mit beliebigen Operatoren außer dem LIKE-Prädikat verwendet werden.<br /><br /> false – Der Datentyp kann nicht in WHERE-Klauseln mit beliebigen Operatoren außer dem LIKE-Prädikat verwendet werden.|  
|IsSearchableWithLike|bool|true – Der Datentyp kann mit dem LIKE-Prädikat verwendet werden.<br /><br /> false – Der Datentyp kann nicht mit dem LIKE-Prädikat verwendet werden.|  
|IsUnsigned|bool|true – Der Datentyp hat kein Vorzeichen.<br /><br /> false – Der Datentyp hat ein Vorzeichen.<br /><br /> DBNull.Value – Nicht zutreffend für den Datentyp.|  
|MaximumScale|short|Wenn es sich beim Typindikator um einen numerischen Typ handelt, ist dies die maximal zulässige Anzahl von Ziffern rechts vom Dezimaltrennzeichen. Andernfalls ist dies DBNull.Value.|  
|MinimumScale|short|Wenn es sich beim Typindikator um einen numerischen Typ handelt, ist dies die minimal zulässige Anzahl von Ziffern rechts vom Dezimaltrennzeichen. Andernfalls ist dies DBNull.Value.|  
|IsConcurrencyType|bool|true – Der Datentyp wird immer dann von der Datenbank aktualisiert, wenn die Zeile geändert wird und sich der Wert der Spalte von allen vorherigen Werten unterscheidet.<br /><br /> false – Der Datentyp wird von der Datenbank nicht bei jeder Änderung der Zeile aktualisiert.<br /><br /> DBNull.Value – Die Datenbank unterstützt diese Art von Datentyp nicht.|  
|IsLiteralSupported|bool|true – Der Datentyp kann als Literal ausgedrückt werden.<br /><br /> true – Der Datentyp kann nicht als Literal ausgedrückt werden.|  
|LiteralPrefix|string|Das auf ein angegebenes Literal angewendete Präfix.|  
|LiteralSuffix|Zeichenfolge|Das auf ein angegebenes Literal angewendete Suffix.|  
|NativeDataType|Zeichenfolge|Bei "NativeDataType" handelt es sich um eine OLE DB-spezifische Spalte zum Verfügbarmachen des OLE DB-Typs des Datentyps.|  
  
## <a name="restrictions"></a>Beschränkungen  
 Mithilfe dieser Schemaauflistung werden Informationen zu den Einschränkungen verfügbar gemacht, die vom verwalteten Anbieter für .NET Framework unterstützt werden, über den derzeit eine Verbindung mit der Datenbank hergestellt wird.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CollectionName|string|Der Name der Auflistung, auf die diese Einschränkungen angewendet werden.|  
|RestrictionName|string|Der Name der Einschränkung in der Auflistung.|  
|RestrictionDefault|string|Ignoriert.|  
|RestrictionNumber|int|Die tatsächliche Position in den Auflistungseinschränkungen, an der sich diese bestimmte Einschränkung befindet.|  
  
## <a name="reservedwords"></a>ReservedWords  
 Mithilfe dieser Schemaauflistung werden Informationen zu den Wörtern verfügbar gemacht, die von der Datenbank reserviert sind, mit der der verwaltete Anbieter für .NET Framework derzeit verbunden ist.  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|ReservedWord|Zeichenfolge|Anbieterspezifische reservierte Wort.|  
  
## <a name="see-also"></a>Siehe auch  
 [Abrufen von Datenbankschemainformationen](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [GetSchema und Schemasammlungen](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
