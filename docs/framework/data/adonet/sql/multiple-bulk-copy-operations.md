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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8a753357719f451ce7acc2d7f42c0493ca2357ab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="f1992-102">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="f1992-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="f1992-103">Sie können mehrere Massenkopiervorgänge mithilfe einer einzigen Instanz der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse durchführen.</span><span class="sxs-lookup"><span data-stu-id="f1992-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="f1992-104">Wenn die Parameter der Vorgänge zwischen den Kopien (z. B. den Namen der Zieltabelle) zu ändern, müssen Sie diese aktualisieren, vor allen nachfolgenden Aufrufen auf eines der **WriteToServer** Methoden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1992-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="f1992-105">Sofern sie nicht explizit geändert werden, bleiben alle Eigenschaftswerte wie im vorherigen Massenkopiervorgang einer angegebenen Instanz erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1992-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1992-106">Es ist effizienter, mehrere Massenkopiervorgänge mithilfe derselben Instanz der <xref:System.Data.SqlClient.SqlBulkCopy> durchzuführen, als für jeden Vorgang eine separate Instanz zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1992-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="f1992-107">Wenn Sie mehrere Massenkopiervorgänge mithilfe desselben <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts durchführen, bestehen keine Einschränkungen, ob sich die Quell- oder Zielinformationen bei jedem Vorgang gleichen oder unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f1992-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="f1992-108">Sie müssen sich jedoch vergewissern, dass die Informationen der Spaltenzuordnung immer ordnungsgemäß festgelegt sind, wenn Sie auf den Server schreiben.</span><span class="sxs-lookup"><span data-stu-id="f1992-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1992-109">Dieses Beispiel wird nicht ausgeführt, es sei denn, Sie die Arbeitstabellen erstellt haben, wie in beschrieben [Einrichtung der Massenkopierbeispiele](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="f1992-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="f1992-110">Die angegebene Code dient zum Veranschaulichen der Syntax für die Verwendung von **"SqlBulkCopy"** nur.</span><span class="sxs-lookup"><span data-stu-id="f1992-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="f1992-111">Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.</span><span class="sxs-lookup"><span data-stu-id="f1992-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1992-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1992-112">See Also</span></span>  
 [<span data-ttu-id="f1992-113">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1992-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="f1992-114">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f1992-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
