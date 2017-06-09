---
title: "Herstellen der Verbindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Herstellen der Verbindung
Zum Herstellen einer Verbindung mit Microsoft SQL Server verwenden Sie das <xref:System.Data.SqlClient.SqlConnection>\-Objekt des .NET Framework\-Datenanbieters für SQL Server.  Wenn Sie eine Verbindung mit einer OLE DB\-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.OleDb.OleDbConnection>\-Objekt des .NET Framework\-Datenanbieters für OLE DB.  Wenn Sie eine Verbindung mit einer ODBC\-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.Odbc.OdbcConnection>\-Objekt des .NET Framework\-Datenanbieters für ODBC.  Zum Herstellen einer Verbindung mit einer Oracle\-Datenquelle verwenden Sie das <xref:System.Data.OracleClient.OracleConnection>\-Objekt des .NET Framework\-Datenanbieters für Oracle.  Informationen zum sicheren Speichern und Abrufen von Verbindungszeichenfolgen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Schließen von Verbindungen  
 Es wird empfohlen, die Verbindung nach Verwendung stets zu schließen, damit sie in den Pool zurückgegeben werden kann.  Der `Using`\-Block in Visual Basic oder C\# verwirft automatisch die Verbindung, wenn der Code den Block verlässt, auch im Falle einer unbehandelten Ausnahme.  Weitere Informationen finden Sie unter [using\-Anweisung](../Topic/using%20Statement%20\(C%23%20Reference\).md) und [Using Statement](../Topic/Using%20Statement%20\(Visual%20Basic\).md).  
  
 Sie können ebenso die `Close`\-Methode oder `Dispose`\-Methode des Verbindungsobjekts des von Ihnen in Anspruch genommenen Anbieters verwenden.  Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise dem Pool nicht hinzugefügt bzw. nicht an den Pool zurückgegeben.  Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist.  Weitere Informationen finden Sie unter [OLE DB\-, ODBC\- und Oracle\-Verbindungspooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
>  Rufen Sie in der `Finalize`\-Methode der Klasse für eine **Connection**, einen **DataReader** oder andere verwaltete Objekte nie `Close` oder `Dispose` auf.  Geben Sie in einer Finalize\-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.  Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`\-Methode.  Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
> [!NOTE]
>  Wenn eine Verbindung aus dem Verbindungspool abgerufen oder an diesen zurückgegeben wird, werden keine Anmelde\- und Abmeldeereignisse auf dem Server ausgelöst, da die Verbindung bei der Rückgabe an den Verbindungspool nicht geschlossen wird.  Weitere Informationen finden Sie unter [SQL Server\-Verbindungspooling \(ADO.NET\)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## Herstellen einer Verbindung mit SQL Server  
 Der .NET Framework\-Datenanbieter für SQL Server unterstützt ein Verbindungszeichenfolgenformat ähnlich dem Verbindungszeichenfolgenformat für OLE DB \(ADO\).  Gültige Zeichenfolgenformatnamen und \-werte finden Sie in der Beschreibung der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>\-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>\-Objekts.  Sie können auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder>\-Klasse verwenden, um zur Laufzeit syntaktisch gültige Verbindungszeichenfolgen zu erstellen.  Weitere Informationen finden Sie unter [Verbindungszeichenfolgen\-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer SQL Server\-Datenbank erstellt und geöffnet wird.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### Integrierte Sicherheit und ASP.NET  
 Die integrierte Sicherheit von SQL Server \(auch bekannt als vertrauenswürdige Verbindungen\) trägt zum Schutz beim Herstellen von Verbindungen mit SQL Server bei, da in der Verbindungszeichenfolge Benutzer\-ID und Kennwort nicht verfügbar gemacht werden, und ist daher die empfohlene Methode für die Authentifizierung einer Verbindung.  Bei der integrierten Sicherheit wird die aktuelle Sicherheitsidentität oder das aktuelle Sicherheitstoken des ausführenden Prozesses verwendet.  Bei Desktop\-Anwendungen handelt es sich dabei i. d. R. um die Identität des aktuell angemeldeten Benutzers.  
  
 Die Sicherheitsidentität für ASP.NET\-Anwendungen kann auf eine von mehreren verschiedenen Optionen festgelegt werden.  Informationen zum besseren Verständnis der in ASP.NET\-Anwendungen beim Herstellen einer Verbindung mit SQL Server verwendeten Sicherheitsidentität finden Sie unter [ASP.NET Impersonation](../Topic/ASP.NET%20Impersonation.md), [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md) und [How to: Access SQL Server Using Windows Integrated Security](../Topic/How%20to:%20Access%20SQL%20Server%20Using%20Windows%20Integrated%20Security.md).  
  
## Herstellen einer Verbindung mit einer OLE DB\-Datenquelle  
 Der .NET Framework\-Datenanbieter für OLE DB stellt Verbindungen mit Datenquellen, die mit OLE DB verfügbar gemacht wurden \(über SQLOLEDB, den OLE DB\-Anbieter für SQL Server\), mithilfe des **OleDbConnection**\-Objekts her.  
  
 Bei dem .NET Framework\-Datenanbieter für OLE DB ist das Verbindungszeichenfolgenformat mit dem in ADO verwendeten Verbindungszeichenfolgenformat bis auf folgende Ausnahmen identisch:  
  
-   Das **Provider**\-Schlüsselwort ist erforderlich.  
  
-   Die Schlüsselwörter **URL**, **Remote Provider** und **Remote Server** werden nicht unterstützt.  
  
 Weitere Informationen zu OLE DB\-Verbindungszeichenfolgen finden Sie unter dem Thema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.  Sie können auch den <xref:System.Data.OleDb.OleDbConnectionStringBuilder> verwenden, um zur Laufzeit Verbindungszeichenfolgen zu erstellen.  
  
> [!NOTE]
>  Das **OleDbConnection**\-Objekt unterstützt nicht das Festlegen oder Abrufen dynamischer, für einen OLE DB\-Anbieter spezifischer Eigenschaften.  Es werden nur Eigenschaften unterstützt, die in der Verbindungszeichenfolge für den OLE DB\-Anbieter übergeben werden können.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer OLE DB\-Datenquelle erstellt und geöffnet wird.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =   
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## Verwenden Sie keine UDL\-Dateien \(Universal Data Link\)  
 Sie können Verbindungsinformationen für eine **OleDbConnection** in einer UDL \(Universal Data Link\)\-Datei bereitstellen, davon wird jedoch abgeraten.  UDL\-Dateien sind nicht verschlüsselt und machen Informationen zur Verbindungszeichenfolge im Klartext verfügbar.  Da es sich bei einer UDL\-Datei um eine externe Ressource der Anwendung handelt, kann sie nicht mit .NET Framework gesichert werden.  
  
## Herstellen einer Verbindung mit einer ODBC\-Datenquelle  
 Der .NET Framework\-Datenanbieter für ODBC stellt Verbindungen mit Datenquellen, die mit ODBC verfügbar gemacht wurden, mithilfe des **OdbcConnection**\-Objekts bereit.  
  
 Das Verbindungszeichenfolgenformat des .NET Framework\-Datenanbieters für ODBC wurde so konzipiert, dass es weitestgehend mit dem ODBC\-Verbindungszeichenfolgenformat übereinstimmt.  Sie können auch einen ODBC\-Datenquellennamen \(DSN, Data Source Name\) angeben.  Detailliertere Informationen zur **OdbcConnection** finden Sie unter den Informationen zur [OdbcConnection\-Klasse](frlrfSystemDataOdbcOdbcConnectionClassTopic).  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer ODBC\-Datenquelle erstellt und geöffnet wird.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =   
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## Herstellen einer Verbindung mit einer Oracle\-Datenquelle  
 Der .NET Framework\-Datenanbieter für Oracle stellt Verbindungen mit Oracle\-Datenquellen mithilfe des **OracleConnection**\-Objekts bereit.  
  
 Das Verbindungszeichenfolgenformat des .NET Framework\-Datenanbieters für Oracle wurde so konzipiert, dass es weitestgehend mit dem Verbindungszeichenfolgenformat des OLE DB\-Anbieters für Oracle \(MSDAORA\) übereinstimmt.  Detailliertere Informationen zur **OracleConnection** finden Sie unter den Informationen zur [OracleConnection Class](frlrfSystemDataOracleClientOracleConnectionClassTopic).  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer Oracle\-Datenquelle erstellt und geöffnet wird.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =   
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)   
 [OLE DB\-, ODBC\- und Oracle\-Verbindungspooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)