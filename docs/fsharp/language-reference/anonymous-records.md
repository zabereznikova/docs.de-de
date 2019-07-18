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
# <a name="anonymous-records"></a>Anonyme Datensätze

Anonyme Datensätze sind einfache Aggregate benannter Werte, die nicht vor der Verwendung deklariert werden müssen. Sie können diese als entweder Strukturen oder Verweistypen deklarieren. Sie sind Verweistypen standardmäßig.

## <a name="syntax"></a>Syntax

Die folgenden Beispiele veranschaulichen die Syntax für anonyme Datensatz. Elemente wie Trennzeichen `[item]` sind optional.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Grundlegende Verwendung

Anonyme Datensätze werden am besten als betrachtet F# Eintragstypen, die nicht vor der Instanziierung deklariert werden müssen.

Erzeugt z. B. wie Sie mit einer Funktion interagieren können hier, die einen anonymen-Eintrag:

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

Das folgende Beispiel baut auf dem vorherigen Beispiel mit einem `printCircleStats` -Funktion, einen anonyme Datensatz als Eingabe akzeptiert:

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

Aufrufen von `printCircleStats` mit jeder anonyme Datensatztyp, in denen die gleiche "Form" nicht wie der Eingabetyp nicht kompiliert:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Anonyme Struktur-Datensätze

Anonyme Datensätze können auch festgelegt werden, als Struktur mit dem optionalen `struct` Schlüsselwort. Im folgende Beispiel erweitert das vorherige Beispiel von erzeugen und nutzen einen anonyme Struktur-Eintrag:

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

### <a name="structness-inference"></a>Structness Typrückschluss

Anonyme Struktur-Datensätze auch zulassen "Structness Typrückschluss", in dem Sie müssen nicht an die `struct` Schlüsselwort an der Aufrufsite. In diesem Beispiel ist Sie elide der `struct` Schlüsselwort beim Aufrufen von `printCircleStats`:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Das Gegenteil des Musters - Angabe `struct` fehl, wenn der Eingabetyp nicht um eine anonyme Struktur-Eintrags: ist zum Kompilieren.

## <a name="embedding-anonymous-records-within-other-types"></a>Einbetten von anonymen Datensätze in andere Typen

Es ist sinnvoll, deklarieren Sie [Unterscheidungs-Unions](discriminated-unions.md) , dessen Fälle sind Datensätze. Aber wenn die Daten in den Datensätzen der gleiche Typ wie die Unterscheidungs-Union ist, müssen Sie alle Typen definieren, als sich gegenseitig rekursiv. Mit anonymen Datensätze vermeidet diese Einschränkung. Im folgenden ist ein Beispiel für Typ und Funktion dieses Muster entspricht, darüber:

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

## <a name="copy-and-update-expressions"></a>Kopieren und Aktualisieren von Ausdrücken

Anonyme Datensätzen unterstützen die Erstellung mit [kopieren und aktualisieren Sie die Ausdrücke](copy-and-update-record-expressions.md). Beispielsweise sieht wie Sie eine neue Instanz eines anonymen Datensatzes erstellen können, die kopiert eine vorhandene aus der Daten:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Im Gegensatz zu benannten Datensätze können anonyme Datensätze Sie ganz unterschiedliche Formen mit Kopie erstellen und Aktualisieren von Ausdrücken. Im folgenden Beispiel wird den gleiche anonyme Datensatz aus dem vorherigen Beispiel und erweitert er in einen neuen anonymen Datensatz:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

Es ist auch möglich, anonyme Datensätze aus Instanzen von benannten Datensätze zu erstellen:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

Sie können auch Daten in und aus Verweis und Struktur anonyme Datensätze kopieren:

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

## <a name="properties-of-anonymous-records"></a>Eigenschaften des anonymen Datensätze

Anonyme Datensätze haben es sich um eine Reihe von Eigenschaften, die wesentlich für dessen vollständig zu verstehen, wie sie verwendet werden können.

### <a name="anonymous-records-are-nominal"></a>Anonyme Datensätze sind geringe

