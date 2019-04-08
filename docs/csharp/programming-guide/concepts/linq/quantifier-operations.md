---
title: Quantifizierer-Vorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 090bc53c3dcedc82972ab7d16fa2968011a7db65
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412252"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="0e84a-102">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="0e84a-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="0e84a-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0e84a-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="0e84a-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="0e84a-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="0e84a-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="0e84a-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="0e84a-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="0e84a-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="0e84a-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e84a-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e84a-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="0e84a-109">Methods</span></span>  
  
|<span data-ttu-id="0e84a-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="0e84a-110">Method Name</span></span>|<span data-ttu-id="0e84a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e84a-111">Description</span></span>|<span data-ttu-id="0e84a-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="0e84a-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="0e84a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e84a-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="0e84a-114">Alle</span><span class="sxs-lookup"><span data-stu-id="0e84a-114">All</span></span>|<span data-ttu-id="0e84a-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0e84a-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="0e84a-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0e84a-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0e84a-117">Beliebig</span><span class="sxs-lookup"><span data-stu-id="0e84a-117">Any</span></span>|<span data-ttu-id="0e84a-118">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0e84a-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="0e84a-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0e84a-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0e84a-120">Enthält</span><span class="sxs-lookup"><span data-stu-id="0e84a-120">Contains</span></span>|<span data-ttu-id="0e84a-121">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="0e84a-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="0e84a-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="0e84a-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="0e84a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e84a-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="0e84a-124">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="0e84a-124">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0e84a-125">Vorgehensweise: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0e84a-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="0e84a-126">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="0e84a-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
