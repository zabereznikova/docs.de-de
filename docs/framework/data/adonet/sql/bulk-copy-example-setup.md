---
title: Einrichtung der Massenkopierbeispiele
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 71daf489fdf5e7e12594e798bc3ac01b1c76b027
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46579458"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="9db88-102">Einrichtung der Massenkopierbeispiele</span><span class="sxs-lookup"><span data-stu-id="9db88-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="9db88-103">Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9db88-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="9db88-104">In diesem Thema gezeigten Codebeispiele verwenden die SQL Server-Beispieldatenbank, **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="9db88-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="9db88-105">Um Änderungen an den vorhandenen Tabellen zu vermeiden, schreiben die Codebeispiele in Tabellen, die zunächst erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9db88-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="9db88-106">Die **"BulkCopyDemoMatchingColumns"** und **"BulkCopyDemoDifferentColumns"** Tabellen basieren beide auf die **AdventureWorks** **Production.Products**  Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9db88-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="9db88-107">In Codebeispielen, die diese Tabellen verwenden, Daten hinzugefügt werden, aus der **Production.Products** Tabelle an eines dieser Beispieltabellen.</span><span class="sxs-lookup"><span data-stu-id="9db88-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="9db88-108">Die **"BulkCopyDemoDifferentColumns"** Tabelle wird verwendet, wenn das Beispiel veranschaulicht, wie Sie die Spalten aus den Quelldaten der Zieltabelle zuordnen **"BulkCopyDemoMatchingColumns"** wird für die meisten anderen Beispiele verwendet.</span><span class="sxs-lookup"><span data-stu-id="9db88-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="9db88-109">In einigen Codebeispielen wird veranschaulicht, wie mit einer <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse in mehrere Tabellen geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="9db88-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="9db88-110">Für diese Beispiele die **"BulkCopyDemoOrderHeader"** und **BulkCopyDemoOrderDetail** Tabellen werden als Zieltabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="9db88-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="9db88-111">Diese Tabellen basieren auf der **Sales.SalesOrderHeader** und **Sales.SalesOrderDetail** Tabellen in **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="9db88-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9db88-112">Die **"SqlBulkCopy"** Codebeispiele werden bereitgestellt, um die Syntax für die Verwendung zu demonstrieren **"SqlBulkCopy"** nur.</span><span class="sxs-lookup"><span data-stu-id="9db88-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="9db88-113">Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.</span><span class="sxs-lookup"><span data-stu-id="9db88-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="9db88-114">Einrichten der Tabellen</span><span class="sxs-lookup"><span data-stu-id="9db88-114">Table Setup</span></span>  
 <span data-ttu-id="9db88-115">Zum Erstellen der Tabellen, die für das ordnungsgemäße Ausführen der Codebeispiele erforderlich sind, müssen Sie die folgenden Transact-SQL-Anweisungen in einer SQL Server-Datenbank ausführen:</span><span class="sxs-lookup"><span data-stu-id="9db88-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="9db88-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9db88-116">See Also</span></span>  
 [<span data-ttu-id="9db88-117">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="9db88-117">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="9db88-118">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9db88-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
