---
title: Verketten von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: b802abae9fc2c1731a623209862f61ed5ee51f9c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247888"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="3fbae-102">Verketten von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="3fbae-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="3fbae-103">Verwenden Sie den <xref:System.Linq.Queryable.Concat%2A>-Operator, um zwei Sequenzen zu verketten.</span><span class="sxs-lookup"><span data-stu-id="3fbae-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="3fbae-104">Der <xref:System.Linq.Queryable.Concat%2A>-Operator wurde für geordnete Multisets definiert, bei denen die Reihenfolgen des Empfängers und das Argument identisch sind.</span><span class="sxs-lookup"><span data-stu-id="3fbae-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="3fbae-105">Die Sortierung in SQL ist der letzte Schritt vor dem Erzeugen von Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="3fbae-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="3fbae-106">Aus diesem Grund wird der <xref:System.Linq.Queryable.Concat%2A> durch Verwendung von `UNION ALL`-Operator implementiert, und die Reihenfolge der Argumente wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3fbae-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="3fbae-107">Um zu gewährleisten, dass die Sortierung der Ergebnisse richtig ist, stellen Sie sicher, dass diese explizit sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="3fbae-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fbae-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fbae-108">Example</span></span>  
 <span data-ttu-id="3fbae-109">In diesem Beispiel wird <xref:System.Linq.Queryable.Concat%2A> verwendet, um eine Sequenz der Telefon- und Faxnummern aller `Customer` (Kunden) und `Employee` (Mitarbeiter) zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3fbae-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="3fbae-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fbae-110">Example</span></span>  
 <span data-ttu-id="3fbae-111">In diesem Beispiel wird <xref:System.Linq.Queryable.Concat%2A> verwendet, um eine Sequenz aller Namens- und Telefonnummernzuordnungen für `Customer` (Kunden) und `Employee` (Mitarbeiter) zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3fbae-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="3fbae-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fbae-112">See also</span></span>

- [<span data-ttu-id="3fbae-113">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="3fbae-113">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="3fbae-114">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="3fbae-114">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
