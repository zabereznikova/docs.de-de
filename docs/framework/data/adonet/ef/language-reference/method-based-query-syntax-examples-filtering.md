---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Filtern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e40e314c-eb30-4f44-a054-41e511e35832
ms.openlocfilehash: 392181f201c7b18b1b38f62f5f35c5657cbbe601
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191995"
---
# <a name="method-based-query-syntax-examples-filtering"></a><span data-ttu-id="fad58-102">Beispiele für die methodenbasierte Abfragesyntax: Filtern</span><span class="sxs-lookup"><span data-stu-id="fad58-102">Method-Based Query Syntax Examples: Filtering</span></span>

<span data-ttu-id="fad58-103">In den Beispielen in diesem Thema wird gezeigt, wie die `Where` -Methode und die-Methode verwendet werden `Where…Contains` , um das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) mithilfe von Methoden basierter Abfrage Syntax abzufragen.</span><span class="sxs-lookup"><span data-stu-id="fad58-103">The examples in this topic demonstrate how to use the `Where` and `Where…Contains` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="fad58-104">Hinweis: Where...`Contains`</span><span class="sxs-lookup"><span data-stu-id="fad58-104">Note, Where…`Contains`</span></span> <span data-ttu-id="fad58-105">kann nicht als Teil einer [kompilierten Abfrage](compiled-queries-linq-to-entities.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fad58-105">cannot be used as a part of a [compiled query](compiled-queries-linq-to-entities.md).</span></span>  
  
 <span data-ttu-id="fad58-106">Für das in den Beispielen verwendete AdventureWorks Sales-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der AdventureWorks-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="fad58-106">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="fad58-107">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="fad58-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="where"></a><span data-ttu-id="fad58-108">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="fad58-108">Where</span></span>  
  
### <a name="example"></a><span data-ttu-id="fad58-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fad58-109">Example</span></span>  

 <span data-ttu-id="fad58-110">Im folgenden Beispiel werden alle Onlinebestellungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fad58-110">The following example returns all online orders.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where1_mq)]
 [!code-vb[DP L2E Examples#Where1_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where1_mq)]  
  
### <a name="example"></a><span data-ttu-id="fad58-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fad58-111">Example</span></span>  

 <span data-ttu-id="fad58-112">Im folgenden Beispiel werden die Aufträge zurückgegeben, bei denen die Bestellmenge größer als 2 und kleiner als 6 ist.</span><span class="sxs-lookup"><span data-stu-id="fad58-112">The following example returns the orders where the order quantity is greater than 2 and less than 6.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where2_mq)]
 [!code-vb[DP L2E Examples#Where2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where2_mq)]  
  
### <a name="example"></a><span data-ttu-id="fad58-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fad58-113">Example</span></span>  

 <span data-ttu-id="fad58-114">Im folgenden Beispiel werden alle Produkte mit roter Farbe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fad58-114">The following example returns all red colored products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#where3_mq)]
 [!code-vb[DP L2E Examples#Where3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#where3_mq)]  
  
### <a name="example"></a><span data-ttu-id="fad58-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fad58-115">Example</span></span>  

 <span data-ttu-id="fad58-116">Im folgenden Beispiel wird die `Where`-Methode verwendet, um Aufträge zu finden, die nach dem 1. Dezember 2003 eingegangen sind. Anschließend kommt die `order.SalesOrderDetail`-Navigationseigenschaft zum Einsatz, um die Details zu den einzelnen Aufträgen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fad58-116">The following example uses the `Where` method to find orders that were made after December 1, 2003 and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty_mq)]
 [!code-vb[DP L2E Examples#WhereNavProperty_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty_mq)]  
  
## <a name="wherecontains"></a><span data-ttu-id="fad58-117">Where…Contains</span><span class="sxs-lookup"><span data-stu-id="fad58-117">Where…Contains</span></span>  
  
### <a name="example"></a><span data-ttu-id="fad58-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fad58-118">Example</span></span>  

 <span data-ttu-id="fad58-119">Im folgenden Beispiel wird ein Array als Teil einer `Where…Contains`-Klausel verwendet, um alle Produkte zu suchen, die eine dem Wert im Array entsprechende `ProductModelID` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fad58-119">The following example uses an array as part of a `Where…Contains` clause to find all products that have a `ProductModelID` that matches a value in the array.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#3)]
 [!code-vb[DP L2E ArraysAndListsInQueries#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#3)]  
  
> [!NOTE]
> <span data-ttu-id="fad58-120">Als Teil des Prädikats in einer `Where…Contains`-Klausel können Sie ein <xref:System.Array>, eine <xref:System.Collections.Generic.List%601> oder eine Auflistung eines beliebigen Typs verwenden, der die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="fad58-120">As part of the predicate in a `Where…Contains` clause, you can use an <xref:System.Array>, a <xref:System.Collections.Generic.List%601>, or a collection of any type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="fad58-121">Sie können auch eine Auflistung innerhalb einer LINQ to Entities-Abfrage deklarieren und initialisieren.</span><span class="sxs-lookup"><span data-stu-id="fad58-121">You can also declare and initialize a collection within a LINQ to Entities query.</span></span> <span data-ttu-id="fad58-122">Weitere Informationen finden Sie im nächsten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fad58-122">See the next example for more information.</span></span>  
  
### <a name="example"></a><span data-ttu-id="fad58-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fad58-123">Example</span></span>  

 <span data-ttu-id="fad58-124">Im folgenden Beispiel werden Arrays in einer `Where…Contains`-Klausel deklariert und initialisiert, um alle Produkte zu suchen, die eine `ProductModelID` oder `Size` aufweisen, die einem Wert in den Arrays entspricht.</span><span class="sxs-lookup"><span data-stu-id="fad58-124">The following example declares and initializes arrays in a `Where…Contains` clause to find all products that have a `ProductModelID` or a `Size` that matches a value in the arrays.</span></span>  
  
 [!code-csharp[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e arraysandlistsinqueries/cs/program.cs#4)]
 [!code-vb[DP L2E ArraysAndListsInQueries#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e arraysandlistsinqueries/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fad58-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fad58-125">See also</span></span>

- [<span data-ttu-id="fad58-126">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="fad58-126">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
