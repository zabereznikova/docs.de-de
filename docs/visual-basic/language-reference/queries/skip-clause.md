---
title: Skip-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 53fc47c7dd26142d2ead49178afefe2775a96580
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543145"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="24931-102">Skip-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24931-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="24931-103">Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="24931-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24931-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24931-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="24931-105">Teile</span><span class="sxs-lookup"><span data-stu-id="24931-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="24931-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="24931-106">Required.</span></span> <span data-ttu-id="24931-107">Ein Wert oder ein Ausdruck, der die Anzahl der Elemente der Sequenz zu überspringenden ergibt.</span><span class="sxs-lookup"><span data-stu-id="24931-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24931-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24931-108">Remarks</span></span>  
 <span data-ttu-id="24931-109">Die `Skip` -Klausel bewirkt, dass eine Abfrage Elemente am Anfang einer Ergebnisliste zu umgehen und die übrigen Elemente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24931-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="24931-110">Die Anzahl der zu überspringenden Elemente wird durch identifiziert die `count` Parameter.</span><span class="sxs-lookup"><span data-stu-id="24931-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="24931-111">Können Sie die `Skip` -Klausel mit der `Take` -Klausel, um einen Bereich von Daten aus jedem Segment einer Abfrage zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="24931-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="24931-112">Dazu übergeben Sie den Index des ersten Elements des Bereichs, der die `Skip` -Klausel und die Größe des Bereichs, der die `Take` Klausel.</span><span class="sxs-lookup"><span data-stu-id="24931-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="24931-113">Bei Verwendung der `Skip` -Klausel in einer Abfrage, Sie müssen auch sicherstellen, dass die Ergebnisse in der Reihenfolge zurückgegeben werden, mit denen die `Skip` -Klausel, um die gewünschten Ergebnisse zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="24931-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="24931-114">Weitere Informationen zum Sortieren von Abfrageergebnissen finden Sie unter [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="24931-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="24931-115">Sie können die `SkipWhile` Klausel, um anzugeben, dass nur bestimmte Elemente, je nach einer angegebenen Bedingung ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="24931-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24931-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24931-116">Example</span></span>  
 <span data-ttu-id="24931-117">Im folgenden Codebeispiel wird die `Skip` -Klausel zusammen mit den `Take` -Klausel zur Rückgabe von Daten aus einer Abfrage in Seiten.</span><span class="sxs-lookup"><span data-stu-id="24931-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="24931-118">Die `GetCustomers` Funktion verwendet die `Skip` -Klausel, um die Kunden in der Liste zu umgehen, bis die angegebenen Wert und verwendet die `Take` -Klausel, um eine Seite mit Kunden, die von diesem Indexwert zurück.</span><span class="sxs-lookup"><span data-stu-id="24931-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="24931-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24931-119">See also</span></span>
- [<span data-ttu-id="24931-120">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24931-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="24931-121">Abfragen</span><span class="sxs-lookup"><span data-stu-id="24931-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="24931-122">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="24931-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="24931-123">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="24931-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="24931-124">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="24931-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="24931-125">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="24931-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="24931-126">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="24931-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
