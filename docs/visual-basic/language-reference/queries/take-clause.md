---
title: Take-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 3082954ef84560ccb70f7a47cd3532f622829392
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349646"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="ef6dc-102">Take-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef6dc-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="ef6dc-103">Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef6dc-104">Syntax</span></span>  
  
```vb  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="ef6dc-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="ef6dc-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="ef6dc-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="ef6dc-106">Required.</span></span> <span data-ttu-id="ef6dc-107">Ein-Wert oder ein Ausdruck, der die Anzahl der Elemente der Sequenz ergibt, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef6dc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef6dc-108">Remarks</span></span>  
 <span data-ttu-id="ef6dc-109">Die `Take`-Klausel bewirkt, dass eine Abfrage eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Ergebnisliste enthält.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="ef6dc-110">Die Anzahl der einzuschließenden Elemente wird durch den `count`-Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="ef6dc-111">Sie können die `Take`-Klausel mit der `Skip`-Klausel verwenden, um einen Datenbereich aus einem beliebigen Segment einer Abfrage zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="ef6dc-112">Übergeben Sie hierzu den Index des ersten Elements des Bereichs an die `Skip`-Klausel und die Größe des Bereichs an die `Take`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="ef6dc-113">In diesem Fall muss die `Take`-Klausel nach der `Skip`-Klausel angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="ef6dc-114">Wenn Sie die `Take`-Klausel in einer Abfrage verwenden, müssen Sie möglicherweise auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die die `Take`-Klausel zum Einbeziehen der beabsichtigten Ergebnisse ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="ef6dc-115">Weitere Informationen zum Sortieren von Abfrage Ergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ef6dc-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="ef6dc-116">Sie können die `TakeWhile`-Klausel verwenden, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden sollen, abhängig von der angegebenen Bedingung.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef6dc-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef6dc-117">Example</span></span>  
 <span data-ttu-id="ef6dc-118">Im folgenden Codebeispiel wird die `Take`-Klausel in Verbindung mit der `Skip`-Klausel verwendet, um Daten aus einer Abfrage in Seiten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="ef6dc-119">Die GetCustomers-Funktion verwendet die `Skip`-Klausel, um die Kunden in der Liste bis zum bereitgestellten Start Index Wert zu umgehen, und verwendet die `Take`-Klausel, um eine Kundenseite zurückzugeben, beginnend mit diesem Indexwert.</span><span class="sxs-lookup"><span data-stu-id="ef6dc-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ef6dc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef6dc-120">See also</span></span>

- [<span data-ttu-id="ef6dc-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef6dc-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ef6dc-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="ef6dc-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="ef6dc-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="ef6dc-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="ef6dc-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="ef6dc-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="ef6dc-125">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="ef6dc-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="ef6dc-126">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="ef6dc-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="ef6dc-127">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="ef6dc-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
