---
title: Quantifizierer-Vorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635482"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="cf999-102">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="cf999-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="cf999-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cf999-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="cf999-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="cf999-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="cf999-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="cf999-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="cf999-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="cf999-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="cf999-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="cf999-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf999-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="cf999-109">Methods</span></span>  
  
|<span data-ttu-id="cf999-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="cf999-110">Method Name</span></span>|<span data-ttu-id="cf999-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf999-111">Description</span></span>|<span data-ttu-id="cf999-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="cf999-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="cf999-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf999-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="cf999-114">Alle</span><span class="sxs-lookup"><span data-stu-id="cf999-114">All</span></span>|<span data-ttu-id="cf999-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cf999-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="cf999-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="cf999-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cf999-117">Beliebig</span><span class="sxs-lookup"><span data-stu-id="cf999-117">Any</span></span>|<span data-ttu-id="cf999-118">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cf999-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="cf999-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="cf999-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cf999-120">Enthält</span><span class="sxs-lookup"><span data-stu-id="cf999-120">Contains</span></span>|<span data-ttu-id="cf999-121">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="cf999-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="cf999-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="cf999-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="cf999-123">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="cf999-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="cf999-124">Alle</span><span class="sxs-lookup"><span data-stu-id="cf999-124">All</span></span>  
<span data-ttu-id="cf999-125">Im folgenden Beispiel wird `All` verwendet, um zu überprüfen, ob alle Zeichenfolgen eine bestimmte Länge besitzen.</span><span class="sxs-lookup"><span data-stu-id="cf999-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="cf999-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="cf999-126">Any</span></span>  
<span data-ttu-id="cf999-127">Im folgenden Beispiel wird `Any` verwendet, um zu überprüfen, ob es Zeichenfolgen gibt, die mit „o“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="cf999-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="cf999-128">Enthält</span><span class="sxs-lookup"><span data-stu-id="cf999-128">Contains</span></span>  
<span data-ttu-id="cf999-129">Im folgenden Beispiel wird `Contains` verwendet, um zu überprüfen, ob ein Array ein bestimmtes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="cf999-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="cf999-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf999-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="cf999-131">Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="cf999-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="cf999-132">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cf999-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="cf999-133">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cf999-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
