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
# <a name="anonymous-records"></a>Anonyme Datensätze

Anonyme Datensätze sind einfache Aggregate benannter Werte, die vor der Verwendung nicht deklariert werden müssen. Sie können sie entweder als Strukturen oder als Verweistypen deklarieren. Sie sind standardmäßig Referenztypen.

## <a name="syntax"></a>Syntax

Die folgenden Beispiele veranschaulichen die Syntax für anonyme Aufzeichnungen. Elemente, die `[item]` als optional getrennt sind.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Grundlegende Verwendung

Anonyme Datensätze werden am besten als Datensatztypen von F- datensätzen betrachtet, die nicht vor der Instanziierung deklariert werden müssen.

Hier erfahren Sie beispielsweise, wie Sie mit einer Funktion interagieren können, die einen anonymen Datensatz erstellt:

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

Im folgenden Beispiel wird das vorherige `printCircleStats` Mit einer Funktion erweitert, die einen anonymen Datensatz als Eingabe verwendet:

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

Wenn `printCircleStats` Sie einen anonymen Datensatztyp aufrufen, der nicht die gleiche "Form" wie der Eingabetyp hat, kann nicht kompiliert werden:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Strukturieren anonymer Datensätze

Anonyme Datensätze können auch als `struct` struct mit dem optionalen Schlüsselwort definiert werden. Im folgenden Beispiel wird das vorherige Beispiel durch das Erstellen und Verwenden eines anonymen Strukturdatensatzes erweitert:

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

### <a name="structness-inference"></a>Strukturrückschluss

Anonyme Datensätze strukturieren lassen auch "Strukturrückschluss" zu, `struct` bei dem Sie das Schlüsselwort auf der Aufrufsite nicht angeben müssen. In diesem Beispiel entschlüsseln Sie das `struct` Schlüsselwort beim Aufrufen `printCircleStats`von:

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Das umgekehrte Muster `struct` , das angibt, wann der Eingabetyp kein anonymer Strukturdatensatz ist - kann nicht kompiliert werden.

## <a name="embedding-anonymous-records-within-other-types"></a>Einbetten anonymer Datensätze in andere Typen

Es ist nützlich, diskriminierte Gewerkschaften zu [deklarieren,](discriminated-unions.md) deren Fälle Datensätze sind. Wenn die Daten in den Datensätzen jedoch den gleichen Typ wie die diskriminierte Union aufweisen, müssen Sie alle Typen als gegenseitig rekursiv definieren. Durch die Verwendung anonymer Datensätze wird diese Einschränkung vermieden. Was folgt, ist ein Beispieltyp und eine Funktion, die muster darüber übereinstimmen:

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

Anonyme Datensätze unterstützen die Konstruktion mit [Kopier- und Aktualisierungsausdrücken](copy-and-update-record-expressions.md). So können Sie z. B. eine neue Instanz eines anonymen Datensatzes erstellen, die die Daten eines vorhandenen Datensatzes kopiert:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Im Gegensatz zu benannten Datensätzen können Sie jedoch mit anonymen Datensätzen völlig unterschiedliche Formulare mit Kopier- und Aktualisierungsausdrücken erstellen. Das folgende Beispiel nimmt denselben anonymen Datensatz aus dem vorherigen Beispiel und erweitert ihn in einen neuen anonymen Datensatz:

```fsharp
let data = {| X = 1; Y = 2 |}
let expandedData = {| data with Z = 3 |} // Gives {| X=1; Y=2; Z=3 |}
```

Es ist auch möglich, anonyme Datensätze aus Instanzen benannter Datensätze zu erstellen:

```fsharp
type R = { X: int }
let data = { X = 1 }
let data' = {| data with Y = 2 |} // Gives {| X=1; Y=2 |}
```

Sie können auch Daten in und aus anonymen Datensätzen kopieren und strukturieren:

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

## <a name="properties-of-anonymous-records"></a>Eigenschaften anonymer Datensätze

Anonyme Datensätze weisen eine Reihe von Merkmalen auf, die für das vollständige Verständnis ihrer Verwendung unerlässlich sind.

### <a name="anonymous-records-are-nominal"></a>Anonyme Datensätze sind nominell

