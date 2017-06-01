---
title: "Massenkopiervorg&#228;nge in SQL&#160;Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Massenkopiervorg&#228;nge in SQL&#160;Server
Microsoft SQL Server beinhaltet das häufig verwendete Befehlszeilenhilfsprogramm **bcp**, mit dem große Dateien schnell in Tabellen oder Ansichten in SQL Server\-Datenbanken kopiert werden können.  Mit der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse können Sie verwaltete Codelösungen schreiben, durch die ähnliche Funktionen bereitgestellt werden.  Es stehen auch andere Möglichkeiten zum Laden von Daten in eine SQL Server\-Tabelle zur Verfügung \(z. B. INSERT\-Anweisungen\), <xref:System.Data.SqlClient.SqlBulkCopy> weist diesen gegenüber jedoch einen deutlichen Leistungsvorteil auf.  
  
 Mit der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse können Daten nur in SQL Server\-Tabellen geschrieben werden.  Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>\-Instanz geladen oder mit einer <xref:System.Data.IDataReader>\-Instanz gelesen werden.  
  
 Mit der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse können Sie folgende Vorgänge ausführen:  
  
-   Einzelne Massenkopiervorgänge  
  
-   Mehrere Massenkopiervorgänge  
  
-   Massenkopiervorgänge innerhalb von Transaktionen  
  
> [!NOTE]
>  Wenn Sie .NET Framework, Version 1.1 oder früher, verwenden \(bei diesen Versionen wird die <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse nicht unterstützt\), können Sie die **BULK INSERT**\-Anweisung von Transact\-SQL für SQL Server mit dem <xref:System.Data.SqlClient.SqlCommand>\-Objekt ausführen.  
  
## In diesem Abschnitt  
 [Beispiel für die Massenkopiereinrichtung](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 Beschreibt die in den Beispielen für Massenkopiervorgänge verwendeten Tabellen und stellt SQL\-Skripts zum Erstellen der Tabellen in der AdventureWorks\-Datenbank bereit.  
  
 [Einzelne Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 Beschreibt die Durchführung eines einzelnen Massenkopiervorgangs für Daten in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse sowie die Durchführung des Massenkopiervorgangs mithilfe von Transact\-SQL\-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>\-Klasse.  
  
 [Mehrere Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 Beschreibt die Durchführung mehrerer Massenkopiervorgänge in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse.  
  
 [Transaktionen und Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 Beschreibt die Durchführung eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Ausführens eines Commit oder Rollback für diese Transaktion.  
  
## Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)