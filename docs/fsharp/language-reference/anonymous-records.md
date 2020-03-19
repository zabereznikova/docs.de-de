---
title: Anonyme Datensätze
description: Erfahren Sie, wie Sie das Erstellen und Verwenden von anonymen Datensätzen verwenden, eine Sprachfunktion, die bei der Bearbeitung von Daten hilft.
ms.date: 06/12/2019
ms.openlocfilehash: ef3aa8fccdb6ff406542932816e4138040845a59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187491"
---
# <a name="anonymous-records"></a><span data-ttu-id="51ffd-103">Anonyme Datensätze</span><span class="sxs-lookup"><span data-stu-id="51ffd-103">Anonymous Records</span></span>

<span data-ttu-id="51ffd-104">Anonyme Datensätze sind einfache Aggregate benannter Werte, die vor der Verwendung nicht deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="51ffd-105">Sie können sie entweder als Strukturen oder als Verweistypen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="51ffd-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="51ffd-106">Sie sind standardmäßig Referenztypen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="51ffd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="51ffd-107">Syntax</span></span>

<span data-ttu-id="51ffd-108">Die folgenden Beispiele veranschaulichen die Syntax für anonyme Aufzeichnungen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="51ffd-109">Elemente, die `[item]` als optional getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="51ffd-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="51ffd-110">Grundlegende Verwendung</span><span class="sxs-lookup"><span data-stu-id="51ffd-110">Basic usage</span></span>

<span data-ttu-id="51ffd-111">Anonyme Datensätze werden am besten als Datensatztypen von F- datensätzen betrachtet, die nicht vor der Instanziierung deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="51ffd-112">Hier erfahren Sie beispielsweise, wie Sie mit einer Funktion interagieren können, die einen anonymen Datensatz erstellt:</span><span class="sxs-lookup"><span data-stu-id="51ffd-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="51ffd-113">Im folgenden Beispiel wird das vorherige `printCircleStats` Mit einer Funktion erweitert, die einen anonymen Datensatz als Eingabe verwendet:</span><span class="sxs-lookup"><span data-stu-id="51ffd-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="51ffd-114">Wenn `printCircleStats` Sie einen anonymen Datensatztyp aufrufen, der nicht die gleiche "Form" wie der Eingabetyp hat, kann nicht kompiliert werden:</span><span class="sxs-lookup"><span data-stu-id="51ffd-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="51ffd-115">Strukturieren anonymer Datensätze</span><span class="sxs-lookup"><span data-stu-id="51ffd-115">Struct anonymous records</span></span>

<span data-ttu-id="51ffd-116">Anonyme Datensätze können auch als `struct` struct mit dem optionalen Schlüsselwort definiert werden.</span><span class="sxs-lookup"><span data-stu-id="51ffd-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="51ffd-117">Im folgenden Beispiel wird das vorherige Beispiel durch das Erstellen und Verwenden eines anonymen Strukturdatensatzes erweitert:</span><span class="sxs-lookup"><span data-stu-id="51ffd-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="51ffd-118">Strukturrückschluss</span><span class="sxs-lookup"><span data-stu-id="51ffd-118">Structness inference</span></span>

<span data-ttu-id="51ffd-119">Anonyme Datensätze strukturieren lassen auch "Strukturrückschluss" zu, `struct` bei dem Sie das Schlüsselwort auf der Aufrufsite nicht angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="51ffd-120">In diesem Beispiel entschlüsseln Sie das `struct` Schlüsselwort beim Aufrufen `printCircleStats`von:</span><span class="sxs-lookup"><span data-stu-id="51ffd-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="51ffd-121">Das umgekehrte Muster `struct` , das angibt, wann der Eingabetyp kein anonymer Strukturdatensatz ist - kann nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="51ffd-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="51ffd-122">Einbetten anonymer Datensätze in andere Typen</span><span class="sxs-lookup"><span data-stu-id="51ffd-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="51ffd-123">Es ist nützlich, diskriminierte Gewerkschaften zu [deklarieren,](discriminated-unions.md) deren Fälle Datensätze sind.</span><span class="sxs-lookup"><span data-stu-id="51ffd-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="51ffd-124">Wenn die Daten in den Datensätzen jedoch den gleichen Typ wie die diskriminierte Union aufweisen, müssen Sie alle Typen als gegenseitig rekursiv definieren.</span><span class="sxs-lookup"><span data-stu-id="51ffd-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="51ffd-125">Durch die Verwendung anonymer Datensätze wird diese Einschränkung vermieden.</span><span class="sxs-lookup"><span data-stu-id="51ffd-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="51ffd-126">Was folgt, ist ein Beispieltyp und eine Funktion, die muster darüber übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="51ffd-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="51ffd-127">Kopieren und Aktualisieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="51ffd-127">Copy and update expressions</span></span>

