---
title: 'Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: bc16dde89f67572b03102b1c091993ed163b443c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203526"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="cc3eb-102">Vorgehensweise: Behandeln von zusammengesetzten Schlüsseln in Abfragen</span><span class="sxs-lookup"><span data-stu-id="cc3eb-102">How to: Handle Composite Keys in Queries</span></span>

<span data-ttu-id="cc3eb-103">Einige Operatoren können nur ein Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="cc3eb-103">Some operators can take only one argument.</span></span> <span data-ttu-id="cc3eb-104">Muss Ihr Argument mehrere Datenbankspalten aufnehmen, müssen Sie einen anonymen Typ erstellen, um die Kombination darzustellen.</span><span class="sxs-lookup"><span data-stu-id="cc3eb-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc3eb-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc3eb-105">Example</span></span>  

 <span data-ttu-id="cc3eb-106">Das folgende Beispiel zeigt eine Abfrage, die den `GroupBy`-Operator aufruft. Dieser kann nur ein `key`-Argument aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="cc3eb-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="cc3eb-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc3eb-107">Example</span></span>  

 <span data-ttu-id="cc3eb-108">Die gleiche Situation betrifft Joins wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cc3eb-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cc3eb-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc3eb-109">See also</span></span>

- [<span data-ttu-id="cc3eb-110">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="cc3eb-110">Query Concepts</span></span>](query-concepts.md)
