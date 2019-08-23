---
title: Einzelne Massenkopiervorgänge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 8cba2201bf8087633103efe45c5236cab3af0a0e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964738"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="ed292-102">Einzelne Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="ed292-102">Single Bulk Copy Operations</span></span>
<span data-ttu-id="ed292-103">Ein SQL Server-Massenkopiervorgang wird am einfachsten durchgeführt, indem ein einzelner Vorgang für eine Datenbank ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ed292-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="ed292-104">Ein Massenkopiervorgang wird in der Standardeinstellung als isolierter Vorgang durchgeführt. Der Kopiervorgang wird nicht transaktiv und ohne die Möglichkeit eines Rollbacks durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ed292-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed292-105">Wenn Sie beim Auftreten eines Fehler einen Rollback der gesamten Massenkopie oder eines Teils davon ausführen müssen, können Sie eine von <xref:System.Data.SqlClient.SqlBulkCopy> verwaltete Transaktion verwenden oder den Massenkopiervorgang innerhalb einer bestehenden Transaktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="ed292-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="ed292-106">**SqlBulkCopy** funktioniert auch mit <xref:System.Transactions> , wenn die Verbindung (implizit oder explizit) in eine **System. Transactions** -Transaktion eingetragen ist.</span><span class="sxs-lookup"><span data-stu-id="ed292-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>  
>   
>  <span data-ttu-id="ed292-107">Weitere Informationen finden Sie unter [Transaktionen und Massen Kopiervorgänge](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="ed292-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="ed292-108">Im Allgemeinen müssen für einen Massenkopiervorgang folgende Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="ed292-108">The general steps for performing a bulk copy operation are as follows:</span></span>  
  
1. <span data-ttu-id="ed292-109">Stellen Sie eine Verbindung mit dem Quellserver her, und rufen Sie die zu kopierenden Daten ab.</span><span class="sxs-lookup"><span data-stu-id="ed292-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="ed292-110">Daten können auch aus anderen Quellen stammen, wenn sie aus einem <xref:System.Data.IDataReader>-Objekt oder einem <xref:System.Data.DataTable>-Objekt abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="ed292-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>  
  
2. <span data-ttu-id="ed292-111">Stellen Sie eine Verbindung mit dem Zielserver her (es sei denn, Sie möchten mit **SqlBulkCopy** eine Verbindung für Sie herstellen).</span><span class="sxs-lookup"><span data-stu-id="ed292-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>  
  
3. <span data-ttu-id="ed292-112">Erstellen Sie ein <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt, und legen Sie die notwendigen Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="ed292-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>  
  
4. <span data-ttu-id="ed292-113">Legen Sie die **DestinationTableName** -Eigenschaft so fest, dass Sie die Ziel Tabelle für den Massen Einfügungs Vorgang angibt.</span><span class="sxs-lookup"><span data-stu-id="ed292-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>  
  
5. <span data-ttu-id="ed292-114">Ruft eine der Methoden " **Write-to-Server** " auf.</span><span class="sxs-lookup"><span data-stu-id="ed292-114">Call one of the **WriteToServer** methods.</span></span>  
  
6. <span data-ttu-id="ed292-115">Aktualisieren Sie optional die Eigenschaften, und wenden Sie ggf. erneut " **Write-Server** " an.</span><span class="sxs-lookup"><span data-stu-id="ed292-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>  
  
7. <span data-ttu-id="ed292-116">Rufen Sie die <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>-Methode auf, oder betten Sie die Massenkopiervorgänge in eine `Using`-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="ed292-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ed292-117">Es wird empfohlen, dass die Datentypen in der Quell- und Zielspalte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ed292-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="ed292-118">Wenn die Datentypen nicht identisch sind, versucht **SqlBulkCopy** , jeden Quellwert mithilfe der von <xref:System.Data.SqlClient.SqlParameter.Value%2A>verwendeten Regeln in den Ziel Datentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ed292-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="ed292-119">Konvertierungen können sich auf die Leistungsfähigkeit auswirken und zu unerwarteten Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="ed292-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="ed292-120">Ein `Double`-Datentyp kann beispielsweise häufig, aber nicht immer in einen `Decimal`-Datentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="ed292-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed292-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed292-121">Example</span></span>  
 <span data-ttu-id="ed292-122">In der folgenden Konsolenanwendung wird veranschaulicht, wie Daten mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ed292-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="ed292-123">In diesem Beispiel wird ein <xref:System.Data.SqlClient.SqlDataReader> zum Kopieren von Daten aus der **Production. Product** -Tabelle in der SQL Server **AdventureWorks** -Datenbank in eine ähnliche Tabelle in derselben Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed292-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server **AdventureWorks** database to a similar table in the same database.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ed292-124">Dieses Beispiel wird nur dann ausgeführt, wenn Sie die Arbeits Tabellen erstellt haben, wie unter [Beispiel für Massen Kopier](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)Vorgänge beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed292-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="ed292-125">Dieser Code wird bereitgestellt, um die Syntax nur für die Verwendung von **SqlBulkCopy** zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="ed292-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="ed292-126">Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.</span><span class="sxs-lookup"><span data-stu-id="ed292-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="ed292-127">Durchführen eines Massenkopiervorgangs mithilfe von Transact-SQL und der Command-Klasse</span><span class="sxs-lookup"><span data-stu-id="ed292-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>  
 <span data-ttu-id="ed292-128">Im folgenden Beispiel wird die <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>-Methode zum Ausführen der BULK INSERT-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ed292-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed292-129">Der Dateipfad für die Datenquelle ist relativ zum Server.</span><span class="sxs-lookup"><span data-stu-id="ed292-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="ed292-130">Der Serverprozess muss auf diesen Pfad zugreifen können, damit der Massenkopiervorgang erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed292-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed292-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed292-131">See also</span></span>

- [<span data-ttu-id="ed292-132">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed292-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="ed292-133">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ed292-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
