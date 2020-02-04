---
title: Byrefs
description: Informationen Sie zu Byref und Byref-ähnlichen Typen in F#, die für die Low-Level-Programmierung verwendet werden.
ms.date: 11/04/2019
ms.openlocfilehash: 05a40059ad5b72829233b0c4135c76eb1cff4da5
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965814"
---
# <a name="byrefs"></a><span data-ttu-id="dc838-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="dc838-103">Byrefs</span></span>

<span data-ttu-id="dc838-104">F#verfügt über zwei wichtige Featurebereiche, die sich auf den Raum der Low-Level-Programmierung befassen:</span><span class="sxs-lookup"><span data-stu-id="dc838-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="dc838-105">Die `byref`/`inref`/`outref` Typen, bei denen es sich um verwaltete Zeiger handelt.</span><span class="sxs-lookup"><span data-stu-id="dc838-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="dc838-106">Sie haben Einschränkungen hinsichtlich der Verwendung, sodass Sie kein Programm kompilieren können, das zur Laufzeit ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="dc838-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="dc838-107">Eine `byref`ähnliche Struktur, bei der es sich um eine [Struktur](structures.md) mit ähnlicher Semantik und denselben Kompilierzeit Beschränkungen wie `byref<'T>`handelt.</span><span class="sxs-lookup"><span data-stu-id="dc838-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="dc838-108">Ein Beispiel hierfür ist <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="dc838-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc838-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc838-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="dc838-110">ByRef, inref und der Wert</span><span class="sxs-lookup"><span data-stu-id="dc838-110">Byref, inref, and outref</span></span>

<span data-ttu-id="dc838-111">Es gibt drei Arten von `byref`:</span><span class="sxs-lookup"><span data-stu-id="dc838-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="dc838-112">`inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="dc838-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="dc838-113">`outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="dc838-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="dc838-114">`byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="dc838-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="dc838-115">Eine `byref<'T>` kann an die Stelle, an der ein `inref<'T>` erwartet wird</span><span class="sxs-lookup"><span data-stu-id="dc838-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="dc838-116">Auf ähnliche Weise kann eine `byref<'T>` an die Stelle, an der ein `outref<'T>` erwartet wird</span><span class="sxs-lookup"><span data-stu-id="dc838-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="dc838-117">Verwenden von ByRefs</span><span class="sxs-lookup"><span data-stu-id="dc838-117">Using byrefs</span></span>

<span data-ttu-id="dc838-118">Um einen `inref<'T>`zu verwenden, müssen Sie einen Zeiger Wert mit `&`erhalten:</span><span class="sxs-lookup"><span data-stu-id="dc838-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="dc838-119">Wenn Sie mit einem `outref<'T>` oder `byref<'T>`in den Zeiger schreiben möchten, müssen Sie auch den Wert, auf den Sie einen Zeiger ziehen, auf `mutable`festlegen.</span><span class="sxs-lookup"><span data-stu-id="dc838-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="dc838-120">Wenn Sie nur den Zeiger schreiben, anstatt ihn zu lesen, sollten Sie die Verwendung von `outref<'T>` anstelle von `byref<'T>`in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="dc838-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="dc838-121">Inref-Semantik</span><span class="sxs-lookup"><span data-stu-id="dc838-121">Inref semantics</span></span>

<span data-ttu-id="dc838-122">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="dc838-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="dc838-123">Semantisch bedeutet dies Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dc838-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="dc838-124">Der Besitzer des `x` Zeigers darf ihn nur zum Lesen des Werts verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc838-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="dc838-125">Jeder Zeiger, der `struct` in `SomeStruct` geschachtelten Feldern abgerufen wird, erhält den Typ `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="dc838-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="dc838-126">Außerdem gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dc838-126">The following is also true:</span></span>

* <span data-ttu-id="dc838-127">Es gibt keine Auswirkung darauf, dass andere Threads oder Aliase keinen Schreibzugriff auf `x`haben.</span><span class="sxs-lookup"><span data-stu-id="dc838-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="dc838-128">Es gibt keine Auswirkung darauf, dass `SomeStruct` aufgrund `x` einer `inref`unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="dc838-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="dc838-129">Bei F# Werttypen, die unveränderlich **sind** , wird der `this` Zeiger als `inref`abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="dc838-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="dc838-130">Alle diese Regeln bedeuten, dass der Besitzer eines `inref` Zeigers den unmittelbaren Inhalt des Speichers, auf den verwiesen wird, möglicherweise nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="dc838-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="dc838-131">Leistungs Semantik</span><span class="sxs-lookup"><span data-stu-id="dc838-131">Outref semantics</span></span>

