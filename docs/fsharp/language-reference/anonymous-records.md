---
title: Anonyme Datensätze
description: Informationen Sie zum Erstellen und anonyme Datensätze, eine Sprachfunktion, die mit der Bearbeitung von Daten unterstützen.
ms.date: 06/12/2019
ms.openlocfilehash: e576210d4fb76ccfd09f8feb157ef4542aa94ccf
ms.sourcegitcommit: c4dfe37032c64a1fba2cc3d5947550d79f95e3b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041804"
---
# <a name="anonymous-records"></a><span data-ttu-id="7637e-103">Anonyme Datensätze</span><span class="sxs-lookup"><span data-stu-id="7637e-103">Anonymous Records</span></span>

<span data-ttu-id="7637e-104">Anonyme Datensätze sind einfache Aggregate benannter Werte, die nicht vor der Verwendung deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7637e-104">Anonymous records are simple aggregates of named values that don't need to be declared before use.</span></span> <span data-ttu-id="7637e-105">Sie können diese als entweder Strukturen oder Verweistypen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="7637e-105">You can declare them as either structs or reference types.</span></span> <span data-ttu-id="7637e-106">Sie sind Verweistypen standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="7637e-106">They're reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="7637e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7637e-107">Syntax</span></span>

<span data-ttu-id="7637e-108">Die folgenden Beispiele veranschaulichen die Syntax für anonyme Datensatz.</span><span class="sxs-lookup"><span data-stu-id="7637e-108">The following examples demonstrate the anonymous record syntax.</span></span> <span data-ttu-id="7637e-109">Elemente wie Trennzeichen `[item]` sind optional.</span><span class="sxs-lookup"><span data-stu-id="7637e-109">Items delimited as `[item]` are optional.</span></span>

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a><span data-ttu-id="7637e-110">Grundlegende Verwendung</span><span class="sxs-lookup"><span data-stu-id="7637e-110">Basic usage</span></span>

<span data-ttu-id="7637e-111">Anonyme Datensätze werden am besten als betrachtet F# Eintragstypen, die nicht vor der Instanziierung deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7637e-111">Anonymous records are best thought of as F# record types that don't need to be declared before instantiation.</span></span>

<span data-ttu-id="7637e-112">Erzeugt z. B. wie Sie mit einer Funktion interagieren können hier, die einen anonymen-Eintrag:</span><span class="sxs-lookup"><span data-stu-id="7637e-112">For example, here how you can interact with a function that produces an anonymous record:</span></span>

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

<span data-ttu-id="7637e-113">Das folgende Beispiel baut auf dem vorherigen Beispiel mit einem `printCircleStats` -Funktion, einen anonyme Datensatz als Eingabe akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="7637e-113">The following example expands on the previous one with a `printCircleStats` function that takes an anonymous record as input:</span></span>

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

<span data-ttu-id="7637e-114">Aufrufen von `printCircleStats` mit jeder anonyme Datensatztyp, in denen die gleiche "Form" nicht wie der Eingabetyp nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="7637e-114">Calling `printCircleStats` with any anonymous record type that doesn't have the same "shape" as the input type will fail to compile:</span></span>

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a><span data-ttu-id="7637e-115">Anonyme Struktur-Datensätze</span><span class="sxs-lookup"><span data-stu-id="7637e-115">Struct anonymous records</span></span>

<span data-ttu-id="7637e-116">Anonyme Datensätze können auch festgelegt werden, als Struktur mit dem optionalen `struct` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7637e-116">Anonymous records can also be defined as struct with the optional `struct` keyword.</span></span> <span data-ttu-id="7637e-117">Im folgende Beispiel erweitert das vorherige Beispiel von erzeugen und nutzen einen anonyme Struktur-Eintrag:</span><span class="sxs-lookup"><span data-stu-id="7637e-117">The following example augments the previous one by producing and consuming a struct anonymous record:</span></span>

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

### <a name="structness-inference"></a><span data-ttu-id="7637e-118">Structness Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="7637e-118">Structness inference</span></span>

