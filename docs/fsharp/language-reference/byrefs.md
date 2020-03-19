---
title: Byrefs
description: Erfahren Sie mehr über byref- und byref-ähnliche Typen in F', die für die Low-Level-Programmierung verwendet werden.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187055"
---
# <a name="byrefs"></a><span data-ttu-id="9bb86-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="9bb86-103">Byrefs</span></span>

<span data-ttu-id="9bb86-104">Die F-Funktion hat zwei Hauptbereiche, die sich im Bereich der Low-Level-Programmierung befassen:</span><span class="sxs-lookup"><span data-stu-id="9bb86-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="9bb86-105">`byref` / Die `inref` / Typen, bei denen es sich um verwaltete Zeiger `outref` handelt.</span><span class="sxs-lookup"><span data-stu-id="9bb86-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="9bb86-106">Sie haben Nutzungseinschränkungen, sodass Sie ein Programm nicht kompilieren können, das zur Laufzeit ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="9bb86-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="9bb86-107">Eine `byref`-like-Struktur, bei der es sich um eine [Struktur](structures.md) handelt, `byref<'T>`die eine ähnliche Semantik und die gleichen Kompilierungszeiteinschränkungen wie aufweist.</span><span class="sxs-lookup"><span data-stu-id="9bb86-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="9bb86-108">Ein Beispiel <xref:System.Span%601>ist .</span><span class="sxs-lookup"><span data-stu-id="9bb86-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="9bb86-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bb86-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="9bb86-110">Byref, inref und outref</span><span class="sxs-lookup"><span data-stu-id="9bb86-110">Byref, inref, and outref</span></span>

<span data-ttu-id="9bb86-111">Es gibt drei `byref`Formen von:</span><span class="sxs-lookup"><span data-stu-id="9bb86-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="9bb86-112">`inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="9bb86-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="9bb86-113">`outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.</span><span class="sxs-lookup"><span data-stu-id="9bb86-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="9bb86-114">`byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.</span><span class="sxs-lookup"><span data-stu-id="9bb86-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="9bb86-115">A `byref<'T>` kann dort `inref<'T>` übergeben werden, wo ein erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="9bb86-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="9bb86-116">Ebenso kann `byref<'T>` ein übergeben `outref<'T>` werden, wo ein erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="9bb86-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="9bb86-117">Verwenden von byrefs</span><span class="sxs-lookup"><span data-stu-id="9bb86-117">Using byrefs</span></span>

<span data-ttu-id="9bb86-118">Um eine `inref<'T>`zu verwenden, müssen Sie `&`einen Zeigerwert mit :</span><span class="sxs-lookup"><span data-stu-id="9bb86-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="9bb86-119">Um mithilfe eines `outref<'T>` oder `byref<'T>`in den Zeiger zu schreiben, müssen Sie `mutable`auch den Wert erstellen, den Sie an einem Zeiger an.</span><span class="sxs-lookup"><span data-stu-id="9bb86-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="9bb86-120">Wenn Sie nur den Zeiger schreiben, anstatt `outref<'T>` ihn `byref<'T>`zu lesen, sollten Sie anstelle von verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bb86-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="9bb86-121">Inref-Semantik</span><span class="sxs-lookup"><span data-stu-id="9bb86-121">Inref semantics</span></span>

<span data-ttu-id="9bb86-122">Betrachten Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="9bb86-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="9bb86-123">Semantisch bedeutet dies Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9bb86-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="9bb86-124">Der Halter `x` des Zeigers darf ihn nur zum Lesen des Werts verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bb86-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="9bb86-125">Jeder Zeiger, `struct` der zu `SomeStruct` Feldern gelangt `inref<_>`ist, die in feldern verschachtelt sind, wird vom Typ angegeben.</span><span class="sxs-lookup"><span data-stu-id="9bb86-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="9bb86-126">Das Folgende gilt auch:</span><span class="sxs-lookup"><span data-stu-id="9bb86-126">The following is also true:</span></span>

* <span data-ttu-id="9bb86-127">Es gibt keine Implikation, dass andere Threads `x`oder Aliase keinen Schreibzugriff auf haben.</span><span class="sxs-lookup"><span data-stu-id="9bb86-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="9bb86-128">Es gibt keine Implikation, die `SomeStruct` `x` unveränderlich ist, da sie eine `inref`ist.</span><span class="sxs-lookup"><span data-stu-id="9bb86-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="9bb86-129">Für Unveränderliche F-Werttypen wird **are** `this` der Zeiger jedoch als eine `inref`abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9bb86-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="9bb86-130">Alle diese Regeln zusammen bedeuten, `inref` dass der Inhaber eines Zeigers den unmittelbaren Inhalt des speicherweisen Speichers nicht ändern darf.</span><span class="sxs-lookup"><span data-stu-id="9bb86-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="9bb86-131">Outref-Semantik</span><span class="sxs-lookup"><span data-stu-id="9bb86-131">Outref semantics</span></span>