<span data-ttu-id="dc838-132">Der Zweck `outref<'T>` ist, anzugeben, dass der Zeiger nur in den Zeiger geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc838-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="dc838-133">Unerwartet, `outref<'T>` das Lesen des zugrunde liegenden Werts trotz seines Namens zulässt.</span><span class="sxs-lookup"><span data-stu-id="dc838-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="dc838-134">Dies dient zu Kompatibilitätszwecken.</span><span class="sxs-lookup"><span data-stu-id="dc838-134">This is for compatibility purposes.</span></span> <span data-ttu-id="dc838-135">`outref<'T>` unterscheidet sich semantisch von `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="dc838-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="dc838-136">Interop mit C-\#</span><span class="sxs-lookup"><span data-stu-id="dc838-136">Interop with C\#</span></span>

<span data-ttu-id="dc838-137">C#unterstützt die Schlüsselwörter `in ref` und `out ref` zusätzlich zu `ref`-Rückgabe.</span><span class="sxs-lookup"><span data-stu-id="dc838-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="dc838-138">Die folgende Tabelle zeigt, wie F# interpretiert wie c# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="dc838-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="dc838-139">C#Erstellen</span><span class="sxs-lookup"><span data-stu-id="dc838-139">C# construct</span></span>|<span data-ttu-id="dc838-140">F#leitet</span><span class="sxs-lookup"><span data-stu-id="dc838-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="dc838-141">`ref` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dc838-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="dc838-142">`ref readonly` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dc838-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="dc838-143">`in ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="dc838-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="dc838-144">`out ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="dc838-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="dc838-145">Die folgende Tabelle zeigt, was F# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="dc838-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="dc838-146">F#Erstellen</span><span class="sxs-lookup"><span data-stu-id="dc838-146">F# construct</span></span>|<span data-ttu-id="dc838-147">Ausgegebenes Konstrukt</span><span class="sxs-lookup"><span data-stu-id="dc838-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="dc838-148">`inref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="dc838-148">`inref<'T>` argument</span></span>|<span data-ttu-id="dc838-149">`[In]`-Attribut für Argument</span><span class="sxs-lookup"><span data-stu-id="dc838-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="dc838-150">`inref<'T>` Rückgabe</span><span class="sxs-lookup"><span data-stu-id="dc838-150">`inref<'T>` return</span></span>|<span data-ttu-id="dc838-151">`modreq` Attribut für Wert</span><span class="sxs-lookup"><span data-stu-id="dc838-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="dc838-152">`inref<'T>` im abstrakten Slot oder in der Implementierung</span><span class="sxs-lookup"><span data-stu-id="dc838-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="dc838-153">`modreq` on-Argument oder Rückgabe</span><span class="sxs-lookup"><span data-stu-id="dc838-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="dc838-154">`outref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="dc838-154">`outref<'T>` argument</span></span>|<span data-ttu-id="dc838-155">`[Out]`-Attribut für Argument</span><span class="sxs-lookup"><span data-stu-id="dc838-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="dc838-156">Typrückschluss und Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="dc838-156">Type inference and overloading rules</span></span>

<span data-ttu-id="dc838-157">Ein `inref<'T>` Typ wird vom F# Compiler in den folgenden Fällen abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="dc838-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="dc838-158">Ein .net-Parameter oder-Rückgabetyp, der über ein `IsReadOnly` Attribut verfügt.</span><span class="sxs-lookup"><span data-stu-id="dc838-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="dc838-159">Der `this` Zeiger auf einen Strukturtyp ohne änderbare Felder.</span><span class="sxs-lookup"><span data-stu-id="dc838-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="dc838-160">Die Adresse eines Speicher Orts, der von einem anderen `inref<_>` Zeiger abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="dc838-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="dc838-161">Wenn eine implizite Adresse eines `inref` übernommen wird, wird eine Überladung mit einem Argument vom Typ `SomeType` einer Überladung mit einem Argument vom Typ `inref<SomeType>`bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="dc838-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="dc838-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dc838-162">For example:</span></span>

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

