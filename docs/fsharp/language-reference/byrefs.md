---
title: Parametry (f#)
description: Informationen Sie zu Byref und Byref-ähnlichen Typen in f#, die für die Low-Level-Programmierung verwendet werden.
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48263231"
---
# <a name="byrefs"></a><span data-ttu-id="3f358-103">Parametry</span><span class="sxs-lookup"><span data-stu-id="3f358-103">Byrefs</span></span>

<span data-ttu-id="3f358-104">F# verfügt über zwei Hauptfunktionen, die sich im Bereich der Programmierung auf unterer Ebene beschäftigen:</span><span class="sxs-lookup"><span data-stu-id="3f358-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="3f358-105">Die `byref` / `inref` / `outref` Typen, die einen verwalteten Zeiger.</span><span class="sxs-lookup"><span data-stu-id="3f358-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="3f358-106">Sie haben Einschränkungen bei der Nutzung, sodass Sie ein Programm kompilieren nicht möglich, die zur Laufzeit ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="3f358-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="3f358-107">Ein `byref`– wie Struktur, die ist eine [Struktur](structures.md) hat ähnliche Semantik und die gleichen Einschränkungen während der Kompilierung wie `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="3f358-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="3f358-108">Ein Beispiel ist die <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="3f358-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f358-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f358-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="3f358-110">ByRef Inref und outref</span><span class="sxs-lookup"><span data-stu-id="3f358-110">Byref, inref, and outref</span></span>

<span data-ttu-id="3f358-111">Es gibt drei Arten von `byref`:</span><span class="sxs-lookup"><span data-stu-id="3f358-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="3f358-112">`inref<'T>`, einen verwalteten Zeiger zum Lesen von des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="3f358-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="3f358-113">`outref<'T>`, einen verwalteten Zeiger zum Schreiben in den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="3f358-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="3f358-114">`byref<'T>`, einen verwalteten Zeiger zum Lesen und schreiben den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="3f358-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="3f358-115">Ein `byref<'T>` übergeben werden kann, wobei ein `inref<'T>` wird erwartet.</span><span class="sxs-lookup"><span data-stu-id="3f358-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="3f358-116">Auf ähnliche Weise eine `byref<'T>` übergeben werden kann, wobei ein `outref<'T>` wird erwartet.</span><span class="sxs-lookup"><span data-stu-id="3f358-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="3f358-117">Verwenden von parametry</span><span class="sxs-lookup"><span data-stu-id="3f358-117">Using byrefs</span></span>

<span data-ttu-id="3f358-118">Verwenden einer `inref<'T>`, benötigen Sie einen Zeigerwert mit `&`:</span><span class="sxs-lookup"><span data-stu-id="3f358-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="3f358-119">Um auf den Zeiger mit einem `outref<'T>` oder `byref<'T>`, achten Sie auch den Wert an, Sie nehmen einen Zeiger auf `mutable`.</span><span class="sxs-lookup"><span data-stu-id="3f358-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="3f358-120">Wenn Sie nur den Zeiger lesen, schreiben, sollten Sie `outref<'T>` anstelle von `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="3f358-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="3f358-121">Inref-Semantik</span><span class="sxs-lookup"><span data-stu-id="3f358-121">Inref semantics</span></span>

<span data-ttu-id="3f358-122">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="3f358-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

<span data-ttu-id="3f358-123">Semantisch gesehen bedeutet dies Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3f358-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="3f358-124">Der Inhaber des der `x` Zeiger kann nur verwenden, um den Wert zu lesen.</span><span class="sxs-lookup"><span data-stu-id="3f358-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="3f358-125">Jeder beliebige Zeigertyp Sperre zum `struct` Felder geschachtelt `SomeStruct` erhalten Typ `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="3f358-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="3f358-126">Folgendes gilt auch:</span><span class="sxs-lookup"><span data-stu-id="3f358-126">The following is also true:</span></span>

* <span data-ttu-id="3f358-127">Es gibt keine Auswirkung, die von anderen Threads, oder Aliase haben keinen Schreibzugriff auf `x`.</span><span class="sxs-lookup"><span data-stu-id="3f358-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="3f358-128">Es gibt keine Auswirkung, `SomeStruct` ist aufgrund des unveränderlich `x` wird ein `inref`.</span><span class="sxs-lookup"><span data-stu-id="3f358-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="3f358-129">Allerdings Wert für F#-Typen, die **sind** unveränderlich, die `this` Zeiger wird davon ausgegangen werden ein `inref`.</span><span class="sxs-lookup"><span data-stu-id="3f358-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="3f358-130">Alle diese Regeln, die zusammen bedeuten, dass den Inhaber des ein `inref` Zeiger kann nicht den unmittelbaren Inhalt des Arbeitsspeichers auf das gezeigt wird nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3f358-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="3f358-131">Outref-Semantik</span><span class="sxs-lookup"><span data-stu-id="3f358-131">Outref semantics</span></span>

<span data-ttu-id="3f358-132">Der Zweck der `outref<'T>` ist, um anzugeben, dass der Zeiger nur aus gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3f358-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="3f358-133">Unerwartet `outref<'T>` zulässt, lesen den zugrunde liegenden Wert trotz seines Namens.</span><span class="sxs-lookup"><span data-stu-id="3f358-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="3f358-134">Dies ist für die Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="3f358-134">This is for compatibility purposes.</span></span> <span data-ttu-id="3f358-135">Semantisch gesehen sind `outref<'T>` funktioniert genauso wie `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="3f358-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="3f358-136">Interoperabilität mit c#</span><span class="sxs-lookup"><span data-stu-id="3f358-136">Interop with C#</span></span> #

<span data-ttu-id="3f358-137">C# unterstützt die `in ref` und `out ref` Schlüsselwörter, zusätzlich zu den `ref` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f358-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="3f358-138">Die folgende Tabelle zeigt, wie f# interpretiert wie c# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="3f358-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="3f358-139">C#-Konstrukt</span><span class="sxs-lookup"><span data-stu-id="3f358-139">C# construct</span></span>|<span data-ttu-id="3f358-140">F#-leitet</span><span class="sxs-lookup"><span data-stu-id="3f358-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="3f358-141">`ref` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f358-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="3f358-142">`ref readonly` Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f358-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="3f358-143">`in ref` Parameter</span><span class="sxs-lookup"><span data-stu-id="3f358-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="3f358-144">`out ref` Parameter</span><span class="sxs-lookup"><span data-stu-id="3f358-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="3f358-145">Die folgende Tabelle zeigt, was f# ausgibt:</span><span class="sxs-lookup"><span data-stu-id="3f358-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="3f358-146">F#-Konstrukts</span><span class="sxs-lookup"><span data-stu-id="3f358-146">F# construct</span></span>|<span data-ttu-id="3f358-147">Ausgegebene-Konstrukt</span><span class="sxs-lookup"><span data-stu-id="3f358-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="3f358-148">`inref<'T>` Argument</span><span class="sxs-lookup"><span data-stu-id="3f358-148">`inref<'T>` argument</span></span>|<span data-ttu-id="3f358-149">`[In]` Attribut für argument</span><span class="sxs-lookup"><span data-stu-id="3f358-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="3f358-150">`inref<'T>` zurück</span><span class="sxs-lookup"><span data-stu-id="3f358-150">`inref<'T>` return</span></span>|<span data-ttu-id="3f358-151">`modreq` Attribut nach Wert</span><span class="sxs-lookup"><span data-stu-id="3f358-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="3f358-152">`inref<'T>` in abstrakten Slot oder Implementierung</span><span class="sxs-lookup"><span data-stu-id="3f358-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="3f358-153">`modreq` auf Argument- oder Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="3f358-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="3f358-154">`outref<'T>` Argument</span><span class="sxs-lookup"><span data-stu-id="3f358-154">`outref<'T>` argument</span></span>|<span data-ttu-id="3f358-155">`[Out]` Attribut für argument</span><span class="sxs-lookup"><span data-stu-id="3f358-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="3f358-156">Typrückschluss und Überladen von Regeln</span><span class="sxs-lookup"><span data-stu-id="3f358-156">Type inference and overloading rules</span></span>

<span data-ttu-id="3f358-157">Ein `inref<'T>` Typ abgeleitet wird, vom F#-Compiler in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="3f358-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="3f358-158">Ein .NET-Parameter oder Rückgabewert den Typ, der verfügt über eine `IsReadOnly` Attribut.</span><span class="sxs-lookup"><span data-stu-id="3f358-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="3f358-159">Die `this` Zeiger auf einen Strukturtyp, die keine änderbaren Felder enthält.</span><span class="sxs-lookup"><span data-stu-id="3f358-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="3f358-160">Die Adresse des Speicherorts im Arbeitsspeicher von einem anderen abgeleitet `inref<_>` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="3f358-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="3f358-161">Wenn eine implizite Adresse eine `inref` ist erstellt wird, eine Überladung mit einem Argument des Typs `SomeType` wird empfohlen, eine Überladung mit einem Argument des Typs `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="3f358-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="3f358-162">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f358-162">For example:</span></span>

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

<span data-ttu-id="3f358-163">In beiden Fällen die Überladungen, die die `System.DateTime` werden aufgelöst, anstatt die Überladungen, die die `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="3f358-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="3f358-164">ByRef-ähnlichen Strukturen</span><span class="sxs-lookup"><span data-stu-id="3f358-164">Byref-like structs</span></span>

<span data-ttu-id="3f358-165">Zusätzlich zu den `byref` / `inref` / `outref` Trio, Sie können Sie eigene Strukturen, die folgen können, definieren `byref`-Semantik wie.</span><span class="sxs-lookup"><span data-stu-id="3f358-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="3f358-166">Dies erfolgt mit der <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:</span><span class="sxs-lookup"><span data-stu-id="3f358-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="3f358-167">`IsByRefLike` impliziert nicht `Struct`.</span><span class="sxs-lookup"><span data-stu-id="3f358-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="3f358-168">Beide müssen für den Typ vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3f358-168">Both must be present on the type.</span></span>

<span data-ttu-id="3f358-169">Ein "`byref`-wie" "Struct" in f# ist ein Stack gebundene Wert.</span><span class="sxs-lookup"><span data-stu-id="3f358-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="3f358-170">Sie wird nie auf dem verwalteten Heap zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3f358-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="3f358-171">Ein `byref`-Struktur für Hochleistungs-Programmierung nützlich ist, wie sie mit leistungsfähiger Prüfungen zur Lebensdauer und nicht-Capture erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="3f358-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="3f358-172">Die Regeln sind:</span><span class="sxs-lookup"><span data-stu-id="3f358-172">The rules are:</span></span>

* <span data-ttu-id="3f358-173">Sie können verwendet werden Methodenrückgabe als Funktionsparameter, Methodenparameter, lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="3f358-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="3f358-174">Sie können nicht statisch sein oder Instanzmember einer Klasse oder einer normalen Struktur.</span><span class="sxs-lookup"><span data-stu-id="3f358-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="3f358-175">Sie können nicht anhand des Konstrukte Closure erfasst werden (`async` Methoden oder Lambdaausdrücke).</span><span class="sxs-lookup"><span data-stu-id="3f358-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="3f358-176">Sie können nicht als generischer Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f358-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="3f358-177">Dieser letzte Punkt ist entscheidend für F#-Programmierung im Pipeline-Stil, als `|>` ist eine generische Funktion, die die Eingabetypen parametrisiert.</span><span class="sxs-lookup"><span data-stu-id="3f358-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="3f358-178">Diese Einschränkung gelockert werden kann, für die `|>` in Zukunft wird Inline und macht keine Aufrufe von nicht-generische Inlinefunktionen in ihrem Text.</span><span class="sxs-lookup"><span data-stu-id="3f358-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="3f358-179">Obwohl diese Regeln sehr stark Nutzung einzuschränken, werden diese zur Erfüllung der Zusage von High Performance computing, auf sichere Weise.</span><span class="sxs-lookup"><span data-stu-id="3f358-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="3f358-180">ByRef-Rückgaben</span><span class="sxs-lookup"><span data-stu-id="3f358-180">Byref returns</span></span>

<span data-ttu-id="3f358-181">ByRef-Rückgaben von f#-Funktionen oder Elemente erstellt und verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3f358-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="3f358-182">Bei der Nutzung einer `byref`-Rückgabemethode, der Wert ist implizit keine Referenz.</span><span class="sxs-lookup"><span data-stu-id="3f358-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="3f358-183">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3f358-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="3f358-184">Verwenden, um die implizite Dereferenzierung, z. B. übergeben einen Verweis über mehrere verkettete Aufrufe zu vermeiden `&x` (wobei `x` ist der Wert).</span><span class="sxs-lookup"><span data-stu-id="3f358-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="3f358-185">Sie können auch direkt auf eine Rückgabe zuweisen `byref`.</span><span class="sxs-lookup"><span data-stu-id="3f358-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="3f358-186">Betrachten Sie das folgende Programm aus (dringend imperative):</span><span class="sxs-lookup"><span data-stu-id="3f358-186">Consider the following (highly imperative) program:</span></span>

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

<span data-ttu-id="3f358-187">Dies ist die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3f358-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="3f358-188">Festlegen des Gültigkeitsbereichs für parametry</span><span class="sxs-lookup"><span data-stu-id="3f358-188">Scoping for byrefs</span></span>

<span data-ttu-id="3f358-189">Ein `let`-gebundener Wert sind keine seinen Verweis, der den Bereich überschreiten, in dem sie definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3f358-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="3f358-190">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="3f358-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="3f358-191">Dies verhindert, dass Sie andere Ergebnisse abhängig zu erhalten, bei der Kompilierung mit Optimierungen aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3f358-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
