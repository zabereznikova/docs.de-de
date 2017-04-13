---
title: "Konfigurieren von Parametern und Parameterdatentypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 537d8a2c-d40b-4000-83eb-bc1fcc93f707
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Konfigurieren von Parametern und Parameterdatentypen
Befehlsobjekte verwenden Parameter, um Werte an SQL\-Anweisungen oder gespeicherte Prozeduren zu übergeben, und ermöglichen so Typüberprüfungen und Validierungen. Im Unterschied zu Befehlstext wird die Parametereingabe als Literalwert und nicht als ausführbarer Code behandelt. Dies hilft beim Schutz vor SQL Injection\-Angriffen, bei denen ein Angreifer einen SQL\-Befehl, der die Sicherheit auf dem Server gefährdet, in eine SQL\-Anweisung einschleust.  
  
 Parametrisierte Befehle können außerdem die Leistung bei der Abfrageausführung verbessern, da sie den Datenbankserver dabei unterstützen, den eingehenden Befehl mit dem richtigen zwischengespeicherten Abfrageplan abzugleichen. Weitere Informationen finden Sie unter [Zwischenspeichern und Wiederverwenden von Ausführungsplänen](http://go.microsoft.com/fwlink/?LinkId=120424) und [Parameter und Wiederverwendung von Ausführungsplänen](http://go.microsoft.com/fwlink/?LinkId=120423) in der SQL Server\-Onlinedokumentation. Parametrisierte Befehle sind aber nicht nur aus Sicherheits\- und Leistungsgründen vorteilhaft, sondern sie stellen auch eine bequeme Methode zum Organisieren von Werten dar, die an eine Datenquelle übergeben werden.  
  
 Ein <xref:System.Data.Common.DbParameter>\-Objekt kann mithilfe des zugehörigen Konstruktors erstellt werden, oder es wird durch Aufrufen der <xref:System.Data.Common.DbCommand.DbParameterCollection%2A>\-Methode der `Add`\-Auflistung zur <xref:System.Data.Common.DbParameterCollection> hinzugefügt. Die `Add`\-Methode verwendet als Eingabe je nach Datenanbieter Konstruktorargumente oder ein vorhandenes Parameterobjekt.  
  
## Bereitstellen der "ParameterDirection"\-Eigenschaft  
 Beim Hinzufügen von Parametern müssen Sie für alle Parameter, die keine Eingabeparameter sind, die <xref:System.Data.ParameterDirection>\-Eigenschaft bereitstellen. Die folgende Tabelle zeigt die `ParameterDirection`\-Werte, die Sie mit der <xref:System.Data.ParameterDirection>\-Enumeration verwenden können.  
  
|Membername|Beschreibung|  
|----------------|------------------|  
|<xref:System.Data.ParameterDirection>|Der Parameter ist ein Eingabeparameter. Dies ist die Standardeinstellung.|  
|<xref:System.Data.ParameterDirection>|Der Parameter kann sowohl für die Eingabe als auch für die Ausgabe verwendet werden.|  
|<xref:System.Data.ParameterDirection>|Der Parameter ist ein Ausgabeparameter.|  
|<xref:System.Data.ParameterDirection>|Der Parameter steht für einen Eingabewert aus einem Vorgang, wie z. B. einer gespeicherten Prozedur, einer integrierten Funktion oder einer benutzerdefinierten Funktion.|  
  
## Arbeiten mit Parameterplatzhaltern  
 Die Syntax für Parameterplatzhalter ist abhängig von der jeweiligen Datenquelle. Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter handhaben die Benennung und das Angeben von Parametern und Parameterplatzhaltern unterschiedlich. Diese Syntax wird an eine bestimmte Datenquelle angepasst, wie in der folgenden Tabelle beschrieben.  
  
|Datenanbieter|Syntax für Parameterbenennung|  
|-------------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|Verwendet benannte Parameter im Format `@`*Parametername*.|  
|<xref:System.Data.OleDb>|Verwendet Positionsparametermarker, die durch ein Fragezeichen \(`?`\) gekennzeichnet sind.|  
|<xref:System.Data.Odbc>|Verwendet Positionsparametermarker, die durch ein Fragezeichen \(`?`\) gekennzeichnet sind.|  
|<xref:System.Data.OracleClient>|Verwendet benannte Parameter im Format `:`*Parametername* \(oder *Parametername*\).|  
  
## Angeben von Parameterdatentypen  
 Der Datentyp eines Parameters ist abhängig vom [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter. Durch Angabe des Typs wird der Wert von `Parameter` in den Typ des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieters konvertiert, bevor er an die Datenquelle übergeben wird. Der Typ eines `Parameter` kann auch in generischer Form angegeben werden, indem die `DbType`\-Eigenschaft des `Parameter`\-Objekts auf einen bestimmten <xref:System.Data.DbType> festgelegt wird.  
  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbietertyp eines `Parameter`\-Objekts wird vom [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ des `Value` des `Parameter`\-Objekts oder vom `DbType` des `Parameter`\-Objekts hergeleitet. Die folgende Tabelle zeigt den abgeleiteten `Parameter`\-Typ basierend auf dem als `Parameter`\-Wert übergebenen Objekt oder dem angegebenen `DbType`.  
  
|.NET Framework\-Typ|DbType|SqlDbType|OleDbType|OdbcType|OracleType|  
|-------------------------|------------|---------------|---------------|--------------|----------------|  
|<xref:System.Boolean>|Boolesch|Bit|Boolean|Bit|Byte|  
|<xref:System.Byte>|Byte|TinyInt|UnsignedTinyInt|TinyInt|Byte|  
|byte\[\]|Binär|VarBinary`.` Diese implizite Konvertierung kann nicht ausgeführt werden, wenn das Bytearray größer als die maximal zulässige Größe eines VarBinary \(8000 Bytes\) ist. Legen Sie für Bytearrays mit mehr als 8000 Bytes explizit <xref:System.Data.SqlDbType> fest.|VarBinary|Binär|Raw|  
|<xref:System.Char>|``|Das Ableiten von <xref:System.Data.SqlDbType> aus char wird nicht unterstützt.|Char|Char|Byte|  
|<xref:System.DateTime>|DateTime|DateTime|DBTimeStamp|DateTime|DateTime|  
|<xref:System.DateTimeOffset>|DateTimeOffset|"DateTimeOffset" in SQL Server 2008. Das Ableiten von <xref:System.Data.SqlDbType> aus DateTimeOffset wird erst ab SQL Server 2008 unterstützt.|||DateTime|  
|<xref:System.Decimal>|Decimal|Decimal|Decimal|Numeric|Nummer|  
|<xref:System.Double>|Double|Float|Double|Double|Double|  
|<xref:System.Single>|Single|Real|Single|Real|Float|  
|<xref:System.Guid>|Guid|UniqueIdentifier|Guid|UniqueIdentifier|Raw|  
|<xref:System.Int16>|Int16|SmallInt|SmallInt|SmallInt|Int16|  
|<xref:System.Int32>|Int32|Int|Int|Int|Int32|  
|<xref:System.Int64>|Int64|BigInt|BigInt|BigInt|Nummer|  
|<xref:System.Object>|Objekt|Variante|Variante|Das Ableiten von OdbcType aus Object wird nicht unterstützt.|Blob|  
|<xref:System.String>|Zeichenfolge|NVarChar. Diese implizite Konvertierung kann nicht ausgeführt werden, wenn die Zeichenfolge die maximale NVarChar\-Länge \(4000 Zeichen\) überschreitet. Legen Sie für Zeichenfolgen mit mehr als 4000 Zeichen explizit <xref:System.Data.SqlDbType> fest.|VarWChar|NVarChar|NVarChar|  
|<xref:System.TimeSpan>|zeit|"Time" in SQL Server 2008. Das Ableiten von <xref:System.Data.SqlDbType> aus TimeSpan wird erst ab SQL Server 2008 unterstützt.|DBTime|zeit|DateTime|  
|<xref:System.UInt16>|UInt16|Das Ableiten von <xref:System.Data.SqlDbType> aus UInt16 wird nicht unterstützt.|UnsignedSmallInt|Int|UInt16|  
|<xref:System.UInt32>|UInt32|Das Ableiten von <xref:System.Data.SqlDbType> aus UInt32 wird nicht unterstützt.|UnsignedInt|BigInt|UInt32|  
|<xref:System.UInt64>|UInt64|Das Ableiten von <xref:System.Data.SqlDbType> aus UInt64 wird nicht unterstützt.|UnsignedBigInt|Numeric|Nummer|  
||AnsiString|VarChar|VarChar|VarChar|VarChar|  
||AnsiStringFixedLength|Char|Char|Char|Char|  
|``|Währung|Money|Währung|Das Ableiten von `OdbcType` aus `Currency` wird nicht unterstützt.|Nummer|  
|``|Datum|"Date" in SQL Server 2008. Das Ableiten von <xref:System.Data.SqlDbType> aus Date wird erst ab SQL Server 2008 unterstützt.|DBDate|Datum|DateTime|  
|``|SByte|Das Ableiten von <xref:System.Data.SqlDbType> aus SByte wird nicht unterstützt.|TinyInt|Das Ableiten von `OdbcType` aus SByte wird nicht unterstützt.|SByte|  
||StringFixedLength|NChar|WChar|NChar|NChar|  
||zeit|"Time" in SQL Server 2008. Das Ableiten von <xref:System.Data.SqlDbType> aus Time wird erst ab SQL Server 2008 unterstützt.|DBTime|zeit|DateTime|  
||VarNumeric|Das Ableiten von <xref:System.Data.SqlDbType> aus VarNumeric wird nicht unterstützt.|VarNumeric|Das Ableiten von `OdbcType` aus VarNumeric wird nicht unterstützt.|Nummer|  
|Benutzerdefinierter Typ \(ein Objekt mit <xref:Microsoft.SqlServer.Server.SqlUserDefinedAggregateAttribute>\)|Object oder String, je nach Anbieter \(SqlClient gibt immer ein Objekt zurück, ODBC immer eine Zeichenfolge, und der verwaltete OLE DB\-Datenanbieter ist in der Lage, beide zu erkennen\).|SqlDbType.Udt, wenn <xref:Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute> vorhanden ist; andernfalls Variant|OleDbType.VarWChar \(wenn der Wert NULL ist\); andernfalls OleDbType.Variant.|OdbcType.NVarChar|wird nicht unterstützt|  
  
> [!NOTE]
>  Beim Konvertieren von "decimal" in einen anderen Typ erhalten Sie nur eine annähernde Entsprechung, da der Wert auf die nächste Ganzzahl abgerundet wird. Wenn das Ergebnis der Konvertierung im Zieltyp nicht darstellbar ist, wird eine <xref:System.OverflowException> ausgelöst.  
  
> [!NOTE]
>  Wenn Sie einen NULL\-Parameterwert an den Server senden, muss nicht <xref:System.DBNull>, sondern `null` angegeben werden \(`Nothing` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\). Der NULL\-Wert im System ist ein leeres Objekt, das über keinen Wert verfügt.<xref:System.DBNull> wird zur Darstellung von NULL\-Werten verwendet. Weitere Informationen zu NULL\-Werten bei Datenbanken finden Sie unter [Behandeln von NULL\-Werten](../../../../docs/framework/data/adonet/sql/handling-null-values.md).  
  
## Ableiten von Parameterinformationen  
 Parameter können auch mit der `DbCommandBuilder`\-Klasse aus einer gespeicherten Prozedur abgeleitet werden. Sowohl die `SqlCommandBuilder`\-Klasse als auch die `OleDbCommandBuilder`\-Klasse stellen die statische Methode `DeriveParameters` bereit, die automatisch die Parameterauflistung eines Befehlsobjekts füllt, das Parameterinformationen aus einer gespeicherten Prozedur verwendet. Beachten Sie, dass `DeriveParameters` alle vorhandenen Parameterinformationen für den Befehl überschreibt.  
  
> [!NOTE]
>  Das Ableiten von Parameterinformationen geht mit einem Leistungsverlust einher, weil zum Abrufen der Informationen ein zusätzlicher Roundtrip durch die Datenquelle erforderlich ist. 	Wenn die Parameterinformationen zur Entwurfszeit bekannt sind, können Sie die Leistung der Anwendung verbessern, indem Sie die Parameter explizit festlegen.  
  
 Weitere Informationen finden Sie unter [Generieren von Befehlen mit 'CommandBuilder'\-Objekten](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md).  
  
## Verwenden von Parametern mit einem "SqlCommand" und einer gespeicherten Prozedur  
 Gespeicherte Prozeduren bieten zahlreiche Vorteile in datengesteuerten Anwendungen. Mit gespeicherten Prozeduren können Datenbankoperationen in einem einzelnen Befehl zusammengefasst, für die beste Leistung optimiert und mit zusätzlicher Sicherheit ausgestattet werden. Während eine gespeicherte Prozedur problemlos aufgerufen werden kann, indem der Name der gespeicherten Prozedur gefolgt von Parameterargumenten als SQL\-Anweisung übergeben wird, ermöglicht die Verwendung der <xref:System.Data.Common.DbCommand.Parameters%2A>\-Auflistung des [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]\-Objekts von <xref:System.Data.Common.DbCommand> eine genauere Definition der Parameter der gespeicherten Prozedur sowie den Zugriff auf Ausgabeparameter und Rückgabewerte.  
  
> [!NOTE]
>  Parametrisierte Anweisungen werden auf dem Server mit `sp_executesql,` ausgeführt, sodass die Wiederverwendung von Abfrageplänen möglich ist. Lokale Cursor oder Variablen im `sp_executesql`\-Batch sind für den Batch, der `sp_executesql` aufruft, nicht sichtbar. Änderungen am Datenbankkontext sind nur bis zum Ende der `sp_executesql`\-Anweisung gültig. Weitere Informationen dazu finden Sie in der SQL Server\-Onlinedokumentation.  
  
 Wenn Sie Parameter mit einem <xref:System.Data.SqlClient.SqlCommand> verwenden, um eine gespeicherte SQL Server\-Prozedur auszuführen, müssen die der <xref:System.Data.SqlClient.SqlCommand.Parameters%2A>\-Auflistung hinzugefügten Parameternamen mit den Namen der Parametermarkierungen in der gespeicherten Prozedur übereinstimmen. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter für SQL Server unterstützt keine Fragezeichenplatzhalter \(?\) für die Übergabe von Parametern an eine SQL\-Anweisung oder gespeicherte Prozedur. Er behandelt die Parameter in der gespeicherten Prozedur als benannte Parameter und sucht nach den entsprechenden Parametermarkierungen. Nehmen wir z. B. an, die gespeicherte Prozedur `CustOrderHist` ist mit einem Parameter mit dem Namen `@CustomerID` definiert. Wenn Ihr Code die gespeicherte Prozedur ausführt, muss er ebenfalls einen Parameter mit dem Namen `@CustomerID` verwenden.  
  
```  
CREATE PROCEDURE dbo.CustOrderHist @CustomerID varchar(5)  
```  
  
### Beispiel  
 Dieses Beispiel zeigt, wie Sie eine gespeicherte SQL Server\-Prozedur in der `Northwind`\-Beispieldatenbank aufrufen können. Der Name der gespeicherten Prozedur ist `dbo.SalesByCategory`, und die Prozedur besitzt einen Eingabeparameter mit dem Namen `@CategoryName` und dem Datentyp `nvarchar(15)`. Der Code erstellt eine neue <xref:System.Data.SqlClient.SqlConnection> innerhalb eines verwendeten Blocks, sodass die Verbindung nach dem Ende der Prozedur verworfen wird. Es werden die Objekte <xref:System.Data.SqlClient.SqlCommand> und <xref:System.Data.SqlClient.SqlParameter> erstellt, und deren Eigenschaften werden festgelegt. Ein <xref:System.Data.SqlClient.SqlDataReader> führt den `SqlCommand` aus und gibt den Resultset aus der gespeicherten Prozedur zurück, wobei die Ausgabe im Konsolenfenster angezeigt wird.  
  
> [!NOTE]
>  Statt die Objekte `SqlCommand` und `SqlParameter` zu erstellen und dann die Eigenschaften in separaten Anweisungen festzulegen, können Sie auch mit einem der überladenen Konstruktoren mehrere Eigenschaften in einer einzigen Anweisung festlegen.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
## Verwenden von Parametern mit einem "OleDbCommand" oder "OdbcCommand"  
 Wenn Sie Parameter mit einem <xref:System.Data.OleDb.OleDbCommand> oder einem <xref:System.Data.Odbc.OdbcCommand> verwenden, muss die Reihenfolge der der `Parameters`\-Auflistung hinzugefügten Parameter mit der Reihenfolge der in der gespeicherten Prozedur definierten Parameter übereinstimmen. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter für OLE DB und der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter für ODBC behandeln Parameter in einer gespeicherten Prozedur als Platzhalter und wenden Parameterwerte der Reihe nach an. Außerdem müssen der `Parameters`\-Auflistung zuerst die Parameter für die Rückgabewerte hinzugefügt werden.  
  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter für OLE DB und der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter für ODBC unterstützen keine benannten Parameter für die Übergabe von Parametern an eine SQL\-Anweisung oder gespeicherte Prozedur. In diesem Fall muss der Fragezeichenplatzhalter \(?\) verwenden. Dies wird im folgenden Beispiel dargestellt.  
  
```  
SELECT * FROM Customers WHERE CustomerID = ?  
```  
  
 Dementsprechend muss die Reihenfolge, in der `Parameter`\-Objekte der `Parameters`\-Auflistung hinzugefügt werden, genau der Position des als Platzhalter für den Parameter fungierenden Fragezeichens \(?\) entsprechen.  
  
### OLE DB\-Beispiel  
  
```vb  
Dim command As OleDbCommand = New OleDbCommand( _  
  "SampleProc", connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As OleDbParameter = command.Parameters.Add( _  
  "RETURN_VALUE", OleDbType.Integer)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@InputParm", OleDbType.VarChar, 12)  
parameter.Value = "Sample Value"  
  
parameter = command.Parameters.Add( _  
  "@OutputParm", OleDbType.VarChar, 28)  
parameter.Direction = ParameterDirection.Output  
```  
  
```csharp  
OleDbCommand command = new OleDbCommand("SampleProc", connection);  
command.CommandType = CommandType.StoredProcedure;  
  
OleDbParameter parameter = command.Parameters.Add(  
  "RETURN_VALUE", OleDbType.Integer);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@InputParm", OleDbType.VarChar, 12);  
parameter.Value = "Sample Value";  
  
parameter = command.Parameters.Add(  
  "@OutputParm", OleDbType.VarChar, 28);  
parameter.Direction = ParameterDirection.Output;  
```  
  
## Beispiel zu "Odbc"  
  
```vb  
Dim command As OdbcCommand = New OdbcCommand( _  
  "{ ? = CALL SampleProc(?, ?) }", connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As OdbcParameter = command.Parameters.Add("RETURN_VALUE", OdbcType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@InputParm", OdbcType.VarChar, 12)  
parameter.Value = "Sample Value"  
  
parameter = command.Parameters.Add( _  
  "@OutputParm", OdbcType.VarChar, 28)  
parameter.Direction = ParameterDirection.Output  
```  
  
```csharp  
OdbcCommand command = new OdbcCommand( _  
  "{ ? = CALL SampleProc(?, ?) }", connection);  
command.CommandType = CommandType.StoredProcedure;  
  
OdbcParameter parameter = command.Parameters.Add( _  
  "RETURN_VALUE", OdbcType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add( _  
  "@InputParm", OdbcType.VarChar, 12);  
parameter.Value = "Sample Value";  
  
parameter = command.Parameters.Add( _  
  "@OutputParm", OdbcType.VarChar, 28);  
parameter.Direction = ParameterDirection.Output;  
```  
  
## Siehe auch  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 ['DataAdapter'\-Parameter](../../../../docs/framework/data/adonet/dataadapter-parameters.md)   
 [Datentypzuordnungen in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)   
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)