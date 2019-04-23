---
title: Transaktionen und Massenkopiervorgänge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f6f0cbc9-f7bf-4d6e-875f-ad1ba0b4aa62
ms.openlocfilehash: f30974e020545a69ad20c03bc05ac6a28f289b01
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074624"
---
# <a name="transaction-and-bulk-copy-operations"></a>Transaktionen und Massenkopiervorgänge
Massenkopiervorgänge können als isolierte Vorgänge oder als Teil einer mehrstufigen Transaktion ausgeführt werden. Die Ausführung als Teil einer mehrstufigen Transaktion ermöglicht es Ihnen, innerhalb ein und derselben Transaktion mehr als einen Massenkopiervorgang sowie andere Datenbankoperationen (z. B. Einfüge-, Update- und Löschvorgänge) auszuführen, ohne dabei auf die Möglichkeit verzichten zu müssen, einen Commit oder einen Rollback für die gesamte Transaktion durchführen zu können.  
  
 Massenkopiervorgänge werden standardmäßig als isolierte Vorgänge ausgeführt. Der Massenkopiervorgang erfolgt auf eine nicht transaktive Art und Weise und bietet keine Möglichkeit für einen Rollback. Bei Bedarf ganz oder teilweise den Massenkopiervorgang beim Rollback ein Fehler auftritt, können Sie eine <xref:System.Data.SqlClient.SqlBulkCopy>-verwaltete Transaktion verwenden, den Massenkopiervorgang innerhalb einer vorhandenen Transaktion ausführen, oder einem **System.Transactions** <xref:System.Transactions.Transaction>.  
  
## <a name="performing-a-non-transacted-bulk-copy-operation"></a>Ausführen eines nicht transaktiven Massenkopiervorgangs  
 Die folgende Konsolenanwendung zeigt, was passiert, wenn während eines nicht transaktiven Massenkopiervorgangs ein Fehler auftritt.  
  
 Im Beispiel enthalten, die Quell- und Zieltabelle jeweils eine `Identity` Spalte mit dem Namen **"ProductID"**. Der Code bereitet zunächst die Zieltabelle vor, indem Löschen aller Zeilen aus, und klicken Sie dann eine einzelne Zeile einfügt, deren **"ProductID"** ist bekannt, in der Quelltabelle vorhanden sein. In der Standardeinstellung wird für jede hinzugefügte Zeile ein neuer Wert für die `Identity`-Spalte in der Zieltabelle generiert. In diesem Beispiel wird beim Öffnen der Verbindung eine Option festgelegt, durch die beim Massenladevorgang stattdessen die `Identity`-Werte aus der Quelltabelle verwendet werden.  
  
 Der Massenkopiervorgang wird mit der Einstellung "10" für die <xref:System.Data.SqlClient.SqlBulkCopy.BatchSize%2A>-Eigenschaft ausgeführt. Wenn der Vorgang auf die ungültige Zeile stößt, wird eine Ausnahme ausgelöst. In diesem ersten Beispiel ist der Massenkopiervorgang nicht Teil einer Transaktion. Für alle bis zum Zeitpunkt des Fehlers kopierten Batches wird ein Commit ausgeführt. Für den Batch mit dem doppelten Schlüssel wird ein Rollback ausgeführt, und der Massenkopiervorgang wird vor der Verarbeitung weiterer Batches angehalten.  
  
