---
title: 'Beispiele für die Abfrageausdruckssyntax: Aggregatoperatoren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 54b5ab6fc5eac6ba522a58afa3aa3c0218e86bcf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397184"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="c92a4-102">Beispiele für die Abfrageausdruckssyntax: Aggregatoperatoren</span><span class="sxs-lookup"><span data-stu-id="c92a4-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="c92a4-103">In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.Average%2A>die <xref:System.Linq.Enumerable.Count%2A>Methoden <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>,, <xref:System.Linq.Enumerable.Sum%2A> und verwendet werden, um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Abfrage Ausdruckssyntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="c92a4-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c92a4-105">In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="c92a4-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="c92a4-106">Average</span><span class="sxs-lookup"><span data-stu-id="c92a4-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="c92a4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-107">Example</span></span>  
 <span data-ttu-id="c92a4-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte jeder Produktart zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c92a4-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="c92a4-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-109">Example</span></span>  
 <span data-ttu-id="c92a4-110">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Average%2A> verwendet, um für jede Kontakt-ID den durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="c92a4-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-111">Example</span></span>  
 <span data-ttu-id="c92a4-112">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Average%2A> verwendet, um für jeden Kontakt die Aufträge mit dem durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="c92a4-113">Anzahl</span><span class="sxs-lookup"><span data-stu-id="c92a4-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="c92a4-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-114">Example</span></span>  
 <span data-ttu-id="c92a4-115">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Count%2A> verwendet, um eine Liste der Kontakt-IDs und der jeweiligen Anzahl von Aufträgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c92a4-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="c92a4-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-116">Example</span></span>  
 <span data-ttu-id="c92a4-117">Im folgenden Beispiel werden die Produkte nach ihrer Farbe gruppiert. Anschließend wird <xref:System.Linq.Enumerable.Count%2A> verwendet, um die Anzahl der Produkte in jeder Farbgruppe zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c92a4-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="c92a4-118">Max.</span><span class="sxs-lookup"><span data-stu-id="c92a4-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="c92a4-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-119">Example</span></span>  
 <span data-ttu-id="c92a4-120">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID den größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="c92a4-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-121">Example</span></span>  
 <span data-ttu-id="c92a4-122">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID die Aufträge mit dem größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="c92a4-123">Min.</span><span class="sxs-lookup"><span data-stu-id="c92a4-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="c92a4-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-124">Example</span></span>  
 <span data-ttu-id="c92a4-125">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jede Kontakt-ID den kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="c92a4-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-126">Example</span></span>  
 <span data-ttu-id="c92a4-127">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jeden Kontakt die Aufträge mit dem kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="c92a4-128">Summe</span><span class="sxs-lookup"><span data-stu-id="c92a4-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="c92a4-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c92a4-129">Example</span></span>  
 <span data-ttu-id="c92a4-130">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um für jede Kontakt-ID den fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c92a4-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="c92a4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c92a4-131">See also</span></span>

- [<span data-ttu-id="c92a4-132">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c92a4-132">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
