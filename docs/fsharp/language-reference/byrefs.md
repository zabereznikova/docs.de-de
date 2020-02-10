---
title: Byrefs
description: Informationen Sie zu Byref und Byref-ähnlichen Typen in F#, die für die Low-Level-Programmierung verwendet werden.
ms.date: 11/04/2019
ms.openlocfilehash: 2d98d325dc4ad26548fb2cc6aa5b872e152ee0a8
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092787"
---
# <a name="byrefs"></a><span data-ttu-id="e76cf-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="e76cf-103">Byrefs</span></span>

<span data-ttu-id="e76cf-104">F#verfügt über zwei wichtige Featurebereiche, die sich auf den Raum der Low-Level-Programmierung befassen:</span><span class="sxs-lookup"><span data-stu-id="e76cf-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="e76cf-105">Die `byref`/`inref`/`outref` Typen, bei denen es sich um verwaltete Zeiger handelt.</span><span class="sxs-lookup"><span data-stu-id="e76cf-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="e76cf-106">Sie haben Einschränkungen hinsichtlich der Verwendung, sodass Sie kein Programm kompilieren können, das zur Laufzeit ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="e76cf-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="e76cf-107">Eine `byref`ähnliche Struktur, bei der es sich um eine [Struktur](structures.md) mit ähnlicher Semantik und denselben Kompilierzeit Beschränkungen wie `byref<'T>`handelt.</span><span class="sxs-lookup"><span data-stu-id="e76cf-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="e76cf-108">Ein Beispiel hierfür ist <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="e76cf-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="e76cf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e76cf-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="e76cf-110">ByRef, inref und der Wert</span><span class="sxs-lookup"><span data-stu-id="e76cf-110">Byref, inref, and outref</span></span>

<span data-ttu-id="e76cf-111">Es gibt drei Arten von `byref`:</span><span class="sxs-lookup"><span data-stu-id="e76cf-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="e76cf-112">`inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="e76cf-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="e76cf-113">`outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="e76cf-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="e76cf-114">`byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="e76cf-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="e76cf-115">Eine `byref<'T>` kann an die Stelle, an der ein `inref<'T>` erwartet wird</span><span class="sxs-lookup"><span data-stu-id="e76cf-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="e76cf-116">Auf ähnliche Weise kann eine `byref<'T>` an die Stelle, an der ein `outref<'T>` erwartet wird</span><span class="sxs-lookup"><span data-stu-id="e76cf-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="e76cf-117">Verwenden von ByRefs</span><span class="sxs-lookup"><span data-stu-id="e76cf-117">Using byrefs</span></span>

<span data-ttu-id="e76cf-118">Um einen `inref<'T>`zu verwenden, müssen Sie einen Zeiger Wert mit `&`erhalten:</span><span class="sxs-lookup"><span data-stu-id="e76cf-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="e76cf-119">Wenn Sie mit einem `outref<'T>` oder `byref<'T>`in den Zeiger schreiben möchten, müssen Sie auch den Wert, auf den Sie einen Zeiger ziehen, auf `mutable`festlegen.</span><span class="sxs-lookup"><span data-stu-id="e76cf-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="e76cf-120">Wenn Sie nur den Zeiger schreiben, anstatt ihn zu lesen, sollten Sie die Verwendung von `outref<'T>` anstelle von `byref<'T>`in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="e76cf-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="e76cf-121">Inref-Semantik</span><span class="sxs-lookup"><span data-stu-id="e76cf-121">Inref semantics</span></span>

<span data-ttu-id="e76cf-122">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e76cf-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="e76cf-123">Semantisch bedeutet dies Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e76cf-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="e76cf-124">Der Besitzer des `x` Zeigers darf ihn nur zum Lesen des Werts verwenden.</span><span class="sxs-lookup"><span data-stu-id="e76cf-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="e76cf-125">Jeder Zeiger, der `struct` in `SomeStruct` geschachtelten Feldern abgerufen wird, erhält den Typ `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="e76cf-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="e76cf-126">Außerdem gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e76cf-126">The following is also true:</span></span>

* <span data-ttu-id="e76cf-127">Es gibt keine Auswirkung darauf, dass andere Threads oder Aliase keinen Schreibzugriff auf `x`haben.</span><span class="sxs-lookup"><span data-stu-id="e76cf-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="e76cf-128">Es gibt keine Auswirkung darauf, dass `SomeStruct` aufgrund `x` einer `inref`unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e76cf-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="e76cf-129">Bei F# Werttypen, die unveränderlich **sind** , wird der `this` Zeiger als `inref`abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e76cf-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="e76cf-130">Alle diese Regeln bedeuten, dass der Besitzer eines `inref` Zeigers den unmittelbaren Inhalt des Speichers, auf den verwiesen wird, möglicherweise nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="e76cf-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="e76cf-131">Leistungs Semantik</span><span class="sxs-lookup"><span data-stu-id="e76cf-131">Outref semantics</span></span>

