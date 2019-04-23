---
title: 'Beispiele für die Abfrageausdruckssyntax: Sortieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: ea9e7cb61facb880a050fbfae3aa9b07c03361fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164150"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="5e2ad-102">Beispiele für die Abfrageausdruckssyntax: Sortieren</span><span class="sxs-lookup"><span data-stu-id="5e2ad-102">Query Expression Syntax Examples: Ordering</span></span>
<span data-ttu-id="5e2ad-103">In diesem Thema wird gezeigt, wie mit der `OrderBy` und `OrderByDescending` Methoden zum Abfragen der [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="5e2ad-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="5e2ad-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="5e2ad-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="5e2ad-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="5e2ad-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="5e2ad-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2ad-107">Example</span></span>  
 <span data-ttu-id="5e2ad-108">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.OrderBy%2A> verwendet, um eine nach Nachnamen sortierte Liste der Kontakte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="5e2ad-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2ad-109">Example</span></span>  
 <span data-ttu-id="5e2ad-110">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.OrderBy%2A> verwendet, um eine Liste von Kontakten nach der Länge der Nachnamen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="5e2ad-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="5e2ad-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="5e2ad-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2ad-112">Example</span></span>  
 <span data-ttu-id="5e2ad-113">Im folgenden Beispiel wird `orderby… descending` (`Order By … Descending` in Visual Basic), das Äquivalent zur <xref:System.Linq.Enumerable.OrderByDescending%2A>-Methode, verwendet, um die Preisliste in absteigender Reihenfolge (höchster Preis zuerst, niedrigster zuletzt) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="5e2ad-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="5e2ad-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="5e2ad-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2ad-115">Example</span></span>  
 <span data-ttu-id="5e2ad-116">Im folgenden Beispiel werden <xref:System.Linq.Queryable.OrderBy%2A> und <xref:System.Linq.Queryable.ThenBy%2A> verwendet, um eine zuerst nach Nachnamen und dann nach Vornamen sortierte Liste der Kontakte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="5e2ad-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="5e2ad-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="5e2ad-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e2ad-118">Example</span></span>  
 <span data-ttu-id="5e2ad-119">Im folgenden Beispiel wird `OrderBy… Descending`, das Äquivalent zur <xref:System.Linq.Enumerable.ThenByDescending%2A>-Methode, verwendet, um eine Liste von Produkten zuerst nach dem Namen und dann absteigend nach dem Listenpreis (höchster Preis zuerst, niedrigster Preis zuletzt) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5e2ad-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="5e2ad-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e2ad-120">See also</span></span>

- [<span data-ttu-id="5e2ad-121">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="5e2ad-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
