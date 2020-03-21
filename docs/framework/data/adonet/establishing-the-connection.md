---
title: Herstellen der Verbindung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: 4606ecb370b7e85cf5ebd92754471f5253321251
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149660"
---
# <a name="establishing-the-connection"></a>Herstellen der Verbindung
Zum Herstellen einer Verbindung mit Microsoft SQL Server verwenden Sie das <xref:System.Data.SqlClient.SqlConnection>-Objekt des .NET Framework-Datenanbieters für SQL Server. Wenn Sie eine Verbindung mit einer OLE DB-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.OleDb.OleDbConnection>-Objekt des .NET Framework-Datenanbieters für OLE DB. Wenn Sie eine Verbindung mit einer ODBC-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.Odbc.OdbcConnection>-Objekt des .NET Framework-Datenanbieters für ODBC. Zum Herstellen einer Verbindung mit einer Oracle-Datenquelle verwenden Sie das <xref:System.Data.OracleClient.OracleConnection>-Objekt des .NET Framework-Datenanbieters für Oracle. Informationen zum sicheren Speichern und Abrufen von Verbindungszeichenfolgen finden Sie unter Schützen von [Verbindungsinformationen](protecting-connection-information.md).  
  
## <a name="closing-connections"></a>Schließen von Verbindungen  
 Es wird empfohlen, die Verbindung nach Verwendung stets zu schließen, damit sie in den Pool zurückgegeben werden kann. Der `Using`-Block in Visual Basic oder C# verwirft automatisch die Verbindung, wenn der Code den Block verlässt, auch im Falle einer unbehandelten Ausnahme. Weitere Informationen finden Sie unter Verwenden von [Anweisung](../../../csharp/language-reference/keywords/using-statement.md) und [Verwendungsanweisung.](../../../visual-basic/language-reference/statements/using-statement.md)  
  
 Sie können ebenso die `Close`-Methode oder `Dispose`-Methode des Verbindungsobjekts des von Ihnen in Anspruch genommenen Anbieters verwenden. Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise dem Pool nicht hinzugefügt bzw. nicht an den Pool zurückgegeben. Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist. Weitere Informationen finden Sie unter [OLE DB, ODBC und Oracle Connection Pooling](ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
> Rufen `Close` Sie `Dispose` keine **Verbindung,** einen **DataReader**oder ein anderes `Finalize` verwaltetes Objekt in der Methode Ihrer Klasse auf. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`-Methode. Weitere Informationen finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).  
  
> [!NOTE]
> Wenn eine Verbindung aus dem Verbindungspool abgerufen oder an diesen zurückgegeben wird, werden keine Anmelde- und Abmeldeereignisse auf dem Server ausgelöst, da die Verbindung bei der Rückgabe an den Verbindungspool nicht geschlossen wird. Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](sql-server-connection-pooling.md).  
  
## <a name="connecting-to-sql-server"></a>Herstellen einer Verbindung mit SQL Server  
 Der .NET Framework-Datenanbieter für SQL Server unterstützt ein Verbindungszeichenfolgenformat ähnlich dem Verbindungszeichenfolgenformat für OLE DB (ADO). Gültige Zeichenfolgenformatnamen und -werte finden Sie in der Beschreibung der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>-Objekts. Sie können auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Klasse verwenden, um zur Laufzeit syntaktisch gültige Verbindungszeichenfolgen zu erstellen. Weitere Informationen finden Sie in [Connection String Builders (Verbindungszeichenfolgengeneratoren)](connection-string-builders.md).  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer SQL Server-Datenbank erstellt und geöffnet wird.  
  
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
  
### <a name="integrated-security-and-aspnet"></a>Integrierte Sicherheit und ASP.NET  
 Die integrierte Sicherheit von SQL Server (auch bekannt als vertrauenswürdige Verbindungen) trägt zum Schutz beim Herstellen von Verbindungen mit SQL Server bei, da in der Verbindungszeichenfolge Benutzer-ID und Kennwort nicht verfügbar gemacht werden, und ist daher die empfohlene Methode für die Authentifizierung einer Verbindung. Bei der integrierten Sicherheit wird die aktuelle Sicherheitsidentität oder das aktuelle Sicherheitstoken des ausführenden Prozesses verwendet. Bei Desktop-Anwendungen handelt es sich dabei i. d. R. um die Identität des aktuell angemeldeten Benutzers.  
  
 Die Sicherheitsidentität für ASP.NET-Anwendungen kann auf eine von mehreren verschiedenen Optionen festgelegt werden. Informationen zur Sicherheitsidentität, die eine ASP.NET Anwendung beim Herstellen einer Verbindung mit SQL Server verwendet, finden Sie unter [ASP.NET Identitätswechsel](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET Authentifizierung](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100))und [How to: Access SQL Server Using Windows Integrated Security](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100)).  
  
## <a name="connecting-to-an-ole-db-data-source"></a>Herstellen einer Verbindung mit einer OLE DB-Datenquelle  
 Der .NET Framework-Datenanbieter für OLE DB stellt Konnektivität zu Datenquellen bereit, die mithilfe von OLE DB (über SQLOLEDB, dem OLE DB-Anbieter für SQL Server) mithilfe des **OleDbConnection-Objekts** verfügbar gemacht werden.  
  
 Bei dem .NET Framework-Datenanbieter für OLE DB ist das Verbindungszeichenfolgenformat mit dem in ADO verwendeten Verbindungszeichenfolgenformat bis auf folgende Ausnahmen identisch:  
  
- Das **Provider** Provider-Schlüsselwort ist erforderlich.  
  
- Die Schlüsselwörter **URL**, **Remote Provider**und **Remote Server** werden nicht unterstützt.  
  
 Weitere Informationen zu OLE DB-Verbindungszeichenfolgen finden Sie unter dem Thema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>. Sie können auch den <xref:System.Data.OleDb.OleDbConnectionStringBuilder> verwenden, um zur Laufzeit Verbindungszeichenfolgen zu erstellen.  
  
> [!NOTE]
> Das **OleDbConnection-Objekt** unterstützt das Festlegen oder Abrufen dynamischer Eigenschaften, die für einen OLE DB-Anbieter spezifisch sind, nicht. Es werden nur Eigenschaften unterstützt, die in der Verbindungszeichenfolge für den OLE DB-Anbieter übergeben werden können.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer OLE DB-Datenquelle erstellt und geöffnet wird.  
  
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
  
## <a name="do-not-use-universal-data-link-files"></a>Verwenden Sie keine UDL-Dateien (Universal Data Link)  
 Es ist möglich, Verbindungsinformationen für eine **OleDbConnection** in einer UdL-Datei (Universal Data Link) anzugeben. Sie sollten dies jedoch vermeiden. UDL-Dateien sind nicht verschlüsselt und machen Informationen zur Verbindungszeichenfolge im Klartext verfügbar. Da es sich bei einer UDL-Datei um eine externe Ressource der Anwendung handelt, kann sie nicht mit .NET Framework gesichert werden.  
  
## <a name="connecting-to-an-odbc-data-source"></a>Herstellen einer Verbindung mit einer ODBC-Datenquelle  
 Der .NET Framework-Datenanbieter für ODBC stellt Verbindungen zu Datenquellen bereit, die mithilfe von ODBC mithilfe des **OdbcConnection-Objekts** verfügbar gemacht werden.  
  
 Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für ODBC wurde so konzipiert, dass es weitestgehend mit dem ODBC-Verbindungszeichenfolgenformat übereinstimmt. Sie können auch einen ODBC-Datenquellennamen (DSN, Data Source Name) angeben. Weitere Informationen zur **OdbcConnection** finden <xref:System.Data.Odbc.OdbcConnection>Sie im .  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer ODBC-Datenquelle erstellt und geöffnet wird.  
  
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
  
## <a name="connecting-to-an-oracle-data-source"></a>Herstellen einer Verbindung mit einer Oracle-Datenquelle  
 Der .NET Framework-Datenanbieter für Oracle stellt mithilfe des **OracleConnection-Objekts** Verbindungen zu Oracle-Datenquellen bereit.  
  
 Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für Oracle wurde so konzipiert, dass es weitestgehend mit dem Verbindungszeichenfolgenformat des OLE DB-Anbieters für Oracle (MSDAORA) übereinstimmt. Weitere Informationen zur **OracleConnection**finden <xref:System.Data.OracleClient.OracleConnection>Sie im .  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer Oracle-Datenquelle erstellt und geöffnet wird.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [Verbindungszeichenfolgen](connection-strings.md)
- [OLE DB-, ODBC- und Oracle-Verbindungspooling](ole-db-odbc-and-oracle-connection-pooling.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
