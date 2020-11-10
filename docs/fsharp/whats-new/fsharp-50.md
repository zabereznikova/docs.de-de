---
title: 'Neues in f # 5,0-f #-Handbuch'
description: 'Verschaffen Sie sich einen Überblick über die neuen Features, die in F # 5,0 verfügbar sind.'
ms.date: 11/06/2020
ms.openlocfilehash: 0c4c9f42c63a1dc8c90213c43edbadd4061c132d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445841"
---
# <a name="whats-new-in-f-50"></a>Neues in F # 5,0

F # 5,0 fügt mehrere Verbesserungen der Sprache f # und F# Interactive hinzu. Sie wird mit **.net 5** veröffentlicht.

## <a name="get-started"></a>Erste Schritte

F # 5,0 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar. Weitere Informationen finden Sie unter [Einstieg in F #](../get-started/index.md) , um weitere Informationen zu erhalten.

## <a name="package-references-in-f-scripts"></a>Paket Verweise in F #-Skripts

F # 5 unterstützt Paket Verweise in f #-Skripts mit `#r "nuget:..."` Syntax. Sehen Sie sich beispielsweise den folgenden Paket Verweis an:

```fsharp
#r "nuget: Newtonsoft.Json"

open Newtonsoft.Json

let o = {| X = 2; Y = "Hello" |}

printfn "%s" (JsonConvert.SerializeObject o)
```

Sie können auch eine explizite Version nach dem Namen des Pakets wie folgt angeben:

```fsharp
#r "nuget: Newtonsoft.Json,11.0.1"
```

Paket Verweise unterstützen Pakete mit nativen Abhängigkeiten, z. b. ml.net.

