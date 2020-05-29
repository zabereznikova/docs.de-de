---
title: 'Neues in f # 4,5-f #-Handbuch'
description: 'Verschaffen Sie sich einen Überblick über die neuen Features, die in F # 4,5 verfügbar sind.'
ms.date: 11/27/2019
ms.openlocfilehash: 2c978c66a4bf231398508cbc1cbb8839228ea8e9
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202356"
---
# <a name="whats-new-in-f-45"></a><span data-ttu-id="0faee-103">Neues in F # 4,5</span><span class="sxs-lookup"><span data-stu-id="0faee-103">What's new in F# 4.5</span></span>

<span data-ttu-id="0faee-104">F # 4,5 fügt der Sprache f # mehrere Verbesserungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="0faee-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="0faee-105">Viele dieser Features wurden hinzugefügt, um Ihnen das Schreiben von effizientem Code in F # zu ermöglichen und gleichzeitig sicherzustellen, dass dieser Code sicher ist.</span><span class="sxs-lookup"><span data-stu-id="0faee-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="0faee-106">Dies bedeutet, dass Sie der Sprache einige Konzepte hinzufügen und bei der Verwendung dieser Konstrukte eine beträchtliche Menge an compileranalysen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0faee-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="0faee-107">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="0faee-107">Get started</span></span>

<span data-ttu-id="0faee-108">F # 4,5 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0faee-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="0faee-109">[Beginnen Sie mit F #](../get-started/index.md) , um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0faee-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="0faee-110">Span-und ByRef-ähnliche Strukturen</span><span class="sxs-lookup"><span data-stu-id="0faee-110">Span and byref-like structs</span></span>

<span data-ttu-id="0faee-111">Der <xref:System.Span%601> in .net Core eingeführte Typ ermöglicht es Ihnen, Puffer im Arbeitsspeicher in einer stark typisierten Weise darzustellen. Dies ist nun in f # ab f # 4,5 zulässig.</span><span class="sxs-lookup"><span data-stu-id="0faee-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="0faee-112">Im folgenden Beispiel wird gezeigt, wie Sie eine Funktion, die auf einer <xref:System.Span%601> mit unterschiedlichen Puffer Darstellungen ausgeführt wird, wieder verwenden können:</span><span class="sxs-lookup"><span data-stu-id="0faee-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="0faee-113">Ein wichtiger Aspekt hierbei ist, dass die Spanne und andere [ByRef-ähnliche Strukturen](../language-reference/structures.md#byreflike-structs) über eine sehr strenge statische Analyse verfügen, die vom Compiler durchgeführt wird und deren Verwendung auf eine Art und Weise einschränkt, die Sie möglicherweise unerwartet finden.</span><span class="sxs-lookup"><span data-stu-id="0faee-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="0faee-114">Dies ist der grundlegende Kompromiss zwischen Leistung, Ausdrucksfähigkeit und Sicherheit, der in F # 4,5 eingeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0faee-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="0faee-115">Überarbeitete ByRefs</span><span class="sxs-lookup"><span data-stu-id="0faee-115">Revamped byrefs</span></span>

