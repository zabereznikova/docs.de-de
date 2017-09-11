---
title: Sortieren von Daten (C#)
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
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
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
ms.openlocfilehash: ff6ef81486074f2e738b62ce37e6cb58bff49bf8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="sorting-data-c"></a><span data-ttu-id="ad8be-102">Sortieren von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="ad8be-102">Sorting Data (C#)</span></span>
<span data-ttu-id="ad8be-103">Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert.</span><span class="sxs-lookup"><span data-stu-id="ad8be-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="ad8be-104">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad8be-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="ad8be-105">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="ad8be-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="ad8be-106">Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="ad8be-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="ad8be-107">![LINQ-Sortierungsvorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="ad8be-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="ad8be-108">Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ad8be-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad8be-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="ad8be-109">Methods</span></span>  
  
|<span data-ttu-id="ad8be-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="ad8be-110">Method Name</span></span>|<span data-ttu-id="ad8be-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad8be-111">Description</span></span>|<span data-ttu-id="ad8be-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ad8be-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="ad8be-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad8be-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="ad8be-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="ad8be-114">OrderBy</span></span>|<span data-ttu-id="ad8be-115">Sortiert Werte in aufsteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ad8be-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="ad8be-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="ad8be-116">OrderByDescending</span></span>|<span data-ttu-id="ad8be-117">Sortiert Werte in absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="ad8be-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="ad8be-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="ad8be-118">ThenBy</span></span>|<span data-ttu-id="ad8be-119">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="ad8be-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName>|  
|<span data-ttu-id="ad8be-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="ad8be-120">ThenByDescending</span></span>|<span data-ttu-id="ad8be-121">Führt eine sekundäre Sortierung in absteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="ad8be-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName>|  
|<span data-ttu-id="ad8be-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="ad8be-122">Reverse</span></span>|<span data-ttu-id="ad8be-123">Kehrt die Reihenfolge der Elemente in einer Auflistung um</span><span class="sxs-lookup"><span data-stu-id="ad8be-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="ad8be-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="ad8be-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ad8be-125">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ad8be-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="ad8be-126">Primäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="ad8be-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="ad8be-127">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ad8be-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="ad8be-128">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ad8be-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
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
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="ad8be-129">Primäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ad8be-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="ad8be-130">Im nächsten Beispiel wird veranschaulicht, wie man die `orderby``descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ad8be-130">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
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
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="ad8be-131">Sekundäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="ad8be-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="ad8be-132">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ad8be-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="ad8be-133">Im folgenden Beispiel wird veranschaulicht, wie man die `orderby`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ad8be-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="ad8be-134">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="ad8be-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
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
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="ad8be-135">Sekundäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="ad8be-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="ad8be-136">Im nächsten Beispiel wird gezeigt, wie man die `orderby``descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ad8be-136">The next example demonstrates how to use the `orderby``descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="ad8be-137">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="ad8be-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ad8be-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad8be-138">See Also</span></span>  
 <span data-ttu-id="ad8be-139"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="ad8be-139"><xref:System.Linq></span></span>   
 <span data-ttu-id="ad8be-140">[Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ad8be-140">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="ad8be-141">[orderby clause (orderby-Klausel)](../../../../csharp/language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ad8be-141">[orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md) </span></span>  
 <span data-ttu-id="ad8be-142">[Vorgehensweise: Sortieren der Ergebnisse einer Join-Klausel](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="ad8be-142">[How to: Order the Results of a Join Clause](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 [<span data-ttu-id="ad8be-143">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="ad8be-143">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

