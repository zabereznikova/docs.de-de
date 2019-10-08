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
ms.openlocfilehash: 32a4c7fd7f1e2f6fe640f3f53f15579f014759d5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004713"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="b9a9c-102">Take-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9a9c-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="b9a9c-103">Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a9c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9a9c-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="b9a9c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b9a9c-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="b9a9c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-106">Required.</span></span> <span data-ttu-id="b9a9c-107">Ein-Wert oder ein Ausdruck, der die Anzahl der Elemente der Sequenz ergibt, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9a9c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b9a9c-108">Remarks</span></span>  
 <span data-ttu-id="b9a9c-109">Die `Take`-Klausel bewirkt, dass eine Abfrage eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Ergebnisliste enthält.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="b9a9c-110">Die Anzahl der einzuschließenden Elemente wird durch den `count`-Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="b9a9c-111">Sie können die `Take`-Klausel mit der `Skip`-Klausel verwenden, um einen Datenbereich aus einem beliebigen Segment einer Abfrage zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="b9a9c-112">Übergeben Sie hierzu den Index des ersten Elements des Bereichs an die `Skip`-Klausel und die Größe des Bereichs an die `Take`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="b9a9c-113">In diesem Fall muss die `Take`-Klausel nach der `Skip`-Klausel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="b9a9c-114">Wenn Sie die `Take`-Klausel in einer Abfrage verwenden, müssen Sie möglicherweise auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die die `Take`-Klausel zum Einbeziehen der beabsichtigten Ergebnisse ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="b9a9c-115">Weitere Informationen zum Sortieren von Abfrage Ergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b9a9c-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="b9a9c-116">Sie können die `TakeWhile`-Klausel verwenden, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden sollen, abhängig von der angegebenen Bedingung.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9a9c-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9a9c-117">Example</span></span>  
 <span data-ttu-id="b9a9c-118">Im folgenden Codebeispiel wird die `Take`-Klausel in Verbindung mit der `Skip`-Klausel verwendet, um Daten aus einer Abfrage in Seiten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="b9a9c-119">Die GetCustomers-Funktion verwendet die `Skip`-Klausel, um die Kunden in der Liste bis zum bereitgestellten Start Index Wert zu umgehen, und verwendet die `Take`-Klausel, um eine Kundenseite zurückzugeben, beginnend mit diesem Indexwert.</span><span class="sxs-lookup"><span data-stu-id="b9a9c-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b9a9c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9a9c-120">See also</span></span>

- [<span data-ttu-id="b9a9c-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b9a9c-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b9a9c-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="b9a9c-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b9a9c-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="b9a9c-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="b9a9c-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="b9a9c-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b9a9c-125">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="b9a9c-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="b9a9c-126">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="b9a9c-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="b9a9c-127">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="b9a9c-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
