---
title: "Mehrere Massenkopiervorgänge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7db77dcd58e48927e8dac9bee82f7f14cdacf196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="multiple-bulk-copy-operations"></a>Mehrere Massenkopiervorgänge
Sie können mehrere Massenkopiervorgänge mithilfe einer einzigen Instanz der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse durchführen. Wenn die Parameter der Vorgänge zwischen den Kopien (z. B. den Namen der Zieltabelle) zu ändern, müssen Sie diese aktualisieren, vor allen nachfolgenden Aufrufen auf eines der **WriteToServer** Methoden, wie im folgenden Beispiel gezeigt. Sofern sie nicht explizit geändert werden, bleiben alle Eigenschaftswerte wie im vorherigen Massenkopiervorgang einer angegebenen Instanz erhalten.  
  
> [!NOTE]
>  Es ist effizienter, mehrere Massenkopiervorgänge mithilfe derselben Instanz der <xref:System.Data.SqlClient.SqlBulkCopy> durchzuführen, als für jeden Vorgang eine separate Instanz zu verwenden.  
  
 Wenn Sie mehrere Massenkopiervorgänge mithilfe desselben <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts durchführen, bestehen keine Einschränkungen, ob sich die Quell- oder Zielinformationen bei jedem Vorgang gleichen oder unterscheiden. Sie müssen sich jedoch vergewissern, dass die Informationen der Spaltenzuordnung immer ordnungsgemäß festgelegt sind, wenn Sie auf den Server schreiben.  
  
> [!IMPORTANT]
>  Dieses Beispiel wird nicht ausgeführt, es sei denn, Sie die Arbeitstabellen erstellt haben, wie in beschrieben [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Die angegebene Code dient zum Veranschaulichen der Syntax für die Verwendung von **"SqlBulkCopy"** nur. Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Massenkopiervorgänge in SQLServer](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
