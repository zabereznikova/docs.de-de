---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Aggregierungsoperatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
ms.openlocfilehash: 8d8f3cebb599eb543d569e36b294e6433a45f432
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520311"
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="21f6a-102">Beispiele für die methodenbasierte Abfragesyntax: Aggregierungsoperatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="21f6a-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="21f6a-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Operatoren <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Sum%2A> und der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen und Daten aggregieren können.</span><span class="sxs-lookup"><span data-stu-id="21f6a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="21f6a-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="21f6a-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="21f6a-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="21f6a-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="21f6a-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="21f6a-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="21f6a-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="21f6a-108">Aggregat</span><span class="sxs-lookup"><span data-stu-id="21f6a-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-109">Example</span></span>  
 <span data-ttu-id="21f6a-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Aggregate%2A>-Methode verwendet, um die ersten 5 Kontakte aus der `Contact`-Tabelle abzurufen und eine Liste der Nachnamen zu erstellen, in der die einzelnen Einträge durch Kommas voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="21f6a-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="21f6a-111">Average</span><span class="sxs-lookup"><span data-stu-id="21f6a-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-112">Example</span></span>  
 <span data-ttu-id="21f6a-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-114">Example</span></span>  
 <span data-ttu-id="21f6a-115">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen Listenpreis der Produkte für die einzelnen Stile zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-116">Example</span></span>  
 <span data-ttu-id="21f6a-117">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um den durchschnittlichen fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-118">Example</span></span>  
 <span data-ttu-id="21f6a-119">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um für jede Kontakt-ID den durchschnittlichen fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-120">Example</span></span>  
 <span data-ttu-id="21f6a-121">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Average%2A>-Methode verwendet, um die Aufträge mit dem durchschnittlichen `TotalDue`-Wert für jeden Kontakt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="21f6a-122">Anzahl</span><span class="sxs-lookup"><span data-stu-id="21f6a-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-123">Example</span></span>  
 <span data-ttu-id="21f6a-124">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode verwendet, um die Anzahl der Produkte in der `Product`-Tabelle zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-125">Example</span></span>  
 <span data-ttu-id="21f6a-126">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode verwendet, um eine Liste der Kontakt-IDs und der jeweiligen Anzahl von Aufträgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-127">Example</span></span>  
 <span data-ttu-id="21f6a-128">In diesem Beispiel werden die Produkte nach ihrer Farbe gruppiert. Anschließend wird die <xref:System.Linq.Enumerable.Count%2A>-Methode verwendet, um die Anzahl der Produkte in jeder Farbgruppe abzurufen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="21f6a-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="21f6a-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-130">Example</span></span>  
 <span data-ttu-id="21f6a-131">In diesem Beispiel wird die Anzahl der Kontakte als lange ganze Zahl abgerufen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="21f6a-132">Max</span><span class="sxs-lookup"><span data-stu-id="21f6a-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-133">Example</span></span>  
 <span data-ttu-id="21f6a-134">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um den größten fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-135">Example</span></span>  
 <span data-ttu-id="21f6a-136">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID den größten fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-137">Example</span></span>  
 <span data-ttu-id="21f6a-138">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Max%2A>-Methode verwendet, um für jede Kontakt-ID die Aufträge mit dem größten `TotalDue`-Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="21f6a-139">Min</span><span class="sxs-lookup"><span data-stu-id="21f6a-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-140">Example</span></span>  
 <span data-ttu-id="21f6a-141">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um den kleinsten fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-142">Example</span></span>  
 <span data-ttu-id="21f6a-143">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jede Kontakt-ID den kleinsten fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-144">Example</span></span>  
 <span data-ttu-id="21f6a-145">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Min%2A>-Methode verwendet, um für jeden Kontakt die Aufträge mit dem kleinsten fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="21f6a-146">Summe</span><span class="sxs-lookup"><span data-stu-id="21f6a-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="21f6a-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-147">Example</span></span>  
 <span data-ttu-id="21f6a-148">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um die Gesamtzahl der Bestellmengen in der `SalesOrderDetail`-Tabelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="21f6a-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="21f6a-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21f6a-149">Example</span></span>  
 <span data-ttu-id="21f6a-150">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Sum%2A>-Methode verwendet, um für jede Kontakt-ID den fälligen Gesamtbetrag zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="21f6a-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="21f6a-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21f6a-151">See Also</span></span>  
 [<span data-ttu-id="21f6a-152">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="21f6a-152">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="21f6a-153">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="21f6a-153">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="21f6a-154">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="21f6a-154">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
