---
title: Untersuchen der Bereiche von Daten mithilfe von Indizes und Bereichen
description: In diesem fortgeschrittenen Tutorial erfahren Sie, wie Sie Daten mithilfe von Indizes und Bereichen untersuchen, um Segmente eines sequenziellen Datasets zu untersuchen.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 118d3c9ccad98ec02195c2b5e26a2ca203990adf
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557188"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="f01c2-103">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="f01c2-103">Indices and ranges</span></span>

<span data-ttu-id="f01c2-104">Bereiche und Indizes bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in <xref:System.Array>, <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="f01c2-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="f01c2-105">Diese Funktionen ermöglichen eine kürzere, klarere Syntax für den Zugriff auf einzelne Elemente oder Bereiche von Elementen in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="f01c2-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="f01c2-106">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="f01c2-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f01c2-107">Verwenden Sie die Syntax für Bereiche in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="f01c2-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="f01c2-108">Lernen Sie die Entwurfsentscheidungen für Start und Ende jeder Sequenz kennen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="f01c2-109">Lernen Sie Szenarien für die Typen <xref:System.Index> und <xref:System.Range> kennen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="f01c2-110">Sprachunterstützung für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="f01c2-110">Language support for indices and ranges</span></span>

<span data-ttu-id="f01c2-111">Diese Sprachunterstützung basiert auf zwei neuen Typen und zwei neuen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f01c2-111">This language support relies on two new types and two new operators.</span></span>
- <span data-ttu-id="f01c2-112"><xref:System.Index?displayProperty=nameWithType>: Stellt einen Index in einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="f01c2-112"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="f01c2-113">Der `^`-Operator, der angibt, dass ein Index relativ zum Ende einer Sequenz ist.</span><span class="sxs-lookup"><span data-stu-id="f01c2-113">The `^` operator, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="f01c2-114"><xref:System.Range?displayProperty=nameWithType>: Stellt einen Unterbereich einer Sequenz dar.</span><span class="sxs-lookup"><span data-stu-id="f01c2-114"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="f01c2-115">Der Bereichsoperator (`..`), die den Beginn und das Ende eines Bereichs als Operanden angibt.</span><span class="sxs-lookup"><span data-stu-id="f01c2-115">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="f01c2-116">Beginnen wir mit den Regeln für Indizes.</span><span class="sxs-lookup"><span data-stu-id="f01c2-116">Let's start with the rules for indices.</span></span> <span data-ttu-id="f01c2-117">Betrachten Sie einen Array `sequence`.</span><span class="sxs-lookup"><span data-stu-id="f01c2-117">Consider an array `sequence`.</span></span> <span data-ttu-id="f01c2-118">Der `0`-Index entspricht `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="f01c2-118">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="f01c2-119">Der `^0`-Index entspricht `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="f01c2-119">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="f01c2-120">Beachten Sie, dass `sequence[^0]` genau wie `sequence[sequence.Length]` eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="f01c2-120">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="f01c2-121">Für eine beliebige Zahl `n` ist der Index `^n` identisch mit `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="f01c2-121">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp-interactive
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

<span data-ttu-id="f01c2-122">Sie können das letzte Wort mit dem `^1`-Index abrufen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-122">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="f01c2-123">Fügen Sie unter der Initialisierung folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f01c2-123">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="f01c2-124">Ein Bereich gibt den *Beginn* und das *Ende* eines Bereichs an.</span><span class="sxs-lookup"><span data-stu-id="f01c2-124">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="f01c2-125">Bereiche sind exklusiv, d.h. das *Ende* ist nicht im Bereich enthalten.</span><span class="sxs-lookup"><span data-stu-id="f01c2-125">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="f01c2-126">Der Bereich `[0..^0]` stellt ebenso wie `[0..sequence.Length]` den gesamten Bereich dar.</span><span class="sxs-lookup"><span data-stu-id="f01c2-126">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="f01c2-127">Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“.</span><span class="sxs-lookup"><span data-stu-id="f01c2-127">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="f01c2-128">Er enthält `words[1]` bis `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="f01c2-128">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="f01c2-129">Das Element `words[4]` befindet sich nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="f01c2-129">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="f01c2-130">Fügen Sie derselben Methode den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="f01c2-130">Add the following code to the same method.</span></span> <span data-ttu-id="f01c2-131">Kopieren Sie ihn, und fügen Sie ihn unten in das interaktive Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="f01c2-131">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="f01c2-132">Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“.</span><span class="sxs-lookup"><span data-stu-id="f01c2-132">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="f01c2-133">Dazu gehören `words[^2]` und `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="f01c2-133">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="f01c2-134">Der Endindex `words[^0]` ist nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f01c2-134">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="f01c2-135">Fügen Sie den folgenden Code auch hinzu:</span><span class="sxs-lookup"><span data-stu-id="f01c2-135">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="f01c2-136">Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:</span><span class="sxs-lookup"><span data-stu-id="f01c2-136">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="f01c2-137">Sie können Bereiche oder Indizes auch als Variablen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f01c2-137">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="f01c2-138">Die Variable kann dann innerhalb der Zeichen `[` und `]` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f01c2-138">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="f01c2-139">Das folgende Beispiel zeigt viele der Gründe für diese Auswahl.</span><span class="sxs-lookup"><span data-stu-id="f01c2-139">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="f01c2-140">Ändern Sie `x`, `y` und `z`, um verschiedene Kombinationen zu testen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-140">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="f01c2-141">Verwenden Sie beim Experimentieren Werte, wo `x` kleiner ist als `y` und `y` kleiner als `z` für gültige Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-141">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="f01c2-142">Fügen Sie den folgenden Code in einer neuen Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="f01c2-142">Add the following code in a new method.</span></span> <span data-ttu-id="f01c2-143">Probieren Sie verschiedene Kombinationen aus:</span><span class="sxs-lookup"><span data-stu-id="f01c2-143">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="f01c2-144">Szenarien für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="f01c2-144">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="f01c2-145">Sie verwenden häufig Bereiche und Indizes, wenn Sie eine Analyse eines Teilbereichs einer vollständigen Sequenz ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="f01c2-145">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="f01c2-146">Aus der neuen Syntax lässt sich klarer herauslesen, welcher Teilbereich beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="f01c2-146">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="f01c2-147">Die lokale Funktion `MovingAverage` nimmt einen <xref:System.Range> als Argument entgegen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-147">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="f01c2-148">Die Methode listet dann genau diesen Bereich bei der Berechnung von Minimum, Maximum und Durchschnitt auf.</span><span class="sxs-lookup"><span data-stu-id="f01c2-148">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="f01c2-149">Probieren Sie den folgenden Code in Ihrem Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="f01c2-149">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="f01c2-150">Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f01c2-150">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
