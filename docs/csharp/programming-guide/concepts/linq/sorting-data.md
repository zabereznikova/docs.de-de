---
title: Sortieren von Daten (C#)
description: Hier erfahren Sie mehr über Sortiervorgänge und die Methoden von Standardabfrageoperatoren, die Sortiervorgänge in LINQ in C# ausführen.
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 0665e5dec95fd2929d24d82568de66597df1c0bd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195505"
---
# <a name="sorting-data-c"></a><span data-ttu-id="f1831-103">Sortieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="f1831-103">Sorting Data (C#)</span></span>

<span data-ttu-id="f1831-104">Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert.</span><span class="sxs-lookup"><span data-stu-id="f1831-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="f1831-105">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1831-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="f1831-106">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="f1831-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="f1831-107">Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz:</span><span class="sxs-lookup"><span data-stu-id="f1831-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span>
  
 ![Grafik, die einen alphabetischen Sortiervorgang zeigt.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="f1831-109">Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f1831-109">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1831-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="f1831-110">Methods</span></span>  
  
|<span data-ttu-id="f1831-111">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f1831-111">Method Name</span></span>|<span data-ttu-id="f1831-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1831-112">Description</span></span>|<span data-ttu-id="f1831-113">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f1831-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="f1831-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1831-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="f1831-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="f1831-115">OrderBy</span></span>|<span data-ttu-id="f1831-116">Sortiert Werte in aufsteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="f1831-116">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f1831-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="f1831-117">OrderByDescending</span></span>|<span data-ttu-id="f1831-118">Sortiert Werte in absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="f1831-118">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f1831-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="f1831-119">ThenBy</span></span>|<span data-ttu-id="f1831-120">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="f1831-120">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f1831-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="f1831-121">ThenByDescending</span></span>|<span data-ttu-id="f1831-122">Führt eine sekundäre Sortierung in absteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="f1831-122">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f1831-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="f1831-123">Reverse</span></span>|<span data-ttu-id="f1831-124">Kehrt die Reihenfolge der Elemente in einer Auflistung um</span><span class="sxs-lookup"><span data-stu-id="f1831-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="f1831-125">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f1831-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f1831-126">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f1831-126">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="f1831-127">Primäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="f1831-127">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="f1831-128">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f1831-128">Primary Ascending Sort</span></span>  

 <span data-ttu-id="f1831-129">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f1831-129">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="f1831-130">Primäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f1831-130">Primary Descending Sort</span></span>  

 <span data-ttu-id="f1831-131">Im nächsten Beispiel wird veranschaulicht, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f1831-131">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="f1831-132">Sekundäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="f1831-132">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="f1831-133">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f1831-133">Secondary Ascending Sort</span></span>  

 <span data-ttu-id="f1831-134">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f1831-134">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="f1831-135">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f1831-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="f1831-136">Sekundäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f1831-136">Secondary Descending Sort</span></span>  

 <span data-ttu-id="f1831-137">Im nächsten Beispiel wird gezeigt, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f1831-137">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="f1831-138">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="f1831-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1831-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1831-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="f1831-140">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="f1831-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="f1831-141">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="f1831-141">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="f1831-142">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="f1831-142">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="f1831-143">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f1831-143">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
