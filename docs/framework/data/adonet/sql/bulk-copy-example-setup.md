---
title: Einrichtung der Massenkopierbeispiele
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 562d36e0aee72fcc0619ec4ed7362622ba652337
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197481"
---
# <a name="bulk-copy-example-setup"></a>Einrichtung der Massenkopierbeispiele

Die <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse kann nur zum Schreiben von Daten in SQL Server-Tabellen verwendet werden. Die in diesem Thema gezeigten Codebeispiele verwenden die SQL Server-Beispieldatenbank **AdventureWorks**. Um eine Änderung der vorhandenen Codebeispiele zu vermeiden, schreiben die Codebeispiele Daten in Tabellen, die zuvor von Ihnen erstellt werden.  
  
 Die Tabellen **BulkCopyDemoMatchingColumns** und **BulkCopyDemoDifferentColumns** basieren beide auf der Tabelle **AdventureWorks** **Production.Products**. In Codebeispielen, in denen diese Tabellen verwendet werden, werden Daten aus der **Production. Products** -Tabelle einer dieser Beispiel Tabellen hinzugefügt. Die **BulkCopyDemoDifferentColumns** -Tabelle wird verwendet, wenn das Beispiel veranschaulicht, wie Spalten aus den Quelldaten der Ziel Tabelle zugeordnet werden. **Bulkcopytomomatchingcolumns** wird für die meisten anderen Beispiele verwendet.  
  
 Einige der Codebeispiele zeigen, wie eine Klasse <xref:System.Data.SqlClient.SqlBulkCopy> zum Schreiben in mehrere Tabellen verwendet werden kann. Für diese Beispiele werden die **BulkCopyDemoOrderHeader** -Tabelle und die **BulkCopyDemoOrderDetail** -Tabelle als Ziel Tabellen verwendet. Diese Tabellen basieren auf der **Sales. SalesOrderHeader** -Tabelle und der **Sales. SalesOrderDetail** -Tabelle in **AdventureWorks**.  
  
> [!NOTE]
> Die **SqlBulkCopy**-Codebeispiele dienen ausschließlich der Veranschaulichung der für **SqlBulkCopy** verwendeten Syntax. Wenn sich die Quell- und Zieltabellen in der gleichen SQL Server-Instanz befinden, ist die Verwendung einer Transact-SQL-Anweisung `INSERT … SELECT` zum Kopieren der Daten einfacher und schneller.  
  
## <a name="table-setup"></a>Einrichten der Tabellen  

 Zum Erstellen der Tabellen, die für die ordnungsgemäße Ausführung der Codebeispiele erforderlich sind, müssen Sie die folgenden Transact-SQL-Anweisungen in einer SQL Server-Datenbank ausführen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Massenkopiervorgänge in SQL Server](bulk-copy-operations-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
