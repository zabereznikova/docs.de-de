---
title: Massenkopiervorgänge in SQL Server
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: efa13eb1633fce3b59040ef8da79dba0f6ea81d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918066"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="55b64-102">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="55b64-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="55b64-103">Microsoft SQL Server enthält ein beliebtes Befehlszeilen-Hilfsprogramm mit dem Namen **bcp** für das schnelle Massen Kopieren großer Dateien in Tabellen oder Sichten in SQL Server Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="55b64-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="55b64-104">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie verwaltete Codelösungen schreiben, durch die ähnliche Funktionen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="55b64-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="55b64-105">Es stehen auch andere Möglichkeiten zum Laden von Daten in eine SQL Server-Tabelle zur Verfügung (z. B. INSERT-Anweisungen), <xref:System.Data.SqlClient.SqlBulkCopy> weist diesen gegenüber jedoch einen deutlichen Leistungsvorteil auf.</span><span class="sxs-lookup"><span data-stu-id="55b64-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="55b64-106">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="55b64-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="55b64-107">Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>-Instanz geladen oder mit einer <xref:System.Data.IDataReader>-Instanz gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="55b64-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="55b64-108">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie folgende Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="55b64-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="55b64-109">Einzelne Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="55b64-109">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="55b64-110">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="55b64-110">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="55b64-111">Massenkopiervorgänge innerhalb von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="55b64-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55b64-112">Wenn Sie .NET Framework Version 1,1 oder früher verwenden (die die <xref:System.Data.SqlClient.SqlBulkCopy> -Klasse nicht unterstützt), können Sie die SQL Server Transact-SQL- **Bulk Insert** - <xref:System.Data.SqlClient.SqlCommand> Anweisung mit dem-Objekt ausführen.</span><span class="sxs-lookup"><span data-stu-id="55b64-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55b64-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="55b64-113">In This Section</span></span>  
 [<span data-ttu-id="55b64-114">Einrichtung der Massenkopierbeispiele</span><span class="sxs-lookup"><span data-stu-id="55b64-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="55b64-115">Beschreibt die in den Beispielen für Massenkopiervorgänge verwendeten Tabellen und stellt SQL-Skripts zum Erstellen der Tabellen in der AdventureWorks-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="55b64-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="55b64-116">Einzelne Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="55b64-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="55b64-117">Beschreibt die Durchführung eines einzelnen Massenkopiervorgangs für Daten in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse sowie die Durchführung des Massenkopiervorgangs mithilfe von Transact-SQL-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="55b64-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="55b64-118">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="55b64-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="55b64-119">Beschreibt die Durchführung mehrerer Massenkopiervorgänge in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="55b64-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="55b64-120">Transaktionen und Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="55b64-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="55b64-121">Beschreibt die Durchführung eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Ausführens eines Commit oder Rollback für diese Transaktion.</span><span class="sxs-lookup"><span data-stu-id="55b64-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b64-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55b64-122">See also</span></span>

- [<span data-ttu-id="55b64-123">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="55b64-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="55b64-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="55b64-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
