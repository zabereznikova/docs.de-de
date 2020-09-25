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
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="2961e-102">Mehrere Massenkopiervorgänge</span><span class="sxs-lookup"><span data-stu-id="2961e-102">Multiple Bulk Copy Operations</span></span>

<span data-ttu-id="2961e-103">Mithilfe einer einzelnen Instanz einer <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse können Sie mehrere Massenkopiervorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="2961e-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="2961e-104">Wenn sich die Vorgangs Parameter zwischen den Kopien ändern (z. b. dem Namen der Ziel Tabelle), müssen Sie diese vor allen nachfolgenden Aufrufen einer der Methoden " **Write-toserver** " aktualisieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2961e-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="2961e-105">Sofern sie nicht explizit geändert werden, bleiben alle Eigenschaftswerte die gleichen wie beim letzten Massenkopiervorgang für eine bestimmte Instanz.</span><span class="sxs-lookup"><span data-stu-id="2961e-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2961e-106">Das Ausführen mehrerer Massenkopiervorgänge mithilfe der gleichen Instanz von <xref:System.Data.SqlClient.SqlBulkCopy> ist normalerweise effizienter als die Verwendung einer separaten Instanz für jeden Vorgang.</span><span class="sxs-lookup"><span data-stu-id="2961e-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="2961e-107">Wenn Sie mehrere Massenkopiervorgänge mithilfe des gleichen <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts ausführen, bestehen normalerweise keine Einschränkungen hinsichtlich der Gleichheit oder Verschiedenheit der Quell- und Zielinformationen für die einzelnen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="2961e-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="2961e-108">Sie müssen jedoch sicherstellen, dass die Informationen zur Spaltenzuordnung bei jedem Schreibvorgang auf dem Server ordnungsgemäß festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2961e-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2961e-109">Dieses Beispiel wird nur dann ausgeführt, wenn Sie die Arbeits Tabellen erstellt haben, wie unter [Beispiel für Massen Kopier](bulk-copy-example-setup.md)Vorgänge beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2961e-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="2961e-110">Der angegebene Code dient nur zur Demonstration der Syntax für die Verwendung von **SqlBulkCopy**.</span><span class="sxs-lookup"><span data-stu-id="2961e-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="2961e-111">Wenn sich die Quell- und Zieltabellen in der gleichen SQL Server-Instanz befinden, ist die Verwendung einer Transact-SQL-Anweisung `INSERT … SELECT` zum Kopieren der Daten einfacher und schneller.</span><span class="sxs-lookup"><span data-stu-id="2961e-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2961e-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2961e-112">See also</span></span>

- [<span data-ttu-id="2961e-113">Massenkopiervorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="2961e-113">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="2961e-114">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2961e-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