<span data-ttu-id="7637e-119">Anonyme Struktur-Datensätze auch zulassen "Structness Typrückschluss", in dem Sie müssen nicht an die `struct` Schlüsselwort an der Aufrufsite.</span><span class="sxs-lookup"><span data-stu-id="7637e-119">Struct anonymous records also allow for "structness inference" where you do not need to specify the `struct` keyword at the call site.</span></span> <span data-ttu-id="7637e-120">In diesem Beispiel ist Sie elide der `struct` Schlüsselwort beim Aufrufen von `printCircleStats`:</span><span class="sxs-lookup"><span data-stu-id="7637e-120">In this example, you elide the `struct` keyword when calling `printCircleStats`:</span></span>

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

<span data-ttu-id="7637e-121">Das Gegenteil des Musters - Angabe `struct` fehl, wenn der Eingabetyp nicht um eine anonyme Struktur-Eintrags: ist zum Kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7637e-121">The reverse pattern - specifying `struct` when the input type is not a struct anonymous record - will fail to compile.</span></span>

## <a name="embedding-anonymous-records-within-other-types"></a><span data-ttu-id="7637e-122">Einbetten von anonymen Datensätze in andere Typen</span><span class="sxs-lookup"><span data-stu-id="7637e-122">Embedding anonymous records within other types</span></span>

<span data-ttu-id="7637e-123">Es ist sinnvoll, deklarieren Sie [Unterscheidungs-Unions](discriminated-unions.md) , dessen Fälle sind Datensätze.</span><span class="sxs-lookup"><span data-stu-id="7637e-123">It's useful to declare [discriminated unions](discriminated-unions.md) whose cases are records.</span></span> <span data-ttu-id="7637e-124">Aber wenn die Daten in den Datensätzen der gleiche Typ wie die Unterscheidungs-Union ist, müssen Sie alle Typen definieren, als sich gegenseitig rekursiv.</span><span class="sxs-lookup"><span data-stu-id="7637e-124">But if the data in the records is the same type as the discriminated union, you must define all types as mutually recursive.</span></span> <span data-ttu-id="7637e-125">Mit anonymen Datensätze vermeidet diese Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="7637e-125">Using anonymous records avoids this restriction.</span></span> <span data-ttu-id="7637e-126">Im folgenden ist ein Beispiel für Typ und Funktion dieses Muster entspricht, darüber:</span><span class="sxs-lookup"><span data-stu-id="7637e-126">What follows is an example type and function that pattern matches over it:</span></span>

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

## <a name="copy-and-update-expressions"></a><span data-ttu-id="7637e-127">Kopieren und Aktualisieren von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="7637e-127">Copy and update expressions</span></span>

