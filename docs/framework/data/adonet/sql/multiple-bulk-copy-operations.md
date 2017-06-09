---
title: "Mehrere Massenkopiervorg&#228;nge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Mehrere Massenkopiervorg&#228;nge
Sie können mehrere Massenkopiervorgänge mithilfe einer einzigen Instanz der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse durchführen.  Wenn sich die Parameter der Vorgänge zwischen den Kopien ändern \(z. B. der Name der Zieltabelle\), müssen Sie diese vor den nachfolgenden Aufrufen einer der **WriteToServer**\-Methoden wie im folgenden Beispiel dargestellt aktualisieren.  Sofern sie nicht explizit geändert werden, bleiben alle Eigenschaftswerte wie im vorherigen Massenkopiervorgang einer angegebenen Instanz erhalten.  
  
> [!NOTE]
>  Es ist effizienter, mehrere Massenkopiervorgänge mithilfe derselben Instanz der <xref:System.Data.SqlClient.SqlBulkCopy> durchzuführen, als für jeden Vorgang eine separate Instanz zu verwenden.  
  
 Wenn Sie mehrere Massenkopiervorgänge mithilfe desselben <xref:System.Data.SqlClient.SqlBulkCopy>\-Objekts durchführen, bestehen keine Einschränkungen, ob sich die Quell\- oder Zielinformationen bei jedem Vorgang gleichen oder unterscheiden.  Sie müssen sich jedoch vergewissern, dass die Informationen der Spaltenzuordnung immer ordnungsgemäß festgelegt sind, wenn Sie auf den Server schreiben.  
  
> [!IMPORTANT]
>  Dieses Beispiel wird nur ausgeführt, wenn Sie die Arbeitstabellen, wie in [Beispiel für die Massenkopiereinrichtung](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md) beschrieben, erstellt haben.  Der angegebene Code dient nur zur Demonstration der Syntax für die Verwendung von **SqlBulkCopy**.  Wenn sich die Quell\- und die Zieltabelle in derselben SQL Server\-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact\-SQL\-`INSERT … SELECT`\-Anweisung kopieren.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## Siehe auch  
 [Massenkopiervorgänge in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)