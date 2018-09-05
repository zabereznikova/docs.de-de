---
title: 'Beispiele für die Abfrageausdruckssyntax: Elementoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 36823b02d581b47493950b6393bda323b2e8f9b7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749183"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="74ca3-102">Beispiele für die Abfrageausdruckssyntax: Elementoperatoren</span><span class="sxs-lookup"><span data-stu-id="74ca3-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="74ca3-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Linq.Enumerable.First%2A> -Methode und die [AdventureWorks Sales-Modell](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="74ca3-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using the query expression syntax.</span></span> <span data-ttu-id="74ca3-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="74ca3-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="74ca3-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="74ca3-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="74ca3-106">First</span><span class="sxs-lookup"><span data-stu-id="74ca3-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="74ca3-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74ca3-107">Example</span></span>  
 <span data-ttu-id="74ca3-108">Das folgende Beispiel verwendet die <xref:System.Linq.Enumerable.First%2A>-Methode, um den ersten Kontakt zurückzugeben, dessen Vorname "Brooke" lautet.</span><span class="sxs-lookup"><span data-stu-id="74ca3-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="74ca3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74ca3-109">See Also</span></span>  
 [<span data-ttu-id="74ca3-110">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="74ca3-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
