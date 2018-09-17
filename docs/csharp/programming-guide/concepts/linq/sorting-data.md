---
title: Sortieren von Daten (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 6a7f687895385bfb77d2a1e3e785742a794bb1b6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45638307"
---
# <a name="sorting-data-c"></a><span data-ttu-id="f3afa-102">Sortieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="f3afa-102">Sorting Data (C#)</span></span>
<span data-ttu-id="f3afa-103">Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert.</span><span class="sxs-lookup"><span data-stu-id="f3afa-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="f3afa-104">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3afa-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="f3afa-105">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="f3afa-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="f3afa-106">Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="f3afa-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="f3afa-107">![LINQ-Sortierungsvorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="f3afa-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="f3afa-108">Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f3afa-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3afa-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="f3afa-109">Methods</span></span>  
  
|<span data-ttu-id="f3afa-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f3afa-110">Method Name</span></span>|<span data-ttu-id="f3afa-111">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="f3afa-111">Description</span></span>|<span data-ttu-id="f3afa-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f3afa-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="f3afa-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3afa-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="f3afa-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="f3afa-114">OrderBy</span></span>|<span data-ttu-id="f3afa-115">Sortiert Werte in aufsteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="f3afa-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f3afa-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="f3afa-116">OrderByDescending</span></span>|<span data-ttu-id="f3afa-117">Sortiert Werte in absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="f3afa-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f3afa-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="f3afa-118">ThenBy</span></span>|<span data-ttu-id="f3afa-119">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="f3afa-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f3afa-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="f3afa-120">ThenByDescending</span></span>|<span data-ttu-id="f3afa-121">Führt eine sekundäre Sortierung in absteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="f3afa-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="f3afa-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="f3afa-122">Reverse</span></span>|<span data-ttu-id="f3afa-123">Kehrt die Reihenfolge der Elemente in einer Auflistung um</span><span class="sxs-lookup"><span data-stu-id="f3afa-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="f3afa-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f3afa-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f3afa-125">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f3afa-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="f3afa-126">Primäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="f3afa-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="f3afa-127">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f3afa-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="f3afa-128">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f3afa-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="f3afa-129">Primäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f3afa-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="f3afa-130">Im nächsten Beispiel wird veranschaulicht, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f3afa-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="f3afa-131">Sekundäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="f3afa-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="f3afa-132">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f3afa-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="f3afa-133">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f3afa-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="f3afa-134">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f3afa-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="f3afa-135">Sekundäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f3afa-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="f3afa-136">Im nächsten Beispiel wird gezeigt, wie man die `orderby descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f3afa-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="f3afa-137">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="f3afa-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3afa-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3afa-138">See Also</span></span>

- <xref:System.Linq>  
- [<span data-ttu-id="f3afa-139">Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="f3afa-139">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
- [<span data-ttu-id="f3afa-140">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="f3afa-140">orderby clause</span></span>](../../../../csharp/language-reference/keywords/orderby-clause.md)  
- [<span data-ttu-id="f3afa-141">Gewusst wie: Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="f3afa-141">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
- [<span data-ttu-id="f3afa-142">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="f3afa-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
