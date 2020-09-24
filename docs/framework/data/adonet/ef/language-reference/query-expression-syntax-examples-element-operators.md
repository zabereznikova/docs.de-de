---
title: 'Beispiele für die Abfrageausdruckssyntax: Elementoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 8cd550120e949f247a17ca6c7dafca06607a4e7e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152987"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="eed5d-102">Beispiele für die Abfrageausdruckssyntax: Elementoperatoren</span><span class="sxs-lookup"><span data-stu-id="eed5d-102">Query Expression Syntax Examples: Element Operators</span></span>

<span data-ttu-id="eed5d-103">In den Beispielen in diesem Thema wird gezeigt, wie die-Methode verwendet wird <xref:System.Linq.Enumerable.First%2A> , um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe der Abfrage Ausdruckssyntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="eed5d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using the query expression syntax.</span></span> <span data-ttu-id="eed5d-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="eed5d-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="eed5d-105">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="eed5d-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="eed5d-106">First</span><span class="sxs-lookup"><span data-stu-id="eed5d-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="eed5d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eed5d-107">Example</span></span>  

 <span data-ttu-id="eed5d-108">Das folgende Beispiel verwendet die <xref:System.Linq.Enumerable.First%2A>-Methode, um den ersten Kontakt zurückzugeben, dessen Vorname "Brooke" lautet.</span><span class="sxs-lookup"><span data-stu-id="eed5d-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="eed5d-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eed5d-109">See also</span></span>

- [<span data-ttu-id="eed5d-110">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="eed5d-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
