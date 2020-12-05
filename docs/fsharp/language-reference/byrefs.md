---
title: Byrefs
description: 'Erfahren Sie mehr über ByRef-und ByRef-ähnliche Typen in F #, die für die Low-Level-Programmierung verwendet werden.'
ms.date: 11/04/2019
ms.openlocfilehash: ff2c06d8940f7341d5d8b1d942be264bfac586c5
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740314"
---
# <a name="byrefs"></a><span data-ttu-id="1bfd0-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="1bfd0-103">Byrefs</span></span>

<span data-ttu-id="1bfd0-104">F # verfügt über zwei wichtige Featurebereiche, die sich auf den Raum von Low-Level-Programmierung befassen:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="1bfd0-105">Die `byref` / `inref` / `outref` Typen, bei denen es sich um verwaltete Zeiger handelt.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="1bfd0-106">Sie haben Einschränkungen hinsichtlich der Verwendung, sodass Sie kein Programm kompilieren können, das zur Laufzeit ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="1bfd0-107">Eine `byref` -like- [Struktur](structures.md) , bei der es sich um eine-Struktur mit ähnlicher Semantik und denselben Einschränkungen der Kompilierzeit wie handelt `byref<'T>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="1bfd0-108">Ein Beispiel hierfür ist <xref:System.Span%601> .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="1bfd0-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bfd0-109">Syntax</span></span>

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a><span data-ttu-id="1bfd0-110">ByRef, inref und der Wert</span><span class="sxs-lookup"><span data-stu-id="1bfd0-110">Byref, inref, and outref</span></span>

<span data-ttu-id="1bfd0-111">Es gibt drei Formen von `byref` :</span><span class="sxs-lookup"><span data-stu-id="1bfd0-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="1bfd0-112">`inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="1bfd0-113">`outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="1bfd0-114">`byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="1bfd0-115">Ein `byref<'T>` kann übermittelt werden, `inref<'T>` Wenn erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="1bfd0-116">Auf ähnliche Weise kann ein-Wert über `byref<'T>` mittelt werden, an dem `outref<'T>` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="1bfd0-117">Verwenden von ByRefs</span><span class="sxs-lookup"><span data-stu-id="1bfd0-117">Using byrefs</span></span>

<span data-ttu-id="1bfd0-118">Um einen zu verwenden `inref<'T>` , benötigen Sie einen Zeiger Wert mit `&` :</span><span class="sxs-lookup"><span data-stu-id="1bfd0-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn $"Now: %O{dt}"

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="1bfd0-119">Um mithilfe von oder in den Zeiger zu `outref<'T>` schreiben `byref<'T>` , müssen Sie auch den Wert, auf den Sie einen Zeiger ziehen, festlegen `mutable` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn $"Now: %O{dt}"
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="1bfd0-120">Wenn Sie nur den Zeiger schreiben, anstatt ihn zu lesen, sollten Sie `outref<'T>` anstelle von verwenden `byref<'T>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="1bfd0-121">Inref-Semantik</span><span class="sxs-lookup"><span data-stu-id="1bfd0-121">Inref semantics</span></span>

<span data-ttu-id="1bfd0-122">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="1bfd0-123">Semantisch bedeutet dies Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="1bfd0-124">Der Inhaber des `x` Zeigers darf ihn nur zum Lesen des Werts verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="1bfd0-125">Jeder Zeiger, der für die in geschachtelten `struct` Felder abgerufen `SomeStruct` wird, erhält den Typ `inref<_>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="1bfd0-126">Außerdem gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-126">The following is also true:</span></span>

* <span data-ttu-id="1bfd0-127">Es gibt keine Auswirkung darauf, dass andere Threads oder Aliase keinen Schreibzugriff auf haben `x` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="1bfd0-128">Es gibt keine Implikation, die `SomeStruct` aufgrund der Verwendung eines unveränderlich ist `x` `inref` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="1bfd0-129">Bei F #-Werttypen, die unveränderlich **sind** , wird der Zeiger jedoch als `this` abgeleitet `inref` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="1bfd0-130">Alle diese Regeln bedeuten, dass der Inhaber eines `inref` Zeigers den unmittelbaren Inhalt des Speichers, auf den verwiesen wird, möglicherweise nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="1bfd0-131">Leistungs Semantik</span><span class="sxs-lookup"><span data-stu-id="1bfd0-131">Outref semantics</span></span>

