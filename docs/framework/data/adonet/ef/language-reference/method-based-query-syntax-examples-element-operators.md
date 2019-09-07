---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 7add62a2792a0fc82346851b7dd835aad5082742
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397460"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="06cda-102">Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren</span><span class="sxs-lookup"><span data-stu-id="06cda-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="06cda-103">In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.First%2A> die-Methode verwendet wird, um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Methoden basierter Abfrage Syntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="06cda-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="06cda-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="06cda-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="06cda-105">Im Beispiel in diesem Thema werden die folgenden `using` / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="06cda-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="06cda-106">Erster</span><span class="sxs-lookup"><span data-stu-id="06cda-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="06cda-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06cda-107">Example</span></span>  
 <span data-ttu-id="06cda-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.First%2A> -Methode verwendet, um die erste e-Mail-Adresse zu suchen, die mit "Caroline" beginnt.</span><span class="sxs-lookup"><span data-stu-id="06cda-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="06cda-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06cda-109">See also</span></span>

- [<span data-ttu-id="06cda-110">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="06cda-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
