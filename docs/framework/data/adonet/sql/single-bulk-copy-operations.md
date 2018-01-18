---
title: "Einzelne Massenkopiervorgänge"
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
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 961981fcdf9709a336d76df99c8f65448e76b98a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="6a225-102">Einzelne Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="6a225-102">Single Bulk Copy Operations</span></span>
<span data-ttu-id="6a225-103">Ein SQL Server-Massenkopiervorgang wird am einfachsten durchgeführt, indem ein einzelner Vorgang für eine Datenbank ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a225-103">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="6a225-104">Ein Massenkopiervorgang wird in der Standardeinstellung als isolierter Vorgang durchgeführt. Der Kopiervorgang wird nicht transaktiv und ohne die Möglichkeit eines Rollbacks durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a225-104">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a225-105">Wenn Sie beim Auftreten eines Fehler einen Rollback der gesamten Massenkopie oder eines Teils davon ausführen müssen, können Sie eine von <xref:System.Data.SqlClient.SqlBulkCopy> verwaltete Transaktion verwenden oder den Massenkopiervorgang innerhalb einer bestehenden Transaktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="6a225-105">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="6a225-106">**"SqlBulkCopy"** funktioniert auch mit <xref:System.Transactions> , wenn die Verbindung (implizit oder explizit) in eingetragen ist ein **System.Transactions** Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6a225-106">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>  
>   
>  <span data-ttu-id="6a225-107">Weitere Informationen finden Sie unter [Transaktionen und Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6a225-107">For more information, see [Transaction and Bulk Copy Operations](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="6a225-108">Im Allgemeinen müssen für einen Massenkopiervorgang folgende Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6a225-108">The general steps for performing a bulk copy operation are as follows:</span></span>  
  
1.  <span data-ttu-id="6a225-109">Stellen Sie eine Verbindung mit dem Quellserver her, und rufen Sie die zu kopierenden Daten ab.</span><span class="sxs-lookup"><span data-stu-id="6a225-109">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="6a225-110">Daten können auch aus anderen Quellen stammen, wenn sie aus einem <xref:System.Data.IDataReader>-Objekt oder einem <xref:System.Data.DataTable>-Objekt abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="6a225-110">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>  
  
2.  <span data-ttu-id="6a225-111">Herstellen einer Verbindung mit dem Zielserver (es sei denn, Sie **"SqlBulkCopy"** zum Herstellen einer Verbindung für Sie).</span><span class="sxs-lookup"><span data-stu-id="6a225-111">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>  
  
3.  <span data-ttu-id="6a225-112">Erstellen Sie ein <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt, und legen Sie die notwendigen Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="6a225-112">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>  
  
4.  <span data-ttu-id="6a225-113">Legen Sie die **DestinationTableName** Einfügevorgang der Eigenschaft, um die Zieltabelle für den Masseneinfügevorgang anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a225-113">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>  
  
5.  <span data-ttu-id="6a225-114">Rufen Sie eine von der **WriteToServer** Methoden.</span><span class="sxs-lookup"><span data-stu-id="6a225-114">Call one of the **WriteToServer** methods.</span></span>  
  
6.  <span data-ttu-id="6a225-115">Aktualisieren Sie optional, Eigenschaften und rufen **WriteToServer** erneut nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="6a225-115">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>  
  
7.  <span data-ttu-id="6a225-116">Rufen Sie die <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>-Methode auf, oder betten Sie die Massenkopiervorgänge in eine `Using`-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="6a225-116">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6a225-117">Es wird empfohlen, dass die Datentypen in der Quell- und Zielspalte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6a225-117">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="6a225-118">Wenn die Datentypen nicht übereinstimmen, **"SqlBulkCopy"** versucht, jeden Quellwert in den Zieldatentyp, die unter Verwendung der Regeln, die vom Anwender verwendete konvertieren <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="6a225-118">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="6a225-119">Konvertierungen können sich auf die Leistungsfähigkeit auswirken und zu unerwarteten Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="6a225-119">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="6a225-120">Ein `Double`-Datentyp kann beispielsweise häufig, aber nicht immer in einen `Decimal`-Datentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a225-120">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a225-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a225-121">Example</span></span>  
 <span data-ttu-id="6a225-122">In der folgenden Konsolenanwendung wird veranschaulicht, wie Daten mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6a225-122">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="6a225-123">In diesem Beispiel wird eine <xref:System.Data.SqlClient.SqlDataReader> dient zum Kopieren von Daten aus der **Production.Product** -Tabelle in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] **AdventureWorks** Datenbank in eine ähnliche Tabelle in der gleichen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6a225-123">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]**AdventureWorks** database to a similar table in the same database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6a225-124">Dieses Beispiel wird nicht ausgeführt, es sei denn, Sie die Arbeitstabellen erstellt haben, wie in beschrieben [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6a225-124">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="6a225-125">Die angegebene Code dient zum Veranschaulichen der Syntax für die Verwendung von **"SqlBulkCopy"** nur.</span><span class="sxs-lookup"><span data-stu-id="6a225-125">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="6a225-126">Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.</span><span class="sxs-lookup"><span data-stu-id="6a225-126">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="6a225-127">Durchführen eines Massenkopiervorgangs mithilfe von Transact-SQL und der Command-Klasse</span><span class="sxs-lookup"><span data-stu-id="6a225-127">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>  
 <span data-ttu-id="6a225-128">Im folgenden Beispiel wird die <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>-Methode zum Ausführen der BULK INSERT-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6a225-128">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a225-129">Der Dateipfad für die Datenquelle ist relativ zum Server.</span><span class="sxs-lookup"><span data-stu-id="6a225-129">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="6a225-130">Der Serverprozess muss auf diesen Pfad zugreifen können, damit der Massenkopiervorgang erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6a225-130">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a225-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a225-131">See Also</span></span>  
 [<span data-ttu-id="6a225-132">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a225-132">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="6a225-133">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="6a225-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
