---
title: Projektionsvorgänge
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: d7efb46ccfe3208ae6c58043a64c236171d0c147
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346630"
---
# <a name="projection-operations-visual-basic"></a><span data-ttu-id="402e2-102">Projection Operations (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="402e2-102">Projection Operations (Visual Basic)</span></span>

<span data-ttu-id="402e2-103">Projektion bezieht sich auf einen Vorgang, bei dem ein Objekt in eine neue Form transformiert wird, die häufig nur aus den Eigenschaften besteht, die anschließend verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="402e2-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="402e2-104">Mithilfe der Projektion können Sie einen neuen Typ erstellen, der aus den einzelnen Objekten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="402e2-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="402e2-105">Sie können eine Eigenschaft projizieren und eine mathematische Funktion für sie ausführen.</span><span class="sxs-lookup"><span data-stu-id="402e2-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="402e2-106">Sie können auch das ursprüngliche Objekt projizieren, ohne es zu ändern.</span><span class="sxs-lookup"><span data-stu-id="402e2-106">You can also project the original object without changing it.</span></span>

<span data-ttu-id="402e2-107">Die Methoden des Standardabfrageoperators, die Projektion ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="402e2-107">The standard query operator methods that perform projection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="402e2-108">Methoden</span><span class="sxs-lookup"><span data-stu-id="402e2-108">Methods</span></span>

|<span data-ttu-id="402e2-109">Methodenname</span><span class="sxs-lookup"><span data-stu-id="402e2-109">Method Name</span></span>|<span data-ttu-id="402e2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="402e2-110">Description</span></span>|<span data-ttu-id="402e2-111">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="402e2-111">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="402e2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="402e2-112">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="402e2-113">Auswählen</span><span class="sxs-lookup"><span data-stu-id="402e2-113">Select</span></span>|<span data-ttu-id="402e2-114">Projektwerte, die auf einer Transform-Funktion basieren.</span><span class="sxs-lookup"><span data-stu-id="402e2-114">Projects values that are based on a transform function.</span></span>|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|
|<span data-ttu-id="402e2-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="402e2-115">SelectMany</span></span>|<span data-ttu-id="402e2-116">Projiziert Sequenzen von Werten, die auf einer Transform-Funktion basieren, und fasst diese dann in eine Sequenz zusammen.</span><span class="sxs-lookup"><span data-stu-id="402e2-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="402e2-117">Mehrere `From`-Klauseln verwenden</span><span class="sxs-lookup"><span data-stu-id="402e2-117">Use multiple `From` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="402e2-118">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="402e2-118">Query Expression Syntax Examples</span></span>

### <a name="select"></a><span data-ttu-id="402e2-119">Auswählen</span><span class="sxs-lookup"><span data-stu-id="402e2-119">Select</span></span>

<span data-ttu-id="402e2-120">Im folgenden Beispiel wird die `Select`-Klausel verwendet, um den ersten Buchstaben jeder Zeichenfolge in einer Liste von Zeichenfolgen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="402e2-120">The following example uses the `Select` clause to project the first letter from each string in a list of strings.</span></span>

```vb
Dim words = New List(Of String) From {"an", "apple", "a", "day"}

Dim query = From word In words
            Select word.Substring(0, 1)

Dim sb As New System.Text.StringBuilder()
For Each letter As String In query
    sb.AppendLine(letter)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' a
' a
' a
' d
```

### <a name="selectmany"></a><span data-ttu-id="402e2-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="402e2-121">SelectMany</span></span>

<span data-ttu-id="402e2-122">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span><span class="sxs-lookup"><span data-stu-id="402e2-122">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span></span>

```vb
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}

Dim query = From phrase In phrases
            From word In phrase.Split(" "c)
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' an
' apple
' a
' day
' the
' quick
' brown
' fox
```

## <a name="select-versus-selectmany"></a><span data-ttu-id="402e2-123">Select im Vergleich zu SelectMany</span><span class="sxs-lookup"><span data-stu-id="402e2-123">Select versus SelectMany</span></span>

