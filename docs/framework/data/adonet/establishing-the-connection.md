---
title: Herstellen der Verbindung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: a416994e5d5a1be5da9571d9f8e7564f0f14f238
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766139"
---
# <a name="establishing-the-connection"></a><span data-ttu-id="9ddb3-102">Herstellen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="9ddb3-102">Establishing the Connection</span></span>
<span data-ttu-id="9ddb3-103">Zum Herstellen einer Verbindung mit Microsoft SQL Server verwenden Sie das <xref:System.Data.SqlClient.SqlConnection>-Objekt des .NET Framework-Datenanbieters für SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-103">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="9ddb3-104">Wenn Sie eine Verbindung mit einer OLE DB-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.OleDb.OleDbConnection>-Objekt des .NET Framework-Datenanbieters für OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-104">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="9ddb3-105">Wenn Sie eine Verbindung mit einer ODBC-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.Odbc.OdbcConnection>-Objekt des .NET Framework-Datenanbieters für ODBC.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-105">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="9ddb3-106">Zum Herstellen einer Verbindung mit einer Oracle-Datenquelle verwenden Sie das <xref:System.Data.OracleClient.OracleConnection>-Objekt des .NET Framework-Datenanbieters für Oracle.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-106">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="9ddb3-107">Sicheren Speichern und Abrufen von Verbindungszeichenfolgen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-107">For securely storing and retrieving connection strings, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="9ddb3-108">Schließen von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="9ddb3-108">Closing Connections</span></span>  
 <span data-ttu-id="9ddb3-109">Es wird empfohlen, die Verbindung nach Verwendung stets zu schließen, damit sie in den Pool zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-109">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="9ddb3-110">Der `Using`-Block in Visual Basic oder C# verwirft automatisch die Verbindung, wenn der Code den Block verlässt, auch im Falle einer unbehandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-110">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="9ddb3-111">Finden Sie unter [mit Anweisung](~/docs/csharp/language-reference/keywords/using-statement.md) und [Using-Anweisung](~/docs/visual-basic/language-reference/statements/using-statement.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-111">See [using Statement](~/docs/csharp/language-reference/keywords/using-statement.md) and [Using Statement](~/docs/visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="9ddb3-112">Sie können ebenso die `Close`-Methode oder `Dispose`-Methode des Verbindungsobjekts des von Ihnen in Anspruch genommenen Anbieters verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-112">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="9ddb3-113">Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise dem Pool nicht hinzugefügt bzw. nicht an den Pool zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-113">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="9ddb3-114">Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-114">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="9ddb3-115">Weitere Informationen finden Sie unter [OLE DB, ODBC und Oracle-Verbindungspooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-115">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ddb3-116">Rufen Sie nicht `Close` oder `Dispose` auf eine **Verbindung**, **DataReader**, oder ein anderes verwaltetes Objekt in der `Finalize` -Methode der Klasse.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-116">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="9ddb3-117">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-117">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="9ddb3-118">Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`-Methode.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-118">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="9ddb3-119">Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-119">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ddb3-120">Wenn eine Verbindung aus dem Verbindungspool abgerufen oder an diesen zurückgegeben wird, werden keine Anmelde- und Abmeldeereignisse auf dem Server ausgelöst, da die Verbindung bei der Rückgabe an den Verbindungspool nicht geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-120">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="9ddb3-121">Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-121">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="9ddb3-122">Herstellen einer Verbindung mit SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ddb3-122">Connecting to SQL Server</span></span>  
 <span data-ttu-id="9ddb3-123">Der .NET Framework-Datenanbieter für SQL Server unterstützt ein Verbindungszeichenfolgenformat ähnlich dem Verbindungszeichenfolgenformat für OLE DB (ADO).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-123">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="9ddb3-124">Gültige Zeichenfolgenformatnamen und -werte finden Sie in der Beschreibung der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-124">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="9ddb3-125">Sie können auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Klasse verwenden, um zur Laufzeit syntaktisch gültige Verbindungszeichenfolgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-125">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="9ddb3-126">Weitere Informationen finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-126">For more information, see [Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="9ddb3-127">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer SQL Server-Datenbank erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-127">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
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
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="9ddb3-128">Integrierte Sicherheit und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ddb3-128">Integrated Security and ASP.NET</span></span>  
 <span data-ttu-id="9ddb3-129">Die integrierte Sicherheit von SQL Server (auch bekannt als vertrauenswürdige Verbindungen) trägt zum Schutz beim Herstellen von Verbindungen mit SQL Server bei, da in der Verbindungszeichenfolge Benutzer-ID und Kennwort nicht verfügbar gemacht werden, und ist daher die empfohlene Methode für die Authentifizierung einer Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-129">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="9ddb3-130">Bei der integrierten Sicherheit wird die aktuelle Sicherheitsidentität oder das aktuelle Sicherheitstoken des ausführenden Prozesses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-130">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="9ddb3-131">Bei Desktop-Anwendungen handelt es sich dabei i. d. R. um die Identität des aktuell angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-131">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="9ddb3-132">Die Sicherheitsidentität für ASP.NET-Anwendungen kann auf eine von mehreren verschiedenen Optionen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-132">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="9ddb3-133">Zum besseren Verständnis der Sicherheits-ID, die eine ASP.NET-Anwendung mit SQL Server herstellt, finden Sie unter [ASP.NET-Identitätswechsel](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [ASP.NET-Authentifizierung](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), und [Vorgehensweise: Zugriff SQL Verwenden von Windows Server integrierte Sicherheit](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).</span><span class="sxs-lookup"><span data-stu-id="9ddb3-133">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [ASP.NET Authentication](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), and [How to: Access SQL Server Using Windows Integrated Security](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="9ddb3-134">Herstellen einer Verbindung mit einer OLE DB-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="9ddb3-134">Connecting to an OLE DB Data Source</span></span>  
 <span data-ttu-id="9ddb3-135">Die .NET Framework-Datenanbieter für OLE DB stellt Verbindungen mit Datenquellen, die mit OLE DB (über SQLOLEDB OLE DB-Anbieter für SQL Server), verfügbar gemacht werden mithilfe der **OleDbConnection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-135">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="9ddb3-136">Bei dem .NET Framework-Datenanbieter für OLE DB ist das Verbindungszeichenfolgenformat mit dem in ADO verwendeten Verbindungszeichenfolgenformat bis auf folgende Ausnahmen identisch:</span><span class="sxs-lookup"><span data-stu-id="9ddb3-136">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="9ddb3-137">Die **Anbieter** -Schlüsselwort ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-137">The **Provider** keyword is required.</span></span>  
  
-   <span data-ttu-id="9ddb3-138">Die **URL**, **Remoteanbieter**, und **Remoteserver** Schlüsselwörter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-138">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="9ddb3-139">Weitere Informationen zu OLE DB-Verbindungszeichenfolgen finden Sie unter dem Thema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-139">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="9ddb3-140">Sie können auch den <xref:System.Data.OleDb.OleDbConnectionStringBuilder> verwenden, um zur Laufzeit Verbindungszeichenfolgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-140">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ddb3-141">Die **OleDbConnection** -Objekt festlegen oder Abrufen von dynamischen Eigenschaften, die spezifisch für einen OLE DB-Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-141">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="9ddb3-142">Es werden nur Eigenschaften unterstützt, die in der Verbindungszeichenfolge für den OLE DB-Anbieter übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-142">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="9ddb3-143">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer OLE DB-Datenquelle erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-143">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
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
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="9ddb3-144">Verwenden Sie keine UDL-Dateien (Universal Data Link)</span><span class="sxs-lookup"><span data-stu-id="9ddb3-144">Do Not Use Universal Data Link Files</span></span>  
 <span data-ttu-id="9ddb3-145">Es ist möglich, die Verbindungsinformationen für eine **OleDbConnection** in einer Datei (Universal Data Link, UDL); jedoch sollten Sie auf diese Weise.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-145">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="9ddb3-146">UDL-Dateien sind nicht verschlüsselt und machen Informationen zur Verbindungszeichenfolge im Klartext verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-146">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="9ddb3-147">Da es sich bei einer UDL-Datei um eine externe Ressource der Anwendung handelt, kann sie nicht mit .NET Framework gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-147">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="9ddb3-148">Herstellen einer Verbindung mit einer ODBC-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="9ddb3-148">Connecting to an ODBC Data Source</span></span>  
 <span data-ttu-id="9ddb3-149">Die .NET Framework-Datenanbieter für ODBC stellt Verbindungen mit Datenquellen, die verfügbar gemacht werden mithilfe von ODBC die **OdbcConnection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-149">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="9ddb3-150">Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für ODBC wurde so konzipiert, dass es weitestgehend mit dem ODBC-Verbindungszeichenfolgenformat übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-150">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="9ddb3-151">Sie können auch einen ODBC-Datenquellennamen (DSN, Data Source Name) angeben.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-151">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="9ddb3-152">Weitere Informationen zu den **OdbcConnection** , finden Sie unter der <xref:System.Data.Odbc.OdbcConnection>.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-152">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="9ddb3-153">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer ODBC-Datenquelle erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-153">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
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
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="9ddb3-154">Herstellen einer Verbindung mit einer Oracle-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="9ddb3-154">Connecting to an Oracle Data Source</span></span>  
 <span data-ttu-id="9ddb3-155">Die .NET Framework-Datenanbieter für Oracle stellt Verbindungen zum Oracle-Datenquellen mithilfe der **OracleConnection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-155">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="9ddb3-156">Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für Oracle wurde so konzipiert, dass es weitestgehend mit dem Verbindungszeichenfolgenformat des OLE DB-Anbieters für Oracle (MSDAORA) übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-156">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="9ddb3-157">Weitere Informationen zu den **OracleConnection**, finden Sie unter der <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-157">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="9ddb3-158">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer Oracle-Datenquelle erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="9ddb3-158">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ddb3-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ddb3-159">See Also</span></span>  
 [<span data-ttu-id="9ddb3-160">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="9ddb3-160">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="9ddb3-161">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9ddb3-161">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="9ddb3-162">OLE DB-, ODBC- und Oracle-Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="9ddb3-162">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 [<span data-ttu-id="9ddb3-163">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9ddb3-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
