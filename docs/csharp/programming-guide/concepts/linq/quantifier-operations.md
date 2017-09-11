---
title: "Quantifizierer-Vorgänge (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f82df05693dffec64bcbc66cc2c0b9db2a7deb20
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="quantifier-operations-c"></a><span data-ttu-id="390c8-102">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="390c8-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="390c8-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="390c8-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="390c8-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="390c8-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="390c8-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="390c8-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="390c8-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="390c8-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="390c8-107">![LINQ-Quantifizierer-Vorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="390c8-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="390c8-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="390c8-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="390c8-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="390c8-109">Methods</span></span>  
  
|<span data-ttu-id="390c8-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="390c8-110">Method Name</span></span>|<span data-ttu-id="390c8-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="390c8-111">Description</span></span>|<span data-ttu-id="390c8-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="390c8-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="390c8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="390c8-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="390c8-114">Alle</span><span class="sxs-lookup"><span data-stu-id="390c8-114">All</span></span>|<span data-ttu-id="390c8-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="390c8-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="390c8-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="390c8-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|<span data-ttu-id="390c8-117">Beliebig</span><span class="sxs-lookup"><span data-stu-id="390c8-117">Any</span></span>|<span data-ttu-id="390c8-118">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="390c8-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="390c8-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="390c8-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|<span data-ttu-id="390c8-120">Enthält</span><span class="sxs-lookup"><span data-stu-id="390c8-120">Contains</span></span>|<span data-ttu-id="390c8-121">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="390c8-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="390c8-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="390c8-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="390c8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="390c8-123">See Also</span></span>  
 <span data-ttu-id="390c8-124"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="390c8-124"><xref:System.Linq></span></span>   
 <span data-ttu-id="390c8-125">[Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="390c8-125">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="390c8-126">[How to: Dynamically Specify Predicate Filters at Runtime (Vorgehensweise: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit)](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="390c8-126">[How to: Dynamically Specify Predicate Filters at Runtime](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span></span>  
 [<span data-ttu-id="390c8-127">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#) (Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#))</span><span class="sxs-lookup"><span data-stu-id="390c8-127">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