<span data-ttu-id="51ffd-128">Anonyme Datensätze unterstützen die Konstruktion mit [Kopier- und Aktualisierungsausdrücken](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="51ffd-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="51ffd-129">So können Sie z. B. eine neue Instanz eines anonymen Datensatzes erstellen, die die Daten eines vorhandenen Datensatzes kopiert:</span><span class="sxs-lookup"><span data-stu-id="51ffd-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="51ffd-130">Im Gegensatz zu benannten Datensätzen können Sie jedoch mit anonymen Datensätzen völlig unterschiedliche Formulare mit Kopier- und Aktualisierungsausdrücken erstellen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="51ffd-131">Das folgende Beispiel nimmt denselben anonymen Datensatz aus dem vorherigen Beispiel und erweitert ihn in einen neuen anonymen Datensatz:</span><span class="sxs-lookup"><span data-stu-id="51ffd-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="51ffd-132">Es ist auch möglich, anonyme Datensätze aus Instanzen benannter Datensätze zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="51ffd-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="51ffd-133">Sie können auch Daten in und aus anonymen Datensätzen kopieren und strukturieren:</span><span class="sxs-lookup"><span data-stu-id="51ffd-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="51ffd-134">Eigenschaften anonymer Datensätze</span><span class="sxs-lookup"><span data-stu-id="51ffd-134">Properties of anonymous records</span></span>

<span data-ttu-id="51ffd-135">Anonyme Datensätze weisen eine Reihe von Merkmalen auf, die für das vollständige Verständnis ihrer Verwendung unerlässlich sind.</span><span class="sxs-lookup"><span data-stu-id="51ffd-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="51ffd-136">Anonyme Datensätze sind nominell</span><span class="sxs-lookup"><span data-stu-id="51ffd-136">Anonymous records are nominal</span></span>

<span data-ttu-id="51ffd-137">Anonyme Datensätze sind [nominale Typen](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="51ffd-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="51ffd-138">Sie sind am besten als benannte [Datensatztypen](records.md) (die auch nominal sind) gedacht, die keine Vorabdeklaration erfordern.</span><span class="sxs-lookup"><span data-stu-id="51ffd-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="51ffd-139">Betrachten Sie das folgende Beispiel mit zwei anonymen Datensatzdeklarationen:</span><span class="sxs-lookup"><span data-stu-id="51ffd-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="51ffd-140">Die `x` `y` und-Werte haben unterschiedliche Typen und sind nicht miteinander kompatibel.</span><span class="sxs-lookup"><span data-stu-id="51ffd-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="51ffd-141">Sie sind nicht gleichsam und nicht vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="51ffd-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="51ffd-142">Um dies zu veranschaulichen, sollten Sie ein benanntes Datensatzäquivalent in Betracht ziehen:</span><span class="sxs-lookup"><span data-stu-id="51ffd-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="51ffd-143">Es gibt nichts von Natur aus anders über anonyme Datensätze im Vergleich zu ihren benannten Datensatzäquivalenten, wenn es um Typäquivalenz oder Vergleich.</span><span class="sxs-lookup"><span data-stu-id="51ffd-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="51ffd-144">Anonyme Datensätze verwenden strukturelle Gleichheit und Vergleich</span><span class="sxs-lookup"><span data-stu-id="51ffd-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="51ffd-145">Wie Datensatztypen sind anonyme Datensätze strukturell gleichsam und vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="51ffd-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="51ffd-146">Dies gilt nur, wenn alle komponentenden Typen Gleichheit und Vergleich unterstützen, wie bei Datensatztypen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="51ffd-147">Um Gleichheit oder Vergleich zu unterstützen, müssen zwei anonyme Datensätze dieselbe "Form" haben.</span><span class="sxs-lookup"><span data-stu-id="51ffd-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="51ffd-148">Anonyme Datensätze sind serialisierbar</span><span class="sxs-lookup"><span data-stu-id="51ffd-148">Anonymous records are serializable</span></span>

<span data-ttu-id="51ffd-149">Sie können anonyme Datensätze genauso serialisieren wie mit benannten Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="51ffd-150">Hier ist ein Beispiel mit [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="51ffd-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="51ffd-151">Anonyme Datensätze sind nützlich, um einfache Daten über ein Netzwerk zu senden, ohne dass sie eine Domäne für Ihre serialisierten/deserialisierten Typen im Voraus definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="51ffd-152">Anonyme Datensätze arbeiten mit anonymen C-Typen zusammen</span><span class="sxs-lookup"><span data-stu-id="51ffd-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="51ffd-153">Es ist möglich, eine .NET-API zu verwenden, die die Verwendung [anonymer C-Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)erfordert.</span><span class="sxs-lookup"><span data-stu-id="51ffd-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="51ffd-154">Anonyme Typen von C-Code sind trivial, mit denen sie mithilfe anonymer Datensätze zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="51ffd-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="51ffd-155">Das folgende Beispiel zeigt, wie sie anonyme Datensätze verwenden, um eine [LINQ-Überladung](../../csharp/programming-guide/concepts/linq/index.md) aufzurufen, die einen anonymen Typ erfordert:</span><span class="sxs-lookup"><span data-stu-id="51ffd-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="51ffd-156">Es gibt eine Vielzahl anderer APIs, die in .NET verwendet werden und die Dieverwendung in einem anonymen Typ erfordern.</span><span class="sxs-lookup"><span data-stu-id="51ffd-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="51ffd-157">Anonyme Datensätze sind Ihr Werkzeug, um mit ihnen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="51ffd-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="51ffd-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="51ffd-158">Limitations</span></span>

<span data-ttu-id="51ffd-159">Anonyme Datensätze haben einige Einschränkungen in ihrer Verwendung.</span><span class="sxs-lookup"><span data-stu-id="51ffd-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="51ffd-160">Einige sind ihrem Design inhärent, andere sind für Veränderungen geeignet.</span><span class="sxs-lookup"><span data-stu-id="51ffd-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="51ffd-161">Einschränkungen bei Musterübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="51ffd-161">Limitations with pattern matching</span></span>

<span data-ttu-id="51ffd-162">Anonyme Datensätze unterstützen im Gegensatz zu benannten Datensätzen keine Musterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="51ffd-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="51ffd-163">Es gibt drei Gründe:</span><span class="sxs-lookup"><span data-stu-id="51ffd-163">There are three reasons:</span></span>

1. <span data-ttu-id="51ffd-164">Ein Muster müsste für jedes Feld eines anonymen Datensatzes berücksichtigt werden, im Gegensatz zu benannten Datensatztypen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="51ffd-165">Dies liegt daran, dass anonyme Datensätze keine strukturelle Untertypisierung unterstützen – sie sind nominale Typen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="51ffd-166">Aufgrund (1) gibt es keine Möglichkeit, zusätzliche Muster in einem Musterübereinstimmungsausdruck zu haben, da jedes einzelne Muster einen anderen anonymen Datensatztyp implizieren würde.</span><span class="sxs-lookup"><span data-stu-id="51ffd-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="51ffd-167">Aufgrund von (3) wäre jedes anonyme Datensatzmuster ausführlicher als die Verwendung der "Punkt"-Notation.</span><span class="sxs-lookup"><span data-stu-id="51ffd-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="51ffd-168">Es gibt einen Vorschlag für eine offene Sprache, um [musterabgleich in begrenzten Kontexten](https://github.com/fsharp/fslang-suggestions/issues/713)zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="51ffd-169">Einschränkungen bei der Veränderbarkeit</span><span class="sxs-lookup"><span data-stu-id="51ffd-169">Limitations with mutability</span></span>

<span data-ttu-id="51ffd-170">Derzeit ist es nicht möglich, `mutable` einen anonymen Datensatz mit Daten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="51ffd-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="51ffd-171">Es gibt einen [Vorschlag für eine offene Sprache,](https://github.com/fsharp/fslang-suggestions/issues/732) um veränderbare Daten zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="51ffd-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="51ffd-172">Einschränkungen bei anonymen Strukturdatensätzen</span><span class="sxs-lookup"><span data-stu-id="51ffd-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="51ffd-173">Es ist nicht möglich, anonyme Strukturen als `IsByRefLike` oder `IsReadOnly`zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="51ffd-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="51ffd-174">Es gibt einen Vorschlag `IsByRefLike` für `IsReadOnly` [offene Sprache](https://github.com/fsharp/fslang-suggestions/issues/712) für und anonyme Datensätze.</span><span class="sxs-lookup"><span data-stu-id="51ffd-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
