---
title: Allgemeine Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 50127ced-2ac8-4d7a-9cd1-5c98c655ff03
ms.openlocfilehash: b6c2c89101f3304a0cab014de2def22195541471
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249473"
---
# <a name="common-schema-collections"></a>Allgemeine Schemaauflistungen
Die allgemeine Schemaauflistung enthält die von den einzelnen verwalteten Anbietern für .NET Framework implementierten Schemaauflistungen. Sie können einen verwalteten .NET Framework-Anbieter abfragen, um die Liste der unterstützten Schemaauflistungen zu ermitteln, indem Sie die **GetSchema-Methode** ohne Argumente aufrufen, oder mit dem Schemasammlungsnamen "MetaDataCollections". Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben. In diesen Auflistungen werden alle erforderlichen Spalten beschrieben. Anbieter können ggf. zusätzliche Spalten hinzufügen. So fügen beispielsweise `SqlClient` und `OracleClient` der Auflistung der Einschränkungen "ParameterName" hinzu.  
  
 Wenn ein Anbieter den Wert einer erforderlichen Spalte nicht ermitteln kann, wird NULL zurückgegeben.  
  
 Weitere Informationen zur Verwendung der **GetSchema-Methoden** finden Sie unter [GetSchema- und Schemasammlungen](getschema-and-schema-collections.md).  
  
## <a name="metadatacollections"></a>MetaDataCollections  
 Mithilfe dieser Schemaauflistung werden Informationen zu allen Schemaauflistungen verfügbar gemacht, die von dem verwalteten Anbieter für .NET Framework unterstützt werden, über den derzeit eine Verbindung mit der Datenbank hergestellt wird.  
  
|ColumnName|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CollectionName|Zeichenfolge|Der Name der Auflistung, die an die **GetSchema-Methode** übergeben werden soll, um die Auflistung zurückzugeben.|  
|NumberOfRestrictions|INT|Die Anzahl der Einschränkungen, die für die Auflistung angegeben werden können.|  
|NumberOfIdentifierParts|INT|Die Anzahl der Bestandteile im zusammengesetzten Bezeichner/Datenbank-Objektnamen. In SQL Server entspricht dies beispielsweise 3 für Tabellen und 4 für Spalten. In Oracle entspricht dies 2 für Tabellen und 3 für Spalten.|  
  
## <a name="datasourceinformation"></a>DataSourceInformation  
 Mithilfe dieser Schemaauflistung werden Informationen zu der Datenquelle verfügbar gemacht, mit der der verwaltete Anbieter für .NET Framework derzeit verbunden ist.  
  
