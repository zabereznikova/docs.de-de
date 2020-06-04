---
title: Filtern von Daten
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: f7a1aa76dc93cc03952e55f5f8fc3f75176a3f9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383416"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="06379-102">Filtern von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06379-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="06379-103">Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="06379-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="06379-104">Es ist auch bekannt als Auswahl.</span><span class="sxs-lookup"><span data-stu-id="06379-104">It is also known as selection.</span></span>

<span data-ttu-id="06379-105">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="06379-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="06379-106">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.</span><span class="sxs-lookup"><span data-stu-id="06379-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![Abbildung zu einem LINQ-Filtervorgang](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="06379-108">Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="06379-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="06379-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="06379-109">Methods</span></span>

|<span data-ttu-id="06379-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="06379-110">Method Name</span></span>|<span data-ttu-id="06379-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06379-111">Description</span></span>|<span data-ttu-id="06379-112">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="06379-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="06379-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06379-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="06379-114">OfType</span><span class="sxs-lookup"><span data-stu-id="06379-114">OfType</span></span>|<span data-ttu-id="06379-115">Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="06379-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="06379-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="06379-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="06379-117">Hierbei gilt:</span><span class="sxs-lookup"><span data-stu-id="06379-117">Where</span></span>|<span data-ttu-id="06379-118">Wählt Werte aus, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="06379-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="06379-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="06379-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="06379-120">Im folgenden Beispiel wird der verwendet, um die Zeichen folgen `Where` , die eine bestimmte Länge aufweisen, aus einem Array zu filtern.</span><span class="sxs-lookup"><span data-stu-id="06379-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="06379-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06379-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="06379-122">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="06379-122">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="06379-123">WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="06379-123">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="06379-124">Gewusst wie: Filtern von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="06379-124">How to: Filter Query Results</span></span>](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="06379-125">Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06379-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="06379-126">Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06379-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="06379-127">Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06379-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