<span data-ttu-id="7637e-128">Anonyme Datensätzen unterstützen die Erstellung mit [kopieren und aktualisieren Sie die Ausdrücke](copy-and-update-record-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7637e-128">Anonymous records support construction with [copy and update expressions](copy-and-update-record-expressions.md).</span></span> <span data-ttu-id="7637e-129">Beispielsweise sieht wie Sie eine neue Instanz eines anonymen Datensatzes erstellen können, die kopiert eine vorhandene aus der Daten:</span><span class="sxs-lookup"><span data-stu-id="7637e-129">For example, here's how you can construct a new instance of an anonymous record that copies an existing one's data:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

<span data-ttu-id="7637e-130">Im Gegensatz zu benannten Datensätze können anonyme Datensätze Sie ganz unterschiedliche Formen mit Kopie erstellen und Aktualisieren von Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="7637e-130">However, unlike named records, anonymous records allow you to construct entirely different forms with copy and update expressions.</span></span> <span data-ttu-id="7637e-131">Im folgenden Beispiel wird den gleiche anonyme Datensatz aus dem vorherigen Beispiel und erweitert er in einen neuen anonymen Datensatz:</span><span class="sxs-lookup"><span data-stu-id="7637e-131">The follow example takes the same anonymous record from the previous example and expands it into a new anonymous record:</span></span>

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

<span data-ttu-id="7637e-132">Es ist auch möglich, anonyme Datensätze aus Instanzen von benannten Datensätze zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7637e-132">It is also possible to construct anonymous records from instances of named records:</span></span>

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

<span data-ttu-id="7637e-133">Sie können auch Daten in und aus Verweis und Struktur anonyme Datensätze kopieren:</span><span class="sxs-lookup"><span data-stu-id="7637e-133">You can also copy data to and from reference and struct anonymous records:</span></span>

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

## <a name="properties-of-anonymous-records"></a><span data-ttu-id="7637e-134">Eigenschaften des anonymen Datensätze</span><span class="sxs-lookup"><span data-stu-id="7637e-134">Properties of anonymous records</span></span>

<span data-ttu-id="7637e-135">Anonyme Datensätze haben es sich um eine Reihe von Eigenschaften, die wesentlich für dessen vollständig zu verstehen, wie sie verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7637e-135">Anonymous records have a number of characteristics that are essential to fully understanding how they can be used.</span></span>

### <a name="anonymous-records-are-nominal"></a><span data-ttu-id="7637e-136">Anonyme Datensätze sind geringe</span><span class="sxs-lookup"><span data-stu-id="7637e-136">Anonymous records are nominal</span></span>

<span data-ttu-id="7637e-137">Anonyme Datensätze sind [Nominale Typen](https://en.wikipedia.org/wiki/Nominal_type_system).</span><span class="sxs-lookup"><span data-stu-id="7637e-137">Anonymous records are [nominal types](https://en.wikipedia.org/wiki/Nominal_type_system).</span></span> <span data-ttu-id="7637e-138">Sie sind bewährte Gedanken, wie mit dem Namen [Datensatz](records.md) Typen (die auch nominale sind), die nicht die Deklaration ein Investitionen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7637e-138">They are best thought as named [record](records.md) types (which are also nominal) that do not require an up-front declaration.</span></span>

<span data-ttu-id="7637e-139">Betrachten Sie das folgende Beispiel mit zwei Deklarationen von anonymen Datensatz:</span><span class="sxs-lookup"><span data-stu-id="7637e-139">Consider the following example with two anonymous record declarations:</span></span>

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

<span data-ttu-id="7637e-140">Die `x` und `y` Werte verschiedene Typen aufweisen und nicht miteinander kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="7637e-140">The `x` and `y` values have different types and are not compatible with one another.</span></span> <span data-ttu-id="7637e-141">Sie sind nicht gleichwertige, und sie sind nicht vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="7637e-141">They are not equatable and they are not comparable.</span></span> <span data-ttu-id="7637e-142">Um dies zu veranschaulichen, betrachten Sie einen benannten Eintrag entspricht:</span><span class="sxs-lookup"><span data-stu-id="7637e-142">To illustrate this, consider a named record equivalent:</span></span>

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

<span data-ttu-id="7637e-143">Es gibt keine irgendetwas grundsätzlich über anonyme Datensätze bei den entsprechenden benannten Eintrag verglichen wird, wenn der Typ Äquivalenz oder der Vergleichsspalte zu.</span><span class="sxs-lookup"><span data-stu-id="7637e-143">There isn't anything inherently different about anonymous records when compared with their named record equivalents when concerning type equivalency or comparison.</span></span>

### <a name="anonymous-records-use-structural-equality-and-comparison"></a><span data-ttu-id="7637e-144">Anonyme Datensätze verwenden, strukturelle Gleichheit und Vergleich</span><span class="sxs-lookup"><span data-stu-id="7637e-144">Anonymous records use structural equality and comparison</span></span>

<span data-ttu-id="7637e-145">Wie Record-Typen werden anonyme Datensätze strukturell gleichwertige und vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="7637e-145">Like record types, anonymous records are structurally equatable and comparable.</span></span> <span data-ttu-id="7637e-146">Dies ist nur true, wenn alle enthaltenen Typen Gleichheits- und Vergleichsoperatoren, wie mit Record-Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7637e-146">This is only true if all constituent types support equality and comparison, like with record types.</span></span> <span data-ttu-id="7637e-147">Um auf Gleichheit oder Vergleich zu unterstützen, müssen zwei anonyme Datensätze die gleiche "Form".</span><span class="sxs-lookup"><span data-stu-id="7637e-147">To support equality or comparison, two anonymous records must have the same "shape".</span></span>

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a><span data-ttu-id="7637e-148">Anonyme Datensätze sind serialisierbar</span><span class="sxs-lookup"><span data-stu-id="7637e-148">Anonymous records are serializable</span></span>

<span data-ttu-id="7637e-149">Sie können anonyme Datensätze serialisieren, ebenso wie mit benannten Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="7637e-149">You can serialize anonymous records just as you can with named records.</span></span> <span data-ttu-id="7637e-150">Es folgt ein Beispiel mit ["newtonsoft.JSON"](https://www.nuget.org/packages/Newtonsoft.Json/):</span><span class="sxs-lookup"><span data-stu-id="7637e-150">Here is an example using [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):</span></span>

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

<span data-ttu-id="7637e-151">Anonyme Datensätze sind nützlich für das Senden von geringe Menge von Daten über ein Netzwerk, ohne dass eine Domäne für die Typen für serialisiert bzw. deserialisiert wurden vorab definieren.</span><span class="sxs-lookup"><span data-stu-id="7637e-151">Anonymous records are useful for sending lightweight data over a network without the need to define a domain for your serialized/deserialized types up front.</span></span>

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a><span data-ttu-id="7637e-152">Anonyme Datensätze Interoperabilität mit C# anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="7637e-152">Anonymous records interoperate with C# anonymous types</span></span>

<span data-ttu-id="7637e-153">Es ist möglich, eine .NET API verwenden, die die Verwendung von erfordert [ C# anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="7637e-153">It is possible to use a .NET API that requires the use of [C# anonymous types](../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span> <span data-ttu-id="7637e-154">C#anonyme Typen sind einfach, die über anonyme Datensätze mit zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7637e-154">C# anonymous types are trivial to interoperate with by using anonymous records.</span></span> <span data-ttu-id="7637e-155">Das folgende Beispiel zeigt, wie Sie anonyme Datensätze verwenden, um das Aufrufen einer [LINQ](../../csharp/programming-guide/concepts/linq/index.md) Überladung, die einen anonymen Typ ist erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7637e-155">The following example shows how to use anonymous records to call a [LINQ](../../csharp/programming-guide/concepts/linq/index.md) overload that requires an anonymous type:</span></span>

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

<span data-ttu-id="7637e-156">Es gibt eine Vielzahl von anderen APIs in .NET verwendet, die Übergabe eines anonymen Typs erfordern.</span><span class="sxs-lookup"><span data-stu-id="7637e-156">There are a multitude of other APIs used throughout .NET that require the use of passing in an anonymous type.</span></span> <span data-ttu-id="7637e-157">Anonyme Datensätze sind Ihr Tool für die Arbeit mit ihnen.</span><span class="sxs-lookup"><span data-stu-id="7637e-157">Anonymous records are your tool for working with them.</span></span>

## <a name="limitations"></a><span data-ttu-id="7637e-158">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7637e-158">Limitations</span></span>

<span data-ttu-id="7637e-159">Anonyme Datensätze sind einige Einschränkungen, in deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="7637e-159">Anonymous records have some restrictions in their usage.</span></span> <span data-ttu-id="7637e-160">Einige sind Bestandteil der videomonitore, andere dagegen offener gegenüber Änderungen.</span><span class="sxs-lookup"><span data-stu-id="7637e-160">Some are inherent to their design, but others are amenable to change.</span></span>

### <a name="limitations-with-pattern-matching"></a><span data-ttu-id="7637e-161">Einschränkungen mit Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="7637e-161">Limitations with pattern matching</span></span>

<span data-ttu-id="7637e-162">Mustervergleich, im Gegensatz zu Datensätzen mit benannten unterstützt anonyme Datensätze nicht.</span><span class="sxs-lookup"><span data-stu-id="7637e-162">Anonymous records do not support pattern matching, unlike named records.</span></span> <span data-ttu-id="7637e-163">Es gibt drei Gründe:</span><span class="sxs-lookup"><span data-stu-id="7637e-163">There are three reasons:</span></span>

1. <span data-ttu-id="7637e-164">Ein Muster müssten für jedes Feld eines anonymen-Datensatzes, im Gegensatz zu benannten Datensatztypen berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="7637e-164">A pattern would have to account for every field of an anonymous record, unlike named record types.</span></span> <span data-ttu-id="7637e-165">Dies ist da anonyme Datensätze nicht die strukturellen Untertypen unterstützen – sie Nominale Typen sind.</span><span class="sxs-lookup"><span data-stu-id="7637e-165">This is because anonymous records do not support structural subtyping – they are nominal types.</span></span>
2. <span data-ttu-id="7637e-166">Wegen (1) gibt es keine Möglichkeit, zusätzliche Mustern in einem Vergleichsausdruck Muster, da jede unterschiedliches Muster für einen anderen anonyme Datensatztyp nahelegt.</span><span class="sxs-lookup"><span data-stu-id="7637e-166">Because of (1), there is no ability to have additional patterns in a pattern match expression, as each distinct pattern would imply a different anonymous record type.</span></span>
3. <span data-ttu-id="7637e-167">Aufgrund von (3) wäre anonymen Datensatzmuster ausführlicher als die Verwendung der Schreibweise von "Punkt".</span><span class="sxs-lookup"><span data-stu-id="7637e-167">Because of (3), any anonymous record pattern would be more verbose than the use of “dot” notation.</span></span>

<span data-ttu-id="7637e-168">Es ist eine open Language Vorschlag, [ermöglichen Musterabgleich in begrenzte Kontexte](https://github.com/fsharp/fslang-suggestions/issues/713).</span><span class="sxs-lookup"><span data-stu-id="7637e-168">There is an open language suggestion to [allow pattern matching in limited contexts](https://github.com/fsharp/fslang-suggestions/issues/713).</span></span>

### <a name="limitations-with-mutability"></a><span data-ttu-id="7637e-169">Einschränkungen im Zusammenhang mit Veränderlichkeit</span><span class="sxs-lookup"><span data-stu-id="7637e-169">Limitations with mutability</span></span>

<span data-ttu-id="7637e-170">Es ist nicht aktuell möglich ist, definieren Sie einen anonyme Datensatz mit `mutable` Daten.</span><span class="sxs-lookup"><span data-stu-id="7637e-170">It is not currently possible to define an anonymous record with `mutable` data.</span></span> <span data-ttu-id="7637e-171">Gibt es eine [öffnen Sprache Vorschlag](https://github.com/fsharp/fslang-suggestions/issues/732) um änderbare Daten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7637e-171">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/732) to allow mutable data.</span></span>

### <a name="limitations-with-struct-anonymous-records"></a><span data-ttu-id="7637e-172">Einschränkungen im Zusammenhang mit einer anonymen Struktur-Datensätze</span><span class="sxs-lookup"><span data-stu-id="7637e-172">Limitations with struct anonymous records</span></span>

<span data-ttu-id="7637e-173">Es ist nicht möglich, die Struktur anonyme Datensätze als deklarieren `IsByRefLike` oder `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="7637e-173">It is not possible to declare struct anonymous records as `IsByRefLike` or `IsReadOnly`.</span></span> <span data-ttu-id="7637e-174">Gibt es eine [Sprache Vorschlag öffnen](https://github.com/fsharp/fslang-suggestions/issues/712) zu für `IsByRefLike` und `IsReadOnly` anonyme Datensätze.</span><span class="sxs-lookup"><span data-stu-id="7637e-174">There is an [open language suggestion](https://github.com/fsharp/fslang-suggestions/issues/712) to for `IsByRefLike` and `IsReadOnly` anonymous records.</span></span>
