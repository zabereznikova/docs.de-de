---
title: 'Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 1527ad26524dbef3ac73b92e136cd22e33046483
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155886"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="7a50d-102">Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="7a50d-102">Formulate Joins and Cross-Product Queries</span></span>

<span data-ttu-id="7a50d-103">In den folgenden Beispielen wird gezeigt, wie Ergebnisse aus mehreren Tabellen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="7a50d-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a50d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-104">Example</span></span>  

 <span data-ttu-id="7a50d-105">Im folgenden Beispiel wird die Fremdschlüssel Navigation in der- `From` Klausel in Visual Basic (- `from` Klausel in c#) verwendet, um alle Bestellungen für Kunden in London auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7a50d-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-106">Example</span></span>  

 <span data-ttu-id="7a50d-107">Im folgenden Beispiel wird die Fremdschlüssel Navigation in der- `Where` Klausel in Visual Basic (- `where` Klausel in c#) verwendet, um nach einem nicht vorhandenen Kurs zu filtern, `Products` dessen `Supplier` im USA ist.</span><span class="sxs-lookup"><span data-stu-id="7a50d-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-108">Example</span></span>  

 <span data-ttu-id="7a50d-109">Im folgenden Beispiel wird die Fremdschlüssel Navigation in der- `From` Klausel in Visual Basic (- `from` Klausel in c#) zum Filtern von Mitarbeitern in Seattle und zum Auflisten ihrer Gebiete verwendet.</span><span class="sxs-lookup"><span data-stu-id="7a50d-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-110">Example</span></span>  

 <span data-ttu-id="7a50d-111">Im folgenden Beispiel wird die Fremdschlüssel Navigation in der- `Select` Klausel in Visual Basic (- `select` Klausel in c#) verwendet, um nach Paaren von Mitarbeitern zu filtern, bei denen ein Mitarbeiter den anderen meldet und in dem beide Mitarbeiter vom gleichen sind `City` .</span><span class="sxs-lookup"><span data-stu-id="7a50d-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-112">Example</span></span>  

 <span data-ttu-id="7a50d-113">Im folgenden Visual Basic Beispiel wird nach allen Kunden und Bestellungen gesucht, es wird sichergestellt, dass die Bestellungen mit Kunden abgeglichen werden, und es wird sichergestellt, dass für jeden Kunden in dieser Liste ein Kontakt Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7a50d-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-114">Example</span></span>  

 <span data-ttu-id="7a50d-115">Im folgenden Beispiel werden zwei Tabellen explizit verknüpft, und die Ergebnisse aus beiden Tabellen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="7a50d-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-116">Example</span></span>  

 <span data-ttu-id="7a50d-117">Im folgenden Beispiel werden explizit drei Tabellen verknüpft, und Ergebnisse aus diesen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="7a50d-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-118">Example</span></span>  

 <span data-ttu-id="7a50d-119">Im folgenden Beispiel wird das Erreichen einer `LEFT OUTER JOIN` mithilfe von `DefaultIfEmpty()` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7a50d-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="7a50d-120">Die `DefaultIfEmpty()`-Methode gibt NULL zurück, wenn es keine `Order` für den `Employee` gibt.</span><span class="sxs-lookup"><span data-stu-id="7a50d-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-121">Example</span></span>  

 <span data-ttu-id="7a50d-122">Das folgende Beispiel projiziert einen `let`-Ausdruck, der sich aus einem Join ergibt.</span><span class="sxs-lookup"><span data-stu-id="7a50d-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-123">Example</span></span>  

 <span data-ttu-id="7a50d-124">Im folgenden Beispiel wird ein `join` mit einem zusammengesetzten Schlüssel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a50d-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="7a50d-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a50d-125">Example</span></span>  

 <span data-ttu-id="7a50d-126">Das folgende Beispiel zeigt die Konstruktion eines `join`, bei dem eine Seite auf NULL festgelegt werden kann und die andere nicht.</span><span class="sxs-lookup"><span data-stu-id="7a50d-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="7a50d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a50d-127">See also</span></span>

- [<span data-ttu-id="7a50d-128">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="7a50d-128">Query Examples</span></span>](query-examples.md)