Anonyme Datensätze sind [nominale Typen](https://en.wikipedia.org/wiki/Nominal_type_system). Sie sind am besten als benannte [Datensatztypen](records.md) (die auch nominal sind) gedacht, die keine Vorabdeklaration erfordern.

Betrachten Sie das folgende Beispiel mit zwei anonymen Datensatzdeklarationen:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Die `x` `y` und-Werte haben unterschiedliche Typen und sind nicht miteinander kompatibel. Sie sind nicht gleichsam und nicht vergleichbar. Um dies zu veranschaulichen, sollten Sie ein benanntes Datensatzäquivalent in Betracht ziehen:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Es gibt nichts von Natur aus anders über anonyme Datensätze im Vergleich zu ihren benannten Datensatzäquivalenten, wenn es um Typäquivalenz oder Vergleich.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Anonyme Datensätze verwenden strukturelle Gleichheit und Vergleich

Wie Datensatztypen sind anonyme Datensätze strukturell gleichsam und vergleichbar. Dies gilt nur, wenn alle komponentenden Typen Gleichheit und Vergleich unterstützen, wie bei Datensatztypen. Um Gleichheit oder Vergleich zu unterstützen, müssen zwei anonyme Datensätze dieselbe "Form" haben.

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Anonyme Datensätze sind serialisierbar

Sie können anonyme Datensätze genauso serialisieren wie mit benannten Datensätzen. Hier ist ein Beispiel mit [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn "Name: %s Age: %d" phillip.name phillip.age
```

Anonyme Datensätze sind nützlich, um einfache Daten über ein Netzwerk zu senden, ohne dass sie eine Domäne für Ihre serialisierten/deserialisierten Typen im Voraus definieren müssen.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Anonyme Datensätze arbeiten mit anonymen C-Typen zusammen

Es ist möglich, eine .NET-API zu verwenden, die die Verwendung [anonymer C-Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)erfordert. Anonyme Typen von C-Code sind trivial, mit denen sie mithilfe anonymer Datensätze zusammenarbeiten können. Das folgende Beispiel zeigt, wie sie anonyme Datensätze verwenden, um eine [LINQ-Überladung](../../csharp/programming-guide/concepts/linq/index.md) aufzurufen, die einen anonymen Typ erfordert:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn "%s has first letter %c" ng.Name ng.FirstLetter
```

Es gibt eine Vielzahl anderer APIs, die in .NET verwendet werden und die Dieverwendung in einem anonymen Typ erfordern. Anonyme Datensätze sind Ihr Werkzeug, um mit ihnen zu arbeiten.

## <a name="limitations"></a>Einschränkungen

Anonyme Datensätze haben einige Einschränkungen in ihrer Verwendung. Einige sind ihrem Design inhärent, andere sind für Veränderungen geeignet.

### <a name="limitations-with-pattern-matching"></a>Einschränkungen bei Musterübereinstimmung

Anonyme Datensätze unterstützen im Gegensatz zu benannten Datensätzen keine Musterübereinstimmung. Es gibt drei Gründe:

1. Ein Muster müsste für jedes Feld eines anonymen Datensatzes berücksichtigt werden, im Gegensatz zu benannten Datensatztypen. Dies liegt daran, dass anonyme Datensätze keine strukturelle Untertypisierung unterstützen – sie sind nominale Typen.
2. Aufgrund (1) gibt es keine Möglichkeit, zusätzliche Muster in einem Musterübereinstimmungsausdruck zu haben, da jedes einzelne Muster einen anderen anonymen Datensatztyp implizieren würde.
3. Aufgrund von (3) wäre jedes anonyme Datensatzmuster ausführlicher als die Verwendung der "Punkt"-Notation.

Es gibt einen Vorschlag für eine offene Sprache, um [musterabgleich in begrenzten Kontexten](https://github.com/fsharp/fslang-suggestions/issues/713)zu ermöglichen.

### <a name="limitations-with-mutability"></a>Einschränkungen bei der Veränderbarkeit

Derzeit ist es nicht möglich, `mutable` einen anonymen Datensatz mit Daten zu definieren. Es gibt einen [Vorschlag für eine offene Sprache,](https://github.com/fsharp/fslang-suggestions/issues/732) um veränderbare Daten zuzulassen.

### <a name="limitations-with-struct-anonymous-records"></a>Einschränkungen bei anonymen Strukturdatensätzen

Es ist nicht möglich, anonyme Strukturen als `IsByRefLike` oder `IsReadOnly`zu deklarieren. Es gibt einen Vorschlag `IsByRefLike` für `IsReadOnly` [offene Sprache](https://github.com/fsharp/fslang-suggestions/issues/712) für und anonyme Datensätze.
