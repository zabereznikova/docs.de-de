---
title: 'Vorgehensweise: Gleichzeitiges Abrufen von zahlreichen Objekten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 48cdb47bec35b5315e03629d3a01657136bf7ed2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781684"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="c9f68-102">Vorgehensweise: Gleichzeitiges Abrufen von zahlreichen Objekten</span><span class="sxs-lookup"><span data-stu-id="c9f68-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="c9f68-103">Sie können in einer Abfrage viele Objekte abrufen, indem Sie <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9f68-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9f68-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9f68-104">Example</span></span>  
 <span data-ttu-id="c9f68-105">Im folgenden Code wird die <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>-Methode verwendet, um ein `Customer`-Objekt und ein `Order`-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c9f68-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c9f68-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9f68-106">See also</span></span>

- [<span data-ttu-id="c9f68-107">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="c9f68-107">Query Concepts</span></span>](query-concepts.md)
