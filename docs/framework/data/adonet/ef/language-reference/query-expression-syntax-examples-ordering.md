---
title: 'Beispiele für die Abfrageausdruckssyntax: Sortieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: ed03fc248ed48f56998bc27f7e880b1e8aa443d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156783"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="5a58e-102">Beispiele für die Abfrageausdruckssyntax: Sortieren</span><span class="sxs-lookup"><span data-stu-id="5a58e-102">Query Expression Syntax Examples: Ordering</span></span>

<span data-ttu-id="5a58e-103">In den Beispielen in diesem Thema wird gezeigt, wie die `OrderBy` -Methode und die-Methode verwendet werden `OrderByDescending` , um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Abfrage Ausdruckssyntax abzu</span><span class="sxs-lookup"><span data-stu-id="5a58e-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="5a58e-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="5a58e-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="5a58e-105">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="5a58e-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="5a58e-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="5a58e-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="5a58e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a58e-107">Example</span></span>  

 <span data-ttu-id="5a58e-108">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.OrderBy%2A> verwendet, um eine nach Nachnamen sortierte Liste der Kontakte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5a58e-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="5a58e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a58e-109">Example</span></span>  

 <span data-ttu-id="5a58e-110">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.OrderBy%2A> verwendet, um eine Liste von Kontakten nach der Länge der Nachnamen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5a58e-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="5a58e-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="5a58e-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="5a58e-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a58e-112">Example</span></span>  

 <span data-ttu-id="5a58e-113">Im folgenden Beispiel wird `orderby… descending` (`Order By … Descending` in Visual Basic), das Äquivalent zur <xref:System.Linq.Enumerable.OrderByDescending%2A>-Methode, verwendet, um die Preisliste in absteigender Reihenfolge (höchster Preis zuerst, niedrigster zuletzt) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5a58e-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="5a58e-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="5a58e-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="5a58e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a58e-115">Example</span></span>  

 <span data-ttu-id="5a58e-116">Im folgenden Beispiel werden <xref:System.Linq.Queryable.OrderBy%2A> und <xref:System.Linq.Queryable.ThenBy%2A> verwendet, um eine zuerst nach Nachnamen und dann nach Vornamen sortierte Liste der Kontakte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5a58e-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="5a58e-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="5a58e-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="5a58e-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a58e-118">Example</span></span>  

 <span data-ttu-id="5a58e-119">Im folgenden Beispiel wird `OrderBy… Descending`, das Äquivalent zur <xref:System.Linq.Enumerable.ThenByDescending%2A>-Methode, verwendet, um eine Liste von Produkten zuerst nach dem Namen und dann absteigend nach dem Listenpreis (höchster Preis zuerst, niedrigster Preis zuletzt) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5a58e-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="5a58e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a58e-120">See also</span></span>

- [<span data-ttu-id="5a58e-121">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="5a58e-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