<span data-ttu-id="1bfd0-132">Der Zweck von `outref<'T>` ist, anzugeben, dass der Zeiger nur in geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="1bfd0-133">Unerwartet `outref<'T>` ermöglicht das Lesen des zugrunde liegenden Werts trotz des Namens.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="1bfd0-134">Dies dient zu Kompatibilitätszwecken.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-134">This is for compatibility purposes.</span></span> <span data-ttu-id="1bfd0-135">Semantisch `outref<'T>` ist nicht anders als `byref<'T>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="1bfd0-136">Interop mit C\#</span><span class="sxs-lookup"><span data-stu-id="1bfd0-136">Interop with C\#</span></span>

<span data-ttu-id="1bfd0-137">C# unterstützt `in ref` die `out ref` Schlüsselwörter und zusätzlich zu den `ref` Rückgabe von.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="1bfd0-138">In der folgenden Tabelle wird gezeigt, wie F # interpretiert, was c# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="1bfd0-139">C#-Konstrukt</span><span class="sxs-lookup"><span data-stu-id="1bfd0-139">C# construct</span></span>|<span data-ttu-id="1bfd0-140">F #-Infer</span><span class="sxs-lookup"><span data-stu-id="1bfd0-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="1bfd0-141">`ref` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1bfd0-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="1bfd0-142">`ref readonly` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1bfd0-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="1bfd0-143">`in ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="1bfd0-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="1bfd0-144">`out ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="1bfd0-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="1bfd0-145">In der folgenden Tabelle wird gezeigt, was F # ausgibt:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="1bfd0-146">F #-Konstrukt</span><span class="sxs-lookup"><span data-stu-id="1bfd0-146">F# construct</span></span>|<span data-ttu-id="1bfd0-147">Ausgegebenes Konstrukt</span><span class="sxs-lookup"><span data-stu-id="1bfd0-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="1bfd0-148">`inref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="1bfd0-148">`inref<'T>` argument</span></span>|<span data-ttu-id="1bfd0-149">`[In]` Attribut für Argument</span><span class="sxs-lookup"><span data-stu-id="1bfd0-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="1bfd0-150">`inref<'T>` hre</span><span class="sxs-lookup"><span data-stu-id="1bfd0-150">`inref<'T>` return</span></span>|<span data-ttu-id="1bfd0-151">`modreq` Attribut für Wert</span><span class="sxs-lookup"><span data-stu-id="1bfd0-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="1bfd0-152">`inref<'T>` im abstrakten Slot oder in der Implementierung</span><span class="sxs-lookup"><span data-stu-id="1bfd0-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="1bfd0-153">`modreq` on-Argument oder Return</span><span class="sxs-lookup"><span data-stu-id="1bfd0-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="1bfd0-154">`outref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="1bfd0-154">`outref<'T>` argument</span></span>|<span data-ttu-id="1bfd0-155">`[Out]` Attribut für Argument</span><span class="sxs-lookup"><span data-stu-id="1bfd0-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="1bfd0-156">Typrückschluss und Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="1bfd0-156">Type inference and overloading rules</span></span>

<span data-ttu-id="1bfd0-157">Ein- `inref<'T>` Typ wird durch den F #-Compiler in den folgenden Fällen abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="1bfd0-158">Ein .net-Parameter oder-Rückgabetyp mit einem- `IsReadOnly` Attribut.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="1bfd0-159">Der `this` Zeiger auf einen Strukturtyp ohne änderbare Felder.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="1bfd0-160">Die Adresse eines Speicher Orts, der von einem anderen Zeiger abgeleitet ist `inref<_>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="1bfd0-161">Wenn eine implizite Adresse eines verwendet wird `inref` , wird eine Überladung mit einem Argument vom Typ einer `SomeType` Überladung mit einem Argument vom Typ bevorzugt `inref<SomeType>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="1bfd0-162">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-162">For example:</span></span>

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

