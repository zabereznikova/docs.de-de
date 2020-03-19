---
title: Neuerungen in F- 4.5 - F-Leitfaden
description: Verschaffen Sie sich einen Überblick über die neuen Funktionen, die in F- 4.5 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186137"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="19645-103">Neuerungen in F- 4.5</span><span class="sxs-lookup"><span data-stu-id="19645-103">What's new in F# 4.5</span></span>

<span data-ttu-id="19645-104">F-4.5 fügt der Sprache F- 4.5 mehrere Verbesserungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="19645-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="19645-105">Viele dieser Funktionen wurden addiert, damit Sie effizienten Code in F- schreiben können, während gleichzeitig sichergestellt wird, dass dieser Code sicher ist.</span><span class="sxs-lookup"><span data-stu-id="19645-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="19645-106">Dies bedeutet, dass der Sprache einige Konzepte und eine erhebliche Menge an Compileranalysen hinzugefügt werden müssen, wenn diese Konstrukte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19645-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="19645-107">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="19645-107">Get started</span></span>

<span data-ttu-id="19645-108">Die F-4.5 ist in allen .NET Core-Verteilungen und Visual Studio-Tools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19645-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="19645-109">[Beginnen Sie mit f',](../get-started/index.md) um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="19645-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="19645-110">Span- und byref-ähnliche Konstruktionen</span><span class="sxs-lookup"><span data-stu-id="19645-110">Span and byref-like structs</span></span>

<span data-ttu-id="19645-111">Mit <xref:System.Span%601> dem in .NET Core eingeführten Typ können Sie Puffer im Arbeitsspeicher in einer stark typisierten Weise darstellen, die nun in F- beginnend mit F-4.5 zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="19645-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="19645-112">Das folgende Beispiel zeigt, wie Sie eine <xref:System.Span%601> Funktion wiederverwenden können, die auf einer mit unterschiedlichen Pufferdarstellungen arbeitet:</span><span class="sxs-lookup"><span data-stu-id="19645-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

<span data-ttu-id="19645-113">Ein wichtiger Aspekt dabei ist, dass Span und andere [byref-ähnliche Strukturen](../language-reference/structures.md#byreflike-structs) eine sehr starre statische Analyse haben, die vom Compiler durchgeführt wird und deren Verwendung auf eine Weise eingeschränkt wird, die Sie möglicherweise als unerwartet empfinden.</span><span class="sxs-lookup"><span data-stu-id="19645-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="19645-114">Dies ist der grundlegende Kompromiss zwischen Leistung, Ausdruckskraft und Sicherheit, der in F- 4.5 eingeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19645-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="19645-115">Überarbeitete byrefs</span><span class="sxs-lookup"><span data-stu-id="19645-115">Revamped byrefs</span></span>

<span data-ttu-id="19645-116">Vor f- 4.5 waren [Byrefs](../language-reference/byrefs.md) in F-Code für zahlreiche Anwendungen unsicher und unsolide.</span><span class="sxs-lookup"><span data-stu-id="19645-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="19645-117">Soundness-Probleme rund um Byrefs wurden in F-4.5 behandelt, und die gleiche statische Analyse für Span- und byref-ähnliche Strukturen wurde ebenfalls angewendet.</span><span class="sxs-lookup"><span data-stu-id="19645-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="19645-118">inref<'T> und outref<'T></span><span class="sxs-lookup"><span data-stu-id="19645-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="19645-119">Um den Begriff eines schreibgeschützten, schreibgeschützten und schreibgeschützten Zeigers darzustellen, `inref<'T>`führt `outref<'T>` F-4.5 die Typen ein, die schreibgeschützte bzw. schreibgeschützte Zeiger darstellen.</span><span class="sxs-lookup"><span data-stu-id="19645-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="19645-120">Jeder hat eine andere Semantik.</span><span class="sxs-lookup"><span data-stu-id="19645-120">Each have different semantics.</span></span> <span data-ttu-id="19645-121">Sie können z. B. nicht in eine `inref<'T>`: schreiben.</span><span class="sxs-lookup"><span data-stu-id="19645-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="19645-122">Standardmäßig leitet der Typrückschluss verwaltete Zeiger `inref<'T>` so ab, dass sie der unveränderlichen Natur des F-Codes entsprechen, es sei denn, etwas wurde bereits als veränderlich deklariert.</span><span class="sxs-lookup"><span data-stu-id="19645-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="19645-123">Um etwas beschreibbar zu machen, müssen Sie `mutable` einen Typ deklarieren, bevor Sie seine Adresse an eine Funktion oder einen Member übergeben, die ihn bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="19645-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="19645-124">Weitere Informationen finden Sie unter [Byrefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="19645-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="19645-125">Readonly-Strukturen</span><span class="sxs-lookup"><span data-stu-id="19645-125">Readonly structs</span></span>

<span data-ttu-id="19645-126">Beginnend mit F- 4.5 können Sie eine <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> Struktur mit:</span><span class="sxs-lookup"><span data-stu-id="19645-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="19645-127">Dadurch können Sie ein veränderbares Element in der Struktur nicht deklarieren und Metadaten aussenden, die es F- und C-Dateien ermöglichen, es als schreibgeschützt zu behandeln, wenn es von einer Assembly verbraucht wird.</span><span class="sxs-lookup"><span data-stu-id="19645-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="19645-128">Weitere Informationen finden Sie unter [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="19645-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="19645-129">Leere Zeiger</span><span class="sxs-lookup"><span data-stu-id="19645-129">Void pointers</span></span>

<span data-ttu-id="19645-130">Der `voidptr` Typ wird zu F-4.5 hinzugefügt, ebenso wie die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="19645-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="19645-131">`NativePtr.ofVoidPtr`, um einen Leerenzeiger in einen systemeigenen Intzeiger umzuwandeln</span><span class="sxs-lookup"><span data-stu-id="19645-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="19645-132">`NativePtr.toVoidPtr`, um einen systemeigenen Int-Zeiger in einen leeren Zeiger zu konvertieren</span><span class="sxs-lookup"><span data-stu-id="19645-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="19645-133">Dies ist hilfreich, wenn Sie mit einer systemeigenen Komponente zusammenarbeiten, die Leerzeiger verwendet.</span><span class="sxs-lookup"><span data-stu-id="19645-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="19645-134">dem `match!`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="19645-134">The `match!` keyword</span></span>

<span data-ttu-id="19645-135">Das `match!` Schlüsselwort verbessert den Musterabgleich, wenn es sich in einem Berechnungsausdruck befindet:</span><span class="sxs-lookup"><span data-stu-id="19645-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

<span data-ttu-id="19645-136">Auf diese Weise können Sie Code kürzen, der häufig Mischoptionen (oder andere Typen) mit Berechnungsausdrücken wie async umfasst.</span><span class="sxs-lookup"><span data-stu-id="19645-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="19645-137">Weitere Informationen finden Sie unter [Match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="19645-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="19645-138">Entspannte Upcasting-Anforderungen in Array-, Listen- und Sequenzausdrücken</span><span class="sxs-lookup"><span data-stu-id="19645-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="19645-139">Durch das Mischen von Typen, bei denen man von einem anderen innerhalb von Array-, Listen- `:>` und `upcast`Sequenzausdrücken erben kann, müssen Sie traditionell einen beliebigen abgeleiteten Typ auf den übergeordneten Typ mit oder umsetzen.</span><span class="sxs-lookup"><span data-stu-id="19645-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="19645-140">Dies ist nun entspannt, wie folgt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="19645-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="19645-141">Einzugsentspannung für Array- und Listenausdrücke</span><span class="sxs-lookup"><span data-stu-id="19645-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="19645-142">Vor F-4.5 mussten Sie Array- und Listenausdrücke übermäßig einrücken, wenn sie als Argumente an Methodenaufrufe übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="19645-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="19645-143">Dies ist nicht mehr erforderlich:</span><span class="sxs-lookup"><span data-stu-id="19645-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
