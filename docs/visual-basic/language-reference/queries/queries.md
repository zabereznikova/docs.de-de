---
title: Abfragen (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic]
- LINQ, queries
ms.assetid: 8edc717c-4a24-4cbc-9c16-11f479c935db
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4a178714055076537033fbda32d7c7c1c544351d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="queries-visual-basic"></a><span data-ttu-id="07919-102">Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07919-102">Queries (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="07919-103">ermöglicht Ihnen die Erstellung [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] Ausdrücke im Code.</span><span class="sxs-lookup"><span data-stu-id="07919-103"> enables you to create [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07919-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="07919-104">In This Section</span></span>  
 [<span data-ttu-id="07919-105">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-105">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 <span data-ttu-id="07919-106">Beschreibt die `Aggregate` -Klausel, die eine oder mehrere Aggregatfunktionen auf eine Auflistung anwendet.</span><span class="sxs-lookup"><span data-stu-id="07919-106">Describes the `Aggregate` clause, which applies one or more aggregate functions to a collection.</span></span>  
  
 [<span data-ttu-id="07919-107">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-107">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 <span data-ttu-id="07919-108">Beschreibt die `Distinct` -Klausel, die die Werte der aktuellen Bereichsvariablen zu unterbinden von doppelten Werten in Abfrageergebnissen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="07919-108">Describes the `Distinct` clause, which restricts the values of the current range variable to eliminate duplicate values in query results.</span></span>  
  
 [<span data-ttu-id="07919-109">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-109">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 <span data-ttu-id="07919-110">Beschreibt die `From` -Klausel, die eine Auflistung und eine Bereichsvariable für eine Abfrage angibt.</span><span class="sxs-lookup"><span data-stu-id="07919-110">Describes the `From` clause, which specifies a collection and a range variable for a query.</span></span>  
  
 [<span data-ttu-id="07919-111">Group By-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-111">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)  
 <span data-ttu-id="07919-112">Beschreibt die `Group By` -Klausel, die die Elemente eines Abfrageergebnisses gruppiert und kann verwendet werden, um Aggregatfunktionen auf jede Gruppe angewendet.</span><span class="sxs-lookup"><span data-stu-id="07919-112">Describes the `Group By` clause, which groups the elements of a query result and can be used to apply aggregate functions to each group.</span></span>  
  
 [<span data-ttu-id="07919-113">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-113">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 <span data-ttu-id="07919-114">Beschreibt die `Group Join` -Klausel, die beiden Auflistungen in einer einzelnen hierarchischen Auflistung kombiniert.</span><span class="sxs-lookup"><span data-stu-id="07919-114">Describes the `Group Join` clause, which combines two collections into a single hierarchical collection.</span></span>  
  
 [<span data-ttu-id="07919-115">Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-115">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 <span data-ttu-id="07919-116">Beschreibt die `Join` -Klausel, die kombiniert zwei Sammlungen in einer einzelnen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="07919-116">Describes the `Join` clause, which combines two collections into a single collection.</span></span>  
  
 [<span data-ttu-id="07919-117">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-117">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 <span data-ttu-id="07919-118">Beschreibt die `Let` -Klausel, die einen Wert berechnet und in der Abfrage einer neuen Variable zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="07919-118">Describes the `Let` clause, which computes a value and assigns it to a new variable in the query.</span></span>  
  
 [<span data-ttu-id="07919-119">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-119">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 <span data-ttu-id="07919-120">Beschreibt die `Order By` -Klausel, die die Sortierreihenfolge für Spalten in einer Abfrage angibt.</span><span class="sxs-lookup"><span data-stu-id="07919-120">Describes the `Order By` clause, which specifies the sort order for columns in a query.</span></span>  
  
 [<span data-ttu-id="07919-121">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-121">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 <span data-ttu-id="07919-122">Beschreibt die `Select` -Klausel, die einen Satz von Bereichsvariablen für eine Abfrage deklariert.</span><span class="sxs-lookup"><span data-stu-id="07919-122">Describes the `Select` clause, which declares a set of range variables for a query.</span></span>  
  
 [<span data-ttu-id="07919-123">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-123">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 <span data-ttu-id="07919-124">Beschreibt die `Skip` -Klausel, die eine angegebene Anzahl von Elementen in einer Auflistung umgeht und anschließend die verbleibenden Elemente zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="07919-124">Describes the `Skip` clause, which bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="07919-125">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 <span data-ttu-id="07919-126">Beschreibt die `Skip While` -Klausel, die Elemente in einer Auflistung umgeht, solange eine angegebene Bedingung `true` und gibt dann die übrigen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="07919-126">Describes the `Skip While` clause, which bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="07919-127">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-127">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 <span data-ttu-id="07919-128">Beschreibt die `Take` -Klausel, die eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="07919-128">Describes the `Take` clause, which returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
 [<span data-ttu-id="07919-129">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-129">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 <span data-ttu-id="07919-130">Beschreibt die `Take While` -Klausel, die Elemente in einer Auflistung enthält, solange eine angegebene Bedingung `true` und überspringt dann die übrigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="07919-130">Describes the `Take While` clause, which includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
 [<span data-ttu-id="07919-131">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="07919-131">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 <span data-ttu-id="07919-132">Beschreibt die `Where` -Klausel, die eine filterbedingung für eine Abfrage angibt.</span><span class="sxs-lookup"><span data-stu-id="07919-132">Describes the `Where` clause, which specifies a filtering condition for a query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07919-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07919-133">See Also</span></span>  
 <span data-ttu-id="07919-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="07919-134">[LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="07919-135"> [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="07919-135"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