<span data-ttu-id="1bfd0-163">In beiden Fällen werden die Überladungen, die nehmen, `System.DateTime` aufgelöst und nicht die über Ladungen, die von übernommen werden `inref<System.DateTime>` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="1bfd0-164">ByRef-ähnliche Strukturen</span><span class="sxs-lookup"><span data-stu-id="1bfd0-164">Byref-like structs</span></span>

<span data-ttu-id="1bfd0-165">Zusätzlich zum `byref` / `inref` / `outref` Trio können Sie auch eigene Strukturen definieren, die der `byref` ähnlichen Semantik entsprechen können.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="1bfd0-166">Dies erfolgt mit dem- <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="1bfd0-167">`IsByRefLike` impliziert nicht `Struct` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="1bfd0-168">Beides muss für den Typ vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-168">Both must be present on the type.</span></span>

<span data-ttu-id="1bfd0-169">Eine " `byref` -like"-Struktur in F # ist ein Stapel gebundener Werttyp.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="1bfd0-170">Sie wird niemals dem verwalteten Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="1bfd0-171">Eine `byref` ähnliche Struktur eignet sich für Hochleistungs Programmierung, da Sie mit einer Reihe von starken Überprüfungen zur Lebensdauer und nicht Erfassung erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="1bfd0-172">Die Regeln lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-172">The rules are:</span></span>

* <span data-ttu-id="1bfd0-173">Sie können als Funktionsparameter, Methoden Parameter, lokale Variablen und Methoden Rückgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="1bfd0-174">Sie können keine statischen Member oder Instanzmember einer Klasse oder einer normalen Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="1bfd0-175">Sie können nicht von einem Closure-Konstrukt ( `async` Methoden oder Lambda-Ausdrücke) aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="1bfd0-176">Sie können nicht als generischer Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="1bfd0-177">Dieser letzte Punkt ist entscheidend für die Programmierung im F #-Pipeline Stil, ebenso wie `|>` eine generische Funktion, die die Eingabetypen parametrisiert.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="1bfd0-178">Diese Einschränkung kann für `|>` in Zukunft gelockert werden, da Sie Inline ist und keine Aufrufe von nicht Inline-generischen Funktionen im Textkörper vornimmt.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="1bfd0-179">Wenngleich diese Regeln die Nutzung stark einschränken, wird dies durchgeführt, um die Zusage von Hochleistungs Computing auf sichere Weise zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="1bfd0-180">ByRef-Rückgaben</span><span class="sxs-lookup"><span data-stu-id="1bfd0-180">Byref returns</span></span>

<span data-ttu-id="1bfd0-181">ByRef-Rückgabe von F #-Funktionen oder-Membern können erstellt und genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="1bfd0-182">Wenn eine `byref` -Rückgabe Methode genutzt wird, wird der Wert implizit dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="1bfd0-183">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn $"%d{squared}"
```

<span data-ttu-id="1bfd0-184">Um einen ByRef-Wert zurückzugeben, muss die Variable, die den Wert enthält, länger als der aktuelle Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="1bfd0-185">Verwenden Sie außerdem `&value` (wobei value eine Variable ist, die länger als der aktuelle Bereich ist), um ByRef zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="1bfd0-186">Verwenden Sie `&x` (wobei `x` der Wert ist), um die implizite Dereferenzierung zu vermeiden, z. b. das Übergeben eines Verweises über mehrere verkettete Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="1bfd0-187">Sie können auch eine Rückgabe direkt zuweisen `byref` .</span><span class="sxs-lookup"><span data-stu-id="1bfd0-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="1bfd0-188">Sehen Sie sich das folgende (hochgradig imperative) Programm an:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-188">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn $"Original sequence: %O{c}"

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn $"New sequence:      %O{c}"

    0 // return an integer exit code
```

<span data-ttu-id="1bfd0-189">Dies ist die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="1bfd0-190">Bereichs Definition für ByRefs</span><span class="sxs-lookup"><span data-stu-id="1bfd0-190">Scoping for byrefs</span></span>

<span data-ttu-id="1bfd0-191">`let`Der Verweis auf einen gebundenen Wert kann nicht den Bereich überschreiten, in dem er definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="1bfd0-192">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="1bfd0-192">For example, the following is disallowed:</span></span>

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

<span data-ttu-id="1bfd0-193">Dadurch wird verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen kompilieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="1bfd0-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