<span data-ttu-id="9bb86-132">Der Zweck `outref<'T>` von ist anzugeben, dass der Zeiger nur geschrieben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="9bb86-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="9bb86-133">Unerwartet, `outref<'T>` erlaubt das Lesen des zugrunde liegenden Werts trotz seines Namens.</span><span class="sxs-lookup"><span data-stu-id="9bb86-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="9bb86-134">Dies dient zu Kompatibilitätszwecken.</span><span class="sxs-lookup"><span data-stu-id="9bb86-134">This is for compatibility purposes.</span></span> <span data-ttu-id="9bb86-135">Semantisch ist `outref<'T>` nicht anders `byref<'T>`als .</span><span class="sxs-lookup"><span data-stu-id="9bb86-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="9bb86-136">Interop mit C\#</span><span class="sxs-lookup"><span data-stu-id="9bb86-136">Interop with C\#</span></span>

<span data-ttu-id="9bb86-137">Neben den `in ref` `out ref` `ref` Rückgaben unterstützt C- die und-Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="9bb86-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="9bb86-138">In der folgenden Tabelle wird gezeigt, wie die Von-Mail-Datei interpretiert wird, was die Emittungen von C-Code ausstrahlen:</span><span class="sxs-lookup"><span data-stu-id="9bb86-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="9bb86-139">C-Konstrukt</span><span class="sxs-lookup"><span data-stu-id="9bb86-139">C# construct</span></span>|<span data-ttu-id="9bb86-140">F-Abfolge</span><span class="sxs-lookup"><span data-stu-id="9bb86-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="9bb86-141">`ref`Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9bb86-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="9bb86-142">`ref readonly`Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9bb86-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="9bb86-143">`in ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="9bb86-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="9bb86-144">`out ref`-Parameter</span><span class="sxs-lookup"><span data-stu-id="9bb86-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="9bb86-145">Die folgende Tabelle zeigt, was die E-Mail-Sendungen von F- aussenden:</span><span class="sxs-lookup"><span data-stu-id="9bb86-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="9bb86-146">F-Konstrukt</span><span class="sxs-lookup"><span data-stu-id="9bb86-146">F# construct</span></span>|<span data-ttu-id="9bb86-147">Emitiertes Konstrukt</span><span class="sxs-lookup"><span data-stu-id="9bb86-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="9bb86-148">`inref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="9bb86-148">`inref<'T>` argument</span></span>|<span data-ttu-id="9bb86-149">`[In]`Attribut auf Argument</span><span class="sxs-lookup"><span data-stu-id="9bb86-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="9bb86-150">`inref<'T>`Rückgabe</span><span class="sxs-lookup"><span data-stu-id="9bb86-150">`inref<'T>` return</span></span>|<span data-ttu-id="9bb86-151">`modreq`Attribut auf Wert</span><span class="sxs-lookup"><span data-stu-id="9bb86-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="9bb86-152">`inref<'T>`in abstraktem Steckplatz oder Implementierung</span><span class="sxs-lookup"><span data-stu-id="9bb86-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="9bb86-153">`modreq`auf Argument oder Rückgabe</span><span class="sxs-lookup"><span data-stu-id="9bb86-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="9bb86-154">`outref<'T>`-Argument</span><span class="sxs-lookup"><span data-stu-id="9bb86-154">`outref<'T>` argument</span></span>|<span data-ttu-id="9bb86-155">`[Out]`Attribut auf Argument</span><span class="sxs-lookup"><span data-stu-id="9bb86-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="9bb86-156">Typrückschluss- und Überladungsregeln</span><span class="sxs-lookup"><span data-stu-id="9bb86-156">Type inference and overloading rules</span></span>

<span data-ttu-id="9bb86-157">In `inref<'T>` den folgenden Fällen wird ein Typ vom F-Compiler abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="9bb86-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="9bb86-158">Ein .NET-Parameter oder Rückgabetyp mit einem `IsReadOnly` Attribut.</span><span class="sxs-lookup"><span data-stu-id="9bb86-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="9bb86-159">Der `this` Zeiger auf einen Strukturtyp, der keine veränderlichen Felder enthält.</span><span class="sxs-lookup"><span data-stu-id="9bb86-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="9bb86-160">Die Adresse eines Speicherspeicherorts, der von einem anderen `inref<_>` Zeiger abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb86-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="9bb86-161">Wenn eine implizite `inref` Adresse von einem übernommen wird, `SomeType` wird eine Überladung mit einem `inref<SomeType>`Argument vom Typ einer Überladung mit einem Argument vom Typ vorgezogen.</span><span class="sxs-lookup"><span data-stu-id="9bb86-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="9bb86-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bb86-162">For example:</span></span>

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

<span data-ttu-id="9bb86-163">In beiden Fällen `System.DateTime` werden die Überladungen gelöst `inref<System.DateTime>`und nicht die Überlastungen, die .</span><span class="sxs-lookup"><span data-stu-id="9bb86-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="9bb86-164">Byref-ähnliche Konstruktionen</span><span class="sxs-lookup"><span data-stu-id="9bb86-164">Byref-like structs</span></span>

