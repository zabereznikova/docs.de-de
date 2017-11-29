---
title: "Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen"
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
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 703823368f451839304ce02ff8b5f7259a44b935
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="d22ce-102">Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="d22ce-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="d22ce-103">In den folgenden Beispielen wird gezeigt, wie Ergebnisse aus mehreren Tabellen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d22ce-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d22ce-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-104">Example</span></span>  
 <span data-ttu-id="d22ce-105">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `From` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` -Klausel in c#), die alle Bestellungen für Kunden aus London auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d22ce-105">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-106">Example</span></span>  
 <span data-ttu-id="d22ce-107">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `Where` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` -Klausel in c#) für die Out-of-Stock filtern `Products` , deren `Supplier` befindet sich in den Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="d22ce-107">The following example uses foreign key navigation in the `Where` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-108">Example</span></span>  
 <span data-ttu-id="d22ce-109">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `From`-Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from`-Klausel in C#), um Mitarbeiter in Seattle herauszufiltern und deren Gebiete anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d22ce-109">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-110">Example</span></span>  
 <span data-ttu-id="d22ce-111">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `Select` -Klausel in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` -Klausel in c#) um mitarbeiterpaare herauszufiltern, in denen ein Mitarbeiter dem anderen untersteht und, in denen beide Mitarbeiter aus der gleichen sind `City`.</span><span class="sxs-lookup"><span data-stu-id="d22ce-111">The following example uses foreign key navigation in the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-112">Example</span></span>  
 <span data-ttu-id="d22ce-113">Die folgenden [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] Beispiel sucht nach allen Kunden und Bestellungen wird sichergestellt, dass die Bestellungen den Kunden zugeordnet sind, und stellt sicher, dass für jeden Kunden in dieser Liste, ein Kontaktname angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d22ce-113">The following [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-114">Example</span></span>  
 <span data-ttu-id="d22ce-115">Im folgenden Beispiel werden zwei Tabellen explizit verknüpft, und die Ergebnisse aus beiden Tabellen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="d22ce-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-116">Example</span></span>  
 <span data-ttu-id="d22ce-117">Im folgenden Beispiel werden explizit drei Tabellen verknüpft, und Ergebnisse aus diesen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="d22ce-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-118">Example</span></span>  
 <span data-ttu-id="d22ce-119">Im folgenden Beispiel wird das Erreichen einer `LEFT OUTER JOIN` mithilfe von `DefaultIfEmpty()` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d22ce-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="d22ce-120">Die `DefaultIfEmpty()`-Methode gibt NULL zurück, wenn es keine `Order` für den `Employee` gibt.</span><span class="sxs-lookup"><span data-stu-id="d22ce-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-121">Example</span></span>  
 <span data-ttu-id="d22ce-122">Das folgende Beispiel projiziert einen `let`-Ausdruck, der sich aus einem Join ergibt.</span><span class="sxs-lookup"><span data-stu-id="d22ce-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-123">Example</span></span>  
 <span data-ttu-id="d22ce-124">Im folgenden Beispiel wird ein `join` mit einem zusammengesetzten Schlüssel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d22ce-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="d22ce-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d22ce-125">Example</span></span>  
 <span data-ttu-id="d22ce-126">Das folgende Beispiel zeigt die Konstruktion eines `join`, bei dem eine Seite auf NULL festgelegt werden kann und die andere nicht.</span><span class="sxs-lookup"><span data-stu-id="d22ce-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="d22ce-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d22ce-127">See Also</span></span>  
 [<span data-ttu-id="d22ce-128">Beispiele für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d22ce-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
