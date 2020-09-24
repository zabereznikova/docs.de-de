---
title: 'Beispiele für die Abfrageausdruckssyntax: Gruppierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: 854d9c2a7371b80dd288a1d6c67272678efda135
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152935"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="50035-102">Beispiele für die Abfrageausdruckssyntax: Gruppierung</span><span class="sxs-lookup"><span data-stu-id="50035-102">Query Expression Syntax Examples: Grouping</span></span>

<span data-ttu-id="50035-103">In den Beispielen in diesem Thema wird gezeigt, wie die-Methode verwendet wird `GroupBy` , um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Abfrage Ausdruckssyntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="50035-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="50035-104">Für das in den Beispielen verwendete AdventureWorks Sales-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der AdventureWorks-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="50035-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="50035-105">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="50035-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="50035-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50035-106">Example</span></span>  

 <span data-ttu-id="50035-107">Das folgende Beispiel gibt nach Postleitzahlen gruppierte `Address`-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="50035-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="50035-108">Die Ergebnisse werden in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="50035-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="50035-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50035-109">Example</span></span>  

 <span data-ttu-id="50035-110">Das folgende Beispiel gibt nach dem ersten Buchstaben des Nachnamens des Kontakts gruppierte `Contact`-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="50035-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="50035-111">Die Ergebnisse werden nach dem ersten Buchstaben des Nachnamens sortiert und in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="50035-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="50035-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50035-112">Example</span></span>  

 <span data-ttu-id="50035-113">Das folgende Beispiel gibt nach Kunden-ID gruppierte `SalesOrderHeader`-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="50035-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="50035-114">Die Anzahl von Verkäufen für jeden Kunden wird ebenfalls zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50035-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="50035-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50035-115">See also</span></span>

- [<span data-ttu-id="50035-116">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="50035-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