Paket Verweise unterstützen auch Pakete mit speziellen Anforderungen zum Verweisen auf abhängige `.dll` s. Beispielsweise muss das [fbeispielpaket](https://www.nuget.org/packages/FParsec/) verwendet werden, um sicherzustellen, dass die Benutzer manuell sicherstellen, dass auf Ihre abhängige `FParsecCS.dll` zuerst verwiesen wurde, bevor `FParsec.dll` in F# Interactive auf verwiesen wurde. Dies ist nicht mehr erforderlich, und Sie können wie folgt auf das Paket verweisen:

```fsharp
#r "nuget: FParsec"

open FParsec

let test p str =
    match run p str with
    | Success(result, _, _)   -> printfn "Success: %A" result
    | Failure(errorMsg, _, _) -> printfn "Failure: %s" errorMsg

test pfloat "1.234"
```

Weitere Informationen zu Paket verweisen finden Sie im [F# Interactive](../tutorials/fsharp-interactive/index.md) Tutorial.

## <a name="string-interpolation"></a>Zeichenfolgeninterpolierung

F #-interinterpolierte Zeichen folgen ähneln c#-oder JavaScript-interpoliert-Zeichen folgen, da Sie in einem Zeichenfolgenliteralzeichen Code in "Löcher" schreiben können. Im Folgenden finden Sie ein einfaches Beispiel:

```fsharp
let name = "Phillip"
let age = 29
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

In F # interpoliert-Zeichen folgen ist es jedoch auch möglich, typisierte Interpolationen wie die- `sprintf` Funktion zu erzwingen, um zu erzwingen, dass ein Ausdruck innerhalb eines interinterpolierten Kontexts einem bestimmten Typ entspricht. Dabei werden die gleichen Format Bearbeiter verwendet.

```fsharp
let name = "Phillip"
let age = 29

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

Im vorangehenden Beispiel für eine typisierte interpolung `%s` erfordert, dass die Interpolations vom Typ `string` ist, während `%d` für die Interpolations-erforderlich ist `integer` .

Darüber hinaus können beliebige F #-Ausdrücke (oder Ausdrücke) auf der Seite eines Interpolations Kontexts platziert werden. Es ist sogar möglich, einen komplizierteren Ausdruck wie folgt zu schreiben:

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

Wir empfehlen zwar nicht, dies in der Praxis zu tun.

## <a name="support-for-nameof"></a>Unterstützung für "nameof"

F # 5 unterstützt den `nameof` -Operator, der das Symbol auflöst, für das es verwendet wird, und seinen Namen in F #-Quelle erstellt. Dies ist in verschiedenen Szenarien hilfreich, z. b. bei der Protokollierung und schützt Ihre Protokollierung vor Änderungen im Quellcode.

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

In der letzten Zeile wird eine Ausnahme ausgelöst, und "Month" wird in der Fehlermeldung angezeigt.

Sie können einen Namen für fast alle F #-Konstrukte verwenden:

```fsharp
module M =
    let f x = nameof x

printfn "%s" (M.f 12)
printfn "%s" (nameof M)
printfn "%s" (nameof M.f)
```

Drei abschließende Ergänzungen sind Änderungen an der Funktionsweise von Operatoren: das Hinzufügen des `nameof<'type-parameter>` Formulars für generische Typparameter und die Möglichkeit, `nameof` als Muster in einem Muster Vergleichs Ausdruck zu verwenden.

Die Quell Zeichenfolge wird durch den Namen eines Operators fest. Wenn Sie das kompilierte Formular benötigen, verwenden Sie den kompilierten Namen eines Operators:

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

Wenn Sie den Namen eines Typparameters eingeben, ist eine etwas andere Syntax erforderlich:

```fsharp

type C<'TType> =
    member _.TypeName = nameof<'TType>
```

Dies ähnelt dem `typeof<'T>` -Operator und dem- `typedefof<'T>` Operator.

F # 5 bietet auch Unterstützung für ein `nameof` Muster, das in Ausdrücken verwendet werden kann `match` :

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

Im vorangehenden Code wird "nameof" anstelle des Zeichenfolgenliterals im Vergleichs Ausdruck verwendet.

## <a name="open-type-declarations"></a>Open-Typdeklarationen

F # 5 bietet auch Unterstützung für Open-Type-Deklarationen. Eine offene Typdeklaration ähnelt dem Öffnen einer statischen Klasse in c#, außer mit einer anderen Syntax und einem leicht abweichenden Verhalten, das für die F #-Semantik geeignet ist.

Mit Open Type-Deklarationen können Sie `open` einen beliebigen Typ zum verfügbar machen von statischem Inhalt darin bereitstellen. Darüber hinaus können Sie `open` F #-definierte Unions und Datensätze zur Offenlegung ihres Inhalts nutzen. Dies kann z. b. hilfreich sein, wenn Sie eine Union in einem Modul definiert haben und auf ihre Fälle zugreifen möchten, aber nicht das gesamte Modul öffnen möchten.

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

Anders als bei c#, wenn Sie zwei Typen haben, die `open type` einen Member mit demselben Namen verfügbar machen, wird das Element aus dem letzten Typ, der mit dem letzten Typ identisch ist, mit `open` dem anderen Namen Dies ist mit der F #-Semantik um shadowingkonsistent, die bereits vorhanden ist.

## <a name="consistent-slicing-behavior-for-built-in-data-types"></a>Konsistentes aufteilen-Verhalten für integrierte Datentypen

Das Verhalten für das Aufteilen der integrierten `FSharp.Core` Datentypen (Array, Liste, Zeichenfolge, 2D-Array, 3D-Array, 4D-Array), das vor F # 5 nicht konsistent ist. Einige Edge-Case-Verhalten haben eine Ausnahme ausgelöst, und andere nicht. In F # 5 geben alle integrierten Typen nun leere Slices für Slices zurück, die nicht generiert werden können:

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

## <a name="fixed-index-slices-for-3d-and-4d-arrays-in-fsharpcore"></a>Festgelegte Index Slices für 3D-und 4D-Arrays in FSharp. Core

F # 5,0 unterstützt das Aufteilen von aufteilen mit einem Fixed-Index in den integrierten 3D-und 4D-Array Typen.

Um dies zu veranschaulichen, sehen Sie sich das folgende 3D-Array an:

*z = 0*
|x\y|0|1|
|---|-|-|
|**0**|0|1|
|**1**|2|3|

*z = 1*
|x\y|0|1|
|---|-|-|
|**0**|4|5|
|**1**|6|7|

Was geschieht, wenn Sie den Slice `[| 4; 5 |]` aus dem Array extrahieren möchten? Dies ist jetzt sehr einfach!

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

## <a name="applicative-computation-expressions"></a>Anwendungsberechnungs-Ausdrücke

[Berechnungs Ausdrücke (CES)](../language-reference/computation-expressions.md) werden heute verwendet, um "kontextbezogene Berechnungen" oder in funktionaler Programmier freundlicher Terminologie, monadische-Berechnungen, zu modellieren.

F # 5 führt Anwendungsabhängigkeiten ein, die ein anderes Berechnungsmodell bieten. Anwendungs abhängige CES ermöglichen effizientere Berechnungen, vorausgesetzt, jede Berechnung ist unabhängig, und ihre Ergebnisse werden am Ende akkumuliert. Wenn Berechnungen voneinander unabhängig sind, können Sie auch trivial parallelisierbar sein, sodass CE-Autoren effizientere Bibliotheken schreiben können. Dieser Vorteil liegt jedoch in einer Einschränkung: Berechnungen, die von zuvor berechneten Werten abhängen, sind nicht zulässig.

Das folgende Beispiel zeigt eine grundlegende Anwendungs Quelle für den- `Result` Typ.

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

Wenn Sie ein Autor der Bibliothek sind, der heute CES in der Bibliothek verfügbar macht, müssen Sie einige zusätzliche Aspekte beachten.

## <a name="interfaces-can-be-implemeneted-at-different-generic-instantiations"></a>Schnittstellen können in unterschiedlichen generischen Instanziierungen implementiert werden.

Nun können Sie die gleiche Schnittstelle in unterschiedlichen generischen Instanziierungen implementieren:

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

## <a name="default-interface-member-consumption"></a>Standardmäßige Verwendung von Schnittstellen Elementen

Mit F # 5 können Sie [Schnittstellen mit Standard Implementierungen](../../csharp/tutorials/default-interface-methods-versions.md)verwenden.

Angenommen, eine in c# definierte Schnittstelle sieht wie folgt aus:

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

Sie können Sie in F # mithilfe einer beliebigen Standardmethode zur Implementierung einer Schnittstelle nutzen:

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

Auf diese Weise können Sie den c#-Code und .NET-Komponenten, die in modernem c# geschrieben sind, sicher nutzen, wenn Sie erwarten, dass Benutzer eine Standard Implementierung nutzen können.

## <a name="simplified-interop-with-nullable-value-types"></a>Vereinfachtes Interop mit Werte zulässt-Werttypen

[Typen](https://docs.microsoft.com/dotnet/api/system.nullable-1) , die NULL-Werte zulassen (in der Vergangenheit als Nullable-Typen bezeichnet), wurden schon seit langem von F # unterstützt, aber die Interaktion mit Ihnen war bisher schon etwas komplizierter, da Sie `Nullable` `Nullable<SomeType>` jedes Mal, wenn Sie einen Wert übergeben wollten, einen-oder-Wrapper erstellen mussten. Nun konvertiert der Compiler einen Werttyp implizit in eine, `Nullable<ThatValueType>` Wenn der Zieltyp übereinstimmt. Der folgende Code ist nun möglich:

```fsharp
#r "nuget: Microsoft.Data.Analysis"

open Microsoft.Data.Analysis

let dateTimes = PrimitiveDataFrameColumn<DateTime>("DateTimes")

// The following line used to fail to compile
dateTimes.Append(DateTime.Parse("2019/01/01"))

// The previous line is now equivalent to this line
dateTimes.Append(Nullable<DateTime>(DateTime.Parse("2019/01/01")))
```

## <a name="preview-reverse-indexes"></a>Vorschau: Reverse-Indizes

F # 5 führt außerdem eine Vorschau für das Zulassen von umgekehrten Indizes ein. Die Syntax lautet `^idx`. So können Sie einen Wert von Element 1 vom Ende einer Liste aus:

```fsharp
let xs = [1..10]

// Get element 1 from the end:
xs.[^1]

// From the end slices

let lastTwoOldStyle = xs.[(xs.Length-2)..]

let lastTwoNewStyle = xs.[^1..]

lastTwoOldStyle = lastTwoNewStyle // true
```

Sie können auch umgekehrte Indizes für Ihre eigenen Typen definieren. Zu diesem Zweck müssen Sie die folgende Methode implementieren:

```fsharp
GetReverseIndex: dimension: int -> offset: int
```

Im folgenden finden Sie ein Beispiel für den- `Span<'T>` Typ:

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

## <a name="preview-overloads-of-custom-keywords-in-computation-expressions"></a>Vorschau: über Ladungen von benutzerdefinierten Schlüsselwörtern in Berechnungs Ausdrücken

Berechnungs Ausdrücke sind ein leistungsfähiges Feature für Bibliotheks-und Frameworkautoren. Sie ermöglichen es Ihnen, die Ausdrucksfähigkeit ihrer Komponenten deutlich zu verbessern, indem Sie bekannte Member definieren und eine DSL für die Domäne bilden, in der Sie arbeiten.

F # 5 fügt eine Vorschau Unterstützung für das Überladen von benutzerdefinierten Vorgängen in Berechnungs Ausdrücken hinzu. Dadurch kann der folgende Code geschrieben und verwendet werden:

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

Vor dieser Änderung konnten Sie den `InputBuilder` Typ wie folgt schreiben, aber Sie konnten ihn nicht so verwenden, wie er im Beispiel verwendet wird. Da über Ladungen, optionale Parameter und jetzt- `System.ParamArray` Typen zulässig sind, funktioniert alles genau wie erwartet.
