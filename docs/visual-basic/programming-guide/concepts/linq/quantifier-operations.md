---
title: Quantifizierervorgänge
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0c1c69cb36ac16126454dc0c24cd84fc85b0b218
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075303"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="3b644-102">Quantifizierer-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b644-102">Quantifier Operations (Visual Basic)</span></span>

<span data-ttu-id="3b644-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3b644-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="3b644-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="3b644-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="3b644-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="3b644-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="3b644-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="3b644-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="3b644-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3b644-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b644-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="3b644-109">Methods</span></span>  
  
|<span data-ttu-id="3b644-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="3b644-110">Method Name</span></span>|<span data-ttu-id="3b644-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b644-111">Description</span></span>|<span data-ttu-id="3b644-112">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="3b644-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3b644-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b644-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="3b644-114">Alle</span><span class="sxs-lookup"><span data-stu-id="3b644-114">All</span></span>|<span data-ttu-id="3b644-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3b644-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3b644-116">Beliebig</span><span class="sxs-lookup"><span data-stu-id="3b644-116">Any</span></span>|<span data-ttu-id="3b644-117">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3b644-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3b644-118">Enthält</span><span class="sxs-lookup"><span data-stu-id="3b644-118">Contains</span></span>|<span data-ttu-id="3b644-119">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="3b644-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="3b644-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="3b644-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="3b644-121">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="3b644-121">Query Expression Syntax Examples</span></span>  

 <span data-ttu-id="3b644-122">In diesen Beispielen wird die- `Aggregate` Klausel in Visual Basic als Teil der Filterbedingung in einer LINQ-Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b644-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="3b644-123">Im folgenden Beispiel wird die `Aggregate` -Klausel und die- <xref:System.Linq.Enumerable.All%2A> Erweiterungsmethode verwendet, um die Personen zurückzugeben, deren Haustiere alle älter sind als ein bestimmtes Alter.</span><span class="sxs-lookup"><span data-stu-id="3b644-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="3b644-124">Im nächsten Beispiel wird die `Aggregate` -Klausel und die- <xref:System.Linq.Enumerable.Any%2A> Erweiterungsmethode verwendet, um von einer Auflistung zurückzugeben, die über mindestens ein Haustier verfügen, das älter ist als ein bestimmtes Alter.</span><span class="sxs-lookup"><span data-stu-id="3b644-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3b644-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b644-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3b644-126">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="3b644-126">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="3b644-127">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="3b644-127">Aggregate Clause</span></span>](../../../language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="3b644-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic) (Gewusst wie: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#))</span><span class="sxs-lookup"><span data-stu-id="3b644-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
