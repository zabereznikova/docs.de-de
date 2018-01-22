---
title: "Beispiele für die methodenbasierte Abfragesyntax: Aggregierungsoperatoren"
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
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f7a6e1058ca120fde45628b86019255e3eb5b9c7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="07d4b-102">Beispiele für die methodenbasierte Abfragesyntax: Aggregierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="07d4b-102">Method-Based Query Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="07d4b-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, und <xref:System.Linq.Enumerable.Sum%2A> Methoden zum Abfragen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) mithilfe der methodenbasierten Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="07d4b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="07d4b-104">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="07d4b-105">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="07d4b-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="07d4b-106">Average</span><span class="sxs-lookup"><span data-stu-id="07d4b-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="07d4b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-107">Example</span></span>  
 <span data-ttu-id="07d4b-108">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="07d4b-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-109">Example</span></span>  
 <span data-ttu-id="07d4b-110">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte jeder Produktart zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="07d4b-110">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-111">Example</span></span>  
 <span data-ttu-id="07d4b-112">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="07d4b-112">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-113">Example</span></span>  
 <span data-ttu-id="07d4b-114">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um für jede Kontakt-ID den durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-114">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-115">Example</span></span>  
 <span data-ttu-id="07d4b-116">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um für jeden Kontakt die Aufträge mit dem durchschnittlichen fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-116">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="07d4b-117">Anzahl</span><span class="sxs-lookup"><span data-stu-id="07d4b-117">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="07d4b-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-118">Example</span></span>  
 <span data-ttu-id="07d4b-119">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode verwendet, um die Anzahl der Produkte in der Tabelle Product zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="07d4b-119">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-120">Example</span></span>  
 <span data-ttu-id="07d4b-121">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode verwendet, um eine Liste der Kontakt-IDs und der jeweiligen Anzahl von Aufträgen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="07d4b-121">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-122">Example</span></span>  
 <span data-ttu-id="07d4b-123">Im folgenden Beispiel werden die Produkte nach ihrer Farbe gruppiert. Anschließend wird die <xref:System.Linq.Enumerable.Count%2A>-Methode verwendet, um die Anzahl der Produkte in jeder Farbgruppe zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="07d4b-123">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="07d4b-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="07d4b-124">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="07d4b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-125">Example</span></span>  
 <span data-ttu-id="07d4b-126">Im folgenden Beispiel wird die Anzahl der Kontakte als lange ganze Zahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-126">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="07d4b-127">Max</span><span class="sxs-lookup"><span data-stu-id="07d4b-127">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="07d4b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-128">Example</span></span>  
 <span data-ttu-id="07d4b-129">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um den größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-129">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-130">Example</span></span>  
 <span data-ttu-id="07d4b-131">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID den größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-131">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-132">Example</span></span>  
 <span data-ttu-id="07d4b-133">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID die Aufträge mit dem größten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-133">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="07d4b-134">Min</span><span class="sxs-lookup"><span data-stu-id="07d4b-134">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="07d4b-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-135">Example</span></span>  
 <span data-ttu-id="07d4b-136">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um den kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-136">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-137">Example</span></span>  
 <span data-ttu-id="07d4b-138">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jede Kontakt-ID den kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-138">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-139">Example</span></span>  
 <span data-ttu-id="07d4b-140">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jeden Kontakt die Aufträge mit dem kleinsten fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-140">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="07d4b-141">Summe</span><span class="sxs-lookup"><span data-stu-id="07d4b-141">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="07d4b-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-142">Example</span></span>  
 <span data-ttu-id="07d4b-143">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um die Gesamtzahl der Bestellmengen in der Tabelle SalesOrderDetail abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-143">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="07d4b-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d4b-144">Example</span></span>  
 <span data-ttu-id="07d4b-145">Im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um für jede Kontakt-ID den fälligen Gesamtbetrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07d4b-145">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="07d4b-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07d4b-146">See Also</span></span>  
 [<span data-ttu-id="07d4b-147">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="07d4b-147">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
