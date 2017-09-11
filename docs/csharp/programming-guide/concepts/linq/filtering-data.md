---
title: Filtern von Daten (C#)
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
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: defa6716f677c44da5dd27cb64b3b1d140a65272
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="filtering-data-c"></a><span data-ttu-id="c8245-102">Filtern von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="c8245-102">Filtering Data (C#)</span></span>
<span data-ttu-id="c8245-103">Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c8245-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="c8245-104">Es ist auch bekannt als Auswahl.</span><span class="sxs-lookup"><span data-stu-id="c8245-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="c8245-105">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c8245-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="c8245-106">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.</span><span class="sxs-lookup"><span data-stu-id="c8245-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="c8245-107">![LINQ-Filtervorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="c8245-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="c8245-108">Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8245-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8245-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="c8245-109">Methods</span></span>  
  
|<span data-ttu-id="c8245-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="c8245-110">Method Name</span></span>|<span data-ttu-id="c8245-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8245-111">Description</span></span>|<span data-ttu-id="c8245-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="c8245-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="c8245-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8245-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="c8245-114">OfType</span><span class="sxs-lookup"><span data-stu-id="c8245-114">OfType</span></span>|<span data-ttu-id="c8245-115">Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="c8245-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="c8245-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="c8245-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|<span data-ttu-id="c8245-117">Where</span><span class="sxs-lookup"><span data-stu-id="c8245-117">Where</span></span>|<span data-ttu-id="c8245-118">Wählt Werte aus, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="c8245-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="c8245-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="c8245-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="c8245-120">Im folgenden Beispiel wird die `where`-Klausel verwendet, um die Zeichenfolgen aus einem Array zu filtern, die eine bestimmte Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c8245-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8245-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8245-121">See Also</span></span>  
 <span data-ttu-id="c8245-122"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="c8245-122"><xref:System.Linq></span></span>   
 <span data-ttu-id="c8245-123">[Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="c8245-123">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="c8245-124">[where-Klausel](../../../../csharp/language-reference/keywords/where-clause.md) </span><span class="sxs-lookup"><span data-stu-id="c8245-124">[where clause](../../../../csharp/language-reference/keywords/where-clause.md) </span></span>  
 <span data-ttu-id="c8245-125">[Vorgehensweise: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="c8245-125">[How to: Dynamically Specify Predicate Filters at Runtime](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span></span>  
 <span data-ttu-id="c8245-126">[How to: Query An Assembly's Metadata with Reflection (LINQ) (C#) (Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span><span class="sxs-lookup"><span data-stu-id="c8245-126">[How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md) </span></span>  
 <span data-ttu-id="c8245-127">[How to: Query for Files with a Specified Attribute or Name (C#) (Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span><span class="sxs-lookup"><span data-stu-id="c8245-127">[How to: Query for Files with a Specified Attribute or Name (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md) </span></span>  
 [<span data-ttu-id="c8245-128">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c8245-128">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

