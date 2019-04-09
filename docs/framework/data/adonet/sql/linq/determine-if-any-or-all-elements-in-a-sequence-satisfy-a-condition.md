---
title: Bestimmen, ob ein Element oder alle Elemente einer Sequenz eine Bedingung erfüllen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: c1bc8e18f2e3b0c67b98713e67fc261649a6a0e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128335"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="02ed0-102">Bestimmen, ob ein Element oder alle Elemente einer Sequenz eine Bedingung erfüllen</span><span class="sxs-lookup"><span data-stu-id="02ed0-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="02ed0-103">Der <xref:System.Linq.Enumerable.All%2A>-Operator gibt `true` zurück, wenn alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="02ed0-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="02ed0-104">Der <xref:System.Linq.Queryable.Any%2A>-Operator gibt `true` zurück, wenn ein beliebiges Element in einer Sequenz eine Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="02ed0-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02ed0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02ed0-105">Example</span></span>  
 <span data-ttu-id="02ed0-106">Im folgenden Beispiel wird eine Sequenz von Kunden mit mindestens einer Bestellung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="02ed0-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="02ed0-107">Die `Where` / `where` Klausel ergibt `true` Wenn der angegebene `Customer` verfügt über eine `Order`.</span><span class="sxs-lookup"><span data-stu-id="02ed0-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="02ed0-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02ed0-108">Example</span></span>  
 <span data-ttu-id="02ed0-109">Der folgende Visual Basic-Code ermittelt die Liste der Kunden, die noch keine Bestellungen übermittelt haben. Außerdem wird sichergestellt, dass für jeden Kunden in dieser Liste Kontaktinformationen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="02ed0-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="02ed0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02ed0-110">Example</span></span>  
 <span data-ttu-id="02ed0-111">Im folgenden C#-Beispiel wird eine Sequenz von Kunden zurückgegeben, deren Bestellungen einen `ShipCity` (Lieferort) aufweisen, der mit "C" anfängt.</span><span class="sxs-lookup"><span data-stu-id="02ed0-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="02ed0-112">Außerdem werden Kunden ohne bisherige Bestellungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="02ed0-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="02ed0-113">(Per Definition gibt der <xref:System.Linq.Queryable.All%2A>-Operator bei einer leeren Sequenz `true` zurück.) Kunden ohne Bestellungen werden mithilfe des `Count`-Operators von der Konsolenausgabe ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="02ed0-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="02ed0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02ed0-114">See also</span></span>

- [<span data-ttu-id="02ed0-115">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="02ed0-115">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
