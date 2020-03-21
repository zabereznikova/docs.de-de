---
title: SQL-CLR-Typenzuordnung
ms.date: 07/23/2018
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
ms.openlocfilehash: 336732e0fe7ca8955702d325309db6a8e61b1722
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174536"
---
# <a name="sql-clr-type-mapping"></a>SQL-CLR-Typenzuordnung
In LINQ to SQL wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in einer beliebigen Programmiersprache erstellt wurde. Bei der Ausführung der Anwendung wandelt LINQ to SQL die sprachintegrierten Abfragen im Objektmodell in SQL um und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt LINQ to SQL diese zurück in Objekte, mit denen in einer Programmiersprache gearbeitet werden kann.  
  
 Um Daten zwischen dem Objektmodell und der Datenbank zu übersetzen, muss eine *Typzuordnung* definiert werden. Mithilfe des Typmappings stellt LINQ to SQL eine Zuordnung zwischen jedem Typ der CLR (Common Language Runtime) und einem bestimmten SQL Server-Typ her. Die Typmappings und andere Mappinginformationen, wie Datenbankstrukturen und Tabellenbeziehungen, können im Objektmodell mithilfe von attributbasiertem Mapping definiert werden. Alternativ dazu können die Mappinginformationen außerhalb des Objektmodells mit einer externen Mappingdatei festgelegt werden. Weitere Informationen finden Sie unter [Attributbasierte Zuordnung](attribute-based-mapping.md) und [externe Zuordnung](external-mapping.md).  
  
 In diesem Thema werden folgende Punkte erläutert:  
  
