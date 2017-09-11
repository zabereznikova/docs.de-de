---
title: "Quantifizierer-Vorgänge (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e0c982508640ef1ecb47d477d3e9330198474ca
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="2c87e-102">Quantifizierer-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c87e-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="2c87e-103">Quantifizierer-Vorgänge Zurückgeben einer <xref:System.Boolean>-Wert, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="2c87e-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="2c87e-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge auf zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="2c87e-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="2c87e-105">Der erste Vorgang fragt, ob eine oder mehrere der Elemente sind die Zeichen "A" das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="2c87e-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="2c87e-106">Der zweite Vorgang fragt, ob alle Elemente sind die Zeichen "A", und das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="2c87e-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="2c87e-107">![LINQ-Quantifizierer-Vorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="2c87e-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="2c87e-108">Die Standardabfrageoperator-Methoden, die Quantifizierer-Vorgänge ausführen, werden im folgenden Abschnitt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2c87e-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c87e-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="2c87e-109">Methods</span></span>  
  
|<span data-ttu-id="2c87e-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="2c87e-110">Method Name</span></span>|<span data-ttu-id="2c87e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c87e-111">Description</span></span>|<span data-ttu-id="2c87e-112">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2c87e-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="2c87e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c87e-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="2c87e-114">Alle</span><span class="sxs-lookup"><span data-stu-id="2c87e-114">All</span></span>|<span data-ttu-id="2c87e-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2c87e-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<span data-ttu-id="2c87e-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2c87e-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2c87e-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2c87e-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="2c87e-118">Beliebig</span><span class="sxs-lookup"><span data-stu-id="2c87e-118">Any</span></span>|<span data-ttu-id="2c87e-119">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2c87e-119">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<span data-ttu-id="2c87e-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2c87e-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2c87e-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2c87e-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="2c87e-122">Enthält</span><span class="sxs-lookup"><span data-stu-id="2c87e-122">Contains</span></span>|<span data-ttu-id="2c87e-123">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="2c87e-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="2c87e-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2c87e-124">Not applicable.</span></span>|<span data-ttu-id="2c87e-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2c87e-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="2c87e-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="2c87e-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="2c87e-127">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2c87e-127">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="2c87e-128">Diese Beispiele verwenden die `Aggregate` -Klausel in Visual Basic als Teil der filterbedingung in einer LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="2c87e-128">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="2c87e-129">Im folgenden Beispiel wird die `Aggregate` -Klausel und der <xref:System.Linq.Enumerable.All%2A>-Erweiterungsmethode, die aus einer Auflistung die Personen zurückzugeben, deren Haustiere älter als ein angegebenes Alter.</xref:System.Linq.Enumerable.All%2A></span><span class="sxs-lookup"><span data-stu-id="2c87e-129">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 <span data-ttu-id="2c87e-130">[!code-vb[CsLINQAnyAll&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2c87e-130">[!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="2c87e-131">Im nächsten Beispiel wird die `Aggregate` -Klausel und der <xref:System.Linq.Enumerable.Any%2A>Erweiterungsmethode, um aus einer Auflistung zurückzugeben denjenigen, die in mindestens einem Haustier, ist älter als ein angegebenes Alter.</xref:System.Linq.Enumerable.Any%2A></span><span class="sxs-lookup"><span data-stu-id="2c87e-131">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 <span data-ttu-id="2c87e-132">[!code-vb[CsLINQAnyAll&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2c87e-132">[!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c87e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c87e-133">See Also</span></span>  
 <span data-ttu-id="2c87e-134"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="2c87e-134"><xref:System.Linq></span></span>   
<span data-ttu-id="2c87e-135"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="2c87e-135"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="2c87e-136"> [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2c87e-136"> [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="2c87e-137"> [Gewusst wie: Abfragen von Sätzen, die eine angegebene Gruppe von Wörtern (LINQ) (Visual Basic) enthalten.](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span><span class="sxs-lookup"><span data-stu-id="2c87e-137"> [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span></span>
