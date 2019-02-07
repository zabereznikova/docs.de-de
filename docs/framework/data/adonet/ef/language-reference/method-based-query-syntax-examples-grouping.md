---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Gruppieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: d414218604887fca2d69a02b40dfa87f13961aae
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825380"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="34b67-102">Beispiele für die methodenbasierte Abfragesyntax: Gruppieren</span><span class="sxs-lookup"><span data-stu-id="34b67-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="34b67-103">Die Beispiele in diesem Thema zeigen, wie mit der `GroupBy` -Methode und die [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mit der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="34b67-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="34b67-104">Für das in den Beispielen verwendete AdventureWorks Sales-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der AdventureWorks-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="34b67-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="34b67-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="34b67-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="34b67-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34b67-106">Example</span></span>  
 <span data-ttu-id="34b67-107">Im folgenden Beispiel wird die `GroupBy`-Methode verwendet, um nach Postleitzahl gruppierte `Address`-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="34b67-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="34b67-108">Die Ergebnisse werden in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="34b67-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="34b67-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34b67-109">Example</span></span>  
 <span data-ttu-id="34b67-110">Im folgenden Beispiel wird die `GroupBy`-Methode verwendet, um nach dem ersten Buchstaben des Nachnamens des Kontakts gruppierte `Contact`-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="34b67-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="34b67-111">Die Ergebnisse werden nach dem ersten Buchstaben des Nachnamens sortiert und in einen anonymen Typ projiziert.</span><span class="sxs-lookup"><span data-stu-id="34b67-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="34b67-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34b67-112">Example</span></span>  
 <span data-ttu-id="34b67-113">Im folgenden Beispiel wird die `GroupBy`-Methode verwendet, um nach Kunden-ID gruppierte `SalesOrderHeader`-Objekte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="34b67-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="34b67-114">Die Anzahl von Verkäufen für jeden Kunden wird ebenfalls zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="34b67-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="34b67-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34b67-115">See also</span></span>
- [<span data-ttu-id="34b67-116">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="34b67-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
