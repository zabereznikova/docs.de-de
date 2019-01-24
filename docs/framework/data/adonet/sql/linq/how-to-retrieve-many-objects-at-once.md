---
title: 'Vorgehensweise: Abrufen von zahlreichen Objekten gleichzeitig'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 31091b6634c9d95c008929680620fb66d95d473c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653787"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="ed3e8-102">Vorgehensweise: Abrufen von zahlreichen Objekten gleichzeitig</span><span class="sxs-lookup"><span data-stu-id="ed3e8-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="ed3e8-103">Sie können in einer Abfrage viele Objekte abrufen, indem Sie <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed3e8-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed3e8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed3e8-104">Example</span></span>  
 <span data-ttu-id="ed3e8-105">Im folgenden Code wird die <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>-Methode verwendet, um ein `Customer`-Objekt und ein `Order`-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ed3e8-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="ed3e8-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed3e8-106">See also</span></span>
- [<span data-ttu-id="ed3e8-107">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="ed3e8-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
