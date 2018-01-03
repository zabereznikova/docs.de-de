---
title: Herstellen der Verbindung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 416d89aef35fef5dd0ac2bca92fb8a90d757a2d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="establishing-the-connection"></a>Herstellen der Verbindung
Zum Herstellen einer Verbindung mit Microsoft SQL Server verwenden Sie das <xref:System.Data.SqlClient.SqlConnection>-Objekt des .NET Framework-Datenanbieters für SQL Server. Wenn Sie eine Verbindung mit einer OLE DB-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.OleDb.OleDbConnection>-Objekt des .NET Framework-Datenanbieters für OLE DB. Wenn Sie eine Verbindung mit einer ODBC-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.Odbc.OdbcConnection>-Objekt des .NET Framework-Datenanbieters für ODBC. Zum Herstellen einer Verbindung mit einer Oracle-Datenquelle verwenden Sie das <xref:System.Data.OracleClient.OracleConnection>-Objekt des .NET Framework-Datenanbieters für Oracle. Sicheren Speichern und Abrufen von Verbindungszeichenfolgen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="closing-connections"></a>Schließen von Verbindungen  
 Es wird empfohlen, die Verbindung nach Verwendung stets zu schließen, damit sie in den Pool zurückgegeben werden kann. Der `Using`-Block in Visual Basic oder C# verwirft automatisch die Verbindung, wenn der Code den Block verlässt, auch im Falle einer unbehandelten Ausnahme. Finden Sie unter [mit Anweisung](~/docs/csharp/language-reference/keywords/using-statement.md) und [Using-Anweisung](~/docs/visual-basic/language-reference/statements/using-statement.md) für Weitere Informationen.  
  
 Sie können ebenso die `Close`-Methode oder `Dispose`-Methode des Verbindungsobjekts des von Ihnen in Anspruch genommenen Anbieters verwenden. Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise dem Pool nicht hinzugefügt bzw. nicht an den Pool zurückgegeben. Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist. Weitere Informationen finden Sie unter [OLE DB, ODBC und Oracle-Verbindungspooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
>  Rufen Sie nicht `Close` oder `Dispose` auf eine **Verbindung**, **DataReader**, oder ein anderes verwaltetes Objekt in der `Finalize` -Methode der Klasse. Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören. Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`-Methode. Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
> [!NOTE]
>  Wenn eine Verbindung aus dem Verbindungspool abgerufen oder an diesen zurückgegeben wird, werden keine Anmelde- und Abmeldeereignisse auf dem Server ausgelöst, da die Verbindung bei der Rückgabe an den Verbindungspool nicht geschlossen wird. Weitere Informationen finden Sie unter [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## <a name="connecting-to-sql-server"></a>Herstellen einer Verbindung mit SQL Server  
 Der .NET Framework-Datenanbieter für SQL Server unterstützt ein Verbindungszeichenfolgenformat ähnlich dem Verbindungszeichenfolgenformat für OLE DB (ADO). Gültige Zeichenfolgenformatnamen und -werte finden Sie in der Beschreibung der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>-Objekts. Sie können auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Klasse verwenden, um zur Laufzeit syntaktisch gültige Verbindungszeichenfolgen zu erstellen. Weitere Informationen finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
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
  
 Die Sicherheitsidentität für ASP.NET-Anwendungen kann auf eine von mehreren verschiedenen Optionen festgelegt werden. Zum besseren Verständnis der Sicherheits-ID, die eine ASP.NET-Anwendung mit SQL Server herstellt, finden Sie unter [ASP.NET-Identitätswechsel](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [ASP.NET-Authentifizierung](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), und [Vorgehensweise: Zugriff SQL Verwenden von Windows Server integrierte Sicherheit](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).  
  
## <a name="connecting-to-an-ole-db-data-source"></a>Herstellen einer Verbindung mit einer OLE DB-Datenquelle  
 Die .NET Framework-Datenanbieter für OLE DB stellt Verbindungen mit Datenquellen, die mit OLE DB (über SQLOLEDB OLE DB-Anbieter für SQL Server), verfügbar gemacht werden mithilfe der **OleDbConnection** Objekt.  
  
 Bei dem .NET Framework-Datenanbieter für OLE DB ist das Verbindungszeichenfolgenformat mit dem in ADO verwendeten Verbindungszeichenfolgenformat bis auf folgende Ausnahmen identisch:  
  
-   Die **Anbieter** -Schlüsselwort ist erforderlich.  
  
-   Die **URL**, **Remoteanbieter**, und **Remoteserver** Schlüsselwörter werden nicht unterstützt.  
  
 Weitere Informationen zu OLE DB-Verbindungszeichenfolgen finden Sie unter dem Thema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>. Sie können auch den <xref:System.Data.OleDb.OleDbConnectionStringBuilder> verwenden, um zur Laufzeit Verbindungszeichenfolgen zu erstellen.  
  
> [!NOTE]
>  Die **OleDbConnection** -Objekt festlegen oder Abrufen von dynamischen Eigenschaften, die spezifisch für einen OLE DB-Anbieter nicht unterstützt. Es werden nur Eigenschaften unterstützt, die in der Verbindungszeichenfolge für den OLE DB-Anbieter übergeben werden können.  
  
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
 Es ist möglich, die Verbindungsinformationen für eine **OleDbConnection** in einer Datei (Universal Data Link, UDL); jedoch sollten Sie auf diese Weise. UDL-Dateien sind nicht verschlüsselt und machen Informationen zur Verbindungszeichenfolge im Klartext verfügbar. Da es sich bei einer UDL-Datei um eine externe Ressource der Anwendung handelt, kann sie nicht mit .NET Framework gesichert werden.  
  
## <a name="connecting-to-an-odbc-data-source"></a>Herstellen einer Verbindung mit einer ODBC-Datenquelle  
 Die .NET Framework-Datenanbieter für ODBC stellt Verbindungen mit Datenquellen, die verfügbar gemacht werden mithilfe von ODBC die **OdbcConnection** Objekt.  
  
 Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für ODBC wurde so konzipiert, dass es weitestgehend mit dem ODBC-Verbindungszeichenfolgenformat übereinstimmt. Sie können auch einen ODBC-Datenquellennamen (DSN, Data Source Name) angeben. Weitere Informationen zu den **OdbcConnection** , finden Sie unter der <xref:System.Data.Odbc.OdbcConnection>.  
  
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
 Die .NET Framework-Datenanbieter für Oracle stellt Verbindungen zum Oracle-Datenquellen mithilfe der **OracleConnection** Objekt.  
  
 Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für Oracle wurde so konzipiert, dass es weitestgehend mit dem Verbindungszeichenfolgenformat des OLE DB-Anbieters für Oracle (MSDAORA) übereinstimmt. Weitere Informationen zu den **OracleConnection**, finden Sie unter der <xref:System.Data.OracleClient.OracleConnection>.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)  
 [OLE DB-, ODBC- und Oracle-Verbindungspooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
