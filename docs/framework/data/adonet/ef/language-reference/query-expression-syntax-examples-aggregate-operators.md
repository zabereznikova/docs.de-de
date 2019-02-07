---
title: 'Beispiele für die Abfrageausdruckssyntax: Aggregierungsoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: bc3a6de1101b3e7626312197bc2d1ba37f7e04a4
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825796"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="b3508-102">Beispiele für die Abfrageausdruckssyntax: Aggregierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b3508-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="b3508-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, und <xref:System.Linq.Enumerable.Sum%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="b3508-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="b3508-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="b3508-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b3508-105">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="b3508-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="b3508-106">Average</span><span class="sxs-lookup"><span data-stu-id="b3508-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3508-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-107">Example</span></span>  
 <span data-ttu-id="b3508-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte jeder Produktart zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b3508-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3508-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-109">Example</span></span>  
 <span data-ttu-id="b3508-110">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Average%2A> verwendet, um für jede Kontakt-ID den durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3508-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-111">Example</span></span>  
 <span data-ttu-id="b3508-112">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Average%2A> verwendet, um für jeden Kontakt die Aufträge mit dem durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="b3508-113">Anzahl</span><span class="sxs-lookup"><span data-stu-id="b3508-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3508-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-114">Example</span></span>  
 <span data-ttu-id="b3508-115">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Count%2A> verwendet, um eine Liste der Kontakt-IDs und der jeweiligen Anzahl von Aufträgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b3508-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="b3508-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-116">Example</span></span>  
 <span data-ttu-id="b3508-117">Im folgenden Beispiel werden die Produkte nach ihrer Farbe gruppiert. Anschließend wird <xref:System.Linq.Enumerable.Count%2A> verwendet, um die Anzahl der Produkte in jeder Farbgruppe zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b3508-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="b3508-118">Max</span><span class="sxs-lookup"><span data-stu-id="b3508-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3508-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-119">Example</span></span>  
 <span data-ttu-id="b3508-120">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID den größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3508-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-121">Example</span></span>  
 <span data-ttu-id="b3508-122">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID die Aufträge mit dem größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="b3508-123">Min</span><span class="sxs-lookup"><span data-stu-id="b3508-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3508-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-124">Example</span></span>  
 <span data-ttu-id="b3508-125">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jede Kontakt-ID den kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="b3508-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-126">Example</span></span>  
 <span data-ttu-id="b3508-127">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jeden Kontakt die Aufträge mit dem kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="b3508-128">Summe</span><span class="sxs-lookup"><span data-stu-id="b3508-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="b3508-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3508-129">Example</span></span>  
 <span data-ttu-id="b3508-130">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um für jede Kontakt-ID den fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3508-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="b3508-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3508-131">See also</span></span>
- [<span data-ttu-id="b3508-132">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b3508-132">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