<span data-ttu-id="e76cf-132">Der Zweck `outref<'T>` ist, anzugeben, dass der Zeiger nur in den Zeiger geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e76cf-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="e76cf-133">Unerwartet, `outref<'T>` das Lesen des zugrunde liegenden Werts trotz seines Namens zulässt.</span><span class="sxs-lookup"><span data-stu-id="e76cf-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="e76cf-134">Dies dient zu Kompatibilitätszwecken.</span><span class="sxs-lookup"><span data-stu-id="e76cf-134">This is for compatibility purposes.</span></span> <span data-ttu-id="e76cf-135">`outref<'T>` unterscheidet sich semantisch von `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="e76cf-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="e76cf-136">Interop mit C-\#</span><span class="sxs-lookup"><span data-stu-id="e76cf-136">Interop with C\#</span></span>

<span data-ttu-id="e76cf-137">C#unterstützt die Schlüsselwörter `in ref` und `out ref` zusätzlich zu `ref`-Rückgabe.</span><span class="sxs-lookup"><span data-stu-id="e76cf-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="e76cf-138">Die folgende Tabelle zeigt, wie F# interpretiert wie c# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="e76cf-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="e76cf-139">C#Erstellen</span><span class="sxs-lookup"><span data-stu-id="e76cf-139">C# construct</span></span>|<span data-ttu-id="e76cf-140">F#leitet</span><span class="sxs-lookup"><span data-stu-id="e76cf-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="e76cf-141">`ref` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e76cf-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="e76cf-142">`ref readonly` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e76cf-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="e76cf-143">`in ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="e76cf-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="e76cf-144">`out ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="e76cf-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="e76cf-145">Die folgende Tabelle zeigt, was F# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="e76cf-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="e76cf-146">F#Erstellen</span><span class="sxs-lookup"><span data-stu-id="e76cf-146">F# construct</span></span>|<span data-ttu-id="e76cf-147">Ausgegebenes Konstrukt</span><span class="sxs-lookup"><span data-stu-id="e76cf-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="e76cf-148">`inref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="e76cf-148">`inref<'T>` argument</span></span>|<span data-ttu-id="e76cf-149">`[In]`-Attribut für Argument</span><span class="sxs-lookup"><span data-stu-id="e76cf-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="e76cf-150">`inref<'T>` Rückgabe</span><span class="sxs-lookup"><span data-stu-id="e76cf-150">`inref<'T>` return</span></span>|<span data-ttu-id="e76cf-151">`modreq` Attribut für Wert</span><span class="sxs-lookup"><span data-stu-id="e76cf-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="e76cf-152">`inref<'T>` im abstrakten Slot oder in der Implementierung</span><span class="sxs-lookup"><span data-stu-id="e76cf-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="e76cf-153">`modreq` on-Argument oder Rückgabe</span><span class="sxs-lookup"><span data-stu-id="e76cf-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="e76cf-154">`outref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="e76cf-154">`outref<'T>` argument</span></span>|<span data-ttu-id="e76cf-155">`[Out]`-Attribut für Argument</span><span class="sxs-lookup"><span data-stu-id="e76cf-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="e76cf-156">Typrückschluss und Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="e76cf-156">Type inference and overloading rules</span></span>

<span data-ttu-id="e76cf-157">Ein `inref<'T>` Typ wird vom F# Compiler in den folgenden Fällen abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="e76cf-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="e76cf-158">Ein .net-Parameter oder-Rückgabetyp, der über ein `IsReadOnly` Attribut verfügt.</span><span class="sxs-lookup"><span data-stu-id="e76cf-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="e76cf-159">Der `this` Zeiger auf einen Strukturtyp ohne änderbare Felder.</span><span class="sxs-lookup"><span data-stu-id="e76cf-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="e76cf-160">Die Adresse eines Speicher Orts, der von einem anderen `inref<_>` Zeiger abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="e76cf-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="e76cf-161">Wenn eine implizite Adresse eines `inref` übernommen wird, wird eine Überladung mit einem Argument vom Typ `SomeType` einer Überladung mit einem Argument vom Typ `inref<SomeType>`bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="e76cf-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="e76cf-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e76cf-162">For example:</span></span>

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

