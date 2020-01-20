---
title: Quantifizierer-Vorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635482"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="2305d-102">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="2305d-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="2305d-103">Quantifizierer-Vorgänge geben einen <xref:System.Boolean>-Wert zurück, der angibt, ob einige oder alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2305d-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="2305d-104">Die folgende Abbildung zeigt zwei verschiedene Quantifizierer-Vorgänge bei zwei verschiedenen Quellsequenzen.</span><span class="sxs-lookup"><span data-stu-id="2305d-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="2305d-105">Der erste Vorgang fragt, ob eines oder mehrere der Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="2305d-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="2305d-106">Der zweite Vorgang fragt, ob alle Elemente das Zeichen „A“ sind. Das Ergebnis ist `true`.</span><span class="sxs-lookup"><span data-stu-id="2305d-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ-Quantifizierer-Vorgänge](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="2305d-108">Die Methoden des Standardabfrageoperators, die Quantifizierer-Vorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2305d-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2305d-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="2305d-109">Methods</span></span>  
  
|<span data-ttu-id="2305d-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="2305d-110">Method Name</span></span>|<span data-ttu-id="2305d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2305d-111">Description</span></span>|<span data-ttu-id="2305d-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2305d-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="2305d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2305d-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="2305d-114">Alle</span><span class="sxs-lookup"><span data-stu-id="2305d-114">All</span></span>|<span data-ttu-id="2305d-115">Bestimmt, ob alle Elemente in einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2305d-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="2305d-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2305d-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2305d-117">Beliebig</span><span class="sxs-lookup"><span data-stu-id="2305d-117">Any</span></span>|<span data-ttu-id="2305d-118">Bestimmt, ob Elemente einer Sequenz eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="2305d-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="2305d-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2305d-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2305d-120">Enthält</span><span class="sxs-lookup"><span data-stu-id="2305d-120">Contains</span></span>|<span data-ttu-id="2305d-121">Bestimmt, ob eine Sequenz ein angegebenes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="2305d-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="2305d-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2305d-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="2305d-123">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2305d-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="2305d-124">Alle</span><span class="sxs-lookup"><span data-stu-id="2305d-124">All</span></span>  
<span data-ttu-id="2305d-125">Im folgenden Beispiel wird `All` verwendet, um zu überprüfen, ob alle Zeichenfolgen eine bestimmte Länge besitzen.</span><span class="sxs-lookup"><span data-stu-id="2305d-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="2305d-126">Beliebig</span><span class="sxs-lookup"><span data-stu-id="2305d-126">Any</span></span>  
<span data-ttu-id="2305d-127">Im folgenden Beispiel wird `Any` verwendet, um zu überprüfen, ob es Zeichenfolgen gibt, die mit „o“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="2305d-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="2305d-128">Enthält</span><span class="sxs-lookup"><span data-stu-id="2305d-128">Contains</span></span>  
<span data-ttu-id="2305d-129">Im folgenden Beispiel wird `Contains` verwendet, um zu überprüfen, ob ein Array ein bestimmtes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="2305d-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="2305d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2305d-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="2305d-131">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="2305d-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="2305d-132">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2305d-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="2305d-133">Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2305d-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