<span data-ttu-id="9bb86-165">`byref` / `inref` / `outref` Zusätzlich zum Trio können Sie eigene Strukturen definieren, `byref`die sich an -like semantics halten können.</span><span class="sxs-lookup"><span data-stu-id="9bb86-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="9bb86-166">Dies geschieht <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> mit dem Attribut:</span><span class="sxs-lookup"><span data-stu-id="9bb86-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="9bb86-167">`IsByRefLike`bedeutet `Struct`nicht .</span><span class="sxs-lookup"><span data-stu-id="9bb86-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="9bb86-168">Beide müssen auf dem Typ vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="9bb86-168">Both must be present on the type.</span></span>

<span data-ttu-id="9bb86-169">Eine`byref`" -like"-Struktur in F ist ein stapelgebundener Werttyp.</span><span class="sxs-lookup"><span data-stu-id="9bb86-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="9bb86-170">Sie wird nie auf dem verwalteten Heap zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9bb86-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="9bb86-171">Eine `byref`-like struct ist nützlich für die Hochleistungsprogrammierung, da sie mit einer Reihe starker Überprüfungen der Lebensdauer und Nicht-Capture erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="9bb86-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="9bb86-172">Die Regeln sind:</span><span class="sxs-lookup"><span data-stu-id="9bb86-172">The rules are:</span></span>

* <span data-ttu-id="9bb86-173">Sie können als Funktionsparameter, Methodenparameter, lokale Variablen, Methodenrückgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bb86-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="9bb86-174">Sie können keine statischen oder Instanzmember einer Klasse oder normalen Struktur sein.</span><span class="sxs-lookup"><span data-stu-id="9bb86-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="9bb86-175">Sie können nicht von einem`async` Abschlusskonstrukt erfasst werden (Methoden oder Lambda-Ausdrücke).</span><span class="sxs-lookup"><span data-stu-id="9bb86-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="9bb86-176">Sie können nicht als generischer Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9bb86-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="9bb86-177">Dieser letzte Punkt ist für die Programmierung `|>` im Pipeline-Stil von entscheidender Bedeutung, ebenso wie eine generische Funktion, die ihre Eingabetypen parametrisiert.</span><span class="sxs-lookup"><span data-stu-id="9bb86-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="9bb86-178">Diese Einschränkung kann `|>` in Zukunft gelockert werden, da sie inline ist und keine Aufrufe von nicht inline generischen Funktionen in ihrem Körper auslöst.</span><span class="sxs-lookup"><span data-stu-id="9bb86-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="9bb86-179">Obwohl diese Regeln die Nutzung stark einschränken, tun sie dies, um das Versprechen von Hochleistungs-Computing auf sichere Weise zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9bb86-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="9bb86-180">Byref kehrt zurück</span><span class="sxs-lookup"><span data-stu-id="9bb86-180">Byref returns</span></span>

<span data-ttu-id="9bb86-181">Byref-Rückgaben von F-Funktionen oder -Membern können erzeugt und verbraucht werden.</span><span class="sxs-lookup"><span data-stu-id="9bb86-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="9bb86-182">Bei der `byref`Verwendung einer -returning-Methode wird der Wert implizit dereferenziert.</span><span class="sxs-lookup"><span data-stu-id="9bb86-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="9bb86-183">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9bb86-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="9bb86-184">Um einen Wert byref zurückzugeben, muss die Variable, die den Wert enthält, länger als der aktuelle Bereich leben.</span><span class="sxs-lookup"><span data-stu-id="9bb86-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="9bb86-185">Um byref zurückzugeben, `&value` verwenden Sie (wobei wert eine Variable ist, die länger als der aktuelle Bereich lebt).</span><span class="sxs-lookup"><span data-stu-id="9bb86-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="9bb86-186">Um die implizite Dereferenzierung zu vermeiden, z. `&x` B. `x` das Übergeben eines Verweises durch mehrere verkettete Aufrufe, verwenden Sie (wobei der Wert ist).</span><span class="sxs-lookup"><span data-stu-id="9bb86-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="9bb86-187">Sie können eine Rücksendung `byref`auch direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9bb86-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="9bb86-188">Betrachten Sie das folgende (höchst zwingende) Programm:</span><span class="sxs-lookup"><span data-stu-id="9bb86-188">Consider the following (highly imperative) program:</span></span>

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

<span data-ttu-id="9bb86-189">Dies ist die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9bb86-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="9bb86-190">Scoping für byrefs</span><span class="sxs-lookup"><span data-stu-id="9bb86-190">Scoping for byrefs</span></span>

<span data-ttu-id="9bb86-191">Ein `let`-bound-Wert darf seinen Verweis nicht über den Bereich hinausgehen, in dem er definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9bb86-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="9bb86-192">Beispielsweise ist Folgendes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="9bb86-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="9bb86-193">Dies verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen kompilieren oder nicht.</span><span class="sxs-lookup"><span data-stu-id="9bb86-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
