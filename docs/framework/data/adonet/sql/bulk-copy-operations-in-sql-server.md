---
title: "Massenkopiervorgänge in SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 31da2fbc7dca4c0c2c077991ddec39e8979b08b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="90b55-102">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="90b55-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="90b55-103">Microsoft SQL Server enthält ein beliebtes Befehlszeilentools-Hilfsprogramm, die mit dem Namen **Bcp** für schnellen Massenkopieren großer Dateiumfänge in Tabellen oder Sichten in SQL Server-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="90b55-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="90b55-104">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie verwaltete Codelösungen schreiben, durch die ähnliche Funktionen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="90b55-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="90b55-105">Es stehen auch andere Möglichkeiten zum Laden von Daten in eine SQL Server-Tabelle zur Verfügung (z. B. INSERT-Anweisungen), <xref:System.Data.SqlClient.SqlBulkCopy> weist diesen gegenüber jedoch einen deutlichen Leistungsvorteil auf.</span><span class="sxs-lookup"><span data-stu-id="90b55-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="90b55-106">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="90b55-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="90b55-107">Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>-Instanz geladen oder mit einer <xref:System.Data.IDataReader>-Instanz gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="90b55-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="90b55-108">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie folgende Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="90b55-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
-   <span data-ttu-id="90b55-109">Einzelne Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="90b55-109">A single bulk copy operation</span></span>  
  
-   <span data-ttu-id="90b55-110">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="90b55-110">Multiple bulk copy operations</span></span>  
  
-   <span data-ttu-id="90b55-111">Massenkopiervorgänge innerhalb von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="90b55-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90b55-112">Bei Verwendung von .NET Framework, Version 1.1 oder früher (nicht unterstützt die <xref:System.Data.SqlClient.SqlBulkCopy> Klasse), können Sie die SQL Server Transact-SQL ausführen **BULK INSERT** Anweisung mithilfe der <xref:System.Data.SqlClient.SqlCommand> Objekt.</span><span class="sxs-lookup"><span data-stu-id="90b55-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90b55-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="90b55-113">In This Section</span></span>  
 [<span data-ttu-id="90b55-114">Einrichten des massenkopierbeispiels</span><span class="sxs-lookup"><span data-stu-id="90b55-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="90b55-115">Beschreibt die in den Beispielen für Massenkopiervorgänge verwendeten Tabellen und stellt SQL-Skripts zum Erstellen der Tabellen in der AdventureWorks-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="90b55-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="90b55-116">Einzelne Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="90b55-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="90b55-117">Beschreibt die Durchführung eines einzelnen Massenkopiervorgangs für Daten in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse sowie die Durchführung des Massenkopiervorgangs mithilfe von Transact-SQL-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="90b55-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="90b55-118">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="90b55-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="90b55-119">Beschreibt die Durchführung mehrerer Massenkopiervorgänge in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="90b55-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="90b55-120">Transaktionen und Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="90b55-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="90b55-121">Beschreibt die Durchführung eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Ausführens eines Commit oder Rollback für diese Transaktion.</span><span class="sxs-lookup"><span data-stu-id="90b55-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b55-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90b55-122">See Also</span></span>  
 [<span data-ttu-id="90b55-123">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90b55-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="90b55-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="90b55-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