<span data-ttu-id="402e2-124">Die Arbeit von jeweils `Select()` und `SelectMany()` besteht darin, einen Ergebniswert (oder Werte) aus den Quellwerten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="402e2-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="402e2-125">`Select()` generiert einen Ergebniswert für jeden Quellwert.</span><span class="sxs-lookup"><span data-stu-id="402e2-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="402e2-126">Das Ergebnis ist daher eine Auflistung, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt.</span><span class="sxs-lookup"><span data-stu-id="402e2-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="402e2-127">Im Gegensatz dazu erzeugt `SelectMany()` ein einziges Gesamtergebnis, das verkettete untergeordnete Auflistungen aus jedem Quellwert enthält.</span><span class="sxs-lookup"><span data-stu-id="402e2-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="402e2-128">Die Transform-Funktion, die als Argument an `SelectMany()` übergeben wird, muss eine aufzählbare Sequenz von Werten für jeden Quellwert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="402e2-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="402e2-129">Diese aufzählbaren Sequenzen werden anschließend von `SelectMany()` zu einer großen Sequenz verkettet.</span><span class="sxs-lookup"><span data-stu-id="402e2-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>

<span data-ttu-id="402e2-130">Die folgenden zwei Abbildungen zeigen den konzeptionellen Unterschied zwischen den Aktionen der beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="402e2-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="402e2-131">In jedem Fall wird davon ausgegangen, dass die Auswahlfunktion (Transform) das Array von Blumen aus jedem Quellwert auswählt.</span><span class="sxs-lookup"><span data-stu-id="402e2-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>

<span data-ttu-id="402e2-132">Die Abbildung zeigt, wie `Select()` eine Auflistung zurückgibt, die über die gleiche Anzahl von Elementen wie die Quellauflistung verfügt.</span><span class="sxs-lookup"><span data-stu-id="402e2-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>

![Grafische Darstellung der Aktion Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)

<span data-ttu-id="402e2-134">Diese Abbildung zeigt, wie `SelectMany()` die Zwischenmodus-Sequenz von Arrays in einem Endergebniswert verkettet, der jeden Wert aus jedem Zwischenmodus-Array enthält.</span><span class="sxs-lookup"><span data-stu-id="402e2-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>

![Grafische Darstellung der Aktion SelectMany&#40;&#41;](./media/projection-operations/select-many-action-graphic.png )

### <a name="code-example"></a><span data-ttu-id="402e2-136">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="402e2-136">Code Example</span></span>

<span data-ttu-id="402e2-137">Im folgenden Beispiel wird das Verhalten von `Select()` und `SelectMany()` verglichen.</span><span class="sxs-lookup"><span data-stu-id="402e2-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="402e2-138">Der Code erstellt eine „Bouquet“ von Blumen, indem er die ersten beiden Elemente aus jeder Liste der Blumennamen in der Quellauflistung aufführt.</span><span class="sxs-lookup"><span data-stu-id="402e2-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="402e2-139">In diesem Beispiel ist der „einzelne Wert“, den die Transformationsfunktion <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> verwendet, selbst eine Auflistung von Werten.</span><span class="sxs-lookup"><span data-stu-id="402e2-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="402e2-140">Dies erfordert die zusätzliche `For Each`-Schleife, um jede Zeichenfolge in den einzelnen Untersequenzen aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="402e2-140">This requires the extra `For Each` loop in order to enumerate each string in each sub-sequence.</span></span>

```vb
Class Bouquet
    Public Flowers As List(Of String)
End Class

Sub SelectVsSelectMany()
    Dim bouquets = New List(Of Bouquet) From {
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}

    Dim output As New System.Text.StringBuilder

    ' Select()
    Dim query1 = bouquets.Select(Function(b) b.Flowers)

    output.AppendLine("Using Select():")
    For Each flowerList In query1
        For Each str As String In flowerList
            output.AppendLine(str)
        Next
    Next

    ' SelectMany()
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)

    output.AppendLine(vbCrLf & "Using SelectMany():")
    For Each str As String In query2
        output.AppendLine(str)
    Next

    ' Display the output
    MsgBox(output.ToString())

    ' This code produces the following output:
    '
    ' Using Select():
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

    ' Using SelectMany()
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

End Sub
```

## <a name="see-also"></a><span data-ttu-id="402e2-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="402e2-141">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="402e2-142">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="402e2-142">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="402e2-143">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="402e2-143">Select Clause</span></span>](../../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="402e2-144">Kombinieren von Daten mithilfe von Joins</span><span class="sxs-lookup"><span data-stu-id="402e2-144">How to: Combine Data with Joins</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)
- [<span data-ttu-id="402e2-145">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="402e2-145">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="402e2-146">Gewusst wie: Zurückgeben eines LINQ-Abfrageergebnisses als bestimmter Typ</span><span class="sxs-lookup"><span data-stu-id="402e2-146">How to: Return a LINQ Query Result as a Specific Type</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)
- [<span data-ttu-id="402e2-147">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="402e2-147">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
