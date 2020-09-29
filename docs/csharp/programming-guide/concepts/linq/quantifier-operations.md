---
title: Quantifizierer-Vorgänge (C#)
description: Erfahren Sie mehr über Quantifizierervorgänge. Diese Vorgänge geben einen booleschen Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: ffefe1715fd8a074692967e825e0f55673bb2b27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202538"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="f615d-104">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="f615d-104">Quantifier Operations (C#)</span></span>

<span data-ttu-id="f615d-105">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f615d-105">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="f615d-106">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="f615d-106">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="f615d-107">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f615d-107">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="f615d-108">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="f615d-108">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="f615d-110">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f615d-110">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f615d-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="f615d-111">Methods</span></span>  
  
|<span data-ttu-id="f615d-112">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f615d-112">Method Name</span></span>|<span data-ttu-id="f615d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f615d-113">Description</span></span>|<span data-ttu-id="f615d-114">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f615d-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="f615d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f615d-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="f615d-116">Alle</span><span class="sxs-lookup"><span data-stu-id="f615d-116">All</span></span>|<span data-ttu-id="f615d-117">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f615d-117">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="f615d-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f615d-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f615d-119">Beliebig</span><span class="sxs-lookup"><span data-stu-id="f615d-119">Any</span></span>|<span data-ttu-id="f615d-120">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f615d-120">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="f615d-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f615d-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f615d-122">Enthält</span><span class="sxs-lookup"><span data-stu-id="f615d-122">Contains</span></span>|<span data-ttu-id="f615d-123">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="f615d-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="f615d-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f615d-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f615d-125">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f615d-125">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="f615d-126">Alle</span><span class="sxs-lookup"><span data-stu-id="f615d-126">All</span></span>  

<span data-ttu-id="f615d-127">Im folgenden Beispiel wird `All` verwendet, um zu überprüfen, ob alle Zeichenfolgen eine bestimmte Länge besitzen.</span><span class="sxs-lookup"><span data-stu-id="f615d-127">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="f615d-128">Beliebig</span><span class="sxs-lookup"><span data-stu-id="f615d-128">Any</span></span>  

<span data-ttu-id="f615d-129">Im folgenden Beispiel wird `Any` verwendet, um zu überprüfen, ob es Zeichenfolgen gibt, die mit „o“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="f615d-129">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="f615d-130">Enthält</span><span class="sxs-lookup"><span data-stu-id="f615d-130">Contains</span></span>  

<span data-ttu-id="f615d-131">Im folgenden Beispiel wird `Contains` verwendet, um zu überprüfen, ob ein Array ein bestimmtes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="f615d-131">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="f615d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f615d-132">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="f615d-133">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="f615d-133">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="f615d-134">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f615d-134">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="f615d-135">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f615d-135">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
