---
title: Anonyme Datensätze
description: Erfahren Sie, wie Sie die Erstellung und Verwendung anonymer Datensätze verwenden, einem sprach Feature, das die Bearbeitung von Daten unterstützt.
ms.date: 06/12/2019
ms.openlocfilehash: 13950048f02ab74362f8174725f5f8615d9d7654
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739814"
---
# <a name="anonymous-records"></a>Anonyme Datensätze

Anonyme Datensätze sind einfache Aggregate benannter Werte, die nicht vor der Verwendung deklariert werden müssen. Sie können Sie als Strukturen oder Verweis Typen deklarieren. Sie sind standardmäßig Verweis Typen.

## <a name="syntax"></a>Syntax

In den folgenden Beispielen wird die anonyme Daten Satz Syntax veranschaulicht. Als Trennzeichen getrennte Elemente `[item]` sind optional.

```fsharp
// Construct an anonymous record
let value-name = [struct] {| Label1: Type1; Label2: Type2; ...|}

// Use an anonymous record as a type parameter
let value-name = Type-Name<[struct] {| Label1: Type1; Label2: Type2; ...|}>

// Define a parameter with an anonymous record as input
let function-name (arg-name: [struct] {| Label1: Type1; Label2: Type2; ...|}) ...
```

## <a name="basic-usage"></a>Grundlegende Verwendung

Anonyme Datensätze werden am besten als F #-Daten Satz Typen betrachtet, die vor der Instanziierung nicht deklariert werden müssen.

Hier finden Sie beispielsweise Informationen zum interagieren mit einer Funktion, die einen anonymen Datensatz erzeugt:

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

Im folgenden Beispiel wird eine Funktion mit einer Funktion erweitert `printCircleStats` , die einen anonymen Datensatz als Eingabe annimmt:

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

Das Aufrufen `printCircleStats` von mit anonymen Daten Satz Typen, die nicht die gleiche Form aufweisen wie der Eingabetyp, kann nicht kompiliert werden:

```fsharp
printCircleStats r {| Diameter = 2.0; Area = 4.0; MyCircumference = 12.566371 |}
// Two anonymous record types have mismatched sets of field names
// '["Area"; "Circumference"; "Diameter"]' and '["Area"; "Diameter"; "MyCircumference"]'
```

## <a name="struct-anonymous-records"></a>Anonyme Strukturdaten Sätze

Anonyme Datensätze können auch als struct mit dem optionalen `struct` Schlüsselwort definiert werden. Im folgenden Beispiel wird die vorherige Struktur durch Erstellen und Verwenden eines anonymen Struktur-Datensatzes erweitert:

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

### <a name="structness-inference"></a>Struktur Rückschluss

Die anonymen Struktur-Datensätze ermöglichen auch "structness Inference", wobei Sie das- `struct` Schlüsselwort nicht an der aufrufssite angeben müssen. In diesem Beispiel entfernen Sie das- `struct` Schlüsselwort, wenn Sie aufrufen `printCircleStats` :

```fsharp

let printCircleStats r (stats: struct {| Area: float; Circumference: float; Diameter: float |}) =
    printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
        r stats.Diameter stats.Area stats.Circumference

printCircleStats r {| Area = 4.0; Circumference = 12.6; Diameter = 12.6 |}
```

Das umgekehrte Muster: die Angabe, `struct` wann der Eingabetyp kein der anonyme Struktur-Datensatz ist, kann nicht kompiliert werden.

## <a name="embedding-anonymous-records-within-other-types"></a>Einbetten anonymer Datensätze in andere Typen

Es ist hilfreich, Unterscheidungs- [Unions](discriminated-unions.md) zu deklarieren, deren Fälle Datensätze sind. Wenn die Daten in den Datensätzen jedoch denselben Typ wie die Unterscheidungs-Union haben, müssen Sie alle Typen als gegenseitig rekursiv definieren. Diese Einschränkung wird durch die Verwendung anonymer Datensätze vermieden. Dabei handelt es sich um einen Beispieltyp und eine Funktion, die mit dem Muster übereinstimmen:

```fsharp
type FullName = { FirstName: string; LastName: string }

// Note that using a named record for Manager and Executive would require mutually recursive definitions.
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

## <a name="copy-and-update-expressions"></a>Copy-und Update-Ausdrücke

Anonyme Datensätze unterstützen die Erstellung mit [Kopier-und Update Ausdrücken](copy-and-update-record-expressions.md). So können Sie z. b. eine neue Instanz eines anonymen Datensatzes erstellen, der die Daten eines vorhandenen Datensatzes kopiert:

```fsharp
let data = {| X = 1; Y = 2 |}
let data' = {| data with Y = 3 |}
```

Im Gegensatz zu benannten Datensätzen können Sie mit anonymen Datensätzen jedoch ganz unterschiedliche Formulare mit Kopier-und Update Ausdrücken erstellen. Im folgenden Beispiel wird derselbe anonyme Datensatz aus dem vorherigen Beispiel angenommen und in einen neuen anonymen Datensatz erweitert:

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

Sie können auch Daten in und aus Verweis-und Struktur anonymen Datensätzen kopieren:

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

Anonyme Datensätze verfügen über eine Reihe von Merkmalen, die für ein vollständiges Verständnis der Verwendung von verwendet werden können.

### <a name="anonymous-records-are-nominal"></a>Anonyme Datensätze sind nominell

Anonyme Datensätze sind [Nominale Typen](https://en.wikipedia.org/wiki/Nominal_type_system). Sie sind am besten als benannte [Daten Satz](records.md) Typen (auch nominale), für die keine vorabdeklaration erforderlich ist.

Beachten Sie das folgende Beispiel mit zwei anonymen Daten Satz Deklarationen:

```fsharp
let x = {| X = 1 |}
let y = {| Y = 1 |}
```

Der `x` -Wert und der- `y` Wert weisen unterschiedliche Typen auf und sind nicht miteinander kompatibel. Sie sind nicht gleich stellbar und nicht vergleichbar. Um dies zu veranschaulichen, sollten Sie eine benannte Daten Satz Entsprechung beachten:

```fsharp
type X = { X: int }
type Y = { Y: int }

