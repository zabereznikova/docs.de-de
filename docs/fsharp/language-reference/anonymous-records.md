---
title: Anonyme Datensätze
description: Erfahren Sie, wie Sie die Erstellung und Verwendung anonymer Datensätze verwenden, einem sprach Feature, das die Bearbeitung von Daten unterstützt.
ms.date: 06/12/2019
ms.openlocfilehash: 0a7a819cc471c6579feacd621ed15aa89a6423ba
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569470"
---
# <a name="anonymous-records"></a><span data-ttu-id="576f3-103">Anonyme Datensätze</span><span class="sxs-lookup"><span data-stu-id="576f3-103">Anonymous Records</span></span>

<span data-ttu-id="576f3-104">Anonyme Datensätze sind einfache Aggregate benannter Werte, die nicht vor der Verwendung deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="576f3-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="576f3-105">Sie können Sie als Strukturen oder Verweis Typen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="576f3-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="576f3-106">Sie sind standardmäßig Verweis Typen.</span><span class="sxs-lookup"><span data-stu-id="576f3-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="576f3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="576f3-107">Syntax</span></span>

<span data-ttu-id="576f3-108">In den folgenden Beispielen wird die anonyme Daten Satz Syntax veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="576f3-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="576f3-109">Elemente, die als `[item]` getrennt sind, sind optional.</span><span class="sxs-lookup"><span data-stu-id="576f3-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="576f3-110">Grundlegende Verwendung</span><span class="sxs-lookup"><span data-stu-id="576f3-110">Basic usage</span></span>

<span data-ttu-id="576f3-111">Anonyme Datensätze werden am besten als F# Daten Satz Typen betrachtet, die vor der Instanziierung nicht deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="576f3-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="576f3-112">Hier finden Sie beispielsweise Informationen zum interagieren mit einer Funktion, die einen anonymen Datensatz erzeugt:</span><span class="sxs-lookup"><span data-stu-id="576f3-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

<span data-ttu-id="576f3-113">Im folgenden Beispiel wird das vorherige mit einer `printCircleStats` Funktion erweitert, die einen anonymen Datensatz als Eingabe annimmt:</span><span class="sxs-lookup"><span data-stu-id="576f3-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let printCircleStats r (stats: {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

<span data-ttu-id="576f3-114">Das Aufrufen von `printCircleStats` mit anonymen Daten Satz Typen, die nicht die gleiche Form aufweisen wie der Eingabetyp, kann nicht kompiliert werden:</span><span class="sxs-lookup"><span data-stu-id="576f3-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="576f3-115">Anonyme Strukturdaten Sätze</span><span class="sxs-lookup"><span data-stu-id="576f3-115">Struct anonymous records</span></span>

<span data-ttu-id="576f3-116">Anonyme Datensätze können auch als struct mit dem optionalen `struct`-Schlüsselwort definiert werden.</span><span class="sxs-lookup"><span data-stu-id="576f3-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="576f3-117">Im folgenden Beispiel wird die vorherige Struktur durch Erstellen und Verwenden eines anonymen Struktur-Datensatzes erweitert:</span><span class="sxs-lookup"><span data-stu-id="576f3-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    // Note that the keyword comes before the '{| |}' brace pair
    struct {| Area = a; Circumference = c; Diameter = d |}

// the 'struct' keyword also comes before the '{| |}' brace pair when declaring the parameter type
let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

let r = 2.0
let stats = getCircleStats r
printCircleStats r stats
```

### <a name="structness-inference"></a><span data-ttu-id="576f3-118">Struktur Rückschluss</span><span class="sxs-lookup"><span data-stu-id="576f3-118">Structness inference</span></span>

<span data-ttu-id="576f3-119">Die anonymen Struktur-Datensätze ermöglichen auch "structness Inference", wobei Sie das `struct`-Schlüsselwort nicht an der aufrufssite angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="576f3-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="576f3-120">In diesem Beispiel entfernen Sie das `struct`-Schlüsselwort, wenn Sie `printCircleStats`aufrufen:</span><span class="sxs-lookup"><span data-stu-id="576f3-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="576f3-121">Das umgekehrte Muster: beim angeben `struct`, wenn der Eingabetyp kein der anonyme Struktur-Datensatz ist, kann nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="576f3-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="576f3-122">Einbetten anonymer Datensätze in andere Typen</span><span class="sxs-lookup"><span data-stu-id="576f3-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="576f3-123">Es ist hilfreich, Unterscheidungs- [Unions](discriminated-unions.md) zu deklarieren, deren Fälle Datensätze sind.</span><span class="sxs-lookup"><span data-stu-id="576f3-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="576f3-124">Wenn die Daten in den Datensätzen jedoch denselben Typ wie die Unterscheidungs-Union haben, müssen Sie alle Typen als gegenseitig rekursiv definieren.</span><span class="sxs-lookup"><span data-stu-id="576f3-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="576f3-125">Diese Einschränkung wird durch die Verwendung anonymer Datensätze vermieden.</span><span class="sxs-lookup"><span data-stu-id="576f3-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="576f3-126">Dabei handelt es sich um einen Beispieltyp und eine Funktion, die mit dem Muster übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="576f3-126">What follows is an example type and function that pattern matches over it:</span></span>

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named for Manager and Executive would require mutually recursive definitions.
type Employee =
    | Engineer of FullName
    | Manager of {| Name: FullName; Reports: Employee list |}
    | Executive of {| Name: FullName; Reports: Employee list; Assistant: Employee |}

let getFirstName e =
    match e with
    | Engineer fullName -> fullName.FirstName
    | Manager m -> m.Name.FirstName
    | Executive ex -> ex.Name.FirstName
```

