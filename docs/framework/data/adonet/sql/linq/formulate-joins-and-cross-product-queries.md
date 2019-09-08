---
title: 'Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 002a644ff5d48b25351228dcd74330707491d6c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782095"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="13a04-102">Gewusst wie: Formulieren von Joins und produktübergreifenden Abfragen</span><span class="sxs-lookup"><span data-stu-id="13a04-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="13a04-103">In den folgenden Beispielen wird gezeigt, wie Ergebnisse aus mehreren Tabellen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="13a04-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13a04-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-104">Example</span></span>  
 <span data-ttu-id="13a04-105">Im folgenden Beispiel wird die Fremdschlüssel Navigation in `From` der-Klausel in`from` Visual Basic ( C#-Klausel in) verwendet, um alle Bestellungen für Kunden in London auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="13a04-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="13a04-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-106">Example</span></span>  
 <span data-ttu-id="13a04-107">Im folgenden Beispiel wird die Fremdschlüssel Navigation in `Where` der-Klausel in`where` Visual Basic ( C#-Klausel in) verwendet, um nach außen `Products` zu `Supplier` filtern, dessen im USA ist.</span><span class="sxs-lookup"><span data-stu-id="13a04-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="13a04-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-108">Example</span></span>  
 <span data-ttu-id="13a04-109">Im folgenden Beispiel wird die Fremdschlüssel Navigation in `From` der-Klausel in`from` Visual Basic ( C#-Klausel in) zum Filtern von Mitarbeitern in Seattle und zum Auflisten ihrer Gebiete verwendet.</span><span class="sxs-lookup"><span data-stu-id="13a04-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="13a04-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-110">Example</span></span>  
 <span data-ttu-id="13a04-111">Im folgenden Beispiel wird die Fremdschlüssel Navigation in `Select` der-Klausel in`select` Visual Basic ( C#-Klausel in) verwendet, um nach Paaren von Mitarbeitern zu filtern, bei denen ein Mitarbeiter den anderen meldet und `City`in dem beide Mitarbeiter vom gleichen sind.</span><span class="sxs-lookup"><span data-stu-id="13a04-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="13a04-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-112">Example</span></span>  
 <span data-ttu-id="13a04-113">Im folgenden Visual Basic Beispiel wird nach allen Kunden und Bestellungen gesucht, es wird sichergestellt, dass die Bestellungen mit Kunden abgeglichen werden, und es wird sichergestellt, dass für jeden Kunden in dieser Liste ein Kontakt Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="13a04-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="13a04-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-114">Example</span></span>  
 <span data-ttu-id="13a04-115">Im folgenden Beispiel werden zwei Tabellen explizit verknüpft, und die Ergebnisse aus beiden Tabellen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="13a04-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="13a04-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-116">Example</span></span>  
 <span data-ttu-id="13a04-117">Im folgenden Beispiel werden explizit drei Tabellen verknüpft, und Ergebnisse aus diesen werden projiziert.</span><span class="sxs-lookup"><span data-stu-id="13a04-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="13a04-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-118">Example</span></span>  
 <span data-ttu-id="13a04-119">Im folgenden Beispiel wird das Erreichen einer `LEFT OUTER JOIN` mithilfe von `DefaultIfEmpty()` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="13a04-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="13a04-120">Die `DefaultIfEmpty()`-Methode gibt NULL zurück, wenn es keine `Order` für den `Employee` gibt.</span><span class="sxs-lookup"><span data-stu-id="13a04-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="13a04-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-121">Example</span></span>  
 <span data-ttu-id="13a04-122">Das folgende Beispiel projiziert einen `let`-Ausdruck, der sich aus einem Join ergibt.</span><span class="sxs-lookup"><span data-stu-id="13a04-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="13a04-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-123">Example</span></span>  
 <span data-ttu-id="13a04-124">Im folgenden Beispiel wird ein `join` mit einem zusammengesetzten Schlüssel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="13a04-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="13a04-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13a04-125">Example</span></span>  
 <span data-ttu-id="13a04-126">Das folgende Beispiel zeigt die Konstruktion eines `join`, bei dem eine Seite auf NULL festgelegt werden kann und die andere nicht.</span><span class="sxs-lookup"><span data-stu-id="13a04-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="13a04-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13a04-127">See also</span></span>

- [<span data-ttu-id="13a04-128">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="13a04-128">Query Examples</span></span>](query-examples.md)
