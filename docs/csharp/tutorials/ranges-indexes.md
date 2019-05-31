---
title: Untersuchen der Bereiche von Daten mithilfe von Indizes und Bereichen
description: In diesem fortgeschrittenen Tutorial erfahren Sie, wie Sie Daten mithilfe von Indizes und Bereichen untersuchen, um Segmente eines sequenziellen Datasets zu untersuchen.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: 64fae4581e265d4f70b8356d5c651b4fdaca3fe9
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431490"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="92733-103">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="92733-103">Indices and ranges</span></span>

<span data-ttu-id="92733-104">Bereiche und Indizes bieten eine prägnante Syntax für den Zugriff auf einzelne Elemente oder Bereiche in <xref:System.Array>, <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="92733-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="92733-105">Diese Funktionen ermöglichen eine kürzere, klarere Syntax für den Zugriff auf einzelne Elemente oder Bereiche von Elementen in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="92733-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="92733-106">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="92733-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="92733-107">Verwenden Sie die Syntax für Bereiche in einer Sequenz.</span><span class="sxs-lookup"><span data-stu-id="92733-107">Use the syntax for ranges in a sequence.</span></span>
> * <span data-ttu-id="92733-108">Lernen Sie die Entwurfsentscheidungen für Start und Ende jeder Sequenz kennen.</span><span class="sxs-lookup"><span data-stu-id="92733-108">Understand the design decisions for the start and end of each sequence.</span></span>
> * <span data-ttu-id="92733-109">Lernen Sie Szenarien für die Typen <xref:System.Index> und <xref:System.Range> kennen.</span><span class="sxs-lookup"><span data-stu-id="92733-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="92733-110">Sprachunterstützung für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="92733-110">Language support for indices and ranges</span></span>

<span data-ttu-id="92733-111">Sie können mit Verwendung des `^`-Zeichens vor dem Index einen Index **vom Ende aus** angeben.</span><span class="sxs-lookup"><span data-stu-id="92733-111">You can specify an index **from the end** using the `^` character before the index.</span></span> <span data-ttu-id="92733-112">Die Indizierung vom Ende aus beginnt mit der Regel, dass `0..^0` den gesamten Bereich angibt.</span><span class="sxs-lookup"><span data-stu-id="92733-112">Indexing from the end starts from the rule that `0..^0` specifies the entire range.</span></span> <span data-ttu-id="92733-113">Starten Sie zum Auflisten eines vollständigen Arrays *beim ersten Element*, und fahren Sie fort bis *hinter das letzte Element*.</span><span class="sxs-lookup"><span data-stu-id="92733-113">To enumerate an entire array, you start *at the first element*, and continue until you are *past the last element*.</span></span> <span data-ttu-id="92733-114">Stellen Sie sich das Verhalten der `MoveNext`-Methode auf einem Enumerator vor: Sie gibt „false“ zurück, wenn die Enumeration das letzte Element passiert.</span><span class="sxs-lookup"><span data-stu-id="92733-114">Think of the behavior of the `MoveNext` method on an enumerator: it returns false when the enumeration passes the last element.</span></span> <span data-ttu-id="92733-115">Der Index `^0` bedeutet „das Ende“, `array[array.Length]`, oder der Index, der dem letzten Element folgt.</span><span class="sxs-lookup"><span data-stu-id="92733-115">The index `^0` means "the end", `array[array.Length]`, or the index that follows the last element.</span></span> <span data-ttu-id="92733-116">Sie kennen `array[2]`. Damit wird das Element „2 from the start“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="92733-116">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="92733-117">Jetzt bezeichnet `array[^2]` das Element „2 from the end“.</span><span class="sxs-lookup"><span data-stu-id="92733-117">Now, `array[^2]` means the element "2 from the end".</span></span> 

<span data-ttu-id="92733-118">Sie können einen **Bereich** mit dem **Bereichsoperator** angeben: `..`.</span><span class="sxs-lookup"><span data-stu-id="92733-118">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="92733-119">So gibt beispielsweise `0..^0` den gesamten Bereich des Arrays an: 0 vom Anfang bis zum Ende, aber nicht einschließlich 0 vom Ende.</span><span class="sxs-lookup"><span data-stu-id="92733-119">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="92733-120">Jeder der beiden Operanden kann „from the start“ oder „from the end“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="92733-120">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="92733-121">Darüber hinaus kann jeder der beiden Operanden weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="92733-121">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="92733-122">Die Standardeinstellungen sind `0` für den Startindex und `^0` für den Endindex.</span><span class="sxs-lookup"><span data-stu-id="92733-122">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

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

