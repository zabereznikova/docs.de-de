---
title: Quantifizierer-Vorgänge (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: e871a77caf0b7cfe361f11462085180c17bf2057
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816043"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="f58ac-102">Quantifizierer-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f58ac-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="f58ac-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f58ac-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="f58ac-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="f58ac-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="f58ac-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f58ac-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="f58ac-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f58ac-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="f58ac-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f58ac-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f58ac-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="f58ac-109">Methods</span></span>  
  
|<span data-ttu-id="f58ac-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f58ac-110">Method Name</span></span>|<span data-ttu-id="f58ac-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f58ac-111">Description</span></span>|<span data-ttu-id="f58ac-112">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f58ac-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f58ac-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f58ac-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f58ac-114">Alle</span><span class="sxs-lookup"><span data-stu-id="f58ac-114">All</span></span>|<span data-ttu-id="f58ac-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f58ac-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f58ac-116">Beliebig</span><span class="sxs-lookup"><span data-stu-id="f58ac-116">Any</span></span>|<span data-ttu-id="f58ac-117">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f58ac-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f58ac-118">Enthält</span><span class="sxs-lookup"><span data-stu-id="f58ac-118">Contains</span></span>|<span data-ttu-id="f58ac-119">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="f58ac-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="f58ac-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f58ac-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f58ac-121">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f58ac-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="f58ac-122">Diese Beispiele verwenden die `Aggregate` -Klausel in Visual Basic als Teil der filterbedingung in einer LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f58ac-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="f58ac-123">Im folgenden Beispiel wird die `Aggregate` Klausel und die <xref:System.Linq.Enumerable.All%2A> Erweiterungsmethode, um aus einer Sammlung diese Personen zurückzugeben, deren Haustiere älter als ein bestimmtes Alter.</span><span class="sxs-lookup"><span data-stu-id="f58ac-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="f58ac-124">Im nächsten Beispiel wird die `Aggregate` Klausel und die <xref:System.Linq.Enumerable.Any%2A> Erweiterungsmethode, um aus einer Auflistung zurückzugeben denjenigen, die in mindestens einem Haustier, ist älter als ein bestimmtes Alter.</span><span class="sxs-lookup"><span data-stu-id="f58ac-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f58ac-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f58ac-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="f58ac-126">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="f58ac-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="f58ac-127">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="f58ac-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="f58ac-128">Vorgehensweise: Abfragen von Sätzen, die einen angegebenen Satz von Wörtern (LINQ) (Visual Basic) enthalten.</span><span class="sxs-lookup"><span data-stu-id="f58ac-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
