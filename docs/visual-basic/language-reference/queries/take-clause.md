---
title: Take-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: bfaccf470d93a6a72451e7ad8b41e8dbb1171c71
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387619"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="7bb71-102">Take-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bb71-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="7bb71-103">Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="7bb71-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb71-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bb71-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="7bb71-105">Teile</span><span class="sxs-lookup"><span data-stu-id="7bb71-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="7bb71-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7bb71-106">Required.</span></span> <span data-ttu-id="7bb71-107">Ein Wert oder ein Ausdruck, der die Anzahl der Elemente der Sequenz zurück, die ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="7bb71-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bb71-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7bb71-108">Remarks</span></span>  
 <span data-ttu-id="7bb71-109">Die `Take` -Klausel bewirkt, dass eine Abfrage, um eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Ergebnisliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bb71-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="7bb71-110">Die Anzahl der einzuschließenden Elemente wird angegeben, durch die `count` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7bb71-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="7bb71-111">Können Sie die `Take` -Klausel mit der `Skip` -Klausel, um einen Bereich von Daten aus jedem Segment einer Abfrage zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7bb71-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="7bb71-112">Dazu übergeben Sie den Index des ersten Elements des Bereichs, der die `Skip` -Klausel und die Größe des Bereichs, der die `Take` Klausel.</span><span class="sxs-lookup"><span data-stu-id="7bb71-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="7bb71-113">In diesem Fall die `Take` -Klausel muss angegeben werden, nachdem die `Skip` Klausel.</span><span class="sxs-lookup"><span data-stu-id="7bb71-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="7bb71-114">Bei Verwendung der `Take` -Klausel in einer Abfrage, Sie müssen auch sicherstellen, dass die Ergebnisse in der Reihenfolge zurückgegeben werden, mit denen die `Take` -Klausel, um die gewünschten Ergebnisse enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bb71-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="7bb71-115">Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7bb71-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="7bb71-116">Sie können die `TakeWhile` Klausel, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden, je nach einer angegebenen Bedingung.</span><span class="sxs-lookup"><span data-stu-id="7bb71-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb71-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7bb71-117">Example</span></span>  
 <span data-ttu-id="7bb71-118">Im folgenden Codebeispiel wird die `Take` -Klausel zusammen mit den `Skip` -Klausel zur Rückgabe von Daten aus einer Abfrage in Seiten.</span><span class="sxs-lookup"><span data-stu-id="7bb71-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="7bb71-119">Die GetCustomers-Funktion verwendet die `Skip` -Klausel, um die Kunden in der Liste zu umgehen, bis die angegebenen Wert und verwendet die `Take` -Klausel, um eine Seite mit Kunden, die von diesem Indexwert zurück.</span><span class="sxs-lookup"><span data-stu-id="7bb71-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7bb71-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bb71-120">See Also</span></span>  
 [<span data-ttu-id="7bb71-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bb71-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="7bb71-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="7bb71-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="7bb71-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="7bb71-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="7bb71-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="7bb71-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="7bb71-125">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="7bb71-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="7bb71-126">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="7bb71-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="7bb71-127">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="7bb71-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