Anonyme Datensätze sind [Nominale Typen](https://en.wikipedia.org/wiki/Nominal_type_system). Sie sind bewährte Gedanken, wie mit dem Namen [Datensatz](records.md) Typen (die auch nominale sind), die nicht die Deklaration ein Investitionen erforderlich sind.

Betrachten Sie das folgende Beispiel mit zwei Deklarationen von anonymen Datensatz:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Die `x` und `y` Werte verschiedene Typen aufweisen und nicht miteinander kompatibel sind. Sie sind nicht gleichwertige, und sie sind nicht vergleichbar. Um dies zu veranschaulichen, betrachten Sie einen benannten Eintrag entspricht:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Es gibt keine irgendetwas grundsätzlich über anonyme Datensätze bei den entsprechenden benannten Eintrag verglichen wird, wenn der Typ Äquivalenz oder der Vergleichsspalte zu.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Anonyme Datensätze verwenden, strukturelle Gleichheit und Vergleich

Wie Record-Typen werden anonyme Datensätze strukturell gleichwertige und vergleichbar. Dies ist nur true, wenn alle enthaltenen Typen Gleichheits- und Vergleichsoperatoren, wie mit Record-Typen unterstützt. Um auf Gleichheit oder Vergleich zu unterstützen, müssen zwei anonyme Datensätze die gleiche "Form".

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Anonyme Datensätze sind serialisierbar

Sie können anonyme Datensätze serialisieren, ebenso wie mit benannten Datensätzen. Es folgt ein Beispiel mit ["newtonsoft.JSON"](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip = {| name="Phillip"; age=28 |}
JsonConvert.SerializeObject(phillip)

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(str)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Anonyme Datensätze sind nützlich für das Senden von geringe Menge von Daten über ein Netzwerk, ohne dass eine Domäne für die Typen für serialisiert bzw. deserialisiert wurden vorab definieren.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Anonyme Datensätze Interoperabilität mit C# anonyme Typen

Es ist möglich, eine .NET API verwenden, die die Verwendung von erfordert [ C# anonyme Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md). C#anonyme Typen sind einfach, die über anonyme Datensätze mit zusammenarbeiten. Das folgende Beispiel zeigt, wie Sie anonyme Datensätze verwenden, um das Aufrufen einer [LINQ](../../csharp/programming-guide/concepts/linq/index.md) Überladung, die einen anonymen Typ ist erforderlich:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Es gibt eine Vielzahl von anderen APIs in .NET verwendet, die Übergabe eines anonymen Typs erfordern. Anonyme Datensätze sind Ihr Tool für die Arbeit mit ihnen.

## <a name="limitations"></a>Einschränkungen

Anonyme Datensätze sind einige Einschränkungen, in deren Verwendung. Einige sind Bestandteil der videomonitore, andere dagegen offener gegenüber Änderungen.

### <a name="limitations-with-pattern-matching"></a>Einschränkungen mit Mustervergleich

Mustervergleich, im Gegensatz zu Datensätzen mit benannten unterstützt anonyme Datensätze nicht. Es gibt drei Gründe:

1. Ein Muster müssten für jedes Feld eines anonymen-Datensatzes, im Gegensatz zu benannten Datensatztypen berücksichtigen. Dies ist da anonyme Datensätze nicht die strukturellen Untertypen unterstützen – sie Nominale Typen sind.
2. Wegen (1) gibt es keine Möglichkeit, zusätzliche Mustern in einem Vergleichsausdruck Muster, da jede unterschiedliches Muster für einen anderen anonyme Datensatztyp nahelegt.
3. Aufgrund von (3) wäre anonymen Datensatzmuster ausführlicher als die Verwendung der Schreibweise von "Punkt".

Es ist eine open Language Vorschlag, [ermöglichen Musterabgleich in begrenzte Kontexte](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Einschränkungen im Zusammenhang mit Veränderlichkeit

Es ist nicht aktuell möglich ist, definieren Sie einen anonyme Datensatz mit `mutable` Daten. Gibt es eine [öffnen Sprache Vorschlag](https://github.com/fsharp/fslang-suggestions/issues/732) um änderbare Daten zu ermöglichen.

### <a name="limitations-with-struct-anonymous-records"></a>Einschränkungen im Zusammenhang mit einer anonymen Struktur-Datensätze

Es ist nicht möglich, die Struktur anonyme Datensätze als deklarieren `IsByRefLike` oder `IsReadOnly`. Gibt es eine [Sprache Vorschlag öffnen](https://github.com/fsharp/fslang-suggestions/issues/712) zu für `IsByRefLike` und `IsReadOnly` anonyme Datensätze.
