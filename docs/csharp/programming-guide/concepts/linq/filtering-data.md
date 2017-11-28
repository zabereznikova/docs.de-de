---
title: Filtern von Daten (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 77a68d5fa0fa606a7d164adf187c8aa0027170bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="filtering-data-c"></a><span data-ttu-id="5389a-102">Filtern von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="5389a-102">Filtering Data (C#)</span></span>
<span data-ttu-id="5389a-103">Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5389a-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="5389a-104">Es ist auch bekannt als Auswahl.</span><span class="sxs-lookup"><span data-stu-id="5389a-104">It is also known as selection.</span></span>  
  
 <span data-ttu-id="5389a-105">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5389a-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="5389a-106">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.</span><span class="sxs-lookup"><span data-stu-id="5389a-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 <span data-ttu-id="5389a-107">![LINQ-Filtervorgang](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span><span class="sxs-lookup"><span data-stu-id="5389a-107">![LINQ Filtering Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")</span></span>  
  
 <span data-ttu-id="5389a-108">Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5389a-108">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5389a-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="5389a-109">Methods</span></span>  
  
|<span data-ttu-id="5389a-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="5389a-110">Method Name</span></span>|<span data-ttu-id="5389a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5389a-111">Description</span></span>|<span data-ttu-id="5389a-112">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="5389a-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="5389a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5389a-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="5389a-114">OfType</span><span class="sxs-lookup"><span data-stu-id="5389a-114">OfType</span></span>|<span data-ttu-id="5389a-115">Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="5389a-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="5389a-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="5389a-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="5389a-117">Where</span><span class="sxs-lookup"><span data-stu-id="5389a-117">Where</span></span>|<span data-ttu-id="5389a-118">Wählt Werte aus, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="5389a-118">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="5389a-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="5389a-119">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="5389a-120">Im folgenden Beispiel wird die `where`-Klausel verwendet, um die Zeichenfolgen aus einem Array zu filtern, die eine bestimmte Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5389a-120">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5389a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5389a-121">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="5389a-122">Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="5389a-122">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="5389a-123">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="5389a-123">where clause</span></span>](../../../../csharp/language-reference/keywords/where-clause.md)  
 [<span data-ttu-id="5389a-124">Gewusst wie: Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5389a-124">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)  
 [<span data-ttu-id="5389a-125">Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5389a-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 [<span data-ttu-id="5389a-126">How to: Query for Files with a Specified Attribute or Name (C#) (Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#))</span><span class="sxs-lookup"><span data-stu-id="5389a-126">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 [<span data-ttu-id="5389a-127">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5389a-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
