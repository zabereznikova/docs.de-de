---
title: 'Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: a06c7d451d9ad2856092910065f1195a86c737ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548516"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="c5107-102">Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="c5107-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="c5107-103">In den folgenden Beispielen wird gezeigt, wie Ergebnisse aus mehreren Tabellen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="c5107-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5107-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-104">Example</span></span>  
 <span data-ttu-id="c5107-105">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `From` -Klausel in Visual Basic (`from` -Klausel in C#), die alle Bestellungen für Kunden aus London auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c5107-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="c5107-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-106">Example</span></span>  
 <span data-ttu-id="c5107-107">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `Where` -Klausel in Visual Basic (`where` -Klausel in C#) zum Filtern nach von Fehlmengen `Products` , deren `Supplier` befindet sich in den Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="c5107-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="c5107-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-108">Example</span></span>  
 <span data-ttu-id="c5107-109">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `From` -Klausel in Visual Basic (`from` -Klausel in C#) zum Filtern nach Mitarbeiter in Seattle und deren Gebiete anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c5107-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="c5107-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-110">Example</span></span>  
 <span data-ttu-id="c5107-111">Das folgende Beispiel verwendet Fremdschlüsselnavigation in der `Select` -Klausel in Visual Basic (`select` -Klausel in C#) um mitarbeiterpaare zu filtern, in dem ein Mitarbeiter dem anderen untersteht und, in denen beide Mitarbeiter aus der gleichen werden `City`.</span><span class="sxs-lookup"><span data-stu-id="c5107-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="c5107-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-112">Example</span></span>  
 <span data-ttu-id="c5107-113">Im folgende Visual Basic-Beispiel sucht nach allen Kunden und Bestellungen, stellt sicher, dass die Bestellungen den Kunden zugeordnet werden und stellt sicher, dass für jeden Kunden in der Liste, ein Kontaktname angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5107-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="c5107-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-114">Example</span></span>  
 <span data-ttu-id="c5107-115">Im folgenden Beispiel werden zwei Tabellen explizit verknüpft, und die Ergebnisse aus beiden Tabellen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="c5107-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="c5107-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-116">Example</span></span>  
 <span data-ttu-id="c5107-117">Im folgenden Beispiel werden explizit drei Tabellen verknüpft, und Ergebnisse aus diesen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="c5107-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="c5107-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-118">Example</span></span>  
 <span data-ttu-id="c5107-119">Im folgenden Beispiel wird das Erreichen einer `LEFT OUTER JOIN` mithilfe von `DefaultIfEmpty()` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c5107-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="c5107-120">Die `DefaultIfEmpty()`-Methode gibt NULL zurück, wenn es keine `Order` für den `Employee` gibt.</span><span class="sxs-lookup"><span data-stu-id="c5107-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="c5107-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-121">Example</span></span>  
 <span data-ttu-id="c5107-122">Das folgende Beispiel projiziert einen `let`-Ausdruck, der sich aus einem Join ergibt.</span><span class="sxs-lookup"><span data-stu-id="c5107-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="c5107-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-123">Example</span></span>  
 <span data-ttu-id="c5107-124">Im folgenden Beispiel wird ein `join` mit einem zusammengesetzten Schlüssel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5107-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="c5107-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5107-125">Example</span></span>  
 <span data-ttu-id="c5107-126">Das folgende Beispiel zeigt die Konstruktion eines `join`, bei dem eine Seite auf NULL festgelegt werden kann und die andere nicht.</span><span class="sxs-lookup"><span data-stu-id="c5107-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="c5107-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5107-127">See also</span></span>
- [<span data-ttu-id="c5107-128">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="c5107-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