<span data-ttu-id="0faee-116">Vor f # 4,5 waren [ByRefs](../language-reference/byrefs.md) in F # unsicher und unvernünftig für zahlreiche Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="0faee-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="0faee-117">Probleme mit der Leistung von ByRefs wurden in F # 4,5 behoben, und die gleiche statische Analyse für Span-und ByRef-ähnliche Strukturen wurde ebenfalls angewendet.</span><span class="sxs-lookup"><span data-stu-id="0faee-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="0faee-118">inref< 't> und nicht< 't></span><span class="sxs-lookup"><span data-stu-id="0faee-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="0faee-119">Um das Konzept eines schreibgeschützten, Lese geschützten und Lese-/Schreib-verwalteten Zeigers darzustellen, führt F # 4,5 die- `inref<'T>` ,-Typen ein, die `outref<'T>` schreibgeschützte bzw. schreibgeschützte Zeiger darstellen.</span><span class="sxs-lookup"><span data-stu-id="0faee-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="0faee-120">Jede hat eine andere Semantik.</span><span class="sxs-lookup"><span data-stu-id="0faee-120">Each have different semantics.</span></span> <span data-ttu-id="0faee-121">Beispielsweise können Sie nicht in einen schreiben `inref<'T>` :</span><span class="sxs-lookup"><span data-stu-id="0faee-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="0faee-122">Standardmäßig leitet der Typrückschluss verwaltete Zeiger so ab, `inref<'T>` dass Sie mit der unveränderlichen Natur von F #-Code übereinstimmen, es sei denn, etwas wurde bereits als änderbar deklariert.</span><span class="sxs-lookup"><span data-stu-id="0faee-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="0faee-123">Damit etwas beschreibbar ist, müssen Sie einen Typ deklarieren, `mutable` bevor Sie die Adresse an eine Funktion oder einen Member übergeben, der Sie bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="0faee-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="0faee-124">Weitere Informationen finden Sie unter [ByRefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="0faee-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="0faee-125">Schreibgeschützte Strukturen</span><span class="sxs-lookup"><span data-stu-id="0faee-125">Readonly structs</span></span>

<span data-ttu-id="0faee-126">Ab F # 4,5 können Sie eine Struktur mit kommentieren <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> :</span><span class="sxs-lookup"><span data-stu-id="0faee-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="0faee-127">Dies ermöglicht es Ihnen nicht, ein änderbares Element in der Struktur zu deklarieren, und gibt Metadaten aus, die F # und c# als schreibgeschützt behandeln können, wenn Sie von einer Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0faee-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="0faee-128">Weitere Informationen finden Sie unter schreibgeschützte [Strukturen](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="0faee-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="0faee-129">Void-Zeiger</span><span class="sxs-lookup"><span data-stu-id="0faee-129">Void pointers</span></span>

<span data-ttu-id="0faee-130">Der `voidptr` Typ wird F # 4,5 hinzugefügt, wie die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="0faee-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="0faee-131">`NativePtr.ofVoidPtr`So konvertieren Sie einen void-Zeiger in einen systemeigenen int-Zeiger</span><span class="sxs-lookup"><span data-stu-id="0faee-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="0faee-132">`NativePtr.toVoidPtr`So konvertieren Sie einen nativen int-Zeiger in einen void-Zeiger</span><span class="sxs-lookup"><span data-stu-id="0faee-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="0faee-133">Dies ist hilfreich, wenn Sie mit einer systemeigenen Komponente interagieren, von der void-Zeiger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0faee-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="0faee-134">dem `match!`-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="0faee-134">The `match!` keyword</span></span>

<span data-ttu-id="0faee-135">Das- `match!` Schlüsselwort erweitert den Musterabgleich, wenn es innerhalb eines Berechnungs Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="0faee-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="0faee-136">Dies ermöglicht es Ihnen, Code zu verkürzen, der häufig das Mischen von Optionen (oder anderen Typen) mit Berechnungs Ausdrücken wie "Async" einschließt.</span><span class="sxs-lookup"><span data-stu-id="0faee-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="0faee-137">Weitere Informationen finden Sie unter [Match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="0faee-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="0faee-138">Gelockerte upcastanforderungen in Array-, Listen-und Sequenz Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="0faee-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="0faee-139">Das Mischen von Typen, bei denen eine von einer anderen innerhalb von Array-, Listen-und Sequenz Ausdrücken erben kann, erforderte in der Regel, dass Sie einen abgeleiteten Typ in seinen übergeordneten Typ mit oder umgewandelt `:>` `upcast` .</span><span class="sxs-lookup"><span data-stu-id="0faee-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="0faee-140">Dies wird nun gelockert und wie folgt veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0faee-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="0faee-141">Einzug der Einzügen für Array-und Listen Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0faee-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="0faee-142">Vor F # 4,5 mussten Array-und Listen Ausdrücke übermäßig eingezogen werden, wenn Sie als Argumente an Methodenaufrufe übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="0faee-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="0faee-143">Dies ist nicht mehr erforderlich:</span><span class="sxs-lookup"><span data-stu-id="0faee-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
