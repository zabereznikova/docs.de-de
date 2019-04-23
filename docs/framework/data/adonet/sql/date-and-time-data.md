---
title: Datums- und Zeitdaten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: 80b7df4922e1398c7290e769e53627a1d46ebc83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344173"
---
# <a name="date-and-time-data"></a>Datums- und Zeitdaten
SQL Server 2008 enthält neue Datentypen zur Behandlung von Datums- und Uhrzeitinformationen. Die neuen Datentypen beinhalten separate Typen für Datum und Uhrzeit sowie erweiterte Datentypen mit einem größerem Bereich, höherer Präzision und Zeitzonenermittlung. Ab .NET Framework Version 3.5 Service Pack (SP) 1 bietet der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) vollständige Unterstützung für alle neuen Funktionen der SQL Server 2008-Datenbank-Engine. Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um diese neuen Funktionen mit SqlClient zu verwenden.  
  
 Versionen von SQL Server vor SQL Server 2008 verfügten nur über zwei Datentypen für Datums- und Uhrzeitwerte: `datetime` und `smalldatetime`. Diese beiden Datentypen enthalten sowohl einen Datumswert als auch einen Uhrzeitwert. Dadurch macht es schwierig, nur mit den Datums- oder nur mit den Uhrzeitwerten zu arbeiten. Außerdem werden nur Datumsangaben nach Einführung des gregorianischen Kalenders in England im Jahr 1753 unterstützt. Weiterhin berücksichtigen diese älteren Datums- und Uhrzeitdatentypen nicht die Zeitzone und erschweren dadurch das Arbeiten mit Daten aus verschiedenen Zeitzonen.  
  
 Die vollständige Dokumentation für SQL Server-Datentypen ist in der SQL Server-Onlinedokumentation verfügbar. In der folgenden Tabelle sind die versionsspezifischen Einsteigerthemen für Datums- und Uhrzeitdaten aufgeführt.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1. [Verwenden von Datums- und Zeitdaten](https://go.microsoft.com/fwlink/?LinkID=98361)  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a>Neue Datums-/Uhrzeitdaten in SQL Server 2008  
 In der folgenden Tabelle werden die neuen Datums- und Uhrzeitdatentypen beschrieben.  
  
|SQL Server-Datentyp|Beschreibung|  
|--------------------------|-----------------|  
|`date`|Der Bereich der gültigen Werte für den `date`-Datentyp reicht vom 1. Januar 0001 bis zum 31. Dezember 9999 mit einer Genauigkeit von einem Tag. Der Standardwert ist der 1. Januar 1900. Die Speichergröße beträgt 3 Bytes.|  
|`time`|Der `time`-Datentyp speichert reine Uhrzeitwerte im 24-Stunden-Format. Der Bereich der gültigen Werte des `time`-Datentyps reicht von 00:00:00.0000000 bis 23:59:59.9999999 mit einer Genauigkeit von 100 Nanosekunden. Der Standardwert ist 00:00:00.0000000 Uhr, also Mitternacht. Der `time`-Datentyp unterstützt eine benutzerdefinierte Genauigkeit der Sekundenbruchteile, und die Speichergröße variiert je nach angegebener Genauigkeit zwischen 3 und 6 Bytes.|  
|`datetime2`|Der `datetime2`-Datentyp fasst den Gültigkeitsbereich und die Genauigkeit der Datentypen `date` und `time` in einem Datentyp zusammen.<br /><br /> Die Standardwerte und Formate der Zeichenfolgenliterale sind identisch mit denen der Datentypen `date` und `time`.|  
|`datetimeoffset`|Der `datetimeoffset`-Datentyp verfügt über alle Funktionen von `datetime2` und über einen zusätzlichen Zeitzonenoffset. Der Zeitzonenoffset wird als [+&#124;-] hh: mm. "HH" sind zwei Ziffern im Bereich von 00 bis 14, die für die Anzahl der Stunden in der Zeitzonenangabe stehen. "MM" sind zwei Ziffern im Bereich von 00 bis 59, die zur Angabe der zusätzlichen Minuten in der Zeitzonenangabe dienen. Uhrzeitformate werden mit einer Genauigkeit von bis zu 100 Nanosekunden unterstützt. Das obligatorische Pluszeichen (+) oder Minuszeichen (-) in der Zeitzonenangabe gibt an, ob der jeweilige Wert zum UTC-Wert (Universal Time Coordinate, koordinierte Weltzeit, auch als "Greenwich Mean Time" bekannt) addiert oder von diesem subtrahiert werden muss, um die lokale Uhrzeit zu ermitteln.|  
  
> [!NOTE]
>  Weitere Informationen zur Verwendung des `Type System Version`-Schlüsselworts finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## <a name="date-format-and-date-order"></a>Datumsformat und Datumsreihenfolge  
 Wie Datums- und Zeitwerte von SQL Server analysiert werden, ist nicht nur von der Typsystemversion und der Serverversion abhängig, sondern auch von der Standardsprache und den Formateinstellungen des Servers. Eine Datumszeichenfolge, die für die Datumsformate einer bestimmten Sprache funktioniert, ist eventuell nicht erkennbar, wenn die Abfrage von einer Verbindung mit anderen Einstellungen für Sprache und Datumsformat ausgeführt wird.  
  
 Die Transact-SQL SET LANGUAGE-Anweisung legt das DATEFORMAT, das die Reihenfolge der Datumsteile bestimmt, implizit fest. Sie können die Transact-SQL-Anweisung SET DATEFORMAT für eine Verbindung verwenden, um Datumswerte eindeutig zu bestimmen, indem die Datumsteile in MDY-, DMY-, YMD-, YDM-, MYD- oder DYM-Reihenfolge sortiert werden.  
  
 Wenn Sie kein DATEFORMAT für die Verbindung angeben, verwendet SQL Server die der Verbindung zugewiesene Standardsprache. So wird beispielsweise eine Datumszeichenfolge von '01/02/03' auf einem Server mit Spracheinstellung "Englisch (USA)" als MDY (2. Januar 2003) und auf einem Server mit Englisch (britisch) als DMY (1. Februar 2003) interpretiert. Das Jahr wird durch die Umstellungsjahrregel von SQL Server festgestellt, die das Umstellungsdatum zum Zuweisen des Jahrhundertwerts definiert. Weitere Informationen finden Sie unter [Option der Wert von two Digit Year cutoff](https://go.microsoft.com/fwlink/?LinkId=120473) in SQL Server-Onlinedokumentation.  
  
> [!NOTE]
>  Das YDM-Datumsformat wird bei der Konvertierung von einem Zeichenfolgenformat in `date`, `time`, `datetime2` oder `datetimeoffset` nicht unterstützt.  
  
 Weitere Informationen zur Interpretation von Datums-und Uhrzeitdaten in SQL Server finden Sie unter [Verwenden von Datums- und Zeitdaten](https://go.microsoft.com/fwlink/?LinkID=98361) in SQL Server 2008-Onlinedokumentation.  
  
## <a name="datetime-data-types-and-parameters"></a>Datentypen und Parameter zur Angabe von Datum und Uhrzeit  
 Zur Unterstützung der neuen Datums- und Uhrzeitdatentypen wurden <xref:System.Data.SqlDbType> die folgenden Enumerationen hinzugefügt:  
  
-   `SqlDbType.Date`  
  
-   `SqlDbType.Time`  
  
-   `SqlDbType.DateTime2`  
  
-   `SqlDbType.DateTimeOffSet`  

Sie können angeben, den den Datentyp des einen <xref:System.Data.SqlClient.SqlParameter> mithilfe eines der vorangehenden <xref:System.Data.SqlDbType> Enumerationen. 

> [!NOTE]
> Kann nicht festgelegt werden die `DbType` Eigenschaft eine `SqlParameter` zu `SqlDbType.Date`.

 Sie können den Typ eines <xref:System.Data.SqlClient.SqlParameter> auch generisch angeben, indem Sie die <xref:System.Data.SqlClient.SqlParameter.DbType%2A>-Eigenschaft eines `SqlParameter`-Objekts auf einen bestimmten <xref:System.Data.DbType>-Enumerationswert festlegen. Zur Unterstützung der Datentypen <xref:System.Data.DbType> und `datetime2` wurden `datetimeoffset` die im Folgenden aufgeführten Enumerationswerte hinzugefügt.  
  
-   DbType.DateTime2  
  
-   DbType.DateTimeOffset  
  
 Diese neuen Enumerationen ergänzen die Enumerationen `Date`, `Time` und `DateTime`, die bereits in früheren .NET Framework-Versionen vorhanden waren.  
  
 Der .NET Framework-Datenanbietertyp eines Parameterobjekts wird vom .NET Framework-Typ des Werts des Parameterobjekts oder vom `DbType` des Parameterobjekts hergeleitet. Zur Unterstützung der neuen Datums- und Uhrzeitdatentypen wurden keine neuen <xref:System.Data.SqlTypes>-Datentypen hinzugefügt. Der folgenden Tabelle können Sie die Zuordnungen zwischen den Datentypen für die Datums- und Uhrzeitangabe in SQL Server 2008 und den entsprechenden CLR-Typen entnehmen.  
  
|SQL Server-Datentyp|.NET Framework-Typ|System.Data.SqlDbType|System.Data.DbType|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|date|System.DateTime|Datum|Datum|  
|Uhrzeit|System.TimeSpan|zeit|zeit|  
|datetime2|System.DateTime|DateTime2|DateTime2|  
|datetimeoffset|System.DateTimeOffset|DateTimeOffset|DateTimeOffset|  
|datetime|System.DateTime|DateTime|DateTime|  
|smalldatetime|System.DateTime|DateTime|DateTime|  
  
### <a name="sqlparameter-properties"></a>SqlParameter-Eigenschaften  
 In der folgenden Tabelle werden die für Datums- und Uhrzeitdatentypen relevanten `SqlParameter`-Eigenschaften beschrieben.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|Ruft ab oder legt fest, ob ein NULL-Wert zulässig ist. Wenn Sie einen NULL-Parameterwert an den Server senden, müssen Sie <xref:System.DBNull> und nicht `null` (in Visual Basic `Nothing`) angeben. Weitere Informationen zu NULL-Werten bei Datenbanken finden Sie unter [Handling Null Values](../../../../../docs/framework/data/adonet/sql/handling-null-values.md).|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|Legt die maximale Anzahl von Ziffern fest, die zur Darstellung des Werts verwendet werden, oder ruft diese ab. Diese Einstellung wird für Datums- und Uhrzeitdatentypen ignoriert.|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|Übernimmt oder bestimmt die Anzahl der Dezimalstellen, der Uhrzeitteil des Werts für aufgelöst wird `Time`, `DateTime2`, und `DateTimeOffset`. Der Standardwert ist 0, d. h., dass die tatsächliche Skalierung aus dem Wert hergeleitet und an den Server gesendet wird.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Dies wird für Datums- und Uhrzeitdatentypen ignoriert.|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Ruft den Parameterwert ab oder legt diesen fest.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Ruft den Parameterwert ab oder legt diesen fest.|  
  
> [!NOTE]
>  Zeitwerte, die kleiner als 0 bzw. größer als oder gleich 24 Stunden sind, lösen eine <xref:System.ArgumentException> aus.  
  
### <a name="creating-parameters"></a>Erstellen von Parametern  
 Sie können ein <xref:System.Data.SqlClient.SqlParameter>-Objekt erstellen, indem Sie dessen Konstruktor verwenden, oder Sie fügen es zu einer <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A>-Auflistung hinzu, indem Sie die `Add`-Methode der <xref:System.Data.SqlClient.SqlParameterCollection> aufrufen. Die `Add`-Methode akzeptiert entweder Konstruktorargumente oder ein bestehendes Parameterobjekt als Eingabe.  
  
 Die nächsten Abschnitte in diesem Thema enthalten Beispiele über das Angeben von Datums- und Uhrzeitparametern. Weitere Beispiele zum Arbeiten mit Parametern, finden Sie unter [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md) und [DataAdapter-Parameter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md).  
  
### <a name="date-example"></a>Datumsbeispiel  
 Das folgende Codefragment zeigt, wie ein `date`-Parameter festgelegt wird.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a>Uhrzeitbeispiel  
 Das folgende Codefragment zeigt, wie ein `time`-Parameter festgelegt wird.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a>Datetime2-Beispiel  
 Das folgende Codefragment zeigt, wie ein `datetime2`-Parameter mit Datums- und Uhrzeitteilen festgelegt wird.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a>DateTimeOffSet-Beispiel  
 Das folgende Codefragment zeigt, wie ein `DateTimeOffSet`-Parameter mit einem Datum, einer Uhrzeit und einem Zeitzonenoffset von 0 festgelegt wird.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a>AddWithValue  
 Sie können Parameter auch wie im folgenden Codefragment dargestellt mithilfe der `AddWithValue`-Methode eines <xref:System.Data.SqlClient.SqlCommand>-Objekts angeben. Mit der `AddWithValue`-Methode können Sie jedoch nicht den <xref:System.Data.SqlClient.SqlParameter.DbType%2A> oder den <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> als Parameter festlegen.  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 Die `@date` Parameter zuordnen konnte eine `date`, `datetime`, oder `datetime2` -Datentyp auf dem Server. Wenn Sie mit den neuen `datetime`-Datentypen arbeiten, müssen Sie die <xref:System.Data.SqlDbType>-Eigenschaft des Parameters explizit auf den Datentyp der Instanz festlegen. Die Verwendung von <xref:System.Data.SqlDbType.Variant> oder die implizite Angabe von Parameterwerten kann Probleme bei der Abwärtskompatibilität mit den `datetime`- und `smalldatetime`-Datentypen verursachen.  
  
 In der folgende Tabelle ist dargestellt, welche `SqlDbTypes` von welchen CLR-Typen hergeleitet werden:  
  
|CLR-Typ|Hergeleiteter SqlDbType|  
|--------------|------------------------|  
|DateTime|SqlDbType.DateTime|  
|TimeSpan|SqlDbType.Time|  
|DateTimeOffset|SqlDbType.DateTimeOffset|  
  
## <a name="retrieving-date-and-time-data"></a>Abrufen von Datums- und Uhrzeitdaten  
 In der folgenden Tabelle werden Methoden zum Abrufen von Datums- und Uhrzeitwerten in SQL Server 2008 beschrieben.  
  
|SqlClient-Methode|Beschreibung|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|Ruft den angegebenen Spaltenwert als <xref:System.DateTime>-Struktur ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|Ruft den angegebenen Spaltenwert als <xref:System.DateTimeOffset>-Struktur ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|Gibt den zugrunde liegenden anbieterspezifischen Typ für das Feld zurück. Gibt dieselben Typen wie `GetFieldType` für neue Datums- und Uhrzeittypen zurück.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|Ruft den Wert der angegebenen Spalte ab. Gibt dieselben Typen wie `GetValue` für die neuen Datums- und Uhrzeittypen zurück.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|Ruft die Werte im angegebenen Array ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|Ruft den Spaltenwert als <xref:System.Data.SqlTypes.SqlString> ab. Wenn die Daten nicht als <xref:System.InvalidCastException> ausgedrückt werden können, wird eine `SqlString` ausgelöst.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|Ruft Spaltendaten als Standard-`SqlDbType` ab. Gibt dieselben Typen wie `GetValue` für die neuen Datums- und Uhrzeittypen zurück.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|Ruft die Werte im angegebenen Array ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|Ruft den Spaltenwert als Zeichenfolge ab, wenn die Typsystemversion auf SQL Server 2005 festgelegt ist. Wenn die Daten nicht als Zeichenfolge ausgedrückt werden können, wird eine <xref:System.InvalidCastException> ausgelöst.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|Ruft den angegebenen Spaltenwert als <xref:System.TimeSpan>-Struktur ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|Ruft den angegebenen Spaltenwert als dessen zugrunde liegenden CLR-Typ ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|Ruft Spaltenwerte in einem Array ab.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|Gibt eine <xref:System.Data.DataTable> zurück, die die Metadaten des Resultsets beschreibt.|  
  
> [!NOTE]
>  Die neuen `SqlDbTypes` für Datum und Uhrzeit bieten keine Unterstützung für Code, der prozessintern in SQL Server ausgeführt wird. Wird einer dieser Typen an den Server übergeben, wird eine Ausnahme ausgelöst.  
  
## <a name="specifying-date-and-time-values-as-literals"></a>Angeben von Datums- und Uhrzeitwerten als Literale  
 Sie können Datums- und Zeitdatentypen mithilfe einer Vielzahl unterschiedlicher Formate für Literalzeichenfolgen angeben, die von SQL Server anschließend zur Laufzeit ausgewertet und in interne Datums-/Zeitstrukturen konvertiert werden. SQL Server erkennt Datums- und Uhrzeitdaten, die in einfache Anführungszeichen (') eingeschlossen werden. In den folgenden Beispielen werden einige Formate veranschaulicht:  
  
-   Alphabetische Datumsformate, z. B. `'October 15, 2006'`.  
  
-   Numerische Datumsformate, beispielsweise `'10/15/2006'`.  
  
-   Unstrukturierte Zeichenfolgenformate, wie `'20061015'`. Dieses Format wird als 15. Oktober 2006 interpretiert, wenn Sie das ISO-Standarddatumsformat verwenden.  
  
> [!NOTE]
>  Eine vollständige Dokumentation zu allen Formaten für Literalzeichenfolgen und anderen Funktionen der Datums- und Zeitdatentypen finden Sie in der SQL Server-Onlinedokumentation.  
  
 Zeitwerte, die kleiner als 0 bzw. größer als oder gleich 24 Stunden sind, lösen eine <xref:System.ArgumentException> aus.  
  
## <a name="resources-in-sql-server-2008-books-online"></a>Ressourcen in der SQL Server 2008-Onlinedokumentation  
 Weitere Informationen zur Arbeit mit Datums- und Zeitwerten in SQL Server 2008 finden Sie in folgenden Ressourcen in der SQL Server 2008-Onlinedokumentation.  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Datums- und Uhrzeitdatentypen und zugehörige Funktionen (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=98360)|Bietet eine Übersicht über alle Transact-SQL-Datentypen und -Funktionen zur Angabe des Datums und der Uhrzeit.|  
|[Verwenden von Datums- und Zeitdaten](https://go.microsoft.com/fwlink/?LinkId=98361)|Enthält Informationen zu den Datentypen und Funktionen zur Angabe des Datums und der Uhrzeit sowie Beispiele für deren Verwendung.|  
|[Data Types (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=98362)|Beschreibt die Systemdatentypen in SQL Server 2008.|  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
