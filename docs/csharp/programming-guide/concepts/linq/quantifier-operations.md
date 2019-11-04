---
title: Quantifizierer-Vorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5899af79799d5b8404e60027d7ba1b005c4b1b79
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423367"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="55f55-102">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="55f55-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="55f55-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="55f55-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="55f55-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="55f55-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="55f55-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="55f55-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="55f55-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="55f55-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="55f55-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="55f55-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55f55-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="55f55-109">Methods</span></span>  
  
|<span data-ttu-id="55f55-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="55f55-110">Method Name</span></span>|<span data-ttu-id="55f55-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="55f55-111">Description</span></span>|<span data-ttu-id="55f55-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="55f55-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="55f55-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55f55-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="55f55-114">Alle</span><span class="sxs-lookup"><span data-stu-id="55f55-114">All</span></span>|<span data-ttu-id="55f55-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="55f55-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="55f55-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="55f55-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="55f55-117">Beliebig</span><span class="sxs-lookup"><span data-stu-id="55f55-117">Any</span></span>|<span data-ttu-id="55f55-118">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="55f55-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="55f55-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="55f55-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="55f55-120">Enthält</span><span class="sxs-lookup"><span data-stu-id="55f55-120">Contains</span></span>|<span data-ttu-id="55f55-121">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="55f55-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="55f55-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="55f55-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="55f55-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55f55-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="55f55-124">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="55f55-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="55f55-125">Vorgehensweise: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="55f55-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="55f55-126">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="55f55-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
