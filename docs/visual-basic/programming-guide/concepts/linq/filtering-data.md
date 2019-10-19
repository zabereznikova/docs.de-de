---
title: Filtern von Daten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 27765247daa2155e685b1cd2bfccebb3216ca672
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582434"
---
# <a name="filtering-data-visual-basic"></a><span data-ttu-id="6efe4-102">Filtern von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6efe4-102">Filtering Data (Visual Basic)</span></span>

<span data-ttu-id="6efe4-103">Mit Filtern wird die Einschränkung des Resultsets auf Elemente bezeichnet, die eine bestimmte Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6efe4-103">Filtering refers to the operation of restricting the result set to contain only those elements that satisfy a specified condition.</span></span> <span data-ttu-id="6efe4-104">Es ist auch bekannt als Auswahl.</span><span class="sxs-lookup"><span data-stu-id="6efe4-104">It is also known as selection.</span></span>

<span data-ttu-id="6efe4-105">Die folgende Abbildung zeigt die Ergebnisse des Filterns einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6efe4-105">The following illustration shows the results of filtering a sequence of characters.</span></span> <span data-ttu-id="6efe4-106">Das Prädikat für den Filtervorgang gibt an, dass das Zeichen A sein muss.</span><span class="sxs-lookup"><span data-stu-id="6efe4-106">The predicate for the filtering operation specifies that the character must be 'A'.</span></span>

![Abbildung zu einem LINQ-Filtervorgang](./media/filtering-data/linq-filter-operation.png)

<span data-ttu-id="6efe4-108">Die Methoden des Standardabfrageoperators, die Auswahl ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6efe4-108">The standard query operator methods that perform selection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="6efe4-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="6efe4-109">Methods</span></span>

|<span data-ttu-id="6efe4-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="6efe4-110">Method Name</span></span>|<span data-ttu-id="6efe4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6efe4-111">Description</span></span>|<span data-ttu-id="6efe4-112">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="6efe4-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="6efe4-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6efe4-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="6efe4-114">OfType</span><span class="sxs-lookup"><span data-stu-id="6efe4-114">OfType</span></span>|<span data-ttu-id="6efe4-115">Wählt Werte aus, je nach ihrer Fähigkeit, in einen angegebenen Typ umgewandelt zu werden.</span><span class="sxs-lookup"><span data-stu-id="6efe4-115">Selects values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="6efe4-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="6efe4-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="6efe4-117">Where</span><span class="sxs-lookup"><span data-stu-id="6efe4-117">Where</span></span>|<span data-ttu-id="6efe4-118">Wählt Werte aus, die auf einer Prädikatfunktion basieren.</span><span class="sxs-lookup"><span data-stu-id="6efe4-118">Selects values that are based on a predicate function.</span></span>|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="6efe4-119">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="6efe4-119">Query Expression Syntax Example</span></span>

<span data-ttu-id="6efe4-120">Im folgenden Beispiel wird die-`Where` verwendet, um die Zeichen folgen, die eine bestimmte Länge aufweisen, nach einem Array zu filtern.</span><span class="sxs-lookup"><span data-stu-id="6efe4-120">The following example uses the `Where` to filter from an array those strings that have a specific length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6efe4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6efe4-121">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="6efe4-122">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="6efe4-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6efe4-123">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="6efe4-123">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="6efe4-124">Gewusst wie: Filtern von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="6efe4-124">How to: Filter Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [<span data-ttu-id="6efe4-125">Gewusst wie: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6efe4-125">How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [<span data-ttu-id="6efe4-126">Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6efe4-126">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [<span data-ttu-id="6efe4-127">Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6efe4-127">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
