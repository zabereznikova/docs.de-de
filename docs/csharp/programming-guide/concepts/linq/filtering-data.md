---
title: Filtern von Daten (C#)
description: Durch Filtern, auch als Auswahl bezeichnet, werden die Ergebnisse auf der Grundlage einer Bedingung eingeschränkt. Hier erfahren Sie mehr über die Methoden des Standardabfrageoperators in LINQ in C#, die Filter ausführen.
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: f9f6d691da73b566e5135f6692c87ba3a8978005
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103930"
---
# <a name="filtering-data-c"></a><span data-ttu-id="3aee0-104">Filtern von Daten (C#)</span><span class="sxs-lookup"><span data-stu-id="3aee0-104">Filtering Data (C#)</span></span>
<span data-ttu-id="3aee0-105">Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="3aee0-105">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="3aee0-106">Es ist auch bekannt als Auswahl.</span><span class="sxs-lookup"><span data-stu-id="3aee0-106">It is also known as selection.</span></span>  
  
 <span data-ttu-id="3aee0-107">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3aee0-107">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="3aee0-108">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.</span><span class="sxs-lookup"><span data-stu-id="3aee0-108">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>  
  
 ![Abbildung zu einem LINQ-Filtervorgang](./media/filtering-data/linq-filter-operation.png)  
  
 <span data-ttu-id="3aee0-110">Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3aee0-110">The standard query operator methods that perform selection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3aee0-111">Methoden</span><span class="sxs-lookup"><span data-stu-id="3aee0-111">Methods</span></span>  
  
|<span data-ttu-id="3aee0-112">Methodenname</span><span class="sxs-lookup"><span data-stu-id="3aee0-112">Method Name</span></span>|<span data-ttu-id="3aee0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aee0-113">Description</span></span>|<span data-ttu-id="3aee0-114">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="3aee0-114">C# Query Expression Syntax</span></span>|<span data-ttu-id="3aee0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aee0-115">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="3aee0-116">OfType</span><span class="sxs-lookup"><span data-stu-id="3aee0-116">OfType</span></span>|<span data-ttu-id="3aee0-117">Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="3aee0-117">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="3aee0-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="3aee0-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3aee0-119">Where</span><span class="sxs-lookup"><span data-stu-id="3aee0-119">Where</span></span>|<span data-ttu-id="3aee0-120">Wählt Werte aus, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="3aee0-120">Selects values that are based on a predicate function.</span></span>|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="3aee0-121">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="3aee0-121">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="3aee0-122">Im folgenden Beispiel wird die `where`-Klausel verwendet, um die Zeichenfolgen aus einem Array zu filtern, die eine bestimmte Länge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3aee0-122">The following example uses the `where` clause to filter from an array those strings that have a specific length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3aee0-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aee0-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3aee0-124">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="3aee0-124">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="3aee0-125">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="3aee0-125">where clause</span></span>](../../../language-reference/keywords/where-clause.md)
- [<span data-ttu-id="3aee0-126">Dynamisches Festlegen von Prädikatfiltern zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3aee0-126">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="3aee0-127">Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3aee0-127">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="3aee0-128">Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#)</span><span class="sxs-lookup"><span data-stu-id="3aee0-128">How to query for files with a specified attribute or name (C#)</span></span>](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="3aee0-129">Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3aee0-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
