---
title: 'Neues in f # 5,0-f #-Handbuch'
description: 'Verschaffen Sie sich einen Überblick über die neuen Features, die in F # 5,0 verfügbar sind.'
ms.date: 11/06/2020
ms.openlocfilehash: 0b25d48a97792e780515226170151f3bbf2f2301
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982465"
---
# <a name="whats-new-in-f-50"></a><span data-ttu-id="db619-103">Neues in F# 5.0</span><span class="sxs-lookup"><span data-stu-id="db619-103">What's new in F# 5.0</span></span>

<span data-ttu-id="db619-104">F # 5,0 fügt mehrere Verbesserungen der Sprache f # und F# Interactive hinzu.</span><span class="sxs-lookup"><span data-stu-id="db619-104">F# 5.0 adds several improvements to the F# language and F# Interactive.</span></span> <span data-ttu-id="db619-105">Sie wird mit **.net 5** veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="db619-105">It is released with **.NET 5**.</span></span>

<span data-ttu-id="db619-106">Sie können das neueste .NET SDK über die [.NET-Downloadseite](https://dotnet.microsoft.com/download) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="db619-106">You can download the latest .NET SDK from the [.NET downloads page](https://dotnet.microsoft.com/download).</span></span>

## <a name="get-started"></a><span data-ttu-id="db619-107">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="db619-107">Get started</span></span>

<span data-ttu-id="db619-108">F # 5,0 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar.</span><span class="sxs-lookup"><span data-stu-id="db619-108">F# 5.0 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="db619-109">Weitere Informationen finden Sie unter [Einstieg in F #](../get-started/index.md) , um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="db619-109">For more information, see [Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="package-references-in-f-scripts"></a><span data-ttu-id="db619-110">Paket Verweise in F #-Skripts</span><span class="sxs-lookup"><span data-stu-id="db619-110">Package references in F# scripts</span></span>

<span data-ttu-id="db619-111">F # 5 unterstützt Paket Verweise in f #-Skripts mit `#r "nuget:..."` Syntax.</span><span class="sxs-lookup"><span data-stu-id="db619-111">F# 5 brings support for package references in F# scripts with `#r "nuget:..."` syntax.</span></span> <span data-ttu-id="db619-112">Sehen Sie sich beispielsweise den folgenden Paket Verweis an:</span><span class="sxs-lookup"><span data-stu-id="db619-112">For example, consider the following package reference:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn "%s" (JsonConvert.SerializeObject o)
```

<span data-ttu-id="db619-113">Sie können auch eine explizite Version nach dem Namen des Pakets wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="db619-113">You can also supply an explicit version after the name of the package like this:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

<span data-ttu-id="db619-114">Paket Verweise unterstützen Pakete mit nativen Abhängigkeiten, z. b. ml.net.</span><span class="sxs-lookup"><span data-stu-id="db619-114">Package references support packages with native dependencies, such as ML.NET.</span></span>

<span data-ttu-id="db619-115">Paket Verweise unterstützen auch Pakete mit speziellen Anforderungen zum Verweisen auf abhängige `.dll` s.</span><span class="sxs-lookup"><span data-stu-id="db619-115">Package references also support packages with special requirements about referencing dependent `.dll`s.</span></span> <span data-ttu-id="db619-116">Beispielsweise muss das [fbeispielpaket](https://www.nuget.org/packages/FParsec/) verwendet werden, um sicherzustellen, dass die Benutzer manuell sicherstellen, dass auf Ihre abhängige `FParsecCS.dll` zuerst verwiesen wurde, bevor `FParsec.dll` in F# Interactive auf verwiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="db619-116">For example, the [FParsec](https://www.nuget.org/packages/FParsec/) package used to require that users manually ensure that its dependent `FParsecCS.dll` was referenced first before `FParsec.dll` was referenced in F# Interactive.</span></span> <span data-ttu-id="db619-117">Dies ist nicht mehr erforderlich, und Sie können wie folgt auf das Paket verweisen:</span><span class="sxs-lookup"><span data-stu-id="db619-117">This is no longer needed, and you can reference the package as follows:</span></span>

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn "Success: %A" result
    | Failure(errorMsg, _, _) -> printfn "Failure: %s" errorMsg

test pfloat "1.234"
```

<span data-ttu-id="db619-118">Diese Funktion implementiert [F #-Tools RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md).</span><span class="sxs-lookup"><span data-stu-id="db619-118">This feature implements [F# Tooling RFC FST-1027](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1027-fsi-references.md).</span></span> <span data-ttu-id="db619-119">Weitere Informationen zu Paket verweisen finden Sie im [F# Interactive](../tutorials/fsharp-interactive/index.md) Tutorial.</span><span class="sxs-lookup"><span data-stu-id="db619-119">For more information on package references, see the [F# Interactive](../tutorials/fsharp-interactive/index.md) tutorial.</span></span>

## <a name="string-interpolation"></a><span data-ttu-id="db619-120">Zeichenfolgeninterpolierung</span><span class="sxs-lookup"><span data-stu-id="db619-120">String interpolation</span></span>

<span data-ttu-id="db619-121">F #-interinterpolierte Zeichen folgen ähneln c#-oder JavaScript-interpoliert-Zeichen folgen, da Sie in einem Zeichenfolgenliteralzeichen Code in "Löcher" schreiben können.</span><span class="sxs-lookup"><span data-stu-id="db619-121">F# interpolated strings are fairly similar to C# or JavaScript interpolated strings, in that they let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="db619-122">Im Folgenden finden Sie ein einfaches Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db619-122">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="db619-123">In F # interpoliert-Zeichen folgen ist es jedoch auch möglich, typisierte Interpolationen wie die- `sprintf` Funktion zu erzwingen, um zu erzwingen, dass ein Ausdruck innerhalb eines interinterpolierten Kontexts einem bestimmten Typ entspricht.</span><span class="sxs-lookup"><span data-stu-id="db619-123">However, F# interpolated strings also allow for typed interpolations, just like the `sprintf` function, to enforce that an expression inside of an interpolated context conforms to a particular type.</span></span> <span data-ttu-id="db619-124">Dabei werden die gleichen Format Bearbeiter verwendet.</span><span class="sxs-lookup"><span data-stu-id="db619-124">It uses the same format specifiers.</span></span>

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="db619-125">Im vorangehenden Beispiel für eine typisierte interpolung `%s` erfordert, dass die Interpolations vom Typ `string` ist, während `%d` für die Interpolations-erforderlich ist `integer` .</span><span class="sxs-lookup"><span data-stu-id="db619-125">In the preceding typed interpolation example, the `%s` requires the interpolation to be of type `string`, whereas the `%d` requires the interpolation to be an `integer`.</span></span>

<span data-ttu-id="db619-126">Darüber hinaus können beliebige F #-Ausdrücke (oder Ausdrücke) auf der Seite eines Interpolations Kontexts platziert werden.</span><span class="sxs-lookup"><span data-stu-id="db619-126">Additionally, any arbitrary F# expression (or expressions) can be placed in side of an interpolation context.</span></span> <span data-ttu-id="db619-127">Es ist sogar möglich, einen komplizierteren Ausdruck wie folgt zu schreiben:</span><span class="sxs-lookup"><span data-stu-id="db619-127">It is even possible to write a more complicated expression, like so:</span></span>

```fsharp
let str =
    $"""The result of squaring each odd item in {[1..10]} is:
{
    let square x = x * x
    let isOdd x = x % 2 <> 0
    let oddSquares xs =
        xs
        |> List.filter isOdd
        |> List.map square
    oddSquares [1..10]
}
"""
```

<span data-ttu-id="db619-128">Wir empfehlen zwar nicht, dies in der Praxis zu tun.</span><span class="sxs-lookup"><span data-stu-id="db619-128">Although we don't recommend doing this too much in practice.</span></span>

<span data-ttu-id="db619-129">Diese Funktion implementiert [F # RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md).</span><span class="sxs-lookup"><span data-stu-id="db619-129">This feature implements [F# RFC FS-1001](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1001-StringInterpolation.md).</span></span>

## <a name="support-for-nameof"></a><span data-ttu-id="db619-130">Unterstützung für "nameof"</span><span class="sxs-lookup"><span data-stu-id="db619-130">Support for nameof</span></span>

<span data-ttu-id="db619-131">F # 5 unterstützt den `nameof` -Operator, der das Symbol auflöst, für das es verwendet wird, und seinen Namen in F #-Quelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="db619-131">F# 5 supports the `nameof` operator, which resolves the symbol it's being used for and produces its name in F# source.</span></span> <span data-ttu-id="db619-132">Dies ist in verschiedenen Szenarien hilfreich, z. b. bei der Protokollierung und schützt Ihre Protokollierung vor Änderungen im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="db619-132">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) (sprintf "Value passed in was %d." month)

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="db619-133">In der letzten Zeile wird eine Ausnahme ausgelöst, und "Month" wird in der Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db619-133">The last line will throw an exception and "month" will be shown in the error message.</span></span>

<span data-ttu-id="db619-134">Sie können einen Namen für fast alle F #-Konstrukte verwenden:</span><span class="sxs-lookup"><span data-stu-id="db619-134">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn "%s" (M.f 12)
printfn "%s" (nameof M)
printfn "%s" (nameof M.f)
```

<span data-ttu-id="db619-135">Drei abschließende Ergänzungen sind Änderungen an der Funktionsweise von Operatoren: das Hinzufügen des `nameof<'type-parameter>` Formulars für generische Typparameter und die Möglichkeit, `nameof` als Muster in einem Muster Vergleichs Ausdruck zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="db619-135">Three final additions are changes to how operators work: the addition of the `nameof<'type-parameter>` form for generic type parameters, and the ability to use `nameof` as a pattern in a pattern match expression.</span></span>

<span data-ttu-id="db619-136">Die Quell Zeichenfolge wird durch den Namen eines Operators fest.</span><span class="sxs-lookup"><span data-stu-id="db619-136">Taking a name of an operator gives its source string.</span></span> <span data-ttu-id="db619-137">Wenn Sie das kompilierte Formular benötigen, verwenden Sie den kompilierten Namen eines Operators:</span><span class="sxs-lookup"><span data-stu-id="db619-137">If you need the compiled form, use the compiled name of an operator:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

<span data-ttu-id="db619-138">Wenn Sie den Namen eines Typparameters eingeben, ist eine etwas andere Syntax erforderlich:</span><span class="sxs-lookup"><span data-stu-id="db619-138">Taking the name of a type parameter requires a slightly different syntax:</span></span>

```fsharp
type C<'TType> =
    member _.TypeName = nameof<'TType>
```

<span data-ttu-id="db619-139">Dies ähnelt dem `typeof<'T>` -Operator und dem- `typedefof<'T>` Operator.</span><span class="sxs-lookup"><span data-stu-id="db619-139">This is similar to the `typeof<'T>` and `typedefof<'T>` operators.</span></span>

<span data-ttu-id="db619-140">F # 5 bietet auch Unterstützung für ein `nameof` Muster, das in Ausdrücken verwendet werden kann `match` :</span><span class="sxs-lookup"><span data-stu-id="db619-140">F# 5 also adds support for a `nameof` pattern that can be used in `match` expressions:</span></span>

```fsharp
[<Struct; IsByRefLike>]
type RecordedEvent = { EventType: string; Data: ReadOnlySpan<byte> }

type MyEvent =
    | AData of int
    | BData of string

let deserialize (e: RecordedEvent) : MyEvent =
    match e.EventType with
    | nameof AData -> AData (JsonSerializer.Deserialize<int> e.Data)
    | nameof BData -> BData (JsonSerializer.Deserialize<string> e.Data)
    | t -> failwithf "Invalid EventType: %s" t
```

<span data-ttu-id="db619-141">Im vorangehenden Code wird "nameof" anstelle des Zeichenfolgenliterals im Vergleichs Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="db619-141">The preceding code uses 'nameof' instead of the string literal in the match expression.</span></span>

<span data-ttu-id="db619-142">Diese Funktion implementiert [F # RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="db619-142">This feature implements [F# RFC FS-1003](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1003-nameof-operator.md).</span></span>

## <a name="open-type-declarations"></a><span data-ttu-id="db619-143">Open-Typdeklarationen</span><span class="sxs-lookup"><span data-stu-id="db619-143">Open type declarations</span></span>

<span data-ttu-id="db619-144">F # 5 bietet auch Unterstützung für Open-Type-Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="db619-144">F# 5 also adds support for open type declarations.</span></span> <span data-ttu-id="db619-145">Eine offene Typdeklaration ähnelt dem Öffnen einer statischen Klasse in c#, außer mit einer anderen Syntax und einem leicht abweichenden Verhalten, das für die F #-Semantik geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="db619-145">An open type declaration is like opening a static class in C#, except with some different syntax and some slightly different behavior to fit F# semantics.</span></span>

<span data-ttu-id="db619-146">Mit Open Type-Deklarationen können Sie `open` einen beliebigen Typ zum verfügbar machen von statischem Inhalt darin bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="db619-146">With open type declarations, you can `open` any type to expose static contents inside of it.</span></span> <span data-ttu-id="db619-147">Darüber hinaus können Sie `open` F #-definierte Unions und Datensätze zur Offenlegung ihres Inhalts nutzen.</span><span class="sxs-lookup"><span data-stu-id="db619-147">Additionally, you can `open` F#-defined unions and records to expose their contents.</span></span> <span data-ttu-id="db619-148">Dies kann z. b. hilfreich sein, wenn Sie eine Union in einem Modul definiert haben und auf ihre Fälle zugreifen möchten, aber nicht das gesamte Modul öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="db619-148">For example, this can be useful if you have a union defined in a module and want to access its cases, but don't want to open the entire module.</span></span>

```fsharp
open type System.Math

let x = Min(1.0, 2.0)

module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn "%A" A
```

<span data-ttu-id="db619-149">Anders als bei c#, wenn Sie zwei Typen haben, die `open type` einen Member mit demselben Namen verfügbar machen, wird das Element aus dem letzten Typ, der mit dem letzten Typ identisch ist, mit `open` dem anderen Namen</span><span class="sxs-lookup"><span data-stu-id="db619-149">Unlike C#, when you `open type` on two types that expose a member with the same name, the member from the last type being `open`ed shadows the other name.</span></span> <span data-ttu-id="db619-150">Dies ist mit der F #-Semantik um shadowingkonsistent, die bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="db619-150">This is consistent with F# semantics around shadowing that exist already.</span></span>

<span data-ttu-id="db619-151">Diese Funktion implementiert [F # RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="db619-151">This feature implements [F# RFC FS-1068](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1068-open-type-declaration.md).</span></span>

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a><span data-ttu-id="db619-152">Konsistentes aufteilen-Verhalten für integrierte Datentypen</span><span class="sxs-lookup"><span data-stu-id="db619-152">Consistent slicing behavior for built-in data types</span></span>

<span data-ttu-id="db619-153">Das Verhalten für das Aufteilen der integrierten `FSharp.Core` Datentypen (Array, Liste, Zeichenfolge, 2D-Array, 3D-Array, 4D-Array), das vor F # 5 nicht konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="db619-153">Behavior for slicing the built-in `FSharp.Core` data types (array, list, string, 2D array, 3D array, 4D array) used to not be consistent prior to F# 5.</span></span> <span data-ttu-id="db619-154">Einige Edge-Case-Verhalten haben eine Ausnahme ausgelöst, und andere nicht.</span><span class="sxs-lookup"><span data-stu-id="db619-154">Some edge-case behavior threw an exception and some wouldn't.</span></span> <span data-ttu-id="db619-155">In F # 5 geben alle integrierten Typen nun leere Slices für Slices zurück, die nicht generiert werden können:</span><span class="sxs-lookup"><span data-stu-id="db619-155">In F# 5, all built-in types now return empty slices for slices that are impossible to generate:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

// Before: would return empty list
// F# 5: same
let emptyList = l.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty array
let emptyArray = a.[-2..(-1)]

// Before: would throw exception
// F# 5: returns empty string
let emptyString = s.[-2..(-1)]
```

<span data-ttu-id="db619-156">Diese Funktion implementiert [F # RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md).</span><span class="sxs-lookup"><span data-stu-id="db619-156">This feature implements [F# RFC FS-1077](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-tolerant-slicing.md).</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a><span data-ttu-id="db619-157">Festgelegte Index Slices für 3D-und 4D-Arrays in FSharp. Core</span><span class="sxs-lookup"><span data-stu-id="db619-157">Fixed-index slices for 3D and 4D arrays in FSharp.Core</span></span>

<span data-ttu-id="db619-158">F # 5,0 unterstützt das Aufteilen von aufteilen mit einem Fixed-Index in den integrierten 3D-und 4D-Array Typen.</span><span class="sxs-lookup"><span data-stu-id="db619-158">F# 5.0 brings support for slicing with a fixed index in the built-in 3D and 4D array types.</span></span>

<span data-ttu-id="db619-159">Um dies zu veranschaulichen, sehen Sie sich das folgende 3D-Array an:</span><span class="sxs-lookup"><span data-stu-id="db619-159">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="db619-160">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="db619-160">*z = 0*</span></span>
| <span data-ttu-id="db619-161">x\y</span><span class="sxs-lookup"><span data-stu-id="db619-161">x\y</span></span>   | <span data-ttu-id="db619-162">0</span><span class="sxs-lookup"><span data-stu-id="db619-162">0</span></span> | <span data-ttu-id="db619-163">1</span><span class="sxs-lookup"><span data-stu-id="db619-163">1</span></span> |
|-------|---|---|
| <span data-ttu-id="db619-164">**0**</span><span class="sxs-lookup"><span data-stu-id="db619-164">**0**</span></span> | <span data-ttu-id="db619-165">0</span><span class="sxs-lookup"><span data-stu-id="db619-165">0</span></span> | <span data-ttu-id="db619-166">1</span><span class="sxs-lookup"><span data-stu-id="db619-166">1</span></span> |
| <span data-ttu-id="db619-167">**1**</span><span class="sxs-lookup"><span data-stu-id="db619-167">**1**</span></span> | <span data-ttu-id="db619-168">2</span><span class="sxs-lookup"><span data-stu-id="db619-168">2</span></span> | <span data-ttu-id="db619-169">3</span><span class="sxs-lookup"><span data-stu-id="db619-169">3</span></span> |

<span data-ttu-id="db619-170">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="db619-170">*z = 1*</span></span>
| <span data-ttu-id="db619-171">x\y</span><span class="sxs-lookup"><span data-stu-id="db619-171">x\y</span></span>   | <span data-ttu-id="db619-172">0</span><span class="sxs-lookup"><span data-stu-id="db619-172">0</span></span> | <span data-ttu-id="db619-173">1</span><span class="sxs-lookup"><span data-stu-id="db619-173">1</span></span> |
|-------|---|---|
| <span data-ttu-id="db619-174">**0**</span><span class="sxs-lookup"><span data-stu-id="db619-174">**0**</span></span> | <span data-ttu-id="db619-175">4</span><span class="sxs-lookup"><span data-stu-id="db619-175">4</span></span> | <span data-ttu-id="db619-176">5</span><span class="sxs-lookup"><span data-stu-id="db619-176">5</span></span> |
| <span data-ttu-id="db619-177">**1**</span><span class="sxs-lookup"><span data-stu-id="db619-177">**1**</span></span> | <span data-ttu-id="db619-178">6</span><span class="sxs-lookup"><span data-stu-id="db619-178">6</span></span> | <span data-ttu-id="db619-179">7</span><span class="sxs-lookup"><span data-stu-id="db619-179">7</span></span> |

<span data-ttu-id="db619-180">Was geschieht, wenn Sie den Slice `[| 4; 5 |]` aus dem Array extrahieren möchten?</span><span class="sxs-lookup"><span data-stu-id="db619-180">What if you wanted to extract the slice `[| 4; 5 |]` from the array?</span></span> <span data-ttu-id="db619-181">Dies ist jetzt sehr einfach!</span><span class="sxs-lookup"><span data-stu-id="db619-181">This is now very simple!</span></span>

```fsharp
// First, create a 3D array to slice

let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="db619-182">Diese Funktion implementiert [F # RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md).</span><span class="sxs-lookup"><span data-stu-id="db619-182">This feature implements [F# RFC FS-1077b](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1077-3d-4d-fixed-index-slicing.md).</span></span>

## <a name="f-quotations-improvements"></a><span data-ttu-id="db619-183">Verbesserungen in F #</span><span class="sxs-lookup"><span data-stu-id="db619-183">F# quotations improvements</span></span>

<span data-ttu-id="db619-184">F #- [Code Zitate](../language-reference/code-quotations.md) haben jetzt die Möglichkeit, Informationen zur Typeinschränkung beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="db619-184">F# [code quotations](../language-reference/code-quotations.md) now have the ability to retain type constraint information.</span></span> <span data-ttu-id="db619-185">Betrachten Sie das folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="db619-185">Consider the following example:</span></span>

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

<span data-ttu-id="db619-186">Die von der Funktion generierte Einschränkung `inline` wird im Code-QUUM beibehalten.</span><span class="sxs-lookup"><span data-stu-id="db619-186">The constraint generated by the `inline` function is retained in the code qutoation.</span></span> <span data-ttu-id="db619-187">Das `negate` Formular der Funktion kann nun ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="db619-187">The `negate` function's quotated form can now be evaluated.</span></span>

<span data-ttu-id="db619-188">Diese Funktion implementiert [F # RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="db619-188">This feature implements [F# RFC FS-1071](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1071-witness-passing-quotations.md).</span></span>

## <a name="applicative-computation-expressions"></a><span data-ttu-id="db619-189">Anwendungsberechnungs-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="db619-189">Applicative Computation Expressions</span></span>

<span data-ttu-id="db619-190">[Berechnungs Ausdrücke (CES)](../language-reference/computation-expressions.md) werden heute verwendet, um "kontextbezogene Berechnungen" oder in funktionaler Programmier freundlicher Terminologie, monadische-Berechnungen, zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="db619-190">[Computation expressions (CEs)](../language-reference/computation-expressions.md) are used today to model "contextual computations", or in more functional programming friendly terminology, monadic computations.</span></span>

<span data-ttu-id="db619-191">F # 5 führt Anwendungsabhängigkeiten ein, die ein anderes Berechnungsmodell bieten.</span><span class="sxs-lookup"><span data-stu-id="db619-191">F# 5 introduces applicative CEs, which offer a different computational model.</span></span> <span data-ttu-id="db619-192">Anwendungs abhängige CES ermöglichen effizientere Berechnungen, vorausgesetzt, jede Berechnung ist unabhängig, und ihre Ergebnisse werden am Ende akkumuliert.</span><span class="sxs-lookup"><span data-stu-id="db619-192">Applicative CEs allow for more efficient computations provided that every computation is independent, and their results are accumulated at the end.</span></span> <span data-ttu-id="db619-193">Wenn Berechnungen voneinander unabhängig sind, können Sie auch trivial parallelisierbar sein, sodass CE-Autoren effizientere Bibliotheken schreiben können.</span><span class="sxs-lookup"><span data-stu-id="db619-193">When computations are independent of one another, they are also trivially parallelizable, allowing CE authors to write more efficient libraries.</span></span> <span data-ttu-id="db619-194">Dieser Vorteil liegt jedoch in einer Einschränkung: Berechnungen, die von zuvor berechneten Werten abhängen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="db619-194">This benefit comes at a restriction, though: computations that depend on previously-computed values are not allowed.</span></span>

<span data-ttu-id="db619-195">Das folgende Beispiel zeigt eine grundlegende Anwendungs Quelle für den- `Result` Typ.</span><span class="sxs-lookup"><span data-stu-id="db619-195">The follow example shows a basic applicative CE for the `Result` type.</span></span>

```fsharp
// First, define a 'zip' function
module Result =
    let zip x1 x2 =
        match x1,x2 with
        | Ok x1res, Ok x2res -> Ok (x1res, x2res)
        | Error e, _ -> Error e
        | _, Error e -> Error e

// Next, define a builder with 'MergeSources' and 'BindReturn'
type ResultBuilder() =
    member _.MergeSources(t1: Result<'T,'U>, t2: Result<'T1,'U>) = Result.zip t1 t2
    member _.BindReturn(x: Result<'T,'U>, f) = Result.map f x

let result = ResultBuilder()

let run r1 r2 r3 =
    // And here is our applicative!
    let res1: Result<int, string> =
        result {
            let! a = r1
            and! b = r2
            and! c = r3
            return a + b - c
        }

    match res1 with
    | Ok x -> printfn "%s is: %d" (nameof res1) x
    | Error e -> printfn "%s is: %s" (nameof res1) e

let printApplicatives () =
    let r1 = Ok 2
    let r2 = Ok 3 // Error "fail!"
    let r3 = Ok 4

    run r1 r2 r3
    run r1 (Error "failure!") r3
```

<span data-ttu-id="db619-196">Wenn Sie ein Autor der Bibliothek sind, der heute CES in der Bibliothek verfügbar macht, müssen Sie einige zusätzliche Aspekte beachten.</span><span class="sxs-lookup"><span data-stu-id="db619-196">If you're a library author who exposes CEs in their library today, there are some additional considerations you'll need to be aware of.</span></span>

<span data-ttu-id="db619-197">Diese Funktion implementiert [F # RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md).</span><span class="sxs-lookup"><span data-stu-id="db619-197">This feature implements [F# RFC FS-1063](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1063-support-letbang-andbang-for-applicative-functors.md).</span></span>

## <a name="interfaces-can-be-implemeneted-at-different-generic-instantiations"></a><span data-ttu-id="db619-198">Schnittstellen können in unterschiedlichen generischen Instanziierungen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="db619-198">Interfaces can be implemeneted at different generic instantiations</span></span>

<span data-ttu-id="db619-199">Nun können Sie die gleiche Schnittstelle in unterschiedlichen generischen Instanziierungen implementieren:</span><span class="sxs-lookup"><span data-stu-id="db619-199">You can now implement the same interface at different generic instantiations:</span></span>

```fsharp
type IA<'T> =
    abstract member Get : unit -> 'T

type MyClass() =
    interface IA<int> with
        member x.Get() = 1
    interface IA<string> with
        member x.Get() = "hello"

let mc = MyClass()
let iaInt = mc :> IA<int>
let iaString = mc :> IA<string>

iaInt.Get() // 1
iaString.Get() // "hello"
```

<span data-ttu-id="db619-200">Diese Funktion implementiert [F # RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md).</span><span class="sxs-lookup"><span data-stu-id="db619-200">This feature implements [F# RFC FS-1031](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1031-Allow%20implementing%20the%20same%20interface%20at%20different%20generic%20instantiations%20in%20the%20same%20type.md).</span></span>

## <a name="default-interface-member-consumption"></a><span data-ttu-id="db619-201">Standardmäßige Verwendung von Schnittstellen Elementen</span><span class="sxs-lookup"><span data-stu-id="db619-201">Default interface member consumption</span></span>

<span data-ttu-id="db619-202">Mit F # 5 können Sie [Schnittstellen mit Standard Implementierungen](../../csharp/tutorials/default-interface-methods-versions.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="db619-202">F# 5 lets you consume [interfaces with default implementations](../../csharp/tutorials/default-interface-methods-versions.md).</span></span>

<span data-ttu-id="db619-203">Angenommen, eine in c# definierte Schnittstelle sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="db619-203">Consider an interface defined in C# like this:</span></span>

```csharp
using System;

namespace CSharp
{
    public interface MyDimasd
    {
        public int Z => 0;
    }
}
```

<span data-ttu-id="db619-204">Sie können Sie in F # mithilfe einer beliebigen Standardmethode zur Implementierung einer Schnittstelle nutzen:</span><span class="sxs-lookup"><span data-stu-id="db619-204">You can consume it in F# through any of the standard means of implementing an interface:</span></span>

```fsharp
open CSharp

// You can implement the interface via a class
type MyType() =
    member _.M() = ()

    interface MyDim

let md = MyType() :> MyDim
printfn "DIM from C#: %d" md.Z

// You can also implement it via an object expression
let md' = { new MyDim }
printfn "DIM from C# but via Object Expression: %d" md'.Z
```

<span data-ttu-id="db619-205">Auf diese Weise können Sie den c#-Code und .NET-Komponenten, die in modernem c# geschrieben sind, sicher nutzen, wenn Sie erwarten, dass Benutzer eine Standard Implementierung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="db619-205">This lets you safely take advantage of C# code and .NET components written in modern C# when they expect users to be able to consume a default implementation.</span></span>

<span data-ttu-id="db619-206">Diese Funktion implementiert [F # RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md).</span><span class="sxs-lookup"><span data-stu-id="db619-206">This feature implements [F# RFC FS-1074](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1074-default-interface-member-consumption.md).</span></span>

## <a name="simplified-interop-with-nullable-value-types"></a><span data-ttu-id="db619-207">Vereinfachtes Interop mit Werte zulässt-Werttypen</span><span class="sxs-lookup"><span data-stu-id="db619-207">Simplified interop with nullable value types</span></span>

<span data-ttu-id="db619-208">[Typen](https://docs.microsoft.com/dotnet/api/system.nullable-1) , die NULL-Werte zulassen (in der Vergangenheit als Nullable-Typen bezeichnet), wurden schon seit langem von F # unterstützt, aber die Interaktion mit Ihnen war bisher schon etwas komplizierter, da Sie `Nullable` `Nullable<SomeType>` jedes Mal, wenn Sie einen Wert übergeben wollten, einen-oder-Wrapper erstellen mussten.</span><span class="sxs-lookup"><span data-stu-id="db619-208">[Nullable (value) types](https://docs.microsoft.com/dotnet/api/system.nullable-1) (called Nullable Types historically) have long been supported by F#, but interacting with them has traditionally been somewhat of a pain since you'd have to construct a `Nullable` or `Nullable<SomeType>` wrapper every time you wanted to pass a value.</span></span> <span data-ttu-id="db619-209">Nun konvertiert der Compiler einen Werttyp implizit in eine, `Nullable<ThatValueType>` Wenn der Zieltyp übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="db619-209">Now the compiler will implicitly convert a value type into a `Nullable<ThatValueType>` if the target type matches.</span></span> <span data-ttu-id="db619-210">Der folgende Code ist nun möglich:</span><span class="sxs-lookup"><span data-stu-id="db619-210">The following code is now possible:</span></span>

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

<span data-ttu-id="db619-211">Diese Funktion implementiert [F # RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md).</span><span class="sxs-lookup"><span data-stu-id="db619-211">This feature implements [F# RFC FS-1075](https://github.com/fsharp/fslang-design/blob/master/FSharp-5.0/FS-1075-nullable-interop.md).</span></span>

## <a name="preview-reverse-indexes"></a><span data-ttu-id="db619-212">Vorschau: Reverse-Indizes</span><span class="sxs-lookup"><span data-stu-id="db619-212">Preview: reverse indexes</span></span>

<span data-ttu-id="db619-213">F # 5 führt außerdem eine Vorschau für das Zulassen von umgekehrten Indizes ein.</span><span class="sxs-lookup"><span data-stu-id="db619-213">F# 5 also introduces a preview for allowing reverse indexes.</span></span> <span data-ttu-id="db619-214">Die Syntax lautet `^idx`.</span><span class="sxs-lookup"><span data-stu-id="db619-214">The syntax is `^idx`.</span></span> <span data-ttu-id="db619-215">So können Sie einen Wert von Element 1 vom Ende einer Liste aus:</span><span class="sxs-lookup"><span data-stu-id="db619-215">Here's how you can an element 1 value from the end of a list:</span></span>

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

<span data-ttu-id="db619-216">Sie können auch umgekehrte Indizes für Ihre eigenen Typen definieren.</span><span class="sxs-lookup"><span data-stu-id="db619-216">You can also define reverse indexes for your own types.</span></span> <span data-ttu-id="db619-217">Zu diesem Zweck müssen Sie die folgende Methode implementieren:</span><span class="sxs-lookup"><span data-stu-id="db619-217">To do so, you'll need to implement the following method:</span></span>

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

<span data-ttu-id="db619-218">Im folgenden finden Sie ein Beispiel für den- `Span<'T>` Typ:</span><span class="sxs-lookup"><span data-stu-id="db619-218">Here's an example for the `Span<'T>` type:</span></span>

```fsharp
open System

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

    member sp.GetReverseIndex(_, offset: int) =
        sp.Length - offset

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let run () =
    let sp = [| 1; 2; 3; 4; 5 |].AsSpan()

    // Pre-# 5.0 slicing on a Span<'T>
    printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..3] // [|1; 2; 3|]
    printSpan sp.[1..3] // |2; 3|]

    // Same slices, but only using from-the-end index
    printSpan sp.[..^0] // [|1; 2; 3; 4; 5|]
    printSpan sp.[..^2] // [|1; 2; 3|]
    printSpan sp.[^4..^2] // [|2; 3|]

run() // Prints the same thing twice
```

<span data-ttu-id="db619-219">Diese Funktion implementiert [F # RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md).</span><span class="sxs-lookup"><span data-stu-id="db619-219">This feature implements [F# RFC FS-1076](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1076-from-the-end-slicing.md).</span></span>

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a><span data-ttu-id="db619-220">Vorschau: über Ladungen von benutzerdefinierten Schlüsselwörtern in Berechnungs Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="db619-220">Preview: overloads of custom keywords in computation expressions</span></span>

<span data-ttu-id="db619-221">Berechnungs Ausdrücke sind ein leistungsfähiges Feature für Bibliotheks-und Frameworkautoren.</span><span class="sxs-lookup"><span data-stu-id="db619-221">Computation expressions are a powerful feature for library and framework authors.</span></span> <span data-ttu-id="db619-222">Sie ermöglichen es Ihnen, die Ausdrucksfähigkeit ihrer Komponenten deutlich zu verbessern, indem Sie bekannte Member definieren und eine DSL für die Domäne bilden, in der Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="db619-222">They allow you to greatly improve the expressiveness of your components by letting you define well-known members and form a DSL for the domain you're working in.</span></span>

<span data-ttu-id="db619-223">F # 5 fügt eine Vorschau Unterstützung für das Überladen von benutzerdefinierten Vorgängen in Berechnungs Ausdrücken hinzu.</span><span class="sxs-lookup"><span data-stu-id="db619-223">F# 5 adds preview support for overloading custom operations in Computation Expressions.</span></span> <span data-ttu-id="db619-224">Dadurch kann der folgende Code geschrieben und verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="db619-224">It allows the following code to be writen and consumed:</span></span>

```fsharp
open System

type InputKind =
    | Text of placeholder:string option
    | Password of placeholder: string option

type InputOptions =
  { Label: string option
    Kind : InputKind
    Validators : (string -> bool) array }

type InputBuilder() =
    member t.Yield(_) =
      { Label = None
        Kind = Text None
        Validators = [||] }

    [<CustomOperation("text")>]
    member this.Text(io, ?placeholder) =
        { io with Kind = Text placeholder }

    [<CustomOperation("password")>]
    member this.Password(io, ?placeholder) =
        { io with Kind = Password placeholder }

    [<CustomOperation("label")>]
    member this.Label(io, label) =
        { io with Label = Some label }

    [<CustomOperation("with_validators")>]
    member this.Validators(io, [<ParamArray>] validators) =
        { io with Validators = validators }

let input = InputBuilder()

let name =
    input {
    label "Name"
    text
    with_validators
        (String.IsNullOrWhiteSpace >> not)
    }

let email =
    input {
    label "Email"
    text "Your email"
    with_validators
        (String.IsNullOrWhiteSpace >> not)
        (fun s -> s.Contains "@")
    }

let password =
    input {
    label "Password"
    password "Must contains at least 6 characters, one number and one uppercase"
    with_validators
        (String.exists Char.IsUpper)
        (String.exists Char.IsDigit)
        (fun s -> s.Length >= 6)
    }
```

<span data-ttu-id="db619-225">Vor dieser Änderung konnten Sie den `InputBuilder` Typ wie folgt schreiben, aber Sie konnten ihn nicht so verwenden, wie er im Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db619-225">Prior to this change, you could write the `InputBuilder` type as it is, but you couldn't use it the way it's used in the example.</span></span> <span data-ttu-id="db619-226">Da über Ladungen, optionale Parameter und jetzt- `System.ParamArray` Typen zulässig sind, funktioniert alles genau wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="db619-226">Since overloads, optional parameters, and now `System.ParamArray` types are allowed, everything just works as you'd expect it to.</span></span>

<span data-ttu-id="db619-227">Diese Funktion implementiert [F # RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md).</span><span class="sxs-lookup"><span data-stu-id="db619-227">This feature implements [F# RFC FS-1056](https://github.com/fsharp/fslang-design/blob/master/preview/FS-1056-allow-custom-operation-overloads.md).</span></span>
