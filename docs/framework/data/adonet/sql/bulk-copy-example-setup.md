---
title: Einrichtung der Massenkopierbeispiele
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 28fa5cde1dcbaf9f38450116a56fc11d904edc1c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040255"
---
# <a name="bulk-copy-example-setup"></a>Einrichtung der Massenkopierbeispiele
Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden. In den in diesem Thema gezeigten Codebeispielen wird die SQL Server-Beispieldatenbank **AdventureWorks**verwendet. Um Änderungen an den vorhandenen Tabellen zu vermeiden, schreiben die Codebeispiele in Tabellen, die zunächst erstellt werden müssen.  
  
 Die **BulkCopyDemoMatchingColumns** -Tabelle und die **BulkCopyDemoDifferentColumns** -Tabelle basieren beide auf der **AdventureWorks** **Production. Products** -Tabelle. In Codebeispielen, in denen diese Tabellen verwendet werden, werden Daten aus der **Production. Products** -Tabelle einer dieser Beispiel Tabellen hinzugefügt. Die **BulkCopyDemoDifferentColumns** -Tabelle wird verwendet, wenn das Beispiel veranschaulicht, wie Spalten aus den Quelldaten der Ziel Tabelle zugeordnet werden. **Bulkcopytomomatchingcolumns** wird für die meisten anderen Beispiele verwendet.  
  
 In einigen Codebeispielen wird veranschaulicht, wie mit einer <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse in mehrere Tabellen geschrieben werden kann. Für diese Beispiele werden die **BulkCopyDemoOrderHeader** -Tabelle und die **BulkCopyDemoOrderDetail** -Tabelle als Ziel Tabellen verwendet. Diese Tabellen basieren auf der **Sales. SalesOrderHeader** -Tabelle und der **Sales. SalesOrderDetail** -Tabelle in **AdventureWorks**.  
  
> [!NOTE]
> Die **SqlBulkCopy** -Codebeispiele werden bereitgestellt, um die Syntax nur für die Verwendung von **SqlBulkCopy** zu veranschaulichen. Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.  
  
## <a name="table-setup"></a>Einrichten der Tabellen  
 Zum Erstellen der Tabellen, die für das ordnungsgemäße Ausführen der Codebeispiele erforderlich sind, müssen Sie die folgenden Transact-SQL-Anweisungen in einer SQL Server-Datenbank ausführen:  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Massenkopiervorgänge in SQL Server](bulk-copy-operations-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
