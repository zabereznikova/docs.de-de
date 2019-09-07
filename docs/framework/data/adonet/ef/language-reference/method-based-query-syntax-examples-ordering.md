---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Sortieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: e10101e2a3534d981b2126884a2a61b411254477
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397331"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="f8d5d-102">Beispiele für die methodenbasierte Abfragesyntax: Sortieren</span><span class="sxs-lookup"><span data-stu-id="f8d5d-102">Method-Based Query Syntax Examples: Ordering</span></span>
<span data-ttu-id="f8d5d-103">In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.ThenBy%2A> die-Methode verwendet wird, um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Methoden basierter Abfrage Syntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f8d5d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="f8d5d-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="f8d5d-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f8d5d-105">In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="f8d5d-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="f8d5d-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="f8d5d-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="f8d5d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8d5d-107">Example</span></span>  
 <span data-ttu-id="f8d5d-108">Im folgenden Beispiel methodenbasierter Abfragesyntax werden <xref:System.Linq.Queryable.OrderBy%2A> und <xref:System.Linq.Queryable.ThenBy%2A> verwendet, um eine zuerst nach Nachnamen und dann nach Vornamen geordnete Liste der Kontakte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8d5d-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="f8d5d-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="f8d5d-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="f8d5d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8d5d-110">Example</span></span>  
 <span data-ttu-id="f8d5d-111">Im folgenden Beispiel werden die <xref:System.Linq.Queryable.OrderBy%2A>-Methode und die <xref:System.Linq.Queryable.ThenByDescending%2A>-Methode verwendet, um die Daten zuerst nach dem Listenpreis und dann absteigend nach dem Produktnamen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f8d5d-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="f8d5d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8d5d-112">See also</span></span>

- [<span data-ttu-id="f8d5d-113">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f8d5d-113">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
