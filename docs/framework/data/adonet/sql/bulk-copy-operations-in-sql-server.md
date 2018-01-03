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
ms.workload: dotnet
ms.openlocfilehash: fadb149e92b65988b8f9f322752bc63e1ee65f19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="bulk-copy-operations-in-sql-server"></a>Massenkopiervorgänge in SQL Server
Microsoft SQL Server enthält ein beliebtes Befehlszeilentools-Hilfsprogramm, die mit dem Namen **Bcp** für schnellen Massenkopieren großer Dateiumfänge in Tabellen oder Sichten in SQL Server-Datenbanken. Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie verwaltete Codelösungen schreiben, durch die ähnliche Funktionen bereitgestellt werden. Es stehen auch andere Möglichkeiten zum Laden von Daten in eine SQL Server-Tabelle zur Verfügung (z. B. INSERT-Anweisungen), <xref:System.Data.SqlClient.SqlBulkCopy> weist diesen gegenüber jedoch einen deutlichen Leistungsvorteil auf.  
  
 Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Daten nur in SQL Server-Tabellen geschrieben werden. Die Datenquelle hingegen ist nicht auf SQL Server beschränkt. Es können beliebige Datenquellen verwendet werden, vorausgesetzt die Daten können in eine <xref:System.Data.DataTable>-Instanz geladen oder mit einer <xref:System.Data.IDataReader>-Instanz gelesen werden.  
  
 Mit der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie folgende Vorgänge ausführen:  
  
-   Einzelne Massenkopiervorgänge  
  
-   Mehrere Massenkopiervorgänge  
  
-   Massenkopiervorgänge innerhalb von Transaktionen  
  
> [!NOTE]
>  Bei Verwendung von .NET Framework, Version 1.1 oder früher (nicht unterstützt die <xref:System.Data.SqlClient.SqlBulkCopy> Klasse), können Sie die SQL Server Transact-SQL ausführen **BULK INSERT** Anweisung mithilfe der <xref:System.Data.SqlClient.SqlCommand> Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 Beschreibt die in den Beispielen für Massenkopiervorgänge verwendeten Tabellen und stellt SQL-Skripts zum Erstellen der Tabellen in der AdventureWorks-Datenbank bereit.  
  
 [Einzelne Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 Beschreibt die Durchführung eines einzelnen Massenkopiervorgangs für Daten in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse sowie die Durchführung des Massenkopiervorgangs mithilfe von Transact-SQL-Anweisungen und der <xref:System.Data.SqlClient.SqlCommand>-Klasse.  
  
 [Mehrere Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 Beschreibt die Durchführung mehrerer Massenkopiervorgänge in eine Instanz von SQL Server unter Verwendung der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse.  
  
 [Transaktionen und Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 Beschreibt die Durchführung eines Massenkopiervorgangs innerhalb einer Transaktion, einschließlich des Ausführens eines Commit oder Rollback für diese Transaktion.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