<span data-ttu-id="e76cf-163">In beiden Fällen werden die über Ladungen, die `System.DateTime` Unternehmen, aufgelöst, anstatt die über Ladungen `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="e76cf-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="e76cf-164">ByRef-ähnliche Strukturen</span><span class="sxs-lookup"><span data-stu-id="e76cf-164">Byref-like structs</span></span>

<span data-ttu-id="e76cf-165">Zusätzlich zum `byref`/`inref`/`outref` Trio können Sie eigene Strukturen definieren, die `byref`ähnlichen Semantik entsprechen können.</span><span class="sxs-lookup"><span data-stu-id="e76cf-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="e76cf-166">Dies erfolgt mit dem <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>-Attribut:</span><span class="sxs-lookup"><span data-stu-id="e76cf-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="e76cf-167">`IsByRefLike` impliziert keine `Struct`.</span><span class="sxs-lookup"><span data-stu-id="e76cf-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="e76cf-168">Beides muss für den Typ vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="e76cf-168">Both must be present on the type.</span></span>

<span data-ttu-id="e76cf-169">Eine "`byref`-like"-Struktur F# in ist ein Stapel gebundener Werttyp.</span><span class="sxs-lookup"><span data-stu-id="e76cf-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="e76cf-170">Sie wird niemals dem verwalteten Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e76cf-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="e76cf-171">Eine `byref`ähnliche Struktur eignet sich für die Hochleistungs Programmierung, da Sie mit einer Reihe von leistungsstarken Überprüfungen zur Lebensdauer und nicht Erfassung erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="e76cf-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="e76cf-172">Die Regeln lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e76cf-172">The rules are:</span></span>

* <span data-ttu-id="e76cf-173">Sie können als Funktionsparameter, Methoden Parameter, lokale Variablen und Methoden Rückgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e76cf-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="e76cf-174">Sie können keine statischen Member oder Instanzmember einer Klasse oder einer normalen Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="e76cf-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="e76cf-175">Sie können nicht von einem Closure-Konstrukt (`async`-Methoden oder Lambda-Ausdrücken) aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="e76cf-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="e76cf-176">Sie können nicht als generischer Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e76cf-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="e76cf-177">Dieser letzte Punkt ist entscheidend für F# die Programmierung im Pipeline Stil, da `|>` eine generische Funktion ist, die seine Eingabetypen parametrisiert.</span><span class="sxs-lookup"><span data-stu-id="e76cf-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="e76cf-178">Diese Einschränkung kann für `|>` in der Zukunft gelockert werden, da Sie Inline ist und keine Aufrufe von nicht Inline-generischen Funktionen im Textkörper vornimmt.</span><span class="sxs-lookup"><span data-stu-id="e76cf-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="e76cf-179">Wenngleich diese Regeln die Nutzung stark einschränken, wird dies durchgeführt, um die Zusage von Hochleistungs Computing auf sichere Weise zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e76cf-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="e76cf-180">ByRef-Rückgaben</span><span class="sxs-lookup"><span data-stu-id="e76cf-180">Byref returns</span></span>

<span data-ttu-id="e76cf-181">ByRef-Rückgaben von F#-Funktionen oder Elemente erstellt und verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e76cf-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="e76cf-182">Bei der Verwendung einer `byref`zurück gebenden Methode wird der Wert implizit dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="e76cf-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="e76cf-183">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e76cf-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) = 
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="e76cf-184">Um einen ByRef-Wert zurückzugeben, muss die Variable, die den Wert enthält, länger als der aktuelle Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="e76cf-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="e76cf-185">Verwenden Sie zum Zurückgeben von ByRef `&value` (wobei value eine Variable ist, die länger als der aktuelle Bereich ist).</span><span class="sxs-lookup"><span data-stu-id="e76cf-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="e76cf-186">Um die implizite Dereferenzierung zu vermeiden, z. b. einen Verweis über mehrere verkettete Aufrufe zu übergeben, verwenden Sie `&x` (wobei `x` der Wert ist).</span><span class="sxs-lookup"><span data-stu-id="e76cf-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="e76cf-187">Sie können einem Rückgabe `byref`auch direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e76cf-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="e76cf-188">Sehen Sie sich das folgende (hochgradig imperative) Programm an:</span><span class="sxs-lookup"><span data-stu-id="e76cf-188">Consider the following (highly imperative) program:</span></span>

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
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="e76cf-189">Dies ist die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e76cf-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="e76cf-190">Bereichs Definition für ByRefs</span><span class="sxs-lookup"><span data-stu-id="e76cf-190">Scoping for byrefs</span></span>

<span data-ttu-id="e76cf-191">Ein `let`gebundener Wert kann nicht den Bereich überschreiten, in dem er definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e76cf-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="e76cf-192">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="e76cf-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="e76cf-193">Dadurch wird verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen kompilieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e76cf-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
