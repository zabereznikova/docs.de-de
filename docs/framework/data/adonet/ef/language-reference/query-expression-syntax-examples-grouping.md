---
title: 'Beispiele für die Abfrageausdruckssyntax: Gruppieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: 0a4aa57ba709852c30223598b9d1af146eaf6013
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211997"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="d497f-102">Beispiele für die Abfrageausdruckssyntax: Gruppieren</span><span class="sxs-lookup"><span data-stu-id="d497f-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="d497f-103">In diesem Thema wird gezeigt, wie mit der `GroupBy` -Methode und die [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="d497f-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="d497f-104">Für das in den Beispielen verwendete AdventureWorks Sales-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der AdventureWorks-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="d497f-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d497f-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="d497f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="d497f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d497f-106">Example</span></span>  
 <span data-ttu-id="d497f-107">Das folgende Beispiel gibt nach Postleitzahlen gruppierte `Address`-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="d497f-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="d497f-108">Die Ergebnisse werden in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="d497f-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="d497f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d497f-109">Example</span></span>  
 <span data-ttu-id="d497f-110">Das folgende Beispiel gibt nach dem ersten Buchstaben des Nachnamens des Kontakts gruppierte `Contact`-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="d497f-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="d497f-111">Die Ergebnisse werden nach dem ersten Buchstaben des Nachnamens sortiert und in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="d497f-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="d497f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d497f-112">Example</span></span>  
 <span data-ttu-id="d497f-113">Das folgende Beispiel gibt nach Kunden-ID gruppierte `SalesOrderHeader`-Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="d497f-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="d497f-114">Die Anzahl von Verkäufen für jeden Kunden wird ebenfalls zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d497f-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="d497f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d497f-115">See also</span></span>

- [<span data-ttu-id="d497f-116">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="d497f-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
