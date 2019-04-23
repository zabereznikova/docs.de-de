---
title: 'Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 2621ab4db207d1b868fbe3778c30c744201b0506
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135251"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="bb54d-102">Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen</span><span class="sxs-lookup"><span data-stu-id="bb54d-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="bb54d-103">Einige Operatoren können nur ein Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="bb54d-103">Some operators can take only one argument.</span></span> <span data-ttu-id="bb54d-104">Muss Ihr Argument mehrere Datenbankspalten aufnehmen, müssen Sie einen anonymen Typ erstellen, um die Kombination darzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb54d-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb54d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb54d-105">Example</span></span>  
 <span data-ttu-id="bb54d-106">Das folgende Beispiel zeigt eine Abfrage, die den `GroupBy`-Operator aufruft. Dieser kann nur ein `key`-Argument aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="bb54d-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="bb54d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb54d-107">Example</span></span>  
 <span data-ttu-id="bb54d-108">Die gleiche Situation betrifft Joins wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bb54d-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bb54d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb54d-109">See also</span></span>

- [<span data-ttu-id="bb54d-110">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="bb54d-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