<span data-ttu-id="92733-123">Der Index jedes Elements verstärkt das Konzept von „from the start“ und „from the end“, und dass Bereiche das Ende des Bereichs ausschließen.</span><span class="sxs-lookup"><span data-stu-id="92733-123">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="92733-124">Der „start“ des gesamten Arrays ist das erste Element.</span><span class="sxs-lookup"><span data-stu-id="92733-124">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="92733-125">Das „end“ des gesamten Arrays liegt *hinter* dem letzten Element.</span><span class="sxs-lookup"><span data-stu-id="92733-125">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="92733-126">Sie können das letzte Wort mit dem `^1`-Index abrufen.</span><span class="sxs-lookup"><span data-stu-id="92733-126">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="92733-127">Fügen Sie unter der Initialisierung folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="92733-127">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="92733-128">Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“.</span><span class="sxs-lookup"><span data-stu-id="92733-128">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="92733-129">Er enthält `words[1]` bis `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="92733-129">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="92733-130">Das Element `words[4]` befindet sich nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="92733-130">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="92733-131">Fügen Sie derselben Methode den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="92733-131">Add the following code to the same method.</span></span> <span data-ttu-id="92733-132">Kopieren Sie ihn, und fügen Sie ihn unten in das interaktive Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="92733-132">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="92733-133">Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“.</span><span class="sxs-lookup"><span data-stu-id="92733-133">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="92733-134">Dazu gehören `words[^2]` und `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="92733-134">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="92733-135">Der Endindex `words[^0]` ist nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="92733-135">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="92733-136">Fügen Sie den folgenden Code auch hinzu:</span><span class="sxs-lookup"><span data-stu-id="92733-136">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="92733-137">Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:</span><span class="sxs-lookup"><span data-stu-id="92733-137">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="92733-138">Sie können Bereiche oder Indizes auch als Variablen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="92733-138">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="92733-139">Die Variable kann dann innerhalb der Zeichen `[` und `]` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="92733-139">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="92733-140">Die obigen Beispiele zeigen zwei Entwurfsentscheidungen, die eine ausführlichere Erläuterung erfordern:</span><span class="sxs-lookup"><span data-stu-id="92733-140">The previous examples show two design decisions that require more explanation:</span></span>

- <span data-ttu-id="92733-141">Bereiche sind *exklusiv*, d.h. das Element am letzten Index befindet sich nicht im Bereich.</span><span class="sxs-lookup"><span data-stu-id="92733-141">Ranges are *exclusive*, meaning the element at the last index isn't in the range.</span></span>
- <span data-ttu-id="92733-142">Der Index `^0` ist *das Ende* der Sammlung, nicht *das letzte Element* in der Sammlung.</span><span class="sxs-lookup"><span data-stu-id="92733-142">The index `^0` is *the end* of the collection, not *the last element* in the collection.</span></span>

<span data-ttu-id="92733-143">Das folgende Beispiel zeigt viele der Gründe für diese Auswahl.</span><span class="sxs-lookup"><span data-stu-id="92733-143">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="92733-144">Ändern Sie `x`, `y` und `z`, um verschiedene Kombinationen zu testen.</span><span class="sxs-lookup"><span data-stu-id="92733-144">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="92733-145">Verwenden Sie beim Experimentieren Werte, wo `x` kleiner ist als `y` und `y` kleiner als `z` für gültige Kombinationen.</span><span class="sxs-lookup"><span data-stu-id="92733-145">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="92733-146">Fügen Sie den folgenden Code in einer neuen Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="92733-146">Add the following code in a new method.</span></span> <span data-ttu-id="92733-147">Probieren Sie verschiedene Kombinationen aus:</span><span class="sxs-lookup"><span data-stu-id="92733-147">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="92733-148">Szenarien für Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="92733-148">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="92733-149">Sie verwenden häufig Bereiche und Indizes, wenn Sie eine Analyse eines Teilbereichs einer vollständigen Sequenz ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="92733-149">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="92733-150">Aus der neuen Syntax lässt sich klarer herauslesen, welcher Teilbereich beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="92733-150">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="92733-151">Die lokale Funktion `MovingAverage` nimmt einen <xref:System.Range> als Argument entgegen.</span><span class="sxs-lookup"><span data-stu-id="92733-151">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="92733-152">Die Methode listet dann genau diesen Bereich bei der Berechnung von Minimum, Maximum und Durchschnitt auf.</span><span class="sxs-lookup"><span data-stu-id="92733-152">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="92733-153">Probieren Sie den folgenden Code in Ihrem Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="92733-153">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="92733-154">Sie können den fertig gestellten Code aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="92733-154">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
