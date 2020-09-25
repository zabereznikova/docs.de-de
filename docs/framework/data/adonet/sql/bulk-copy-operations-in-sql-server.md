---
title: Massenkopiervorgänge in SQL Server
description: Erfahren Sie, wie Sie mit der SqlBulkCopy-Klasse verwaltete Code Lösungen schreiben, die große Dateien per Massen Kopiervorgang in Tabellen oder Sichten in SQL Server Datenbanken kopieren.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 43d63f3671ea8ff05da3e10580c2784fa3aae581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197430"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="ffa52-103">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="ffa52-103">Bulk Copy Operations in SQL Server</span></span>

<span data-ttu-id="ffa52-104">Microsoft SQL Server enthält ein beliebtes Befehlszeilen-Hilfsprogramm mit dem Namen **bcp** zum schnellen Massenkopieren großer Dateiumfänge in Tabellen oder Ansichten in SQL Server-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ffa52-104">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="ffa52-105">Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse ermöglicht Ihnen das Schreiben von verwalteten Codelösungen, die eine ähnliche Funktionalität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ffa52-105">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="ffa52-106">Es gibt eine Reihe weiterer Verfahren, Daten in eine SQL-Server-Tabelle zu laden (beispielsweise INSERT-Anweisungen), doch bietet <xref:System.Data.SqlClient.SqlBulkCopy> ihnen gegenüber einen erheblichen Leistungsvorteil.</span><span class="sxs-lookup"><span data-stu-id="ffa52-106">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="ffa52-107">Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse kann nur zum Schreiben von Daten in SQL Server-Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffa52-107">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="ffa52-108">Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>-Instanz geladen oder mit einer <xref:System.Data.IDataReader>-Instanz gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ffa52-108">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="ffa52-109">Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse bietet folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="ffa52-109">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="ffa52-110">Einen einzelnen Massenkopiervorgang</span><span class="sxs-lookup"><span data-stu-id="ffa52-110">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="ffa52-111">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="ffa52-111">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="ffa52-112">Einen Massenkopiervorgang innerhalb einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="ffa52-112">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ffa52-113">Wenn Sie .NET Framework, Version 1.1 oder früher, verwenden (bei diesen Versionen wird die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse nicht unterstützt), können Sie die **BULK INSERT**-Anweisung von Transact-SQL für SQL Server mit dem <xref:System.Data.SqlClient.SqlCommand>-Objekt ausführen.</span><span class="sxs-lookup"><span data-stu-id="ffa52-113">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffa52-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ffa52-114">In This Section</span></span>  

 [<span data-ttu-id="ffa52-115">Beispiel für Massen Kopiervorgang</span><span class="sxs-lookup"><span data-stu-id="ffa52-115">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="ffa52-116">In diesem Artikel werden die Tabellen beschrieben, die in den Beispielen für Massenkopiervorgänge verwendet werden, und SQL-Skripts zum Erstellen der Tabellen in der AdventureWorks-Datenbank werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ffa52-116">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="ffa52-117">Einzelne Massen Kopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="ffa52-117">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="ffa52-118">In diesem Artikel wird das Durchführen einzelner Massenkopiervorgänge für Daten in eine SQL Server-Instanz mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse beschrieben und wie der Massenkopiervorgang mithilfe von Transact-SQL-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>-Klasse durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ffa52-118">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="ffa52-119">Mehrere Massen Kopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="ffa52-119">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="ffa52-120">Beschreibt das Ausführen mehrerer Massenkopiervorgänge von Daten in eine SQL Server-Instanz mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse</span><span class="sxs-lookup"><span data-stu-id="ffa52-120">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="ffa52-121">Transaktionen und Massen Kopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="ffa52-121">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="ffa52-122">Beschreibt das Ausführen eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Commits oder Rollbacks einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="ffa52-122">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa52-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffa52-123">See also</span></span>

- [<span data-ttu-id="ffa52-124">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ffa52-124">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="ffa52-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ffa52-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
