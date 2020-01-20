---
title: Untersuchen der Bereiche von Daten mithilfe von Indizes und Bereichen
description: In diesem fortgeschrittenen Tutorial erfahren Sie, wie Sie Daten mithilfe von Indizes und Bereichen untersuchen, um Segmente eines sequenziellen Datasets zu untersuchen.
ms.date: 09/20/2019
ms.technology: csharp-fundamentals
ms.custom: mvc
ms.openlocfilehash: 3d4c022ff8d6e7f260632e34d6f28277014c85c8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345621"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="32611-103">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="32611-103">Indices and ranges</span></span>

<span data-ttu-id="32611-104">Bereiche und Indizes bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="32611-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="32611-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="32611-105">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="32611-106">Verwenden Sie die Syntax für Bereiche in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="32611-106">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="32611-107">Lernen Sie die Entwurfsentscheidungen für Start und Ende jeder Sequenz kennen.</span><span class="sxs-lookup"><span data-stu-id="32611-107">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="32611-108">Lernen Sie Szenarien für die Typen <xref:System.Index> und <xref:System.Range> kennen.</span><span class="sxs-lookup"><span data-stu-id="32611-108">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="32611-109">Sprachunterstützung für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="32611-109">Language support for indices and ranges</span></span>

<span data-ttu-id="32611-110">Diese Sprachunterstützung basiert auf zwei neuen Typen und zwei neuen Operatoren:</span><span class="sxs-lookup"><span data-stu-id="32611-110">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="32611-111"><xref:System.Index?displayProperty=nameWithType>: Stellt einen Index in einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="32611-111"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="32611-112">Der Index vom Endeoperator `^`, der angibt, dass ein Index relativ zum Ende einer Sequenz ist.</span><span class="sxs-lookup"><span data-stu-id="32611-112">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="32611-113"><xref:System.Range?displayProperty=nameWithType>: Stellt einen Unterbereich einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="32611-113"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="32611-114">Der Bereichsoperator `..`, der den Beginn und das Ende eines Bereichs als seine Operanden angibt.</span><span class="sxs-lookup"><span data-stu-id="32611-114">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="32611-115">Beginnen wir mit den Regeln für Indizes.</span><span class="sxs-lookup"><span data-stu-id="32611-115">Let's start with the rules for indices.</span></span> <span data-ttu-id="32611-116">Betrachten Sie einen Array `sequence`.</span><span class="sxs-lookup"><span data-stu-id="32611-116">Consider an array `sequence`.</span></span> <span data-ttu-id="32611-117">Der `0`-Index entspricht `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="32611-117">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="32611-118">Der `^0`-Index entspricht `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="32611-118">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="32611-119">Beachten Sie, dass `sequence[^0]` genau wie `sequence[sequence.Length]` eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="32611-119">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="32611-120">Für eine beliebige Zahl `n` ist der Index `^n` identisch mit `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="32611-120">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="32611-121">Sie können das letzte Wort mit dem `^1`-Index abrufen.</span><span class="sxs-lookup"><span data-stu-id="32611-121">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="32611-122">Fügen Sie unter der Initialisierung folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="32611-122">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="32611-123">Ein Bereich gibt den *Beginn* und das *Ende* eines Bereichs an.</span><span class="sxs-lookup"><span data-stu-id="32611-123">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="32611-124">Bereiche sind exklusiv, d.h. das *Ende* ist nicht im Bereich enthalten.</span><span class="sxs-lookup"><span data-stu-id="32611-124">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="32611-125">Der Bereich `[0..^0]` stellt ebenso wie `[0..sequence.Length]` den gesamten Bereich dar.</span><span class="sxs-lookup"><span data-stu-id="32611-125">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="32611-126">Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“.</span><span class="sxs-lookup"><span data-stu-id="32611-126">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="32611-127">Er enthält `words[1]` bis `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="32611-127">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="32611-128">Das Element `words[4]` befindet sich nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="32611-128">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="32611-129">Fügen Sie derselben Methode den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="32611-129">Add the following code to the same method.</span></span> <span data-ttu-id="32611-130">Kopieren Sie ihn, und fügen Sie ihn unten in das interaktive Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="32611-130">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="32611-131">Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“.</span><span class="sxs-lookup"><span data-stu-id="32611-131">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="32611-132">Dazu gehören `words[^2]` und `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="32611-132">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="32611-133">Der Endindex `words[^0]` ist nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="32611-133">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="32611-134">Fügen Sie den folgenden Code auch hinzu:</span><span class="sxs-lookup"><span data-stu-id="32611-134">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="32611-135">Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:</span><span class="sxs-lookup"><span data-stu-id="32611-135">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="32611-136">Sie können Bereiche oder Indizes auch als Variablen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="32611-136">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="32611-137">Die Variable kann dann innerhalb der Zeichen `[` und `]` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="32611-137">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="32611-138">Das folgende Beispiel zeigt viele der Gründe für diese Auswahl.</span><span class="sxs-lookup"><span data-stu-id="32611-138">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="32611-139">Ändern Sie `x`, `y` und `z`, um verschiedene Kombinationen zu testen.</span><span class="sxs-lookup"><span data-stu-id="32611-139">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="32611-140">Verwenden Sie beim Experimentieren Werte, wo `x` kleiner ist als `y` und `y` kleiner als `z` für gültige Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="32611-140">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="32611-141">Fügen Sie den folgenden Code in einer neuen Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="32611-141">Add the following code in a new method.</span></span> <span data-ttu-id="32611-142">Probieren Sie verschiedene Kombinationen aus:</span><span class="sxs-lookup"><span data-stu-id="32611-142">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a><span data-ttu-id="32611-143">Typunterstützung für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="32611-143">Type support for indices and ranges</span></span>

