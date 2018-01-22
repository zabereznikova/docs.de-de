---
title: "Beispiele für die Abfrageausdruckssyntax: Aggregierungsoperatoren"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 76af42681767b17fd69fac5bfd924e02b0f6b9b0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="4272f-102">Beispiele für die Abfrageausdruckssyntax: Aggregierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="4272f-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="4272f-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, und <xref:System.Linq.Enumerable.Sum%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mithilfe der Abfrageausdruckssyntax Abfragen.</span><span class="sxs-lookup"><span data-stu-id="4272f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="4272f-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="4272f-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4272f-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="4272f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="4272f-106">Average</span><span class="sxs-lookup"><span data-stu-id="4272f-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="4272f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-107">Example</span></span>  
 <span data-ttu-id="4272f-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte jeder Produktart zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4272f-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="4272f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-109">Example</span></span>  
 <span data-ttu-id="4272f-110">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Average%2A> verwendet, um für jede Kontakt-ID den durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="4272f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-111">Example</span></span>  
 <span data-ttu-id="4272f-112">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Average%2A> verwendet, um für jeden Kontakt die Aufträge mit dem durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="4272f-113">Anzahl</span><span class="sxs-lookup"><span data-stu-id="4272f-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="4272f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-114">Example</span></span>  
 <span data-ttu-id="4272f-115">Im folgenden Beispiel wird <xref:System.Linq.Enumerable.Count%2A> verwendet, um eine Liste der Kontakt-IDs und der jeweiligen Anzahl von Aufträgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4272f-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="4272f-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-116">Example</span></span>  
 <span data-ttu-id="4272f-117">Im folgenden Beispiel werden die Produkte nach ihrer Farbe gruppiert. Anschließend wird <xref:System.Linq.Enumerable.Count%2A> verwendet, um die Anzahl der Produkte in jeder Farbgruppe zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4272f-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="4272f-118">Max</span><span class="sxs-lookup"><span data-stu-id="4272f-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="4272f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-119">Example</span></span>  
 <span data-ttu-id="4272f-120">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID den größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="4272f-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-121">Example</span></span>  
 <span data-ttu-id="4272f-122">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID die Aufträge mit dem größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="4272f-123">Min</span><span class="sxs-lookup"><span data-stu-id="4272f-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="4272f-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-124">Example</span></span>  
 <span data-ttu-id="4272f-125">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jede Kontakt-ID den kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="4272f-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-126">Example</span></span>  
 <span data-ttu-id="4272f-127">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jeden Kontakt die Aufträge mit dem kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="4272f-128">Summe</span><span class="sxs-lookup"><span data-stu-id="4272f-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="4272f-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4272f-129">Example</span></span>  
 <span data-ttu-id="4272f-130">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um für jede Kontakt-ID den fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4272f-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="4272f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4272f-131">See Also</span></span>  
 [<span data-ttu-id="4272f-132">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4272f-132">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
