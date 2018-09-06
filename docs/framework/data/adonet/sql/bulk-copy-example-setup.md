---
title: Einrichtung der Massenkopierbeispiele
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 71daf489fdf5e7e12594e798bc3ac01b1c76b027
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877397"
---
# <a name="bulk-copy-example-setup"></a>Einrichtung der Massenkopierbeispiele
Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden. In diesem Thema gezeigten Codebeispiele verwenden die SQL Server-Beispieldatenbank, **AdventureWorks**. Um Änderungen an den vorhandenen Tabellen zu vermeiden, schreiben die Codebeispiele in Tabellen, die zunächst erstellt werden müssen.  
  
 Die **"BulkCopyDemoMatchingColumns"** und **"BulkCopyDemoDifferentColumns"** Tabellen basieren beide auf die **AdventureWorks** **Production.Products**  Tabelle. In Codebeispielen, die diese Tabellen verwenden, Daten hinzugefügt werden, aus der **Production.Products** Tabelle an eines dieser Beispieltabellen. Die **"BulkCopyDemoDifferentColumns"** Tabelle wird verwendet, wenn das Beispiel veranschaulicht, wie Sie die Spalten aus den Quelldaten der Zieltabelle zuordnen **"BulkCopyDemoMatchingColumns"** wird für die meisten anderen Beispiele verwendet.  
  
 In einigen Codebeispielen wird veranschaulicht, wie mit einer <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse in mehrere Tabellen geschrieben werden kann. Für diese Beispiele die **"BulkCopyDemoOrderHeader"** und **BulkCopyDemoOrderDetail** Tabellen werden als Zieltabellen verwendet. Diese Tabellen basieren auf der **Sales.SalesOrderHeader** und **Sales.SalesOrderDetail** Tabellen in **AdventureWorks**.  
  
> [!NOTE]
>  Die **"SqlBulkCopy"** Codebeispiele werden bereitgestellt, um die Syntax für die Verwendung zu demonstrieren **"SqlBulkCopy"** nur. Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.  
  
## <a name="table-setup"></a>Einrichten der Tabellen  
 Zum Erstellen der Tabellen, die für das ordnungsgemäße Ausführen der Codebeispiele erforderlich sind, müssen Sie die folgenden Transact-SQL-Anweisungen in einer SQL Server-Datenbank ausführen:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Massenkopiervorgänge in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
