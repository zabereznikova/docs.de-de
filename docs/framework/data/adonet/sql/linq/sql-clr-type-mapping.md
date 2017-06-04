---
title: "SQL CLR-Typzuordnung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# SQL CLR-Typzuordnung
In LINQ to SQL wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in einer beliebigen Programmiersprache erstellt wurde.  Bei der Ausführung der Anwendung wandelt LINQ to SQL die sprachintegrierten Abfragen im Objektmodell in SQL um und sendet sie zur Ausführung an die Datenbank.  Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt LINQ to SQL diese zurück in Objekte, mit denen in einer Programmiersprache gearbeitet werden kann.  
  
 Damit Daten zwischen Objektmodell und Datenbank übertragen werden können, muss ein *Typmapping* definiert werden.  Mithilfe des Typmappings stellt LINQ to SQL eine Zuordnung zwischen jedem Typ der CLR \(Common Language Runtime\) und einem bestimmten SQL Server\-Typ her.  Die Typmappings und andere Mappinginformationen, wie Datenbankstrukturen und Tabellenbeziehungen, können im Objektmodell mithilfe von attributbasiertem Mapping definiert werden.  Alternativ dazu können die Mappinginformationen außerhalb des Objektmodells mit einer externen Mappingdatei festgelegt werden.  Weitere Informationen finden Sie unter [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) und [Externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
 In diesem Thema werden folgende Punkte erläutert:  
  
-   [Standardtypmapping](#DefaultTypeMapping)  
  
-   [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix)  
  
-   [Verhaltensunterschiede zwischen CLR\- und SQL\-Ausführung](#BehaviorDiffs)  
  
-   [Enumerationsmapping](#EnumMapping)  
  
-   [Numerisches Mapping](#NumericMapping)  
  
-   [Text\- und XML\-Mapping](#TextMapping)  
  
-   [Datums\- und Uhrzeitmapping](#DateMapping)  
  
-   [Binäres Mapping](#BinaryMapping)  
  
-   [Verschiedene Mappingtypen](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>   
## Standardtypmapping  
 Das Objektmodell oder die externe Mappingdatei kann mithilfe des objektrelationalen Designers \(O\/R\-Designer\) oder mit dem Befehlszeilentool SQLMetal automatisch erstellt werden.  Durch Standardtypmappings für diese Tools wird festgelegt, welche CLR\-Typen bestimmten Spalten in der SQL Server\-Datenbank zugeordnet werden sollen.  Weitere Informationen zur Verwendung dieser Tools finden Sie unter [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md).  
  
 Mithilfe der <xref:System.Data.Linq.DataContext.CreateDatabase%2A>\-Methode kann weiterhin eine SQL Server\-Datenbank auf Grundlage der Mappinginformationen des Objektmodells oder der externen Mappingdatei erstellt werden.  Mit den Standardtypmappings für die <xref:System.Data.Linq.DataContext.CreateDatabase%2A>\-Methode wird festgelegt, welche Typen von SQL Server\-Spalten für das Mapping der CLR\-Typen im Objektmodell erstellt werden.  Weitere Informationen finden Sie unter [Vorgehensweise: Dynamisches Erstellen einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
<a name="BehaviorMatrix"></a>   
## Laufzeitverhaltens\-Matrix des Typmappings  
 In der folgenden Grafik wird das erwartete Laufzeitverhalten spezifischer Typmappings dargestellt, wenn Daten von der Datenbank abgerufen oder in ihr gespeichert werden.  Mit Ausnahme der Serialisierung unterstützt LINQ to SQL kein Mapping zwischen CLR\- oder SQL Server\-Datentypen, die nicht in dieser Matrix aufgeführt sind.  Weitere Informationen zur Unterstützung von Serialisierung finden Sie unter [Binäre Serialisierung](#BinarySerialization).  
  
> [!NOTE]
>  Einige Typmappings können bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen.  
  
### Benutzerdefinierte Typmappings  
 Mit LINQ to SQL sind die Standardtypmappings nicht auf diejenigen beschränkt, die von O\/R\-Designer, SQLMetal und der <xref:System.Data.Linq.DataContext.CreateDatabase%2A>\-Methode verwendet werden.  Sie können benutzerdefinierte Typmappings erstellen, indem Sie sie explizit in einer DBML\-Datei angeben.  Mit dieser DBML\-Datei können Sie danach den Objektmodellcode und die Mappingdatei erstellen.  Weitere Informationen finden Sie unter [Benutzerdefinierte SQL\-CLR\-Typmappings](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).  
  
<a name="BehaviorDiffs"></a>   
## Verhaltensunterschiede zwischen CLR\- und SQL\-Ausführung  
 Aufgrund der Unterschiede bezüglich Präzision und Ausführung zwischen der CLR und SQL Server können Berechnungen zu unterschiedlichen Ergebnissen und unterschiedlichem Verhalten führen.  Berechnungen, die in LINQ to SQL\-Abfragen ausgeführt wurden, werden erst in Transact\-SQL übersetzt und dann für die SQL Server\-Datenbank ausgeführt.  Außerhalb von LINQ to SQL\-Abfragen ausgeführte Berechnungen werden im Kontext der CLR ausgeführt.  
  
 Folgende Beispiele zeigen einige Unterschiede im Verhalten zwischen der CLR und SQL Server:  
  
-   In SQL Server und der CLR werden verschiedene vergleichbare Datentypen unterschiedlich sortiert.  Zum Beispiel werden SQL Server\-Daten des Typs `UNIQUEIDENTIFIER` anders sortiert als CLR\-Daten des Typs <xref:System.Guid?displayProperty=fullName>.  
  
-   SQL Server behandelt verschiedene Vorgänge für Zeichenfolgenvergleiche anders als die CLR.  In SQL Server ist das Verhalten bei Zeichenfolgenvergleichen von den Sortierungseinstellungen auf dem Server abhängig.  Weitere Informationen finden Sie unter [Arbeiten mit Sortierungen](http://go.microsoft.com/fwlink/?LinkId=115330) in der Microsoft SQL Server\-Onlinedokumentation.  
  
-   Für einige zugeordnete Funktionen werden von SQL Server andere Werte zurückgegeben als von der CLR.  Die Funktionen für die Überprüfung auf Gleichheit beispielsweise unterscheiden sich, da von SQL Server zwei Zeichenketten als gleich aufgefasst werden, wenn sie sich lediglich durch nachgestellte Leerzeichen unterscheiden, während solche Zeichenketten von der CLR als unterschiedlich aufgefasst werden.  
  
<a name="EnumMapping"></a>   
## Enumerationsmapping  
 LINQ to SQL unterstützt für das Mapping des CLR\-<xref:System.Enum?displayProperty=fullName>\-Typs zu SQL Server\-Typen zwei Arten:  
  
-   Zuordnung zu numerischen SQL\-Typen \(`TINYINT`, `SMALLINT`, `INT`, `BIGINT`\)  
  
     Wenn ein CLR\-<xref:System.Enum?displayProperty=fullName>\-Typ einem numerischen SQL\-Typ zugeordnet wird, wird der zugrunde liegende CLR\-<xref:System.Enum?displayProperty=fullName>\-Typ dem Wert der SQL Server\-Datenbankspalte zugeordnet.  Enthält z. B. ein <xref:System.Enum?displayProperty=fullName> mit dem Namen `DaysOfWeek` einen Member mit dem Namen `Tue` und dem zugrunde liegenden Ganzzahlwert 3, wird dieser dem Datenbankwert 3 zugeordnet.  
  
-   Zuordnung zu SQL\-Texttypen \(`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`\)  
  
     Wenn ein CLR\-<xref:System.Enum?displayProperty=fullName>\-Typ einem SQL\-Texttyp zugeordnet wird, wird der SQL\-Datenbankwert den Namen der CLR\-<xref:System.Enum?displayProperty=fullName>\-Member zugeordnet.  Enthält z. B. ein <xref:System.Enum?displayProperty=fullName> mit dem Namen `DaysOfWeek` einen Member mit dem Namen `Tue` und dem zugrunde liegenden Ganzzahlwert 3, wird dieser dem Datenbankwert `Tue` zugeordnet.  
  
> [!NOTE]
>  Beim Mapping von SQL\-Texttypen zu einer CLR\-<xref:System.Enum?displayProperty=fullName> sollten nur die Namen der <xref:System.Enum>\-Member in der zugeordneten SQL\-Spalte enthalten sein.  Andere Werte werden in der der <xref:System.Enum> zugeordneten SQL\-Spalte nicht unterstützt.  
  
 Mit dem O\/R\-Designer und dem SQLMetal\-Befehlszeilentool kann ein SQL\-Typ nicht automatisch einer CLR\-<xref:System.Enum>\-Klasse zugeordnet werden.  Sie müssen diese Zuordnung explizit konfigurieren, indem Sie eine DBML\-Datei zur Verwendung mit dem O\/R\-Designer und SQLMetal anpassen.  Weitere Informationen über die benutzerdefinierte Typzuordnung finden Sie unter [Benutzerdefinierte SQL\-CLR\-Typmappings](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).  
  
 Da eine SQL\-Spalte für eine Enumeration vom gleichen Typ wie andere numerische Spalten und Textspalten ist, erkennen diese Tools die Absicht nicht und führen standardmäßig die Zuordnung aus, die in den Abschnitten [Numerisches Mapping](#NumericMapping) und [Text\- und XML\-Mapping](#TextMapping) beschrieben ist.  Weitere Informationen über das Generieren von Code mit der DBML\-Datei finden Sie unter [Codegenerierung in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
 Die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode erstellt eine SQL\-Spalte eines numerischen Typs zum Mapping eines CLR\-<xref:System.Enum?displayProperty=fullName>\-Typs.  
  
<a name="NumericMapping"></a>   
## Numerisches Mapping  
 Mit LINQ to SQL können viele numerische CLR\- und SQL Server\-Typen zugeordnet werden.  Die Tabelle enthält auch die CLR\-Typen, die von O\/R\-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server\-Typ|Von O\/R\-Designer und SQLMetal verwendetes CLR\-Standardtypmapping|  
|---------------------|-------------------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=fullName>|  
|`TINYINT`|<xref:System.Int16?displayProperty=fullName>|  
|`INT`|<xref:System.Int32?displayProperty=fullName>|  
|`BIGINT`|<xref:System.Int64?displayProperty=fullName>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=fullName>|  
|`MONEY`|<xref:System.Decimal?displayProperty=fullName>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=fullName>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=fullName>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=fullName>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=fullName>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode verwendet werden, um festzulegen, welche Typen von SQL\-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR\-Typen erstellt werden.  
  
|CLR\-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> verwendeter Standard\-SQL Server\-Typ|  
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=fullName>|`BIT`|  
|<xref:System.Byte?displayProperty=fullName>|`TINYINT`|  
|<xref:System.Int16?displayProperty=fullName>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=fullName>|`INT`|  
|<xref:System.Int64?displayProperty=fullName>|`BIGINT`|  
|<xref:System.SByte?displayProperty=fullName>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=fullName>|`INT`|  
|<xref:System.UInt32?displayProperty=fullName>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=fullName>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=fullName>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=fullName>|`REAL`|  
|<xref:System.Double?displayProperty=fullName>|`FLOAT`|  
  
 Es können viele andere numerische Mappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen.  Weitere Informationen finden Sie unter [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix).  
  
### Dezimal\- und Währungstypen  
 Die Standardgenauigkeit des SQL Server\-Typs `DECIMAL` \(18 Dezimalstellen links und rechts des Dezimalpunkts\) ist wesentlich geringer als die Genauigkeit des CLR\-Typs <xref:System.Decima?displayProperty=fullName>l, dem dieser SQL Server\-Typ standardmäßig zugeordnet wird.  Dies kann beim Speichern von Daten in der Datenbank zu Genauigkeitsverlust führen.  Umgekehrt kann jedoch das gleiche auftreten, wenn der SQL Server\-Typ `DECIMAL` für eine Genauigkeit von mehr als 29 Stellen konfiguriert ist.  Wenn der SQL Server\-Typ `DECIMAL` für eine höhere Genauigkeit konfiguriert ist als der CLR\-Typ <xref:System.Decimal?displayProperty=fullName>, kann Genauigkeitsverlust beim Abrufen von Daten aus der Datenbank auftreten.  
  
 Die SQL Server\-Typen `MONEY` und `SMALLMONEY`, die standardmäßig ebenfalls dem CLR\-Typ <xref:System.Decimal?displayProperty=fullName> zugeordnet werden, haben eine niedrigere Genauigkeit. Dies kann beim Speichern von Daten in der Datenbank einen Überlauf oder Datenverlust verursachen.  
  
<a name="TextMapping"></a>   
## Text\- und XML\-Mapping  
 Es gibt viele textbasierte Typen und XML\-Typen, die mit LINQ to SQL zugeordnet werden können.  Die Tabelle enthält auch die CLR\-Typen, die von O\/R\-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server\-Typ|Von O\/R\-Designer und SQLMetal verwendetes CLR\-Standardtypmapping|  
|---------------------|-------------------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=fullName>|  
|`NCHAR`|<xref:System.String?displayProperty=fullName>|  
|`VARCHAR`|<xref:System.String?displayProperty=fullName>|  
|`NVARCHAR`|<xref:System.String?displayProperty=fullName>|  
|`TEXT`|<xref:System.String?displayProperty=fullName>|  
|`NTEXT`|<xref:System.String?displayProperty=fullName>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=fullName>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode verwendet werden, um festzulegen, welche Typen von SQL\-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR\-Typen erstellt werden.  
  
|CLR\-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> verwendeter Standard\-SQL Server\-Typ|  
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=fullName>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=fullName>|`NVARCHAR(4000)`|  
|<xref:System.Char?displayProperty=fullName>\[\]|`NVARCHAR(4000)`|  
|Benutzerdefinierter Typ, mit dem `Parse()` und `ToString()` implementiert werden.|`NVARCHAR(MAX)`|  
  
 Es können viele andere textbasierte und XML\-Mappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen.  Weitere Informationen finden Sie unter [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix).  
  
### XML\-Typen  
 Der `XML`\-Datentyp von SQL Server ist seit Microsoft SQL Server 2005 verfügbar.  Der `XML`\-Datentyp von SQL Server kann <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument> oder <xref:System.String> zugeordnet werden.  Wenn die Spalte XML\-Fragmente speichert, die nicht in <xref:System.Xml.Linq.XElement> eingelesen werden können, muss die Spalte <xref:System.String> zugeordnet werden, um Laufzeitfehler zu vermeiden.  Zu den XML\-Fragmenten, die <xref:System.String> zugeordnet werden müssen, zählen die folgenden:  
  
-   Eine Sequenz von XML\-Elementen  
  
-   Attribute  
  
-   Öffentliche Bezeichner \(Public Identifier, PI\)  
  
-   Kommentare  
  
 Obwohl <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument>, wie in der [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix) dargestellt, SQL Server zugeordnet werden kann, verfügt die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode nicht über ein Standard\-SQL Server\-Typmapping für diese Typen.  
  
### Benutzerdefinierte Typen  
 Wenn eine Klasse `Parse()` und `ToString()` implementiert, können deren Objekte einem beliebigen SQL\-Texttyp \(`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`, `TEXT`, `NTEXT`, `XML`\) zugeordnet werden.  Das Objekt wird in der Datenbank gespeichert, indem der von `ToString()` zurückgegebene Wert in der zugeordneten Datenbankspalte gespeichert wird.  Das Objekt wird rekonstruiert, indem `Parse()` für die von der Datenbank zurückgegebene Zeichenfolge aufgerufen wird.  
  
> [!NOTE]
>  LINQ to SQL unterstützt keine Serialisierung mithilfe von <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=fullName>.  
  
<a name="DateMapping"></a>   
## Datums\- und Uhrzeitmapping  
 Mit LINQ to SQL können viele SQL Server\-Datums\- und Uhrzeittypen zugeordnet werden.  Die Tabelle enthält auch die CLR\-Typen, die von O\/R\-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server\-Typ|Von O\/R\-Designer und SQLMetal verwendetes CLR\-Standardtypmapping|  
|---------------------|-------------------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=fullName>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=fullName>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=fullName>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=fullName>|  
|`DATE`|<xref:System.DateTime?displayProperty=fullName>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=fullName>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode verwendet werden, um festzulegen, welche Typen von SQL\-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR\-Typen erstellt werden.  
  
|CLR\-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> verwendeter Standard\-SQL Server\-Typ|  
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=fullName>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=fullName>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=fullName>|`TIME`|  
  
 Es können viele andere Datums\- und Uhrzeitmappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen.  Weitere Informationen finden Sie unter [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix).  
  
> [!NOTE]
>  Die SQL Server\-Typen `DATETIME2`, `DATETIMEOFFSET`, `DATE` und `TIME` sind seit Microsoft SQL Server 2008 verfügbar.  LINQ to SQL unterstützt das Mapping dieser neuen Typen seit .NET Framework, Version 3.5, SP1.  
  
### System.DateTime  
 Der Bereich und die Genauigkeit des CLR\-Typs <xref:System.DateTime?displayProperty=fullName> sind größer als der Bereich und die Genauigkeit des SQL Server\-Typs `DATETIME`. Diese beiden Typen werden mit dem Standardtypmapping der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode einander zugeordnet.  Um Ausnahmen im Zusammenhang mit außerhalb des Bereichs von `DATETIME` liegenden Datumswerten zu vermeiden, sollte der seit Microsoft SQL Server 2008 verfügbare `DATETIME2`\-Typ verwendet werden.  `DATETIME2`  kann den Bereich und die Genauigkeit des CLR\-Typs <xref:System.DateTime?displayProperty=fullName> aufnehmen.  
  
 SQL Server\-Datumswerte unterstützen keine <xref:System.TimeZone>, eine Funktion, die in der CLR große Bedeutung hat.  <xref:System.TimeZone>\-Werte werden ohne <xref:System.TimeZone>\-Umwandlung in der Datenbank gespeichert, unabhängig von den ursprünglichen <xref:System.DateTimeKind>\-Informationen.  Werden <xref:System.DateTime>\-Werte aus der Datenbank abgerufen, werden diese wie in <xref:System.DateTime> mit einer <xref:System.DateTimeKind> von <xref:System.DateTimeKind> geladen.  Weitere Informationen zu unterstützten <xref:System.DateTime?displayProperty=fullName>\-Methoden finden Sie unter [System.DateTime\-Methoden](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md).  
  
### System.TimeSpan  
 Mit Microsoft SQL Server 2008 und .NET Framework 3.5 SP1 kann der CLR\-Typ <xref:System.TimeSpan?displayProperty=fullName> dem SQL Server\-Typ `TIME` zugeordnet werden.  Es gibt jedoch große Unterschiede im von dem CLR\-Typ <xref:System.TimeSpan?displayProperty=fullName> und dem SQL Server\-Typ `TIME` unterstützten Bereich.  Das Mapping von Stundenwerten kleiner als 0 oder größer als 23:59:59.9999999 zum SQL\-Typ `TIME` hat Überlaufausnahmen zur Folge.  Weitere Informationen finden Sie unter [System.TimeSpan\-Methoden](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md).  
  
 In Microsoft SQL Server 2000 und SQL Server 2005 können <xref:System.TimeSpan> keine Datenbankfelder zugeordnet werden.  Dennoch werden Operationen für <xref:System.TimeSpan> unterstützt, da <xref:System.TimeSpan>\-Werte von <xref:System.DateTime>\-Subtraktionen zurückgegeben oder als Literal oder gebundene Variable in einen Ausdruck integriert werden können.  
  
<a name="BinaryMapping"></a>   
## Binäres Mapping  
 Es gibt mehrere SQL Server\-Typen, die dem CLR\-Typ <xref:System.Data.Linq.Binary?displayProperty=fullName> zugeordnet werden können.  In der folgenden Tabelle sind die SQL Server\-Typen aufgeführt, für die von O\/R\-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei der CLR\-Typ <xref:System.Data.Linq.Binary?displayProperty=fullName> definiert wird.  
  
|SQL Server\-Typ|Von O\/R\-Designer und SQLMetal verwendetes CLR\-Standardtypmapping|  
|---------------------|-------------------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`VARBINARY(MAX)` mit dem Attribut `FILESTREAM`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=fullName>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode verwendet werden, um festzulegen, welche Typen von SQL\-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR\-Typen erstellt werden.  
  
|CLR\-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> verwendeter Standard\-SQL Server\-Typ|  
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=fullName>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=fullName>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>|`VARBINARY(MAX)`|  
  
 Es können viele andere binäre Mappings ausgewählt werden. Einige davon können jedoch bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen.  Weitere Informationen finden Sie unter [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix).  
  
### SQL Server FILESTREAM  
 Das `FILESTREAM`\-Attribut für `VARBINARY(MAX)`\-Spalten ist seit Microsoft SQL Server 2008 verfügbar. Dieses Attribut kann ab .NET Framework Version 3.5 SP1 mit LINQ to SQL zugeordnet werden.  
  
 Obwohl `VARBINARY(MAX)`\-Spalten mit dem `FILESTREAM`\-Attribut <xref:System.Data.Linq.Binary>\-Objekten zugeordnet werden können, können von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode keine Spalten mit dem `FILESTREAM`\-Attribut automatisch erstellt werden.  Weitere Informationen über `FILESTREAM` finden Sie in der Microsoft SQL Server\-Onlinedokumentation unter [Übersicht über FILESTREAM](http://go.microsoft.com/fwlink/?LinkId=115291).  
  
<a name="BinarySerialization"></a>   
### Binäre Serialisierung  
 Wenn eine Klasse die <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle implementiert, kann ein Objekt in ein beliebiges binäres SQL\-Feld \(`BINARY`, `VARBINARY`, `IMAGE`\) serialisiert werden.  Das Objekt wird je nach Implementierung der <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle serialisiert und deserialisiert.  Weitere Informationen finden Sie unter [Binäre Serialisierung](http://go.microsoft.com/fwlink/?LinkId=115581).  
  
<a name="MiscMapping"></a>   
## Verschiedene Mappingtypen  
 In der folgenden Tabelle sind die Standardtypmappings für verschiedene Typen aufgeführt, die noch nicht erwähnt wurden.  Die Tabelle enthält auch die CLR\-Typen, die von O\/R\-Designer und SQLMetal für die auf einer bestehenden Datenbank basierende Erstellung eines Objektmodells oder einer externen Mappingdatei ausgewählt werden.  
  
|SQL Server\-Typ|Von O\/R\-Designer und SQLMetal verwendetes CLR\-Standardtypmapping|  
|---------------------|-------------------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=fullName>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=fullName>|  
  
 In der nächsten Tabelle werden die Standardtypmappings angezeigt, die von der <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName>\-Methode verwendet werden, um festzulegen, welche Typen von SQL\-Spalten für die Zuordnung zu den im Objektmodell oder der externen Mappingdatei definierten CLR\-Typen erstellt werden.  
  
|CLR\-Typ|Von <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=fullName> verwendeter Standard\-SQL Server\-Typ|  
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=fullName>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=fullName>|`SQL_VARIANT`|  
  
 LINQ to SQL unterstützt keine anderen Typmappings für diese Typen.  Weitere Informationen finden Sie unter [Laufzeitverhaltens\-Matrix des Typmappings](#BehaviorMatrix).  
  
## Siehe auch  
 [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)   
 [Externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)   
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)   
 [SQL\-CLR\-Typenkonflikte](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)