|ColumnName|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CompositeIdentifierSeparatorPattern|Zeichenfolge|Der reguläre Ausdruck, der den Trennzeichen zum Trennen der Bestandteile in einem zusammengesetzten Bezeichner entspricht. Beispiel: „\\“. (für SQL Server)\@ \\oder "&#124;". (für Oracle).<br /><br /> Ein zusammengesetzter Bezeichner wird in der Regel für einen Datenbankobjektnamen\@verwendet, z. B. pubs.dbo.authors oder pubs dbo.authors.<br /><br /> Verwenden Sie für SQL Server\\den regulären Ausdruck " .". Verwenden Sie für\@ OracleClient "&#124;\\.".<br /><br /> Verwenden Sie Catalog_name_separator für ODBC.<br /><br /> Verwenden Sie DBLITERAL_CATALOG_SEPARATOR oder DBLITERAL_SCHEMA_SEPARATOR für OLE DB.|  
|DataSourceProductName|Zeichenfolge|Der Name des Produkts, auf das durch den Anbieter zugegriffen wird, z. B. "Oracle" oder "SQLServer".|  
|DataSourceProductVersion|Zeichenfolge|Gibt die Version des Produkts, auf das durch den Anbieter zugegriffen wird, im systemeigenen Format der Datenquellen an, nicht im Microsoft-Format.<br /><br /> In einigen Fällen sind die Werte von "DataSourceProductVersion" und "DataSourceProductVersionNormalized" identisch. Bei OLE DB und ODBC sind diese Werte immer identisch, da sie in der zugrunde liegenden systemeigenen API demselben Funktionsaufruf zugeordnet sind.|  
|DataSourceProductVersionNormalized|Zeichenfolge|Eine normalisierte Version der Datenquelle, damit sie mithilfe von `String.Compare()` verglichen werden kann. Das Format ist für alle Versionen des Anbieters konsistent, um zu verhindern, dass Version 10 zwischen Version 1 und Version 2 einsortiert wird.<br /><br /> Beispielsweise verwendet der Oracle-Anbieter für seine normalisierte Version das Format "nn.nn.nn.nn.nn", wodurch eine Oracle 8i-Datenquelle "08.01.07.04.01" zurückgibt. SQL Server verwendet das typische Microsoft-Format "nn.nn.nnnn".<br /><br /> In einigen Fällen sind die Werte von DataSourceProductVersion und DataSourceProductVersionNormalized identisch. Bei OLE DB und ODBC sind diese Werte immer identisch, da sie in der zugrunde liegenden systemeigenen API demselben Funktionsaufruf zugeordnet sind.|  
|GroupByBehavior|<xref:System.Data.Common.GroupByBehavior>|Gibt die Beziehung zwischen den Spalten in einer GROUP BY-Klausel und den nicht zusammengesetzten Spalten in der Auswahlliste an.|  
|IdentifierPattern|Zeichenfolge|Ein regulärer Ausdruck, der einem Bezeichner entspricht und über einen Wert verfügt, der den Bezeichner darstellt. Beispiel: "[A-Za-z0-9_#$]".|  
|IdentifierCase|<xref:System.Data.Common.IdentifierCase>|Gibt an, ob die Groß- und Kleinschreibung bei nicht in Anführungszeichen stehenden Bezeichnern berücksichtigt werden soll.|  
|OrderByColumnsInSelect|bool|Gibt an, ob Spalten in einer ORDER BY-Klausel in der Auswahlliste vorhanden sein müssen. Der Wert "true" gibt an, dass die Spalten in der Auswahlliste vorhanden sein müssen. Der Wert "false" gibt an, dass sie nicht in der Auswahlliste vorhanden sein müssen.|  
|ParameterMarkerFormat|Zeichenfolge|Eine Formatzeichenfolge, die die Formatierung des Parameters darstellt.<br /><br /> Wenn benannte Parameter von der Datenquelle unterstützt werden, muss sich der erste Platzhalter in dieser Zeichenfolge an der Stelle befinden, an der der Parametername formatiert wird.<br /><br /> Wenn die Datenquelle z. B. erwartet, dass Parameter benannt und mit{0}einem ':' vorangestellt werden, wäre dies ": ". Bei der Formatierung dieses Beispiels mit dem Parameternamen "p1" lautet die resultierende Zeichenfolge also ":p1".<br /><br /> Wenn die Datenquelle erwartet, dass Parameter\@mit dem ' ' vorangestellt werden, aber die Namen sie bereits enthalten, wäre dies '{0}', und das Ergebnis der Formatierung eines Parameters mit dem Namen "\@p1" wäre einfach "p1".\@<br /><br /> Für Datenquellen, die keine benannten Parameter erwarten und die Verwendung des Zeichens '?' erwarten, kann die Formatzeichenfolge einfach als '?' angegeben werden, wodurch der Parametername ignoriert würde. Für OLE DB geben wir '?' zurück.|  
|ParameterMarkerPattern|Zeichenfolge|Ein regulärer Ausdruck, der einer Parametermarkierung entspricht. Er verfügt (sofern vorhanden) über einen Wert, der dem Parameternamen entspricht.<br /><br /> Wenn z. B. benannte\@Parameter mit einem ' ' -Lead-In-Zeichen unterstützt werden, das im Parameternamen enthalten ist, wäre dies: "(\@[A-Za-z0-9_']*)".<br /><br /> Wenn benannte Parameter jedoch mit einem ':' als Lead-In-Zeichen unterstützt werden und es nicht Teil des Parameternamens ist, wäre\*dies: ":([A-Za-z0-9_'] )".<br /><br /> Wenn die Datenquelle keine benannten Parameter unterstützt, wäre dies natürlich einfach "?".|  
|ParameterNameMaxLength|INT|Die maximale Länge eines Parameternamens in Zeichen. In Visual Studio werden im Falle der Unterstützung von Parameternamen 30 Zeichen als Mindestwert für die maximale Länge erwartet.<br /><br /> Wenn benannte Parameter von der Datenquelle nicht unterstützt werden, gibt diese Eigenschaft Null (0) zurück.|  
|ParameterNamePattern|Zeichenfolge|Ein regulärer Ausdruck, der den gültigen Parameternamen entspricht. Je nach Datenquelle sind die Regeln bezüglich der für Parameternamen zulässigen Zeichen verschieden.<br /><br /> In Visual Studio wird im Falle der Unterstützung von Parameternamen erwartet, dass die Zeichen "\p{Lu}\p{Ll}\p{Lt}\p{Lm}\p{Lo}\p{Nl}\p{Nd}" die in jedem Fall unterstützte Gruppe von für Parameternamen gültigen Zeichen darstellen.|  
|QuotedIdentifierPattern|Zeichenfolge|Ein regulärer Ausdruck, der einem Bezeichner in Anführungszeichen entspricht und über einen Wert verfügt, der den Bezeichner ohne Anführungszeichen darstellt. Wenn die Datenquelle z. B. doppelte Anführungszeichen verwendet, um angesetzte\\Bezeichner zu identifizieren, wäre dies: "(([-"]&#124;\\")*)".\\|  
|QuotedIdentifierCase|<xref:System.Data.Common.IdentifierCase>|Gibt an, ob die Groß- und Kleinschreibung bei Bezeichnern in Anführungszeichen berücksichtigt werden muss.|  
|StatementSeparatorPattern|Zeichenfolge|Ein regulärer Ausdruck, der dem Trennzeichen für Anweisungen entspricht.|  
|StringLiteralPattern|Zeichenfolge|Ein regulärer Ausdruck, der einem Zeichenfolgenliteral entspricht und über einen Wert verfügt, der das Literal darstellt. Wenn die Datenquelle z. B. einfache Anführungszeichen verwendet, um Zeichenfolgen zu identifizieren, wäre dies: "(([''&#124;'')*')'"''''''''''''''''''''(')|  
|SupportedJoinOperators|<xref:System.Data.Common.SupportedJoinOperators>|Gibt an, welche SQL-Joinanweisungen von der Datenquelle unterstützt werden.|  
  
## <a name="datatypes"></a>DataTypes  
 Mithilfe dieser Schemaauflistung werden Informationen zu den Datentypen verfügbar gemacht, die von der Datenbank unterstützt werden, mit der der verwaltete Anbieter für .NET Framework derzeit verbunden ist.  
  
|ColumnName|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|TypName|Zeichenfolge|Der anbieterspezifische Datentypname.|  
|ProviderDbType|INT|Der anbieterspezifische Typwert, der beim Angeben des Typs eines Parameters verwendet werden soll. Beispiel: SqlDbType.Money oder OracleType.Blob.|  
|ColumnSize|long|Die Länge einer nicht numerischen Spalte oder eines nicht numerischen Parameters bezieht sich entweder auf die maximale oder auf die für diesen Typ vom Anbieter definierte Länge.<br /><br /> Bei Zeichendaten ist dies die maximale oder definierte Länge in Einheiten, entsprechend der Definition in der Datenquelle. In Oracle wird eine Länge und anschließend die tatsächliche Speichergröße für einige Zeichendatentypen angegeben. Dadurch wird für Oracle nur die Länge in Einheiten definiert.<br /><br /> Bei Datum/Uhrzeit-Datentypen ist dies die Länge der Zeichenfolgendarstellung (dabei wird von der maximal zulässigen Genauigkeit der Sekundenbruchteil-Komponente ausgegangen).<br /><br /> Wenn der Datentyp numerisch ist, ist dies die obere Grenze der maximalen Genauigkeit des Datentyps.|  
|CreateFormat|Zeichenfolge|Formatzeichenfolge, die darstellt, wie diese Spalte einer Datendefinitionsanweisung (z. B. CREATE TABLE) hinzugefügt wird. Jedes Element im CreateParameter-Array muss durch eine "Parametermarkierung" in der Formatzeichenfolge dargestellt werden.<br /><br /> Für den SQL-Datentyp DECIMAL ist eine Angabe zur Genauigkeit und zur Dezimalstellenanzahl erforderlich. In diesem Fall wäre die Formatzeichenfolge{0}{1}"DECIMAL( , )".|  
|CreateParameters|Zeichenfolge|Die Erstellungsparameter, die beim Erstellen einer Spalte dieses Datentyps angegeben werden müssen. Die Erstellungsparameter sind in der Zeichenfolge durch ein Komma getrennt in der Reihenfolge aufgelistet, in der sie bereitgestellt werden sollen.<br /><br /> Für den SQL-Datentyp DECIMAL ist eine Angabe zur Genauigkeit und zur Dezimalstellenanzahl erforderlich. In diesem Fall müssen die Erstellungsparameter die Zeichenfolge "Genauigkeit, Dezimalstellenanzahl" enthalten.<br /><br /> In einem Textbefehl zum Erstellen einer DECIMAL-Spalte mit einer Genauigkeit von 10 und einem{0}Maßstab{1}von 2 könnte der Wert der CreateFormat-Spalte DECIMAL( , )" sein, und die vollständige Typspezifikation wäre DECIMAL(10,2).|  
|DataType|Zeichenfolge|Der Name des .NET Framework-Typs des Datentyps.|  
|IsAutoincrementable|bool|true – Die Werte dieses Datentyps können automatisch erhöht werden.<br /><br /> false – Die Werte dieses Datentyps können nicht automatisch erhöht werden.<br /><br /> Beachten Sie, dass auf diese Weise lediglich angegeben wird, ob eine Spalte dieses Datentyps automatisch erhöht werden kann, und nicht, dass alle Spalten dieses Typs automatisch erhöht werden.|  
|IsBestMatch|bool|true – Der Datentyp stellt die höchste Übereinstimmung zwischen allen Datentypen im Datenspeicher und dem durch den Wert in der DataType-Spalte angegebenen .NET Framework-Datentyp dar.<br /><br /> false – Der Datentyp stellt nicht die höchste Übereinstimmung dar.<br /><br /> Für jede Gruppe von Zeilen, in der der Wert der DataType-Spalte derselbe ist, wird die IsBestMatch-Spalte nur in einer Zeile auf "true" festgelegt.|  
|IsCaseSensitive|bool|true – Bei dem Datentyp handelt es sich um einen Zeichentyp, und die Groß- und Kleinschreibung muss berücksichtigt werden.<br /><br /> true – Bei dem Datentyp handelt es sich nicht um einen Zeichentyp, und die Groß- und Kleinschreibung muss nicht berücksichtigt werden.|  
|IsFixedLength|bool|true – Die von der DLL (Data Definition Language) erstellten Spalten dieses Datentyps weisen eine feste Länge auf.<br /><br /> false – Die von der DLL (Data Definition Language) erstellten Spalten dieses Datentyps weisen eine variable Länge auf.<br /><br /> DBNull.Value – Es ist nicht bekannt, ob dieses Feld vom Anbieter einer Spalte mit fester oder variabler Länge zugeordnet wird.|  
|IsFixedPrecisionScale|bool|true – Der Datentyp verfügt über eine feste Genauigkeit und Dezimalstellenanzahl.<br /><br /> false – Der Datentyp verfügt nicht über eine feste Genauigkeit und Dezimalstellenanzahl.|  
|IsLong|bool|true – Der Datentyp enthält sehr lange Daten. Die Definition hierfür ist anbieterspezifisch.<br /><br /> false – Der Datentyp enthält keine sehr langen Daten.|  
|IsNullable|bool|true – Der Datentyp lässt NULL-Werte zu.<br /><br /> false – Der Datentyp lässt keine NULL-Werte zu.<br /><br /> DBNull.Value – Es ist nicht bekannt, ob der Datentyp NULL-Werte zulässt.|  
|IsSearchable|bool|true – Der Datentyp kann in WHERE-Klauseln mit beliebigen Operatoren außer dem LIKE-Prädikat verwendet werden.<br /><br /> FALSE – Der Datentyp kann nicht in WHERE-Klauseln mit beliebigen Operatoren außer dem LIKE-Prädikat verwendet werden.|  
|IsSearchableWithLike|bool|TRUE – Der Datentyp kann mit dem LIKE-Prädikat verwendet werden.<br /><br /> FALSE – Der Datentyp kann nicht mit dem LIKE-Prädikat verwendet werden.|  
|IsUnsigned|bool|true – Der Datentyp hat kein Vorzeichen.<br /><br /> false – Der Datentyp hat ein Vorzeichen.<br /><br /> DBNull.Value – Nicht zutreffend für den Datentyp.|  
|MaximumScale|short|Wenn es sich beim Typindikator um einen numerischen Typ handelt, ist dies die maximal zulässige Anzahl von Ziffern rechts vom Dezimaltrennzeichen. Andernfalls ist dies DBNull.Value.|  
|MinimumScale|short|Wenn es sich beim Typindikator um einen numerischen Typ handelt, ist dies die minimal zulässige Anzahl von Ziffern rechts vom Dezimaltrennzeichen. Andernfalls ist dies DBNull.Value.|  
|IsConcurrencyType|bool|true – Der Datentyp wird immer dann von der Datenbank aktualisiert, wenn die Zeile geändert wird und sich der Wert der Spalte von allen vorherigen Werten unterscheidet.<br /><br /> false – Der Datentyp wird von der Datenbank nicht bei jeder Änderung der Zeile aktualisiert.<br /><br /> DBNull.Value – Die Datenbank unterstützt diese Art von Datentyp nicht.|  
|IsLiteralSupported|bool|true – Der Datentyp kann als Literal ausgedrückt werden.<br /><br /> true – Der Datentyp kann nicht als Literal ausgedrückt werden.|  
|LiteralPrefix|Zeichenfolge|Das auf ein angegebenes Literal angewendete Präfix.|  
|LiteralSuffix|Zeichenfolge|Das auf ein angegebenes Literal angewendete Suffix.|  
|NativeDataType|String|Bei "NativeDataType" handelt es sich um eine OLE DB-spezifische Spalte zum Verfügbarmachen des OLE DB-Typs des Datentyps.|  
  
## <a name="restrictions"></a>Beschränkungen  
 Mithilfe dieser Schemaauflistung werden Informationen zu den Einschränkungen verfügbar gemacht, die vom verwalteten Anbieter für .NET Framework unterstützt werden, über den derzeit eine Verbindung mit der Datenbank hergestellt wird.  
  
|ColumnName|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|CollectionName|Zeichenfolge|Der Name der Auflistung, auf die diese Einschränkungen angewendet werden.|  
|RestrictionName|Zeichenfolge|Der Name der Einschränkung in der Auflistung.|  
|RestrictionDefault|Zeichenfolge|Ignoriert.|  
|RestrictionNumber|INT|Die tatsächliche Position in den Auflistungseinschränkungen, an der sich diese bestimmte Einschränkung befindet.|  
  
## <a name="reservedwords"></a>ReservedWords  
 Mithilfe dieser Schemaauflistung werden Informationen zu den Wörtern verfügbar gemacht, die von der Datenbank reserviert sind, mit der der verwaltete Anbieter für .NET Framework derzeit verbunden ist.  
  
|ColumnName|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|ReservedWord|Zeichenfolge|Anbieterspezifisches reserviertes Wort.|  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)
- ["GetSchema" und Schemaauflistungen](getschema-and-schema-collections.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