<span data-ttu-id="32611-144">Indizes und Bereiche stellen eine klare, präzise Syntax für den Zugriff auf ein einzelnes Element oder einen Teilbereich von Elementen in einer Sequenz bereit.</span><span class="sxs-lookup"><span data-stu-id="32611-144">Indexes and ranges provide clear, concise syntax to access a single element or a sub-range of elements in a sequence.</span></span> <span data-ttu-id="32611-145">Ein Indexausdruck gibt in der Regel den Typ der Elemente einer Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="32611-145">An index expression typically returns the type of the elements of a sequence.</span></span> <span data-ttu-id="32611-146">Ein Bereichsausdruck gibt in der Regel den gleichen Sequenztyp wie die Quellsequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="32611-146">A range expression typically returns the same sequence type as the source sequence.</span></span>

<span data-ttu-id="32611-147">Wenn ein Typ einen [Indexer](../programming-guide/indexers/index.md) mit einem <xref:System.Index>- oder <xref:System.Range>-Parameter bereitstellt, unterstützt er explizit Indizes bzw. Bereiche.</span><span class="sxs-lookup"><span data-stu-id="32611-147">If a type provides an [indexer](../programming-guide/indexers/index.md) with an <xref:System.Index> or <xref:System.Range> parameter, it explicitly supports indices or ranges respectively.</span></span> <span data-ttu-id="32611-148">Wenn der Typ einen Indexer bereitstellt, der einen einzelnen <xref:System.Range>-Parameter annimmt, kann er einen anderen Sequenztyp zurückgeben, etwa <xref:System.Span%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="32611-148">When the type provides an indexer that takes a single <xref:System.Range> parameter, it may choose to return a different sequence type, such as <xref:System.Span%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="32611-149">Ein Typ ist **zählbar**, wenn er über eine Eigenschaft mit dem Namen `Length` oder `Count` mit einem zugreifbaren Getter und einem Rückgabetyp von `int` verfügt.</span><span class="sxs-lookup"><span data-stu-id="32611-149">A type is **countable** if it has a property named `Length` or `Count` with an accessible getter and a return type of `int`.</span></span> <span data-ttu-id="32611-150">Ein zählbarer Typ, der Indizes oder Bereiche nicht explizit unterstützt, kann implizite Unterstützung dafür bieten.</span><span class="sxs-lookup"><span data-stu-id="32611-150">A countable type that doesn't explicitly support indices or ranges may provide an implicit support for them.</span></span> <span data-ttu-id="32611-151">Weitere Informationen finden Sie in den Abschnitten [Implizite Indexunterstützung](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) und [Implizite Bereichsunterstützung](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) der [Featurevorschläge](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="32611-151">For more information, see the [Implicit Index support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) and [Implicit Range support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) sections of the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span> <span data-ttu-id="32611-152">Bereiche, die die implizite Bereichsunterstützung verwenden, geben denselben Sequenztyp wie die Quellsequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="32611-152">Ranges using implicit range support return the same sequence type as the source sequence.</span></span>

<span data-ttu-id="32611-153">Beispielsweise unterstützen die folgenden .NET-Typen Indizes und Bereiche: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601> und <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="32611-153">For example, the following .NET types support both indices and ranges: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601>, and <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="32611-154"><xref:System.Collections.Generic.List%601> unterstützt Indizes, jedoch keine Bereiche.</span><span class="sxs-lookup"><span data-stu-id="32611-154">The <xref:System.Collections.Generic.List%601> supports indices but doesn't support ranges.</span></span>

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="32611-155">Szenarien für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="32611-155">Scenarios for indices and ranges</span></span>

<span data-ttu-id="32611-156">Sie verwenden häufig Bereiche und Indizes, wenn Sie eine Analyse eines Teilbereichs einer vollständigen Sequenz ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="32611-156">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="32611-157">Aus der neuen Syntax lässt sich klarer herauslesen, welcher Teilbereich beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="32611-157">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="32611-158">Die lokale Funktion `MovingAverage` nimmt einen <xref:System.Range> als Argument entgegen.</span><span class="sxs-lookup"><span data-stu-id="32611-158">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="32611-159">Die Methode listet dann genau diesen Bereich bei der Berechnung von Minimum, Maximum und Durchschnitt auf.</span><span class="sxs-lookup"><span data-stu-id="32611-159">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="32611-160">Probieren Sie den folgenden Code in Ihrem Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="32611-160">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="32611-161">Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="32611-161">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
