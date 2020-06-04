---
title: Skip-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 427d14453260a54bd3f2ab9a8ac75dedacd291f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359657"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="addd8-102">Skip-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="addd8-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="addd8-103">Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="addd8-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="addd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="addd8-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="addd8-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="addd8-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="addd8-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="addd8-106">Required.</span></span> <span data-ttu-id="addd8-107">Ein-Wert oder ein Ausdruck, der die Anzahl der zu über springenden Elemente der Sequenz ergibt.</span><span class="sxs-lookup"><span data-stu-id="addd8-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="addd8-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="addd8-108">Remarks</span></span>  
 <span data-ttu-id="addd8-109">Die `Skip` -Klausel bewirkt, dass eine Abfrage Elemente am Anfang einer Ergebnisliste umgeht und die restlichen Elemente zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="addd8-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="addd8-110">Die Anzahl der zu über springenden Elemente wird durch den- `count` Parameter identifiziert.</span><span class="sxs-lookup"><span data-stu-id="addd8-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="addd8-111">Sie können die- `Skip` Klausel mit der- `Take` Klausel verwenden, um einen Datenbereich aus einem beliebigen Segment einer Abfrage zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="addd8-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="addd8-112">Übergeben Sie hierzu den Index des ersten Elements des Bereichs an die `Skip` -Klausel und die Größe des Bereichs an die- `Take` Klausel.</span><span class="sxs-lookup"><span data-stu-id="addd8-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="addd8-113">Wenn Sie die- `Skip` Klausel in einer Abfrage verwenden, müssen Sie möglicherweise auch sicherstellen, dass die Ergebnisse in einer Reihenfolge zurückgegeben werden, die die- `Skip` Klausel zum Umgehen der beabsichtigten Ergebnisse ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="addd8-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="addd8-114">Weitere Informationen zum Sortieren von Abfrage Ergebnissen finden Sie unter [Order By-Klausel](order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="addd8-114">For more information about ordering query results, see [Order By Clause](order-by-clause.md).</span></span>  
  
 <span data-ttu-id="addd8-115">Sie können die- `SkipWhile` Klausel verwenden, um anzugeben, dass nur bestimmte Elemente ignoriert werden, abhängig von der angegebenen Bedingung.</span><span class="sxs-lookup"><span data-stu-id="addd8-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="addd8-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="addd8-116">Example</span></span>  
 <span data-ttu-id="addd8-117">Im folgenden Codebeispiel wird die- `Skip` Klausel in Verbindung mit der- `Take` Klausel verwendet, um Daten aus einer Abfrage in Seiten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="addd8-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="addd8-118">Die- `GetCustomers` Funktion verwendet die- `Skip` Klausel, um die Kunden in der Liste bis zum bereitgestellten Start Index Wert zu umgehen, und verwendet die- `Take` Klausel, um eine Kundenseite zurückzugeben, beginnend mit diesem Indexwert.</span><span class="sxs-lookup"><span data-stu-id="addd8-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="addd8-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="addd8-119">See also</span></span>

- [<span data-ttu-id="addd8-120">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="addd8-120">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="addd8-121">Abfragen</span><span class="sxs-lookup"><span data-stu-id="addd8-121">Queries</span></span>](index.md)
- [<span data-ttu-id="addd8-122">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="addd8-122">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="addd8-123">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="addd8-123">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="addd8-124">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="addd8-124">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="addd8-125">SkipWhile-Klausel</span><span class="sxs-lookup"><span data-stu-id="addd8-125">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="addd8-126">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="addd8-126">Take Clause</span></span>](take-clause.md)
