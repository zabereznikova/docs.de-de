---
title: Filtern von Daten (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fa2d3b6c5b81f137ab3a81f9b18707bb2da91f6e
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="f2d6e-102">Filtern von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2d6e-102">Filtering Data (Visual Basic)</span></span>
<span data-ttu-id="f2d6e-103">Filtern bezeichnet der Vorgang, der Einschränkung des Resultsets, die nur die Elemente enthält, die eine angegebene Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="f2d6e-104">Es ist auch bekannt als Markierung.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="f2d6e-105">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Sequenz von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="f2d6e-106">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen "A" sein muss.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="f2d6e-107">![LINQ-Filtervorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="f2d6e-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="f2d6e-108">Die Standardabfrageoperator-Methoden die Durchführung der Auswahl werden im folgenden Abschnitt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2d6e-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="f2d6e-109">Methods</span></span>  
  
|<span data-ttu-id="f2d6e-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="f2d6e-110">Method Name</span></span>|<span data-ttu-id="f2d6e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2d6e-111">Description</span></span>|<span data-ttu-id="f2d6e-112">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f2d6e-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f2d6e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2d6e-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f2d6e-114">OfType</span><span class="sxs-lookup"><span data-stu-id="f2d6e-114">OfType</span></span>|<span data-ttu-id="f2d6e-115">Wählt Werte danach, ob Sie in einen angegebenen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="f2d6e-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-116">Not applicable.</span></span>|<span data-ttu-id="f2d6e-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f2d6e-117"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f2d6e-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f2d6e-118"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f2d6e-119">Where</span><span class="sxs-lookup"><span data-stu-id="f2d6e-119">Where</span></span>|<span data-ttu-id="f2d6e-120">Wählt Werte, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-120">Selects values that are based on a predicate function.</span></span>|`Where`|<span data-ttu-id="f2d6e-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f2d6e-121"><xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f2d6e-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f2d6e-122"><xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="f2d6e-123">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="f2d6e-123">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="f2d6e-124">Im folgenden Beispiel wird die `Where` diese Zeichenfolgen aus einem Array zu filtern, die eine bestimmte Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f2d6e-124">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>  
  
```vb  
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}  
  
Dim query = From word In words   
            Where word.Length = 3   
            Select word  
  
Dim sb As New System.Text.StringBuilder()  
For Each str As String In query  
    sb.AppendLine(str)  
Next  
  
' Display the results.  
MsgBox(sb.ToString())  
  
' This code produces the following output:  
  
' the  
' fox  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2d6e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d6e-125">See Also</span></span>  
 <span data-ttu-id="f2d6e-126"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f2d6e-126"><xref:System.Linq></span></span>   
<span data-ttu-id="f2d6e-127"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f2d6e-127"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="f2d6e-128"> [Wobei Klausel](../../../../visual-basic/language-reference/queries/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f2d6e-128"> [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md) </span></span>  
<span data-ttu-id="f2d6e-129"> [Gewusst wie: Filtern von Abfrageergebnissen](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f2d6e-129"> [How to: Filter Query Results](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md) </span></span>  
<span data-ttu-id="f2d6e-130"> [Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f2d6e-130"> [How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
<span data-ttu-id="f2d6e-131"> [Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="f2d6e-131"> [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
<span data-ttu-id="f2d6e-132"> [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f2d6e-132"> [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)</span></span>