<span data-ttu-id="dc838-163">In beiden Fällen werden die über Ladungen, die `System.DateTime` Unternehmen, aufgelöst, anstatt die über Ladungen `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="dc838-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="dc838-164">ByRef-ähnliche Strukturen</span><span class="sxs-lookup"><span data-stu-id="dc838-164">Byref-like structs</span></span>

<span data-ttu-id="dc838-165">Zusätzlich zum `byref`/`inref`/`outref` Trio können Sie eigene Strukturen definieren, die `byref`ähnlichen Semantik entsprechen können.</span><span class="sxs-lookup"><span data-stu-id="dc838-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="dc838-166">Dies erfolgt mit dem <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>-Attribut:</span><span class="sxs-lookup"><span data-stu-id="dc838-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="dc838-167">`IsByRefLike` impliziert keine `Struct`.</span><span class="sxs-lookup"><span data-stu-id="dc838-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="dc838-168">Beides muss für den Typ vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="dc838-168">Both must be present on the type.</span></span>

<span data-ttu-id="dc838-169">Ein "`byref`-wie" "Struct" in F# ist ein Stack gebundene Wert.</span><span class="sxs-lookup"><span data-stu-id="dc838-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="dc838-170">Sie wird niemals dem verwalteten Heap zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="dc838-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="dc838-171">Eine `byref`ähnliche Struktur eignet sich für die Hochleistungs Programmierung, da Sie mit einer Reihe von leistungsstarken Überprüfungen zur Lebensdauer und nicht Erfassung erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="dc838-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="dc838-172">Die Regeln lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dc838-172">The rules are:</span></span>

* <span data-ttu-id="dc838-173">Sie können als Funktionsparameter, Methoden Parameter, lokale Variablen und Methoden Rückgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc838-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="dc838-174">Sie können keine statischen Member oder Instanzmember einer Klasse oder einer normalen Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="dc838-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="dc838-175">Sie können nicht von einem Closure-Konstrukt (`async`-Methoden oder Lambda-Ausdrücken) aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="dc838-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="dc838-176">Sie können nicht als generischer Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc838-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="dc838-177">Dieser letzte Punkt ist entscheidend für F# die Programmierung im Pipeline Stil, da `|>` eine generische Funktion ist, die seine Eingabetypen parametrisiert.</span><span class="sxs-lookup"><span data-stu-id="dc838-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="dc838-178">Diese Einschränkung kann für `|>` in der Zukunft gelockert werden, da Sie Inline ist und keine Aufrufe von nicht Inline-generischen Funktionen im Textkörper vornimmt.</span><span class="sxs-lookup"><span data-stu-id="dc838-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="dc838-179">Wenngleich diese Regeln die Nutzung stark einschränken, wird dies durchgeführt, um die Zusage von Hochleistungs Computing auf sichere Weise zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="dc838-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="dc838-180">ByRef-Rückgaben</span><span class="sxs-lookup"><span data-stu-id="dc838-180">Byref returns</span></span>

<span data-ttu-id="dc838-181">ByRef-Rückgaben von F#-Funktionen oder Elemente erstellt und verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="dc838-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="dc838-182">Bei der Verwendung einer `byref`zurück gebenden Methode wird der Wert implizit dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="dc838-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="dc838-183">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dc838-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) = 
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="dc838-184">Um einen ByRef-Wert zurückzugeben, muss die Variable, die den Wert enthält, länger als der aktuelle Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="dc838-184">To return a value byref, the variable which contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="dc838-185">Verwenden Sie außerdem & Wert (wobei value eine Variable ist, die länger als der aktuelle Bereich ist), um ByRef zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc838-185">Also, to return byref, use &value (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="dc838-186">Um die implizite Dereferenzierung zu vermeiden, z. b. einen Verweis über mehrere verkettete Aufrufe zu übergeben, verwenden Sie `&x` (wobei `x` der Wert ist).</span><span class="sxs-lookup"><span data-stu-id="dc838-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="dc838-187">Sie können einem Rückgabe `byref`auch direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="dc838-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="dc838-188">Sehen Sie sich das folgende (hochgradig imperative) Programm an:</span><span class="sxs-lookup"><span data-stu-id="dc838-188">Consider the following (highly imperative) program:</span></span>

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

<span data-ttu-id="dc838-189">Dies ist die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="dc838-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="dc838-190">Bereichs Definition für ByRefs</span><span class="sxs-lookup"><span data-stu-id="dc838-190">Scoping for byrefs</span></span>

<span data-ttu-id="dc838-191">Ein `let`gebundener Wert kann nicht den Bereich überschreiten, in dem er definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="dc838-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="dc838-192">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="dc838-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="dc838-193">Dadurch wird verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen ein-oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="dc838-193">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