> [!NOTE]
>  In diesem Beispiel wird nicht ausgeführt werden, es sei denn, Sie die Arbeitstabellen erstellt haben, wie in beschrieben [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Dieser Code wird bereitgestellt, um zu veranschaulichen die Syntax für die Verwendung von **"SqlBulkCopy"** nur. Wenn Quell-und Ziel in der gleichen SQL Server-Instanz befinden, es ist einfacher und schneller eine [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` Anweisung, um die Daten zu kopieren.  
  
 [!code-csharp[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/VB/source.vb#1)]  
  
## <a name="performing-a-dedicated-bulk-copy-operation-in-a-transaction"></a>Ausführen eines dedizierten Massenkopiervorgangs in einer Transaktion  
 Standardmäßig ist ein Massenkopiervorgang seine eigene Transaktion. Wenn Sie einen dedizierten Massenkopiervorgang ausführen möchten, erstellen Sie eine neue Instanz von <xref:System.Data.SqlClient.SqlBulkCopy> mit einer Verbindungszeichenfolge, oder Sie verwenden ein vorhandenes <xref:System.Data.SqlClient.SqlConnection>-Objekt ohne aktive Transaktion. In allen Szenarien erstellt der Massenkopiervorgang die Transaktion und führt dann einen Commit oder einen Rollback aus.  
  
 Sie können die <xref:System.Data.SqlClient.SqlBulkCopyOptions.UseInternalTransaction>-Option im <xref:System.Data.SqlClient.SqlBulkCopy>-Klassenkonstruktor explizit angeben und so einen Massenkopiervorgang explizit dazu zwingen, seine eigene Transaktion auszuführen, wodurch jeder Batch des Massenkopiervorgangs innerhalb einer separaten Transaktion ausgeführt wird.  
  
> [!NOTE]
>  Da verschiedene Batches in unterschiedlichen Transaktionen ausgeführt werden, wird für alle Zeilen im aktuellen Batch ein Rollback ausgeführt, wenn beim Ausführen des Massenkopiervorgangs ein Fehler auftritt. Zeilen aus früheren Batches verbleiben jedoch in der Datenbank.  
  
 Die folgende Konsolenanwendung ähnelt mit einer Ausnahme dem vorherigen Beispiel: In diesem Beispiel verwaltet der Massenkopiervorgang eine eigene Transaktion. Für alle bis zum Zeitpunkt des Fehlers kopierten Batches wird ein Commit ausgeführt. Für den Batch mit dem doppelten Schlüssel wird ein Rollback ausgeführt, und der Massenkopiervorgang wird vor der Verarbeitung weiterer Batches angehalten.  
  
> [!IMPORTANT]
>  In diesem Beispiel wird nicht ausgeführt werden, es sei denn, Sie die Arbeitstabellen erstellt haben, wie in beschrieben [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Dieser Code wird bereitgestellt, um zu veranschaulichen die Syntax für die Verwendung von **"SqlBulkCopy"** nur. Wenn Quell-und Ziel in der gleichen SQL Server-Instanz befinden, es ist einfacher und schneller eine [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` Anweisung, um die Daten zu kopieren.  
  
 [!code-csharp[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/VB/source.vb#1)]  
  
## <a name="using-existing-transactions"></a>Verwenden vorhandener Transaktionen  
 Sie können ein vorhandenes <xref:System.Data.SqlClient.SqlTransaction>-Objekt als Parameter in einem <xref:System.Data.SqlClient.SqlBulkCopy>-Konstruktor angeben. In dieser Situation wird der Massenkopiervorgang in einer vorhandenen Transaktion ausgeführt. Der Transaktionszustand bleibt unverändert (d. h., es erfolgt weder ein Commit noch ein Abbruch). Daher ist es möglich, dass in einer Anwendung der Massenkopiervorgang in einer Transaktion zusammen mit anderen Datenbankoperationen ausgeführt wird. Wenn Sie jedoch kein <xref:System.Data.SqlClient.SqlTransaction>-Objekt angeben und einen NULL-Verweis übergeben und die Verbindung außerdem eine aktive Transaktion aufweist, wird eine Ausnahme ausgelöst.  
  
 Wenn Sie einen Rollback für den gesamten Massenkopiervorgang ausführen müssen, weil ein Fehler aufgetreten ist, oder wenn der Massenkopiervorgang als Teil eines größeren Prozesses ausgeführt werden soll, für den ein Rollback ausgeführt werden kann, können Sie dem <xref:System.Data.SqlClient.SqlTransaction>-Konstruktor ein <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt bereitstellen.  
  
 Die folgende Konsolenanwendung ähnelt der im vorherigen Beispiel, jedoch mit einem Unterschied: In diesem Beispiel ist der Massenkopiervorgang Teil einer größeren, externen Transaktion. Wenn der Fehler für einen Primärschlüsselkonflikt auftritt, wird ein Rollback für die gesamte Transaktion ausgeführt. In diesem Fall werden der Zieltabelle keine Zeilen hinzugefügt.  
  
> [!IMPORTANT]
>  In diesem Beispiel wird nicht ausgeführt werden, es sei denn, Sie die Arbeitstabellen erstellt haben, wie in beschrieben [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Dieser Code wird bereitgestellt, um zu veranschaulichen die Syntax für die Verwendung von **"SqlBulkCopy"** nur. Wenn Quell-und Ziel in der gleichen SQL Server-Instanz befinden, es ist einfacher und schneller eine [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` Anweisung, um die Daten zu kopieren.  
  
 [!code-csharp[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Massenkopiervorgänge in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
