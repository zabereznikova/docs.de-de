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
ms.openlocfilehash: 0dddb411af1b4ee269e091c07553a94589d90b2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604028"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="333a7-102">Take-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="333a7-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="333a7-103">Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="333a7-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="333a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="333a7-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="333a7-105">Teile</span><span class="sxs-lookup"><span data-stu-id="333a7-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="333a7-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="333a7-106">Required.</span></span> <span data-ttu-id="333a7-107">Ein Wert oder einen Ausdruck, der die Anzahl der Elemente der Sequenz zurückzugebenden ergibt.</span><span class="sxs-lookup"><span data-stu-id="333a7-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="333a7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="333a7-108">Remarks</span></span>  
 <span data-ttu-id="333a7-109">Die `Take` -Klausel bewirkt, dass eine Abfrage an eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Ergebnisliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="333a7-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="333a7-110">Die Anzahl der einzuschließenden Elemente gemäß der `count` Parameter.</span><span class="sxs-lookup"><span data-stu-id="333a7-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="333a7-111">Sie können die `Take` -Klausel mit der `Skip` -Klausel, um einen Datenbereich aus einem beliebigen Abschnitt einer Abfrage zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="333a7-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="333a7-112">Übergeben Sie den Index des ersten Elements des Bereichs, der zu diesem Zweck die `Skip` -Klausel und die Größe des Bereichs, der die `Take` Klausel.</span><span class="sxs-lookup"><span data-stu-id="333a7-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="333a7-113">In diesem Fall die `Take` -Klausel muss angegeben werden, nachdem die `Skip` Klausel.</span><span class="sxs-lookup"><span data-stu-id="333a7-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="333a7-114">Bei Verwendung der `Take` -Klausel einer Abfrage, Sie müssen auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die es ermöglichen, wird die `Take` -Klausel, um die gewünschten Ergebnisse einschließen.</span><span class="sxs-lookup"><span data-stu-id="333a7-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="333a7-115">Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="333a7-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="333a7-116">Sie können die `TakeWhile` -Klausel, um anzugeben, dass nur bestimmte Elemente zurückgegeben werden, abhängig von einer angegebenen Bedingung.</span><span class="sxs-lookup"><span data-stu-id="333a7-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="333a7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="333a7-117">Example</span></span>  
 <span data-ttu-id="333a7-118">Im folgenden Codebeispiel wird mit der `Take` -Klausel zusammen mit der `Skip` -Klausel, um Daten aus einer Abfrage in Seiten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="333a7-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="333a7-119">Die GetCustomers-Funktion verwendet die `Skip` -Klausel, um die Kunden in der Liste zu umgehen, bis die angegebenen Wert und verwendet die `Take` -Klausel, um das Zurückgeben einer Seite mit Kunden, die von diesem Indexwert ab.</span><span class="sxs-lookup"><span data-stu-id="333a7-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="333a7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="333a7-120">See Also</span></span>  
 [<span data-ttu-id="333a7-121">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="333a7-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="333a7-122">Abfragen</span><span class="sxs-lookup"><span data-stu-id="333a7-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="333a7-123">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="333a7-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="333a7-124">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="333a7-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="333a7-125">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="333a7-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="333a7-126">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="333a7-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="333a7-127">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="333a7-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
