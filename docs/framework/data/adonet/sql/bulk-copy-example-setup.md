---
title: "Beispiel f&#252;r die Massenkopiereinrichtung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Beispiel f&#252;r die Massenkopiereinrichtung
Mit der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse können Daten nur in SQL Server\-Tabellen geschrieben werden.  Die in diesem Thema enthaltenen Codebeispiele verwenden die SQL Server\-Beispieldatenbank **AdventureWorks**.  Um Änderungen an den vorhandenen Tabellen zu vermeiden, schreiben die Codebeispiele in Tabellen, die zunächst erstellt werden müssen.  
  
 Die **BulkCopyDemoMatchingColumns**\-Tabelle und die **BulkCopyDemoDifferentColumns**\-Tabelle basieren beide auf der **Production.Products**\-Tabelle der **AdventureWorks**\-Datenbank.  In Codebeispielen, in denen diese Tabellen verwendet werden, werden der jeweiligen Beispieltabelle Daten aus der **Production.Products**\-Tabelle hinzugefügt.  Die **BulkCopyDemoDifferentColumns**\-Tabelle wird in Beispielen verwendet, in denen das Zuordnen von Spalten aus der Datenquelle zur Zieltabelle veranschaulicht wird. In den meisten anderen Beispielen wird die **BulkCopyDemoMatchingColumns**\-Tabelle verwendet.  
  
 In einigen Codebeispielen wird veranschaulicht, wie mit einer <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse in mehrere Tabellen geschrieben werden kann.  In diesen Beispielen werden als Zieltabellen die **BulkCopyDemoOrderHeader**\-Tabelle und die **BulkCopyDemoOrderDetail**\-Tabelle verwendet.  Diese Tabellen basieren auf der **Sales.SalesOrderHeader**\-Tabelle und der **Sales.SalesOrderDetail**\-Tabelle in der **AdventureWorks**\-Datenbank.  
  
> [!NOTE]
>  Die **SqlBulkCopy**\-Codebeispiele dienen ausschließlich der Veranschaulichung der für **SqlBulkCopy** verwendeten Syntax.  Wenn sich die Quell\- und die Zieltabelle in derselben SQL Server\-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact\-SQL\-`INSERT … SELECT`\-Anweisung kopieren.  
  
## Einrichten der Tabellen  
 Zum Erstellen der Tabellen, die für das ordnungsgemäße Ausführen der Codebeispiele erforderlich sind, müssen Sie die folgenden Transact\-SQL\-Anweisungen in einer SQL Server\-Datenbank ausführen:  
  
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
  
## Siehe auch  
 [Massenkopiervorgänge in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)