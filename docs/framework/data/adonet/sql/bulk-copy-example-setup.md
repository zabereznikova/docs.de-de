---
title: Einrichtung der Massenkopierbeispiele
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 80350d112da03c00e422432ce271ca5ea3ac58ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148841"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="79b02-102">Einrichtung der Massenkopierbeispiele</span><span class="sxs-lookup"><span data-stu-id="79b02-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="79b02-103">Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse kann nur zum Schreiben von Daten in SQL Server-Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79b02-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="79b02-104">Die in diesem Thema gezeigten Codebeispiele verwenden die SQL Server-Beispieldatenbank **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="79b02-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="79b02-105">Um eine Änderung der vorhandenen Codebeispiele zu vermeiden, schreiben die Codebeispiele Daten in Tabellen, die zuvor von Ihnen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="79b02-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="79b02-106">Die Tabellen **BulkCopyDemoMatchingColumns** und **BulkCopyDemoDifferentColumns** basieren beide auf der Tabelle **AdventureWorks** **Production.Products**.</span><span class="sxs-lookup"><span data-stu-id="79b02-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="79b02-107">In Codebeispielen, die diese Tabellen verwenden, werden Daten aus der Tabelle **Production.Products** einer dieser Beispieltabellen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="79b02-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="79b02-108">Die Tabelle **BulkCopyDemoDifferentColumns** wird verwendet, um im Beispiel zu veranschaulichen, wie Spalten aus den Quelldaten der Zieltabelle zugeordnet werden; für die meisten anderen Beispiele wird **BulkCopyDemoMatchingColumns** verwendet.</span><span class="sxs-lookup"><span data-stu-id="79b02-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="79b02-109">Einige der Codebeispiele zeigen, wie eine Klasse <xref:System.Data.SqlClient.SqlBulkCopy> zum Schreiben in mehrere Tabellen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="79b02-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="79b02-110">Für diese Beispiele werden die Tabellen **BulkCopyDemoOrderHeader** und **BulkCopyDemoOrderDetail** als Zieltabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="79b02-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="79b02-111">Diese Tabellen basieren auf den Tabellen **Sales.SalesOrderHeader** und **Sales.SalesOrderDetail** in **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="79b02-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="79b02-112">Die **SqlBulkCopy**-Codebeispiele dienen ausschließlich der Veranschaulichung der für **SqlBulkCopy** verwendeten Syntax.</span><span class="sxs-lookup"><span data-stu-id="79b02-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="79b02-113">Wenn sich die Quell- und Zieltabellen in der gleichen SQL Server-Instanz befinden, ist die Verwendung einer Transact-SQL-Anweisung `INSERT … SELECT` zum Kopieren der Daten einfacher und schneller.</span><span class="sxs-lookup"><span data-stu-id="79b02-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="79b02-114">Einrichten der Tabellen</span><span class="sxs-lookup"><span data-stu-id="79b02-114">Table Setup</span></span>  
 <span data-ttu-id="79b02-115">Zum Erstellen der Tabellen, die für die ordnungsgemäße Ausführung der Codebeispiele erforderlich sind, müssen Sie die folgenden Transact-SQL-Anweisungen in einer SQL Server-Datenbank ausführen.</span><span class="sxs-lookup"><span data-stu-id="79b02-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```sql
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a><span data-ttu-id="79b02-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79b02-116">See also</span></span>

- [<span data-ttu-id="79b02-117">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="79b02-117">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="79b02-118">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79b02-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
