---
title: Sortieren von Daten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1870d401ffdeeb2452ace1b74a8fb70e19c9b9ed
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="f4eb6-102">Sortieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4eb6-102">Sorting Data (Visual Basic)</span></span>
<span data-ttu-id="f4eb6-103">Bei einem Sortiervorgang sortiert die Elemente einer Sequenz basierend auf einem oder mehreren Attributen.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="f4eb6-104">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="f4eb6-105">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="f4eb6-106">Die folgende Abbildung zeigt die Ergebnisse einer Operation alphabetische Sortierung für eine Sequenz von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>  
  
 <span data-ttu-id="f4eb6-107">![LINQ-Sortierung Vorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span><span class="sxs-lookup"><span data-stu-id="f4eb6-107">![LINQ Sorting Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_ordering.png "LINQ_Ordering")</span></span>  
  
 <span data-ttu-id="f4eb6-108">Die Standardabfrageoperator-Methoden, die Daten zu sortieren, werden im folgenden Abschnitt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4eb6-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="f4eb6-109">Methods</span></span>  
  
|<span data-ttu-id="f4eb6-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f4eb6-110">Method Name</span></span>|<span data-ttu-id="f4eb6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4eb6-111">Description</span></span>|<span data-ttu-id="f4eb6-112">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f4eb6-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f4eb6-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4eb6-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f4eb6-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="f4eb6-114">OrderBy</span></span>|<span data-ttu-id="f4eb6-115">Werden Werte in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-115">Sorts values in ascending order.</span></span>|`Order By`|<span data-ttu-id="f4eb6-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-116"><xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f4eb6-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-117"><xref:System.Linq.Queryable.OrderBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f4eb6-118">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="f4eb6-118">OrderByDescending</span></span>|<span data-ttu-id="f4eb6-119">Werden Werte in absteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-119">Sorts values in descending order.</span></span>|`Order By … Descending`|<span data-ttu-id="f4eb6-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-120"><xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f4eb6-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-121"><xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f4eb6-122">ThenBy</span><span class="sxs-lookup"><span data-stu-id="f4eb6-122">ThenBy</span></span>|<span data-ttu-id="f4eb6-123">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-123">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<span data-ttu-id="f4eb6-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-124"><xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f4eb6-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-125"><xref:System.Linq.Queryable.ThenBy%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f4eb6-126">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="f4eb6-126">ThenByDescending</span></span>|<span data-ttu-id="f4eb6-127">Führt eine sekundäre Sortierung in absteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-127">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<span data-ttu-id="f4eb6-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-128"><xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f4eb6-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-129"><xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f4eb6-130">Reverse</span><span class="sxs-lookup"><span data-stu-id="f4eb6-130">Reverse</span></span>|<span data-ttu-id="f4eb6-131">Kehrt die Reihenfolge der Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-131">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="f4eb6-132">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-132">Not applicable.</span></span>|<span data-ttu-id="f4eb6-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-133"><xref:System.Linq.Enumerable.Reverse%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f4eb6-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f4eb6-134"><xref:System.Linq.Queryable.Reverse%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="f4eb6-135">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f4eb6-135">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="f4eb6-136">Beispiele von primärer Sortierung</span><span class="sxs-lookup"><span data-stu-id="f4eb6-136">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="f4eb6-137">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f4eb6-137">Primary Ascending Sort</span></span>  
 <span data-ttu-id="f4eb6-138">Im folgenden Beispiel wird veranschaulicht, wie die `Order By` -Klausel in einer LINQ-Abfrage, um die Zeichenfolgen in einem Array nach Zeichenfolgenlänge in aufsteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-138">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
' quick  
' brown  
' jumps  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="f4eb6-139">Primäre absteigende Sortierung an.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-139">Primary Descending Sort</span></span>  
 <span data-ttu-id="f4eb6-140">Im nächsten Beispiel wird veranschaulicht, wie die `Order By Descending` -Klausel in einer LINQ-Abfrage, um die Zeichenfolgen nach ihrem ersten Buchstaben in absteigender Reihenfolge sortieren.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-140">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' quick  
' jumps  
' fox  
' brown  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="f4eb6-141">Beispiele von sekundärer Sortierung</span><span class="sxs-lookup"><span data-stu-id="f4eb6-141">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="f4eb6-142">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f4eb6-142">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="f4eb6-143">Im folgenden Beispiel wird veranschaulicht, wie die `Order By` -Klausel in einer LINQ-Abfrage, um eine primäre und sekundäre Sortierung der Zeichenfolgen in einem Array auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-143">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="f4eb6-144">Die Zeichenfolgen werden primär der Länge nach und sekundär nach dem ersten Buchstaben der Zeichenfolge in aufsteigender Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-144">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1)   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' brown  
' jumps  
' quick  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="f4eb6-145">Sekundäre absteigende Sortierung an.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-145">Secondary Descending Sort</span></span>  
 <span data-ttu-id="f4eb6-146">Im nächsten Beispiel wird veranschaulicht, wie die `Order By Descending` -Klausel in einer LINQ-Abfrage, um eine primäre Sortierung in aufsteigender und eine sekundäre Sortierung in absteigender Reihenfolge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-146">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="f4eb6-147">Die Zeichenfolgen werden primär der Länge nach und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="f4eb6-147">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```vb  
Dim words = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim sortQuery = From word In words   
                Order By word.Length, word.Substring(0, 1) Descending   
                Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In sortQuery  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' fox  
' the  
' quick  
' jumps  
' brown  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4eb6-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4eb6-148">See Also</span></span>  
 <span data-ttu-id="f4eb6-149"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f4eb6-149"><xref:System.Linq></span></span>   
<span data-ttu-id="f4eb6-150"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f4eb6-150"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="f4eb6-151"> [Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f4eb6-151"> [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="f4eb6-152"> [Gewusst wie: Sortieren von Abfrageergebnissen](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f4eb6-152"> [How to: Sort Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="f4eb6-153"> [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f4eb6-153"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
