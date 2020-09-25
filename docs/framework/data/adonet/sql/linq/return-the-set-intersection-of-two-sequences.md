---
title: Zurückgeben der Schnittmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 421ec544345e41f910bf80c855a3a6b4de1c46a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200224"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="99b0a-102">Zurückgeben der Schnittmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="99b0a-102">Return the Set Intersection of Two Sequences</span></span>

<span data-ttu-id="99b0a-103">Verwenden Sie den <xref:System.Linq.Queryable.Intersect%2A>-Operator, um die Schnittmenge von zwei Sequenzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="99b0a-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b0a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99b0a-104">Example</span></span>  

 <span data-ttu-id="99b0a-105">In diesem Beispiel wird verwendet <xref:System.Linq.Queryable.Intersect%2A> , um eine Sequenz aller Länder/Regionen zurückzugeben, in denen und aktiv sind `Customers` `Employees` .</span><span class="sxs-lookup"><span data-stu-id="99b0a-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="99b0a-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird die <xref:System.Linq.Queryable.Intersect%2A>-Operation nur für Sätze gut definiert.</span><span class="sxs-lookup"><span data-stu-id="99b0a-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="99b0a-107">Die Semantik für Multisets ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="99b0a-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b0a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99b0a-108">See also</span></span>

- [<span data-ttu-id="99b0a-109">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="99b0a-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="99b0a-110">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="99b0a-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