let x = { X = 1 }
let y = { Y = 1 }
```

Es gibt keine Unterschiede zu anonymen Datensätzen, wenn Sie mit ihren benannten Daten Satz Entsprechungen verglichen werden, wenn die typäquivalenz oder der Vergleich vorliegt.

### <a name="anonymous-records-use-structural-equality-and-comparison"></a>Anonyme Datensätze verwenden strukturelle Gleichheit und Vergleich

Ebenso wie Daten Satz Typen sind anonyme Datensätze strukturell gleich und vergleichbar. Dies gilt nur, wenn alle konstituierenden Typen Gleichheit und Vergleich unterstützen, wie z. b. Daten Satz Typen. Um Gleichheit oder Vergleiche zu unterstützen, müssen zwei anonyme Datensätze die gleiche Form aufweisen.

```fsharp
{| a = 1+1 |} = {| a = 2 |} // true
{| a = 1+1 |} > {| a = 1 |} // true

// error FS0001: Two anonymous record types have mismatched sets of field names '["a"]' and '["a"; "b"]'
{| a = 1 + 1 |} = {| a = 2;  b = 1|}
```

### <a name="anonymous-records-are-serializable"></a>Anonyme Datensätze sind serialisierbar.

Sie können anonyme Datensätze genauso wie mit benannten Datensätzen serialisieren. Im folgenden finden Sie ein Beispiel für die Verwendung [Newtonsoft.Jsin](https://www.nuget.org/packages/Newtonsoft.Json/):

```fsharp
open Newtonsoft.Json

let phillip' = {| name="Phillip"; age=28 |}
let philStr = JsonConvert.SerializeObject(phillip')

let phillip = JsonConvert.DeserializeObject<{|name: string; age: int|}>(philStr)
printfn $"Name: {phillip.name} Age: %d{phillip.age}"
```

Anonyme Datensätze sind nützlich, um Lightweight-Daten über ein Netzwerk zu senden, ohne dass Sie vorab eine Domäne für die serialisierten/deserialisierten Typen definieren müssen.

### <a name="anonymous-records-interoperate-with-c-anonymous-types"></a>Anonyme Datensätze interagieren mit anonymen c#-Typen

Es ist möglich, eine .NET-API zu verwenden, die die Verwendung [Anonymer c#-Typen](../../csharp/programming-guide/classes-and-structs/anonymous-types.md)erfordert. Anonyme c#-Typen sind für die Interoperabilität mit mithilfe anonymer Datensätze trivial. Im folgenden Beispiel wird gezeigt, wie anonyme Datensätze verwendet werden, um eine [LINQ](../../csharp/programming-guide/concepts/linq/index.md) -Überladung aufzurufen, die einen anonymen Typ erfordert:

```fsharp
open System.Linq

let names = [ "Ana"; "Felipe"; "Emilia"]
let nameGrouping = names.Select(fun n -> {| Name = n; FirstLetter = n.[0] |})
for ng in nameGrouping do
    printfn $"{ng.Name} has first letter {ng.FirstLetter}"
```

Es gibt zahlreiche andere APIs, die in .NET verwendet werden und die Verwendung der Übergabe eines anonymen Typs erfordern. Anonyme Datensätze sind das Tool für die Arbeit mit Ihnen.

## <a name="limitations"></a>Einschränkungen

Für anonyme Datensätze gelten einige Einschränkungen bei der Verwendung. Einige sind in Ihrem Design verankert, andere können jedoch geändert werden.

### <a name="limitations-with-pattern-matching"></a>Einschränkungen bei der Muster Übereinstimmung

Anonyme Datensätze unterstützen im Gegensatz zu benannten Datensätzen keinen Musterabgleich. Es gibt drei Gründe:

1. Ein Muster muss jedes Feld eines anonymen Datensatzes berücksichtigen, anders als benannte Daten Satz Typen. Dies liegt daran, dass anonyme Datensätze keine strukturelle unter Typisierung unterstützen – Sie sind Nominale Typen.
2. Aufgrund von (1) gibt es keine Möglichkeit, zusätzliche Muster in einem Muster Vergleichs Ausdruck zu haben, da jedes unterschiedliche Muster einen anderen anonymen Daten Satz Typ impliziert.
3. Aufgrund von (3) wären alle anonymen Daten Satzmuster ausführlicher als die Verwendung der "Punkt"-Notation.

Es gibt einen offenen sprach Vorschlag, um den Musterabgleich [in eingeschränkten Kontexten zuzulassen](https://github.com/fsharp/fslang-suggestions/issues/713).

### <a name="limitations-with-mutability"></a>Einschränkungen mit Veränderlichkeit

Es ist derzeit nicht möglich, einen anonymen Datensatz mit Daten zu definieren `mutable` . Es gibt einen [offenen sprach Vorschlag](https://github.com/fsharp/fslang-suggestions/issues/732) , um änderbare Daten zuzulassen.

### <a name="limitations-with-struct-anonymous-records"></a>Einschränkungen mit anonymen Strukturdaten Sätzen

Es ist nicht möglich, die anonymen Strukturdaten Sätze als oder zu deklarieren `IsByRefLike` `IsReadOnly` . Es gibt einen [offenen sprach Vorschlag](https://github.com/fsharp/fslang-suggestions/issues/712) für `IsByRefLike` und `IsReadOnly` Anonyme Datensätze.
