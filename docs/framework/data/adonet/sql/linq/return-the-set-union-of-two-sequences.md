---
title: Zurückgeben der Vereinigungsmenge von zwei Sequenzen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 0fe32d8c3c37e99a50ca03262dc6184337b4450e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200201"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="1eb6c-102">Zurückgeben der Vereinigungsmenge von zwei Sequenzen</span><span class="sxs-lookup"><span data-stu-id="1eb6c-102">Return the Set Union of Two Sequences</span></span>

<span data-ttu-id="1eb6c-103">Verwenden Sie den <xref:System.Linq.Queryable.Union%2A>-Operator, um die Vereinigungsmenge von zwei Sequenzen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1eb6c-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eb6c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1eb6c-104">Example</span></span>  

 <span data-ttu-id="1eb6c-105">In diesem Beispiel <xref:System.Linq.Queryable.Union%2A> wird verwendet, um eine Sequenz aller Länder/Regionen zurückzugeben, in denen entweder oder vorhanden ist `Customers` `Employees` .</span><span class="sxs-lookup"><span data-stu-id="1eb6c-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="1eb6c-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird der- <xref:System.Linq.Queryable.Union%2A> Operator für Multisets als ungeordnete Verkettung der Multisets definiert (effektiv das Ergebnis der- [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) Klausel in SQL).</span><span class="sxs-lookup"><span data-stu-id="1eb6c-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="1eb6c-107">Weitere Informationen und Beispiele finden Sie unter <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1eb6c-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1eb6c-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1eb6c-108">See also</span></span>

- [<span data-ttu-id="1eb6c-109">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="1eb6c-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="1eb6c-110">Übersetzen von Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="1eb6c-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
