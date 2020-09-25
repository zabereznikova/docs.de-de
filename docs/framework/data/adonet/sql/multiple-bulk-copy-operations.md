---
title: Mehrere Massenkopiervorgänge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: d447f09fcbfe108346b81a2bced44cf305e2844b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172670"
---
# <a name="multiple-bulk-copy-operations"></a>Mehrere Massenkopiervorgänge

Mithilfe einer einzelnen Instanz einer <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie mehrere Massenkopiervorgänge ausführen. Wenn sich die Vorgangs Parameter zwischen den Kopien ändern (z. b. dem Namen der Ziel Tabelle), müssen Sie diese vor allen nachfolgenden Aufrufen einer der Methoden " **Write-toserver** " aktualisieren, wie im folgenden Beispiel gezeigt. Sofern sie nicht explizit geändert werden, bleiben alle Eigenschaftswerte die gleichen wie beim letzten Massenkopiervorgang für eine bestimmte Instanz.  
  
> [!NOTE]
> Das Ausführen mehrerer Massenkopiervorgänge mithilfe der gleichen Instanz von <xref:System.Data.SqlClient.SqlBulkCopy> ist normalerweise effizienter als die Verwendung einer separaten Instanz für jeden Vorgang.  
  
 Wenn Sie mehrere Massenkopiervorgänge mithilfe des gleichen <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts ausführen, bestehen normalerweise keine Einschränkungen hinsichtlich der Gleichheit oder Verschiedenheit der Quell- und Zielinformationen für die einzelnen Vorgänge. Sie müssen jedoch sicherstellen, dass die Informationen zur Spaltenzuordnung bei jedem Schreibvorgang auf dem Server ordnungsgemäß festgelegt sind.  
  
> [!IMPORTANT]
> Dieses Beispiel wird nur dann ausgeführt, wenn Sie die Arbeits Tabellen erstellt haben, wie unter [Beispiel für Massen Kopier](bulk-copy-example-setup.md)Vorgänge beschrieben. Der angegebene Code dient nur zur Demonstration der Syntax für die Verwendung von **SqlBulkCopy**. Wenn sich die Quell- und Zieltabellen in der gleichen SQL Server-Instanz befinden, ist die Verwendung einer Transact-SQL-Anweisung `INSERT … SELECT` zum Kopieren der Daten einfacher und schneller.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Massenkopiervorgänge in SQL Server](bulk-copy-operations-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