- [Standardtypmapping](#DefaultTypeMapping)  
  
- [Laufzeitverhaltens-Matrix des Typmappings](#BehaviorMatrix)  
  
- [Verhaltensunterschiede zwischen CLR- und SQL-Ausführung](#BehaviorDiffs)  
  
- [Enumerationsmapping](#EnumMapping)  
  
- [Numerisches Mapping](#NumericMapping)  
  
- [Text- und XML-Mapping](#TextMapping)  
  
- [Datums- und Uhrzeitmapping](#DateMapping)  
  
- [Binäres Mapping](#BinaryMapping)  
  
- [Verschiedene Mappingtypen](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>
## <a name="default-type-mapping"></a>Standardtypmapping  
 Das Objektmodell oder die externe Mappingdatei kann mithilfe des objektrelationalen Designers (O/R-Designer) oder mit dem Befehlszeilentool SQLMetal automatisch erstellt werden. Durch Standardtypmappings für diese Tools wird festgelegt, welche CLR-Typen bestimmten Spalten in der SQL Server-Datenbank zugeordnet werden sollen. Weitere Informationen zur Verwendung dieser Tools finden Sie unter [Erstellen des Objektmodells](creating-the-object-model.md).  
  
 Mithilfe der <xref:System.Data.Linq.DataContext.CreateDatabase%2A>-Methode kann weiterhin eine SQL Server-Datenbank auf Grundlage der Mappinginformationen des Objektmodells oder der externen Mappingdatei erstellt werden. Mit den Standardtypmappings für die <xref:System.Data.Linq.DataContext.CreateDatabase%2A>-Methode wird festgelegt, welche Typen von SQL Server-Spalten für das Mapping der CLR-Typen im Objektmodell erstellt werden. Weitere Informationen finden Sie unter [Gewusst wie: Dynamisches Erstellen einer Datenbank](how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>
## <a name="type-mapping-run-time-behavior-matrix"></a>Laufzeitverhaltens-Matrix des Typmappings  
 In der folgenden Grafik wird das erwartete Laufzeitverhalten spezifischer Typmappings dargestellt, wenn Daten von der Datenbank abgerufen oder in ihr gespeichert werden. Mit Ausnahme der Serialisierung unterstützt LINQ to SQL kein Mapping zwischen CLR- oder SQL Server-Datentypen, die nicht in dieser Matrix aufgeführt sind. Weitere Informationen zur Serialisierungsunterstützung finden Sie unter [Binäre Serialisierung](#BinarySerialization).  

![SQL Server zu SQL CLR-Datentypzuordnungstabelle](./media/sql-clr-type-mapping.png)

> [!NOTE]
> Einige Typmappings können bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen.  
  
### <a name="custom-type-mapping"></a>Benutzerdefinierte Typzuordnung  
 Mit LINQ to SQL sind die Standardtypmappings nicht auf diejenigen beschränkt, die von O/R-Designer, SQLMetal und der <xref:System.Data.Linq.DataContext.CreateDatabase%2A>-Methode verwendet werden. Sie können benutzerdefinierte Typmappings erstellen, indem Sie sie explizit in einer DBML-Datei angeben. Mit dieser DBML-Datei können Sie danach den Objektmodellcode und die Mappingdatei erstellen. Weitere Informationen finden Sie unter [SQL-CLR Custom Type Mappings](sql-clr-custom-type-mappings.md).  
  
<a name="BehaviorDiffs"></a>
## <a name="behavior-differences-between-clr-and-sql-execution"></a>Verhaltensunterschiede zwischen CLR- und SQL-Ausführung  
 Aufgrund der Unterschiede bezüglich Präzision und Ausführung zwischen der CLR und SQL Server können Berechnungen zu unterschiedlichen Ergebnissen und unterschiedlichem Verhalten führen. Berechnungen, die in LINQ to SQL-Abfragen ausgeführt wurden, werden erst in Transact-SQL übersetzt und dann für die SQL Server-Datenbank ausgeführt. Außerhalb von LINQ to SQL-Abfragen ausgeführte Berechnungen werden im Kontext der CLR ausgeführt.  
  
 Folgende Beispiele zeigen einige Unterschiede im Verhalten zwischen der CLR und SQL Server:  
  
- In SQL Server und der CLR werden verschiedene vergleichbare Datentypen unterschiedlich sortiert. Zum Beispiel werden SQL Server-Daten des Typs `UNIQUEIDENTIFIER` anders sortiert als CLR-Daten des Typs <xref:System.Guid?displayProperty=nameWithType>.  
  
- SQL Server behandelt verschiedene Vorgänge für Zeichenfolgenvergleiche anders als die CLR. In SQL Server ist das Verhalten bei Zeichenfolgenvergleichen von den Sortierungseinstellungen auf dem Server abhängig. Weitere Informationen finden Sie unter [Arbeiten mit Sortierungen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187582(v=sql.105)) in Microsoft SQL Server Books Online.  
  
- Für einige zugeordnete Funktionen werden von SQL Server andere Werte zurückgegeben als von der CLR. Die Funktionen für die Überprüfung auf Gleichheit beispielsweise unterscheiden sich, da von SQL Server zwei Zeichenketten als gleich aufgefasst werden, wenn sie sich lediglich durch nachgestellte Leerzeichen unterscheiden, während solche Zeichenketten von der CLR als unterschiedlich aufgefasst werden.  
  
<a name="EnumMapping"></a>
## <a name="enum-mapping"></a>Enumerationsmapping  
 LINQ to SQL unterstützt für das Mapping des CLR-<xref:System.Enum?displayProperty=nameWithType>-Typs zu SQL Server-Typen zwei Arten:  
  
- Zuordnung zu numerischen SQL-Typen (`TINYINT`, `SMALLINT`, `INT`, `BIGINT`)  
  
     Wenn ein CLR-<xref:System.Enum?displayProperty=nameWithType>-Typ einem numerischen SQL-Typ zugeordnet wird, wird der zugrunde liegende CLR-<xref:System.Enum?displayProperty=nameWithType>-Typ dem Wert der SQL Server-Datenbankspalte zugeordnet. Enthält z. B. ein <xref:System.Enum?displayProperty=nameWithType> mit dem Namen `DaysOfWeek` einen Member mit dem Namen `Tue` und dem zugrunde liegenden Ganzzahlwert 3, wird dieser dem Datenbankwert 3 zugeordnet.  
  
- Zuordnung zu SQL-Texttypen (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`)  
  
     Wenn ein CLR-<xref:System.Enum?displayProperty=nameWithType>-Typ einem SQL-Texttyp zugeordnet wird, wird der SQL-Datenbankwert den Namen der CLR-<xref:System.Enum?displayProperty=nameWithType>-Member zugeordnet. Enthält z. B. ein <xref:System.Enum?displayProperty=nameWithType> mit dem Namen `DaysOfWeek` einen Member mit dem Namen `Tue` und dem zugrunde liegenden Ganzzahlwert 3, wird dieser dem Datenbankwert `Tue` zugeordnet.  
  
> [!NOTE]
> Beim Mapping von SQL-Texttypen zu einer CLR-<xref:System.Enum?displayProperty=nameWithType> sollten nur die Namen der <xref:System.Enum>-Member in der zugeordneten SQL-Spalte enthalten sein. Andere Werte werden in der der <xref:System.Enum> zugeordneten SQL-Spalte nicht unterstützt.  
  
 Mit dem O/R-Designer und dem SQLMetal-Befehlszeilentool kann ein SQL-Typ nicht automatisch einer CLR-<xref:System.Enum>-Klasse zugeordnet werden. Sie müssen diese Zuordnung explizit konfigurieren, indem Sie eine DBML-Datei zur Verwendung mit dem O/R-Designer und SQLMetal anpassen. Weitere Informationen zur benutzerdefinierten Typzuordnung finden Sie unter [SQL-CLR Custom Type Mappings](sql-clr-custom-type-mappings.md).  
  
 Da eine SQL-Spalte, die für die Enumeration vorgesehen ist, vom gleichen Typ wie andere numerische Spalten und Textspalten ist; Diese Tools erkennen Ihre Absicht und Standardzuordnung nicht, wie in den folgenden Abschnitten [Numerische Zuordnung](#NumericMapping) und [Text und XML-Zuordnung](#TextMapping) beschrieben. Weitere Informationen zum Generieren von Code mit der DBML-Datei finden Sie unter [Codegenerierung in LINQ zu SQL](code-generation-in-linq-to-sql.md).  
  
 Die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode erstellt eine SQL-Spalte eines numerischen Typs zum Mapping eines CLR-<xref:System.Enum?displayProperty=nameWithType>-Typs.  
  
<a name="NumericMapping"></a>
## <a name="numeric-mapping"></a>Numerisches Mapping  
 Mit LINQ to SQL können viele numerische CLR- und SQL Server-Typen zugeordnet werden. Die Tabelle enthält auch die CLR-Typen, die von O/R-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server-Typ|Von O/R-Designer und SQLMetal verwendetes CLR-Standardtypmapping|  
|---------------------|-----------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=nameWithType>|  
|`TINYINT`|<xref:System.Int16?displayProperty=nameWithType>|  
|`INT`|<xref:System.Int32?displayProperty=nameWithType>|  
|`BIGINT`|<xref:System.Int64?displayProperty=nameWithType>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`MONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=nameWithType>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=nameWithType>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode verwendet werden, um festzulegen, welche Typen von SQL-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR-Typen erstellt werden.  
  
|CLR-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> verwendeter Standard-SQL Server-Typ|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|`BIT`|  
|<xref:System.Byte?displayProperty=nameWithType>|`TINYINT`|  
|<xref:System.Int16?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=nameWithType>|`INT`|  
|<xref:System.Int64?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.SByte?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=nameWithType>|`INT`|  
|<xref:System.UInt32?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=nameWithType>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=nameWithType>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=nameWithType>|`REAL`|  
|<xref:System.Double?displayProperty=nameWithType>|`FLOAT`|  
  
 Es können viele andere numerische Mappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen. Weitere Informationen finden Sie in der [Typzuordnungslaufzeitverhaltensmatrix](#BehaviorMatrix).  
  
### <a name="decimal-and-money-types"></a>Dezimal- und Währungstypen  
 Die Standardgenauigkeit des `DECIMAL` SQL Server-Typs (18 Dezimalstellen links und rechts vom Dezimaltrennzeichen) <xref:System.Decimal?displayProperty=nameWithType> ist viel kleiner als die Genauigkeit des CLR-Typs, mit dem er standardmäßig gekoppelt ist. Dies kann beim Speichern von Daten in der Datenbank zu Genauigkeitsverlust führen. Umgekehrt kann jedoch das gleiche auftreten, wenn der SQL Server-Typ `DECIMAL` für eine Genauigkeit von mehr als 29 Stellen konfiguriert ist. Wenn der SQL Server-Typ `DECIMAL` für eine höhere Genauigkeit konfiguriert ist als der CLR-Typ <xref:System.Decimal?displayProperty=nameWithType>, kann Genauigkeitsverlust beim Abrufen von Daten aus der Datenbank auftreten.  
  
 Die SQL Server-Typen `MONEY` und `SMALLMONEY`, die standardmäßig ebenfalls dem CLR-Typ <xref:System.Decimal?displayProperty=nameWithType> zugeordnet werden, haben eine niedrigere Genauigkeit. Dies kann beim Speichern von Daten in der Datenbank einen Überlauf oder Datenverlust verursachen.  
  
<a name="TextMapping"></a>
## <a name="text-and-xml-mapping"></a>Text- und XML-Mapping  
 Es gibt viele textbasierte Typen und XML-Typen, die mit LINQ to SQL zugeordnet werden können. Die Tabelle enthält auch die CLR-Typen, die von O/R-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server-Typ|Von O/R-Designer und SQLMetal verwendetes CLR-Standardtypmapping|  
|---------------------|-----------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`VARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NVARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`TEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`NTEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=nameWithType>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode verwendet werden, um festzulegen, welche Typen von SQL-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR-Typen erstellt werden.  
  
|CLR-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> verwendeter Standard-SQL Server-Typ|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=nameWithType>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=nameWithType>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=nameWithType>[]|`NVARCHAR(4000)`|  
|Benutzerdefinierter Typ, mit dem `Parse()` und `ToString()` implementiert werden.|`NVARCHAR(MAX)`|  
  
 Es können viele andere textbasierte und XML-Mappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen. Weitere Informationen finden Sie in der [Typzuordnungslaufzeitverhaltensmatrix](#BehaviorMatrix).  
  
### <a name="xml-types"></a>XML-Typen  
 Der `XML`-Datentyp von SQL Server ist seit Microsoft SQL Server 2005 verfügbar. Der `XML`-Datentyp von SQL Server kann <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> oder <xref:System.String> zugeordnet werden. Wenn die Spalte XML-Fragmente speichert, die nicht in <xref:System.Xml.Linq.XElement> eingelesen werden können, muss die Spalte <xref:System.String> zugeordnet werden, um Laufzeitfehler zu vermeiden. Zu den XML-Fragmenten, die <xref:System.String> zugeordnet werden müssen, zählen die folgenden:  
  
- Eine Sequenz von XML-Elementen  
  
- Attributes  
  
- Öffentliche Bezeichner (Public Identifier, PI)  
  
- Kommentare  
  
 Obwohl Sie <xref:System.Xml.Linq.XElement> SQL <xref:System.Xml.Linq.XDocument> Server zuordnen und SQL Server zuordnen können, <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> wie in der [Typzuordnungslaufzeitverhaltensmatrix](#BehaviorMatrix)dargestellt, verfügt die Methode über keine standardmäßige SQL Server-Typzuordnung für diese Typen.  
  
### <a name="custom-types"></a>Benutzerdefinierte Typen  
 Wenn eine Klasse `Parse()` `ToString()`implementiert und , können Sie das`CHAR`Objekt `NCHAR` `VARCHAR`einem `NVARCHAR` `TEXT`beliebigen `NTEXT` `XML`SQL-Texttyp zuordnen ( , , , , , , . Das Objekt wird in der Datenbank gespeichert, indem der von `ToString()` zurückgegebene Wert in der zugeordneten Datenbankspalte gespeichert wird. Das Objekt wird rekonstruiert, indem `Parse()` für die von der Datenbank zurückgegebene Zeichenfolge aufgerufen wird.  
  
> [!NOTE]
> LINQ to SQL unterstützt keine Serialisierung mithilfe von <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>.  
  
<a name="DateMapping"></a>
## <a name="date-and-time-mapping"></a>Datums- und Uhrzeitmapping  
 Mit LINQ to SQL können viele SQL Server-Datums- und Uhrzeittypen zugeordnet werden. Die Tabelle enthält auch die CLR-Typen, die von O/R-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server-Typ|Von O/R-Designer und SQLMetal verwendetes CLR-Standardtypmapping|  
|---------------------|-----------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=nameWithType>|  
|`DATE`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=nameWithType>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode verwendet werden, um festzulegen, welche Typen von SQL-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR-Typen erstellt werden.  
  
|CLR-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> verwendeter Standard-SQL Server-Typ|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=nameWithType>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=nameWithType>|`TIME`|  
  
 Es können viele andere Datums- und Uhrzeitmappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen. Weitere Informationen finden Sie in der [Typzuordnungslaufzeitverhaltensmatrix](#BehaviorMatrix).  
  
> [!NOTE]
> Die SQL Server-Typen `DATETIME2`, `DATETIMEOFFSET`, `DATE` und `TIME` sind seit Microsoft SQL Server 2008 verfügbar. LINQ to SQL unterstützt das Mapping dieser neuen Typen seit .NET Framework, Version 3.5, SP1.  
  
### <a name="systemdatetime"></a>System.DateTime  
 Der Bereich und die Genauigkeit des CLR-Typs <xref:System.DateTime?displayProperty=nameWithType> sind größer als der Bereich und die Genauigkeit des SQL Server-Typs `DATETIME`. Diese beiden Typen werden mit dem Standardtypmapping der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode einander zugeordnet. Um Ausnahmen im Zusammenhang mit außerhalb des Bereichs von `DATETIME` liegenden Datumswerten zu vermeiden, sollte der seit Microsoft SQL Server 2008 verfügbare `DATETIME2`-Typ verwendet werden. `DATETIME2`kann dem Bereich und der <xref:System.DateTime?displayProperty=nameWithType>Präzision der CLR entsprechen.  
  
 SQL Server-Datumswerte unterstützen keine <xref:System.TimeZone>, eine Funktion, die in der CLR große Bedeutung hat. <xref:System.TimeZone>-Werte werden ohne <xref:System.TimeZone>-Umwandlung in der Datenbank gespeichert, unabhängig von den ursprünglichen <xref:System.DateTimeKind>-Informationen. Werden <xref:System.DateTime>-Werte aus der Datenbank abgerufen, werden diese wie in <xref:System.DateTime> mit einer <xref:System.DateTimeKind> von <xref:System.DateTimeKind.Unspecified> geladen. Weitere Informationen zu <xref:System.DateTime?displayProperty=nameWithType> unterstützten Methoden finden Sie unter [System.DateTime-Methoden](system-datetime-methods.md).  
  
### <a name="systemtimespan"></a>System.TimeSpan  
 Mit Microsoft SQL Server 2008 und .NET Framework 3.5 SP1 kann der CLR-Typ <xref:System.TimeSpan?displayProperty=nameWithType> dem SQL Server-Typ `TIME` zugeordnet werden. Es gibt jedoch große Unterschiede im von dem CLR-Typ <xref:System.TimeSpan?displayProperty=nameWithType> und dem SQL Server-Typ `TIME` unterstützten Bereich. Das Mapping von Stundenwerten kleiner als 0 oder größer als 23:59:59.9999999 zum SQL-Typ `TIME` hat Überlaufausnahmen zur Folge. Weitere Informationen finden Sie unter [System.TimeSpan-Methoden](system-timespan-methods.md).  
  
 In Microsoft SQL Server 2000 und SQL Server 2005 können <xref:System.TimeSpan> keine Datenbankfelder zugeordnet werden. Dennoch werden Operationen für <xref:System.TimeSpan> unterstützt, da <xref:System.TimeSpan>-Werte von <xref:System.DateTime>-Subtraktionen zurückgegeben oder als Literal oder gebundene Variable in einen Ausdruck integriert werden können.  
  
<a name="BinaryMapping"></a>
## <a name="binary-mapping"></a>Binäres Mapping  
 Es gibt mehrere SQL Server-Typen, die dem CLR-Typ <xref:System.Data.Linq.Binary?displayProperty=nameWithType> zugeordnet werden können. In der folgenden Tabelle sind die SQL Server-Typen aufgeführt, für die von O/R-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei der CLR-Typ <xref:System.Data.Linq.Binary?displayProperty=nameWithType> definiert wird.  
  
|SQL Server-Typ|Von O/R-Designer und SQLMetal verwendetes CLR-Standardtypmapping|  
|---------------------|-----------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`mit `FILESTREAM` dem Attribut|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode verwendet werden, um festzulegen, welche Typen von SQL-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR-Typen erstellt werden.  
  
|CLR-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> verwendeter Standard-SQL Server-Typ|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
  
 Es können viele andere binäre Mappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen. Weitere Informationen finden Sie in der [Typzuordnungslaufzeitverhaltensmatrix](#BehaviorMatrix).  
  
### <a name="sql-server-filestream"></a>SQL Server FILESTREAM  
 Das `FILESTREAM`-Attribut für `VARBINARY(MAX)`-Spalten ist seit Microsoft SQL Server 2008 verfügbar. Dieses Attribut kann ab .NET Framework Version 3.5 SP1 mit LINQ to SQL zugeordnet werden.  
  
 Obwohl `VARBINARY(MAX)`-Spalten mit dem `FILESTREAM`-Attribut <xref:System.Data.Linq.Binary>-Objekten zugeordnet werden können, können von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode keine Spalten mit dem `FILESTREAM`-Attribut automatisch erstellt werden. Weitere Informationen `FILESTREAM`zu finden Sie unter [FILESTREAM Overview](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb933993(v=sql.105)).  
  
<a name="BinarySerialization"></a>
### <a name="binary-serialization"></a>Binäre Serialisierung  
 Wenn eine Klasse die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementiert, kann ein Objekt in ein beliebiges binäres SQL-Feld (`BINARY`, `VARBINARY`, `IMAGE`) serialisiert werden. Das Objekt wird je nach Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle serialisiert und deserialisiert. Weitere Informationen finden Sie unter [Binäre Serialisierung](../../../../../standard/serialization/binary-serialization.md).
  
<a name="MiscMapping"></a>
## <a name="miscellaneous-mapping"></a>Verschiedene Mappingtypen  
 In der folgenden Tabelle sind die Standardtypmappings für verschiedene Typen aufgeführt, die noch nicht erwähnt wurden. Die Tabelle enthält auch die CLR-Typen, die von O/R-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server-Typ|Von O/R-Designer und SQLMetal verwendetes CLR-Standardtypmapping|  
|---------------------|-----------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=nameWithType>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=nameWithType>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode verwendet werden, um festzulegen, welche Typen von SQL-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR-Typen erstellt werden.  
  
|CLR-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> verwendeter Standard-SQL Server-Typ|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=nameWithType>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=nameWithType>|`SQL_VARIANT`|  
  
 LINQ to SQL unterstützt keine anderen Typmappings für diese Typen.  Weitere Informationen finden Sie in der [Typzuordnungslaufzeitverhaltensmatrix](#BehaviorMatrix).  
  
## <a name="see-also"></a>Weitere Informationen

- [Attributbasierte Zuordnung](attribute-based-mapping.md)
- [Externe Zuordnung](external-mapping.md)
- [Datentypen und Funktionen](data-types-and-functions.md)
- [SQL-CLR-Typenkonflikte](sql-clr-type-mismatches.md)
