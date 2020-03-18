---
title: Sortieren von Daten (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 29a5e3e685bdc73536961b7783f4986796b46bdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167906"
---
# <a name="sorting-data-c"></a><span data-ttu-id="ecd5f-102">Sortieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="ecd5f-102">Sorting Data (C#)</span></span>
<span data-ttu-id="ecd5f-103">Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="ecd5f-104">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="ecd5f-105">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="ecd5f-106">Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz:</span><span class="sxs-lookup"><span data-stu-id="ecd5f-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span>
  
 ![Grafik, die einen alphabetischen Sortiervorgang zeigt.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="ecd5f-108">Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ecd5f-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="ecd5f-109">Methods</span></span>  
  
|<span data-ttu-id="ecd5f-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="ecd5f-110">Method Name</span></span>|<span data-ttu-id="ecd5f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecd5f-111">Description</span></span>|<span data-ttu-id="ecd5f-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ecd5f-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="ecd5f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecd5f-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ecd5f-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="ecd5f-114">OrderBy</span></span>|<span data-ttu-id="ecd5f-115">Sortiert Werte in aufsteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ecd5f-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ecd5f-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="ecd5f-116">OrderByDescending</span></span>|<span data-ttu-id="ecd5f-117">Sortiert Werte in absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ecd5f-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ecd5f-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="ecd5f-118">ThenBy</span></span>|<span data-ttu-id="ecd5f-119">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="ecd5f-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ecd5f-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="ecd5f-120">ThenByDescending</span></span>|<span data-ttu-id="ecd5f-121">Führt eine sekundäre Sortierung in absteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="ecd5f-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ecd5f-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="ecd5f-122">Reverse</span></span>|<span data-ttu-id="ecd5f-123">Kehrt die Reihenfolge der Elemente in einer Auflistung um</span><span class="sxs-lookup"><span data-stu-id="ecd5f-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="ecd5f-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ecd5f-125">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ecd5f-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="ecd5f-126">Primäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="ecd5f-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="ecd5f-127">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ecd5f-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="ecd5f-128">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="ecd5f-129">Primäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ecd5f-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="ecd5f-130">Im nächsten Beispiel wird veranschaulicht, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="ecd5f-131">Sekundäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="ecd5f-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="ecd5f-132">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ecd5f-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="ecd5f-133">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="ecd5f-134">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="ecd5f-135">Sekundäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ecd5f-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="ecd5f-136">Im nächsten Beispiel wird gezeigt, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="ecd5f-137">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="ecd5f-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ecd5f-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecd5f-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="ecd5f-139">Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="ecd5f-139">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="ecd5f-140">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="ecd5f-140">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="ecd5f-141">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="ecd5f-141">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="ecd5f-142">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ecd5f-142">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
