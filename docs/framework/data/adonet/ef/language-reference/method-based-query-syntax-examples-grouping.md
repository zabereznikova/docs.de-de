---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Gruppieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 1bc2ab6f7dbfb3b2babcc5a9565a7bfd9fd962c4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="60d61-102">Beispiele für die methodenbasierte Abfragesyntax: Gruppieren</span><span class="sxs-lookup"><span data-stu-id="60d61-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="60d61-103">In den Beispielen in diesem Thema veranschaulichen das Verwenden der `GroupBy` -Methode und die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="60d61-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="60d61-104">Für das in den Beispielen verwendete AdventureWorks Sales-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der AdventureWorks-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="60d61-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="60d61-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="60d61-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="60d61-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60d61-106">Example</span></span>  
 <span data-ttu-id="60d61-107">Im folgenden Beispiel wird die `GroupBy`-Methode verwendet, um nach Postleitzahl gruppierte `Address`-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="60d61-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="60d61-108">Die Ergebnisse werden in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="60d61-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="60d61-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60d61-109">Example</span></span>  
 <span data-ttu-id="60d61-110">Im folgenden Beispiel wird die `GroupBy`-Methode verwendet, um nach dem ersten Buchstaben des Nachnamens des Kontakts gruppierte `Contact`-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="60d61-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="60d61-111">Die Ergebnisse werden nach dem ersten Buchstaben des Nachnamens sortiert und in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="60d61-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="60d61-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60d61-112">Example</span></span>  
 <span data-ttu-id="60d61-113">Im folgenden Beispiel wird die `GroupBy`-Methode verwendet, um nach Kunden-ID gruppierte `SalesOrderHeader`-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="60d61-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="60d61-114">Die Anzahl von Verkäufen für jeden Kunden wird ebenfalls zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="60d61-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="60d61-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60d61-115">See Also</span></span>  
 [<span data-ttu-id="60d61-116">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="60d61-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