## <a name="copy-and-update-expressions"></a><span data-ttu-id="576f3-127">Copy-und Update-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="576f3-127">Copy and update expressions</span></span>

<span data-ttu-id="576f3-128">Anonyme Datensätze unterstützen die Erstellung mit [Kopier-und Update Ausdrücken](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="576f3-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="576f3-129">So können Sie z. b. eine neue Instanz eines anonymen Datensatzes erstellen, der die Daten eines vorhandenen Datensatzes kopiert:</span><span class="sxs-lookup"><span data-stu-id="576f3-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="576f3-130">Im Gegensatz zu benannten Datensätzen können Sie mit anonymen Datensätzen jedoch ganz unterschiedliche Formulare mit Kopier-und Update Ausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="576f3-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="576f3-131">Im folgenden Beispiel wird derselbe anonyme Datensatz aus dem vorherigen Beispiel angenommen und in einen neuen anonymen Datensatz erweitert:</span><span class="sxs-lookup"><span data-stu-id="576f3-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="576f3-132">Es ist auch möglich, anonyme Datensätze aus Instanzen benannter Datensätze zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="576f3-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="576f3-133">Sie können auch Daten in und aus Verweis-und Struktur anonymen Datensätzen kopieren:</span><span class="sxs-lookup"><span data-stu-id="576f3-133">You can also copy data to and from reference and struct anonymous records:</span></span>

```fsharp
// Copy data from a reference record into a struct anonymous record
type R1 = { X: int }
let r1 = { X = 1 }

let data1 = struct {| r1 with Y = 1 |}

// Copy data from a struct record into a reference anonymous record
[<Struct>]
type R2 = { X: int }
let r2 = { X = 1 }

let data2 = {| r1 with Y = 1 |}

// Copy the reference anonymous record data into a struct anonymous record
let data3 = struct {| data2 with Z = r2.X |}
```

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="576f3-134">Eigenschaften anonymer Datensätze</span><span class="sxs-lookup"><span data-stu-id="576f3-134">Properties of anonymous records</span></span>

<span data-ttu-id="576f3-135">Anonyme Datensätze verfügen über eine Reihe von Merkmalen, die für ein vollständiges Verständnis der Verwendung von verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="576f3-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="576f3-136">Anonyme Datensätze sind nominell</span><span class="sxs-lookup"><span data-stu-id="576f3-136">Anonymous records are nominal</span></span>

<span data-ttu-id="576f3-137">Anonyme Datensätze sind [Nominale Typen](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="576f3-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="576f3-138">Sie sind am besten als benannte [Daten Satz](records.md) Typen (auch nominale), für die keine vorabdeklaration erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="576f3-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="576f3-139">Beachten Sie das folgende Beispiel mit zwei anonymen Daten Satz Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="576f3-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="576f3-140">Die Werte für `x` und `y` haben unterschiedliche Typen und sind nicht miteinander kompatibel.</span><span class="sxs-lookup"><span data-stu-id="576f3-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="576f3-141">Sie sind nicht gleich stellbar und nicht vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="576f3-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="576f3-142">Um dies zu veranschaulichen, sollten Sie eine benannte Daten Satz Entsprechung beachten:</span><span class="sxs-lookup"><span data-stu-id="576f3-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="576f3-143">Es gibt keine Unterschiede zu anonymen Datensätzen, wenn Sie mit ihren benannten Daten Satz Entsprechungen verglichen werden, wenn die typäquivalenz oder der Vergleich vorliegt.</span><span class="sxs-lookup"><span data-stu-id="576f3-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="576f3-144">Anonyme Datensätze verwenden strukturelle Gleichheit und Vergleich</span><span class="sxs-lookup"><span data-stu-id="576f3-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="576f3-145">Ebenso wie Daten Satz Typen sind anonyme Datensätze strukturell gleich und vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="576f3-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="576f3-146">Dies gilt nur, wenn alle konstituierenden Typen Gleichheit und Vergleich unterstützen, wie z. b. Daten Satz Typen.</span><span class="sxs-lookup"><span data-stu-id="576f3-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="576f3-147">Um Gleichheit oder Vergleiche zu unterstützen, müssen zwei anonyme Datensätze die gleiche Form aufweisen.</span><span class="sxs-lookup"><span data-stu-id="576f3-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="576f3-148">Anonyme Datensätze sind serialisierbar.</span><span class="sxs-lookup"><span data-stu-id="576f3-148">Anonymous records are serializable</span></span>

<span data-ttu-id="576f3-149">Sie können anonyme Datensätze genauso wie mit benannten Datensätzen serialisieren.</span><span class="sxs-lookup"><span data-stu-id="576f3-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="576f3-150">Hier ist ein Beispiel für die Verwendung von " [newtonsoft. JSON](https://www.nuget.org/packages/Newtonsoft.Json/)":</span><span class="sxs-lookup"><span data-stu-id="576f3-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="576f3-151">Anonyme Datensätze sind nützlich, um Lightweight-Daten über ein Netzwerk zu senden, ohne dass Sie vorab eine Domäne für die serialisierten/deserialisierten Typen definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="576f3-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="576f3-152">Anonyme Datensätze interagieren mit C# anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="576f3-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="576f3-153">Es ist möglich, eine .NET-API zu verwenden, die die Verwendung [ C# anonymer Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)erfordert.</span><span class="sxs-lookup"><span data-stu-id="576f3-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="576f3-154">C#anonyme Typen sind trivial für die Interoperabilität mit mithilfe anonymer Datensätze.</span><span class="sxs-lookup"><span data-stu-id="576f3-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="576f3-155">Im folgenden Beispiel wird gezeigt, wie anonyme Datensätze verwendet werden, um eine [LINQ](../../csharp/programming-guide/concepts/linq/index.md) -Überladung aufzurufen, die einen anonymen Typ erfordert:</span><span class="sxs-lookup"><span data-stu-id="576f3-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="576f3-156">Es gibt zahlreiche andere APIs, die in .NET verwendet werden und die Verwendung der Übergabe eines anonymen Typs erfordern.</span><span class="sxs-lookup"><span data-stu-id="576f3-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="576f3-157">Anonyme Datensätze sind das Tool für die Arbeit mit Ihnen.</span><span class="sxs-lookup"><span data-stu-id="576f3-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="576f3-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="576f3-158">Limitations</span></span>

<span data-ttu-id="576f3-159">Für anonyme Datensätze gelten einige Einschränkungen bei der Verwendung.</span><span class="sxs-lookup"><span data-stu-id="576f3-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="576f3-160">Einige sind in Ihrem Design verankert, andere können jedoch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="576f3-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="576f3-161">Einschränkungen bei der Muster Übereinstimmung</span><span class="sxs-lookup"><span data-stu-id="576f3-161">Limitations with pattern matching</span></span>

<span data-ttu-id="576f3-162">Anonyme Datensätze unterstützen im Gegensatz zu benannten Datensätzen keinen Musterabgleich.</span><span class="sxs-lookup"><span data-stu-id="576f3-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="576f3-163">Es gibt drei Gründe:</span><span class="sxs-lookup"><span data-stu-id="576f3-163">There are three reasons:</span></span>

1. <span data-ttu-id="576f3-164">Ein Muster muss jedes Feld eines anonymen Datensatzes berücksichtigen, anders als benannte Daten Satz Typen.</span><span class="sxs-lookup"><span data-stu-id="576f3-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="576f3-165">Dies liegt daran, dass anonyme Datensätze keine strukturelle unter Typisierung unterstützen – Sie sind Nominale Typen.</span><span class="sxs-lookup"><span data-stu-id="576f3-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="576f3-166">Aufgrund von (1) gibt es keine Möglichkeit, zusätzliche Muster in einem Muster Vergleichs Ausdruck zu haben, da jedes unterschiedliche Muster einen anderen anonymen Daten Satz Typ impliziert.</span><span class="sxs-lookup"><span data-stu-id="576f3-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="576f3-167">Aufgrund von (3) wären alle anonymen Daten Satzmuster ausführlicher als die Verwendung der "Punkt"-Notation.</span><span class="sxs-lookup"><span data-stu-id="576f3-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="576f3-168">Es gibt einen offenen sprach Vorschlag, um den Musterabgleich [in eingeschränkten Kontexten zuzulassen](https://github.com/fsharp/fslang-suggestions/issues/713).</span><span class="sxs-lookup"><span data-stu-id="576f3-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="576f3-169">Einschränkungen mit Veränderlichkeit</span><span class="sxs-lookup"><span data-stu-id="576f3-169">Limitations with mutability</span></span>

<span data-ttu-id="576f3-170">Es ist derzeit nicht möglich, einen anonymen Datensatz mit `mutable` Daten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="576f3-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="576f3-171">Es gibt einen [offenen sprach Vorschlag](https://github.com/fsharp/fslang-suggestions/issues/732) , um änderbare Daten zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="576f3-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="576f3-172">Einschränkungen mit anonymen Strukturdaten Sätzen</span><span class="sxs-lookup"><span data-stu-id="576f3-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="576f3-173">Es ist nicht möglich, die anonymen Strukturdaten Sätze als `IsByRefLike` oder `IsReadOnly`zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="576f3-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="576f3-174">Für `IsByRefLike` und `IsReadOnly` anonyme Datensätze ist ein [offener sprach Vorschlag](https://github.com/fsharp/fslang-suggestions/issues/712) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="576f3-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
