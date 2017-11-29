---
title: "Quantifizierer-Vorgänge (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bc48c69179b1f8876efaa465295e94a9a0e0fb6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="6ae71-102">Quantifizierer-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ae71-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="6ae71-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6ae71-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="6ae71-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="6ae71-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="6ae71-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="6ae71-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="6ae71-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="6ae71-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="6ae71-107">![LINQ-Quantifizierer-Vorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="6ae71-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="6ae71-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ae71-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ae71-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="6ae71-109">Methods</span></span>  
  
|<span data-ttu-id="6ae71-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="6ae71-110">Method Name</span></span>|<span data-ttu-id="6ae71-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ae71-111">Description</span></span>|<span data-ttu-id="6ae71-112">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="6ae71-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="6ae71-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ae71-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="6ae71-114">Alle</span><span class="sxs-lookup"><span data-stu-id="6ae71-114">All</span></span>|<span data-ttu-id="6ae71-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6ae71-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6ae71-116">Beliebig</span><span class="sxs-lookup"><span data-stu-id="6ae71-116">Any</span></span>|<span data-ttu-id="6ae71-117">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6ae71-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="6ae71-118">Enthält</span><span class="sxs-lookup"><span data-stu-id="6ae71-118">Contains</span></span>|<span data-ttu-id="6ae71-119">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="6ae71-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="6ae71-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="6ae71-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="6ae71-121">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="6ae71-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="6ae71-122">Diese Beispiele verwenden die `Aggregate` -Klausel in Visual Basic als Teil der filterbedingung in einer LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="6ae71-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="6ae71-123">Im folgenden Beispiel wird die `Aggregate` Klausel und die <xref:System.Linq.Enumerable.All%2A> Extension-Methode, um aus einer Auflistung die Personen zurückzugeben, deren Haustieren älter als ein bestimmtes Alter sind.</span><span class="sxs-lookup"><span data-stu-id="6ae71-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="6ae71-124">Im nächste Beispiel wird die `Aggregate` Klausel und die <xref:System.Linq.Enumerable.Any%2A> Erweiterungsmethode zurückzugebenden aus einer Auflistung, die Personen, die in mindestens einem Haustier, die älter als ein bestimmtes Alter handelt.</span><span class="sxs-lookup"><span data-stu-id="6ae71-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6ae71-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ae71-125">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="6ae71-126">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6ae71-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="6ae71-127">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="6ae71-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="6ae71-128">Vorgehensweise: Abfragen von Sätzen, die einen angegebenen Satz von Wörtern (LINQ) (Visual Basic) enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ae71-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
