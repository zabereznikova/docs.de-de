---
title: Codekonventionen für F#
description: 'Informieren Sie sich über allgemeine Richtlinien und Idiome beim Schreiben von F #-Code.'
ms.date: 01/15/2020
ms.openlocfilehash: 87955c379f0abba929b0ced75d62d2601f37dc5a
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739901"
---
# <a name="f-coding-conventions"></a>Codekonventionen für F#

Die folgenden Konventionen sind von der Erfahrung beim Arbeiten mit großen F #-CodeBases formuliert. Die [fünf Prinzipien von gutem F #-Code](index.md#five-principles-of-good-f-code) sind die Grundlage für jede Empfehlung. Sie beziehen sich auf die [Entwurfs Richtlinien für die f #-Komponente](component-design-guidelines.md), gelten jedoch für jeden f #-Code, nicht nur für Komponenten wie Bibliotheken.

## <a name="organizing-code"></a>Organisieren von Code

F # bietet zwei Hauptmethoden zum Organisieren von Code: Module und Namespaces. Diese sind ähnlich, haben jedoch die folgenden Unterschiede:

* Namespaces werden als .NET-Namespaces kompiliert. Module werden als statische Klassen kompiliert.
* Namespaces sind immer die oberste Ebene. Module können auf oberster Ebene und in anderen Modulen geschachtelt sein.
* Namespaces können mehrere Dateien umfassen. Module können nicht.
* Module können mit und ergänzt `[<RequireQualifiedAccess>]` werden `[<AutoOpen>]` .

Die folgenden Richtlinien helfen Ihnen, diese zum Organisieren Ihres Codes zu verwenden.

### <a name="prefer-namespaces-at-the-top-level"></a>Namespaces auf oberster Ebene bevorzugen

Für jeden öffentlich verwendbaren Code werden Namespaces für Module auf der obersten Ebene bevorzugt. Da Sie als .NET-Namespaces kompiliert werden, können Sie von c# ohne Probleme genutzt werden.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Die Verwendung eines Moduls der obersten Ebene wird möglicherweise nicht anders angezeigt, wenn es nur von F # aufgerufen wird, aber für c#-Consumer sind Aufrufer möglicherweise überrascht, wenn Sie sich `MyClass` mit dem Modul qualifizieren müssen `MyCode` .

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Sorgfältig anwenden `[<AutoOpen>]`

Das `[<AutoOpen>]` Konstrukt kann den Bereich der verfügbaren Aufrufer verschmutzen, und die Antwort auf den Ort, von dem aus Sie stammt, ist "Magic". Dies ist keine gute Sache. Eine Ausnahme von dieser Regel ist die F #-Kernbibliothek selbst (obwohl diese Tatsache auch etwas strittig ist).

Es ist jedoch eine bequeme Methode, wenn Sie über Hilfsfunktionen für eine öffentliche API verfügen, die Sie separat von der öffentlichen API organisieren möchten.

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

Auf diese Weise können Sie Implementierungsdetails von der öffentlichen API einer Funktion vollständig trennen, ohne dass Sie jedes Mal, wenn Sie Sie aufrufen, ein Hilfsobjekt vollständig qualifizieren müssen.

Außerdem kann das verfügbar machen von Erweiterungs Methoden und Ausdrucks-Generatoren auf Namespace Ebene mit ordentlich ausgedrückt werden `[<AutoOpen>]` .

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Verwenden `[<RequireQualifiedAccess>]` Sie, wenn Namen Konflikte verursachen könnten, oder wenn Sie sich für die Lesbarkeit sorgen.

Das Hinzufügen des- `[<RequireQualifiedAccess>]` Attributs zu einem Modul gibt an, dass das Modul möglicherweise nicht geöffnet wird und dass Verweise auf die Elemente des Moduls einen expliziten qualifizierten Zugriff erfordern. Beispielsweise verfügt das `Microsoft.FSharp.Collections.List` Modul über dieses Attribut.

Dies ist nützlich, wenn Funktionen und Werte im Modulnamen haben, die mit den Namen in anderen Modulen wahrscheinlich in Konflikt stehen. Wenn qualifizierter Zugriff erforderlich ist, kann die langfristige Wartbarkeit und die Entwicklung einer Bibliothek erheblich gesteigert werden.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Sortier `open` Anweisungen topologisch

In F # ist die Reihenfolge der Deklarationen, einschließlich der-Anweisungen, wichtig `open` . Dies ist anders als bei c#, bei dem die Auswirkung von `using` und `using static` unabhängig von der Reihenfolge dieser Anweisungen in einer Datei ist.

In F # können Elemente, die in einem Bereich geöffnet werden, andere als Schatten darstellen. Dies bedeutet, dass das Neuanordnen `open` von Anweisungen die Bedeutung von Code ändern könnte. Folglich wird eine beliebige Sortierung aller `open` Anweisungen (z. b. alphanumerisch) nicht empfohlen, sodass Sie nicht unterschiedliche Verhalten generieren können, die Sie möglicherweise erwarten.

Stattdessen wird empfohlen, dass Sie Sie [topologisch](https://en.wikipedia.org/wiki/Topological_sorting)sortieren. Ordnen Sie die `open` Anweisungen in der Reihenfolge an, in der die _Ebenen_ Ihres Systems definiert sind. Eine alphanumerische Sortierung innerhalb verschiedener topologischer Ebenen kann auch berücksichtigt werden.

Im folgenden finden Sie ein Beispiel für die topologische Sortierung der öffentlichen API-Datei für den F #-compilerdienst:

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open FSharp.Compiler
open FSharp.Compiler.AbstractIL
open FSharp.Compiler.AbstractIL.Diagnostics
open FSharp.Compiler.AbstractIL.IL
open FSharp.Compiler.AbstractIL.ILBinaryReader
open FSharp.Compiler.AbstractIL.Internal
open FSharp.Compiler.AbstractIL.Internal.Library

open FSharp.Compiler.AccessibilityLogic
open FSharp.Compiler.Ast
open FSharp.Compiler.CompileOps
open FSharp.Compiler.CompileOptions
open FSharp.Compiler.Driver

open Internal.Utilities
open Internal.Utilities.Collections
```

Beachten Sie, dass ein Zeilenumbruch topologische Ebenen trennt, wobei jede Ebene später alphanumerisch sortiert wird. Dadurch wird Code ordnungsgemäß organisiert, ohne versehentlich Werte zu shadoauen.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Verwenden von Klassen zum enthalten von Werten mit Nebeneffekten

Es gibt viele Male, wenn ein Wert initialisiert werden kann, z. b. beim Instanziieren eines Kontexts in einer Datenbank oder einer anderen Remote Ressource. Es ist verlockend, solche Dinge in einem Modul zu initialisieren und in nachfolgenden Funktionen zu verwenden:

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

Dies ist aus einigen Gründen häufig eine gute Idee:

Zuerst wird die Anwendungskonfiguration mit und in die Codebasis übermittelt `dep1` `dep2` . Dies ist in größeren Codebasen schwierig zu verwalten.

Zweitens sollten statisch initialisierte Daten keine Werte enthalten, die nicht Thread sicher sind, wenn die Komponente selbst mehrere Threads verwendet. Dies wird eindeutig durch verletzt `dep3` .

Schließlich wird die Modul Initialisierung in einen statischen Konstruktor für die gesamte Kompilierungseinheit kompiliert. Wenn ein Fehler bei der Initialisierung von Let-gebundenen Werten in diesem Modul auftritt, wird er als ein-Wert angezeigt, `TypeInitializationException` der für die gesamte Lebensdauer der Anwendung zwischengespeichert wird. Dies kann schwierig zu diagnostizieren sein. Es gibt in der Regel eine innere Ausnahme, die Sie zu einem bestimmten Zweck haben können. wenn dies nicht der Fall ist, gibt es nicht, was die Grundursache ist.

Verwenden Sie stattdessen einfach eine einfache Klasse zum Speichern von Abhängigkeiten:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Dies ermöglicht Folgendes:

1. Verschieben eines beliebigen abhängigen Zustands außerhalb der API selbst.
2. Die Konfiguration kann nun außerhalb der API durchgeführt werden.
3. Fehler bei der Initialisierung der abhängigen Werte werden wahrscheinlich nicht als Manifest angezeigt `TypeInitializationException` .
4. Die API ist jetzt einfacher zu testen.

## <a name="error-management"></a>Fehler Verwaltung

Die Fehler Verwaltung in großen Systemen ist ein komplexes und differenziertes Verhalten, und es gibt keine Silber Aufzählungen, um sicherzustellen, dass Ihre Systeme fehlertolerant sind und sich gut Verhalten. Die folgenden Richtlinien sollten Anleitungen zum Navigieren in diesem schwierigen Bereich bieten.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Darstellen von Fehler Fällen und ungültigen Zuständen in Typen, die in Ihrer Domäne intrinsisch sind

Bei Unterscheidungs- [Unions](../language-reference/discriminated-unions.md)bietet F # Ihnen die Möglichkeit, einen fehlerhaften Programmzustand in Ihrem Typsystem darzustellen. Zum Beispiel:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In diesem Fall gibt es drei bekannte Möglichkeiten, dass das Zurückziehen von Geld aus einem Bankkonto fehlschlagen kann. Jeder Fehlerfall wird im-Typ dargestellt und kann daher sicher im gesamten Programm behandelt werden.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f{am}"
    | InsufficientFunds balance -> printfn "Failed: balance is %f{balance}"
    | CardExpired expiredDate -> printfn "Failed: card expired on %O{expiredDate}"
    | UndisclosedFailure -> printfn "Failed: unknown"
```

Wenn Sie die verschiedenen Methoden modellieren können, mit denen in Ihrer Domäne ein Fehler **auftreten kann,** wird der Fehler Behandlungs Code nicht mehr als etwas behandelt, mit dem Sie zusätzlich zum regulären Programmablauf arbeiten müssen. Es ist einfach ein Teil des normalen Programmflusses und wird nicht als **außergewöhnlich** angesehen. Dies hat zwei wesentliche Vorteile:

1. Sie ist einfacher zu verwalten, wenn sich Ihre Domäne im Laufe der Zeit ändert.
2. Fehlerfälle sind einfacher für Komponententests.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Verwenden Sie Ausnahmen, wenn Fehler nicht mit Typen dargestellt werden können.

Nicht alle Fehler können in einer Problemdomäne dargestellt werden. Diese Arten von Fehlern sind *außergewöhnlich* , sodass Sie Ausnahmen in F # verursachen und abfangen können.

Zuerst wird empfohlen, dass Sie die [Richtlinien für den Ausnahme Entwurf](../../standard/design-guidelines/exceptions.md)lesen. Diese sind auch auf F # anwendbar.

Die wichtigsten in F # verfügbaren Konstrukte für das Auslassen von Ausnahmen sollten in der folgenden Reihenfolge berücksichtigt werden:

| Funktion | Syntax | Zweck |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Löst eine `System.ArgumentNullException` mit dem angegebenen Argument Namen aus. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Löst eine `System.ArgumentException` mit dem angegebenen Argument Namen und der angegebenen Meldung aus. |
| `invalidOp` | `invalidOp "message"` | Löst eine `System.InvalidOperationException` mit der angegebenen Meldung aus. |
|`raise`| `raise (ExceptionType("message"))` | Allgemeiner Mechanismus zum Auslösen von Ausnahmen. |
| `failwith` | `failwith "message"` | Löst eine `System.Exception` mit der angegebenen Meldung aus. |
| `failwithf` | `failwithf "format string" argForFormatString` | Löst eine `System.Exception` mit einer Meldung aus, die von der Format Zeichenfolge und Ihren Eingaben bestimmt wird. |

Verwenden `nullArg` `invalidArg` Sie, und `invalidOp` als Mechanismus zum Auslösen `ArgumentNullException` `ArgumentException` und `InvalidOperationException` bei Bedarf.

Die `failwith` -Funktion und die- `failwithf` Funktion sollten im allgemeinen vermieden werden, da Sie den `Exception` Basistyp und keine bestimmte Ausnahme auslöst. Gemäß den [Richtlinien für den Ausnahme Entwurf](../../standard/design-guidelines/exceptions.md)sollten Sie spezifischere Ausnahmen auslöst, wenn dies möglich ist.

### <a name="use-exception-handling-syntax"></a>Syntax für die Ausnahmebehandlung verwenden

F # unterstützt Ausnahme Muster über die `try...with` Syntax:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Die Abstimmung von Funktionen, die im Falle einer Ausnahme mit Musterabgleich durchgeführt werden sollen, kann etwas kompliziert sein, wenn Sie den Code bereinigen möchten. Eine solche Vorgehensweise ist die Verwendung [aktiver Muster](../language-reference/active-patterns.md) als Mittel zum Gruppieren von Funktionen in Bezug auf einen Fehlerfall mit einer Ausnahme selbst. Beispielsweise können Sie eine API nutzen, die beim Auslösen einer Ausnahme wertvolle Informationen in die Ausnahme Metadaten einschließt. In einigen Situationen kann es hilfreich sein, einen nützlichen Wert im Text der erfassten Ausnahme innerhalb des aktiven Musters zu entpacken und diesen Wert zurückzugeben.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Verwenden Sie keine monadische-Fehlerbehandlung zum Ersetzen von Ausnahmen.

Ausnahmen werden bei der funktionalen Programmierung als etwas Tabu betrachtet. Tatsächlich verstoßen Ausnahmen gegen Reinheit, daher ist es sicher, dass Sie nicht Recht funktional betrachtet werden. Dies ignoriert jedoch die Realität, in der der Code ausgeführt werden muss, und dass Laufzeitfehler auftreten können. Schreiben Sie im allgemeinen Code in der Annahme, dass die meisten Dinge weder rein noch Gesamt sind, um unangenehme Überraschungen zu minimieren.

Es ist wichtig, die folgenden Hauptstärken/Aspekte von Ausnahmen hinsichtlich ihrer Relevanz und Eignung in der .NET-Laufzeit und im sprachübergreifenden Ökosystem als Ganzes zu berücksichtigen:

1. Sie enthalten ausführliche Diagnoseinformationen, die beim Debuggen eines Problems sehr hilfreich sind.
2. Sie werden von der Laufzeit und anderen .NET-Sprachen gut verstanden.
3. Sie können im Vergleich zu Code, der aus seiner Methode entfernt *wird, signifikante* Bausteine verringern, indem eine Teilmenge ihrer Semantik auf Ad-hoc-Basis implementiert wird.

Dieser dritte Punkt ist wichtig. Bei nicht trivialen komplexen Vorgängen kann das Verwenden von Ausnahmen zum Umgang mit Strukturen wie diesem führen:

```fsharp
Result<Result<MyType, string>, string list>
```

Dies kann problemlos zu zerbrechlichem Code wie Muster Übereinstimmungen bei "getyptypisierten" Fehlern führen:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Außerdem kann es verlockend sein, jede Ausnahme im Wunsch nach einer "einfachen" Funktion zu verschlucken, die einen "schöneren" Typ zurückgibt:

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Leider `tryReadAllText` kann zahlreiche Ausnahmen basierend auf den unzähligen Dingen auslösen, die in einem Dateisystem auftreten können. dieser Code verwirft alle Informationen über das, was in Ihrer Umgebung tatsächlich schief geht. Wenn Sie diesen Code durch einen Ergebnistyp ersetzen, werden Sie wieder zur "erstaunlich typisierten" Fehlermeldungs-Verarbeitung zurückkehren:

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

Wenn Sie das Ausnahme Objekt selbst im `Error` Konstruktor platzieren, erzwingen Sie lediglich, dass Sie den Ausnahmetyp an der aufrufssite und nicht in der Funktion ordnungsgemäß behandeln. Auf diese Weise werden überprüfte Ausnahmen erstellt, die bekanntermaßen als Aufrufer einer API behandelt werden.

Eine gute Alternative zu den obigen Beispielen besteht darin, *bestimmte* Ausnahmen abzufangen und einen sinnvollen Wert im Kontext dieser Ausnahme zurückzugeben. Wenn Sie die `tryReadAllText` Funktion wie folgt ändern, `None` hat eine höhere Bedeutung:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Anstatt als Catch-all zu funktionieren, verarbeitet diese Funktion nun ordnungsgemäß den Fall, dass eine Datei nicht gefunden wurde, und weist diese Bedeutung einer Rückgabe zu. Dieser Rückgabewert kann diesem Fehlerfall zugeordnet werden, während keine Kontextinformationen verworfen werden oder Aufrufer gezwungen werden, einen Fall zu behandeln, der an diesem Punkt im Code möglicherweise nicht relevant ist.

Typen wie `Result<'Success, 'Error>` sind für grundlegende Vorgänge geeignet, bei denen Sie nicht eingebettet sind, und optionale F #-Typen eignen sich perfekt für die Darstellung, wenn etwas entweder *etwas* oder *nichts* zurückgeben könnte. Sie sind jedoch kein Ersatz für Ausnahmen und sollten nicht in einem Versuch verwendet werden, Ausnahmen zu ersetzen. Vielmehr sollten Sie umsichtig angewendet werden, um bestimmte Aspekte der Ausnahme-und Fehler Verwaltungs Richtlinie in gezielter Weise zu behandeln.

## <a name="partial-application-and-point-free-programming"></a>Partielle Anwendungs-und punktfreie Programmierung

F # unterstützt die partielle Anwendung und somit verschiedene Möglichkeiten zum Programmieren in einem Point-Free-Stil. Dies kann für die Wiederverwendung von Code innerhalb eines Moduls oder die Implementierung von etwas von Vorteil sein, aber es ist nicht möglich, öffentlich verfügbar zu machen. Im Allgemeinen ist die Point-Free-Programmierung keine Grundlage für sich selbst und kann eine bedeutende kognitive Barriere für Personen hinzufügen, die nicht in den Stil eintauchen.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Verwenden Sie keine partielle Anwendung und Currying in öffentlichen APIs.

Mit wenigen Ausnahmen kann die Verwendung einer partiellen Anwendung in öffentlichen APIs für Consumer verwirrend sein. In der Regel `let` sind-gebundene Werte in F #-Code **Werte**, nicht **Funktions Werte**. Das Kombinieren von Werten und Funktionswerten kann dazu führen, dass eine kleine Anzahl von Codezeilen in Exchange für einen sehr viel kognitiven mehr Aufwand gespeichert wird, insbesondere bei Kombination mit Operatoren wie z `>>` . b. zum Verfassen von Funktionen.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Sehen Sie sich die Auswirkungen auf die Tools für die punktfreie Programmierung an

Geschweiften Funktionen bezeichnen ihre Argumente nicht. Dies hat Auswirkungen auf das Tool. Beachten Sie die folgenden zwei Funktionen:

```fsharp
let func name age =
    printfn "My name is {name} and I am %d{age} years old!"

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Beide sind gültige Funktionen, aber `funcWithApplication` eine Curry-Funktion. Wenn Sie mit dem Mauszeiger auf die Typen in einem Editor zeigen, sehen Sie Folgendes:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

In Tools wie Visual Studio geben Quick Infos in Tools wie Visual Studio keine aussagekräftigen Informationen dazu, was die `string` `int` Eingabetypen und tatsächlich darstellen.

Wenn Sie auf einen Punkt freien Code wie den öffentlich verwendbaren Code stoßen `funcWithApplication` , empfiehlt es sich, eine vollständige weiterung-Erweiterung durchzuführen, damit die Tools für Argumente aussagekräftige Namen haben können.

Außerdem kann das Debuggen von Punkt freiem Code eine Herausforderung darstellen, wenn dies nicht möglich ist. Debugtools basieren auf Werten, die an Namen gebunden sind (z. b. `let` Bindungen), sodass Sie Zwischenwerte in der Mitte der Ausführung überprüfen können. Wenn Ihr Code keine zu überprüfenden Werte aufweist, müssen Sie nichts Debuggen. In Zukunft werden Debuggingtools möglicherweise so weiterentwickelt, dass diese Werte auf der Grundlage zuvor ausgeführter Pfade synthetisieren werden, aber es ist keine gute Idee, Ihre Wetten auf *potenzielle* Debuggingfunktionen zu

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Als Verfahren zum reduzieren interner Bausteine sollten Sie eine partielle Anwendung als Technik in Erwägung gezogen

Im Gegensatz zum vorherigen Punkt ist die partielle Anwendung ein wunderbares Tool zum Reduzieren von Code Steinen innerhalb einer Anwendung oder der tieferen internale einer API. Dies kann hilfreich für Komponententests bei der Implementierung komplizierterer APIs sein, bei denen Code Bausteine häufig ein Problem ist. Der folgende Code zeigt beispielsweise, wie Sie die meisten optimalen Frameworks durchführen können, ohne eine externe Abhängigkeit von einem solchen Framework zu treffen und eine Verwandte, maßgeschneiderte API erlernen zu müssen.

Sehen Sie sich beispielsweise die folgende Lösungs Topografie an:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` kann Code wie z. b. verfügbar machen:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Komponententests `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` sind leicht:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Durch das teilweise anwenden `doTransaction` von mit einem Kontext Objekt können Sie die Funktion in allen Komponententests aufzurufen, ohne jedes Mal einen simulierte Kontext erstellen zu müssen:

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

Diese Technik sollte nicht universell auf die gesamte CodeBase angewendet werden, aber Sie ist eine gute Möglichkeit, die Bausteine für komplizierte internale und Unittests zu verringern.

## <a name="access-control"></a>Zugriffssteuerung

F # verfügt über mehrere Optionen für die [Zugriffs Steuerung](../language-reference/access-control.md), die von den Funktionen geerbt werden, die in der .NET-Laufzeit verfügbar sind. Diese können nicht nur für Typen verwendet werden. Sie können Sie auch für Funktionen verwenden.

* Bevorzugen Sie nicht- `public` Typen und Member, bis Sie öffentlich nutzbar sein müssen. Dadurch wird auch das Paar der Consumer minimiert.
* Möchten Sie alle Hilfsfunktionen beibehalten `private` .
* Sie sollten die Verwendung von `[<AutoOpen>]` in einem privaten Modul von Hilfsfunktionen in Erwägung gezogen, wenn Sie zahlreich werden.

## <a name="type-inference-and-generics"></a>Typrückschluss und Generika

Mithilfe des Typrückschlusses können Sie viele Bausteine speichern. Und die automatische Generalisierung im F #-Compiler kann Ihnen dabei helfen, allgemeineren Code zu schreiben, bei dem Sie fast keinen zusätzlichen Aufwand benötigen. Diese Features sind jedoch nicht universell geeignet.

* Sie sollten Argument Namen mit expliziten Typen in öffentlichen APIs bezeichnen und sind hierfür nicht auf den Typrückschluss angewiesen.

    Der Grund hierfür ist, dass **Sie** die Form ihrer API steuern müssen, nicht den Compiler. Obwohl der Compiler eine gute Aufgabe beim Ableiten von Typen für Sie erledigen kann, ist es möglich, dass sich die Form der API ändert, wenn sich die internale, auf die Sie sich verlassen, geändert haben. Das ist möglicherweise das, was Sie möchten, aber es führt fast sicherlich zu einer wichtigen API-Änderung, die Downstreamconsumer dann behandeln müssen. Wenn Sie die Form ihrer öffentlichen API explizit steuern, können Sie stattdessen diese wichtigen Änderungen steuern. In DDD-Begriffen kann dies als antibeschädigungs Schicht angesehen werden.

* Sie sollten den generischen Argumenten einen aussagekräftigen Namen geben.

    Wenn Sie nicht wirklich generischen Code schreiben, der nicht spezifisch für eine bestimmte Domäne ist, kann ein aussagekräftiger Name anderen Programmierern helfen, die Domäne, in der Sie arbeiten, zu verstehen. Ein Typparameter `'Document` mit dem Namen im Kontext der Interaktion mit einer dokumentdatenbank macht es z. b. klarer, dass generische Dokumenttypen von der Funktion oder dem Member akzeptiert werden können, mit denen Sie arbeiten.

* Es empfiehlt sich, generische Typparameter mit PascalCase zu benennen.

    Dies ist die allgemeine Art und Weise, wie es in .net der Fall ist. Daher empfiehlt es sich, anstelle von snake_case oder CamelCase die PascalCase-Methode zu verwenden.

Zum Schluss ist die automatische Generalisierung nicht immer ein Segen für Personen, die noch nicht mit F # oder einer großen CodeBase vertraut sind. Es gibt einen kognitiven Aufwand bei der Verwendung generischer Komponenten. Wenn außerdem automatisch verallgemeinerte Funktionen nicht mit unterschiedlichen Eingabetypen verwendet werden (selbst wenn Sie als solche verwendet werden sollen), gibt es keinen echten Vorteil, wenn Sie zu diesem Zeitpunkt generisch sind. Denken Sie immer daran, ob der Code, den Sie schreiben, tatsächlich von generischen Vorteilen profitiert.

## <a name="performance"></a>Leistung

### <a name="consider-structs-for-small-types-with-high-allocation-rates"></a>Strukturen für kleine Typen mit hohen Zuordnungs Raten in Erwägung gezogen

Die Verwendung von Strukturen (auch als Werttypen bezeichnet) kann für Code zu einer höheren Leistung führen, da Sie in der Regel die Zuordnung von Objekten vermeidet. Strukturen sind jedoch nicht immer eine "schnellere Schaltfläche": Wenn die Größe der Daten in einer Struktur 16 Bytes überschreitet, kann das Kopieren der Daten oft zu mehr CPU-Zeit als die Verwendung eines Referenz Typs führen.

Berücksichtigen Sie die folgenden Bedingungen, um zu bestimmen, ob Sie eine Struktur verwenden sollten:

- Wenn die Größe Ihrer Daten 16 Bytes oder kleiner ist.
- Wenn es wahrscheinlich ist, dass viele Instanzen dieser Typen im Arbeitsspeicher eines laufenden Programms ansässig sind.

Wenn die erste Bedingung zutrifft, sollten Sie im Allgemeinen eine Struktur verwenden. Wenn beides zutrifft, sollten Sie fast immer eine Struktur verwenden. Es gibt möglicherweise Fälle, in denen die vorherigen Bedingungen zutreffen, aber die Verwendung einer Struktur ist nicht besser oder schlechter als die Verwendung eines Referenz Typs, aber Sie sind wahrscheinlich selten. Es ist wichtig, immer zu messen, wenn Änderungen wie diese vorgenommen werden, und nicht mit Annahmen oder intuitions arbeiten.

#### <a name="consider-struct-tuples-when-grouping-small-value-types-with-high-allocation-rates"></a>Strukturtupel bei der Gruppierung von kleinen Werttypen mit hohen Zuordnungs Sätzen in Erwägung ziehen

Beachten Sie die folgenden zwei Funktionen:

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

Wenn Sie diese Funktionen mit einem statistischen [Benchmarktool wie benchmarkdotnet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass die `runWithStructTuple` Funktion, die strukturtupel verwendet, 40% schneller ausführt und keinen Arbeitsspeicher zuweist.

Diese Ergebnisse sind jedoch nicht immer in Ihrem eigenen Code zu sehen. Wenn Sie eine Funktion als markieren `inline` , kann der Code, der referenztupel verwendet, einige zusätzliche Optimierungen erhalten, oder der Code, der die zuordnen würde, könnte einfach entfernt werden. Sie sollten die Ergebnisse immer Messen, wenn die Leistung relevant ist, und niemals basierend auf Annahme oder Intuition arbeiten.

#### <a name="consider-struct-records-when-the-type-is-small-and-has-high-allocation-rates"></a>Strukturdaten Sätze in Erwägung gezogen, wenn der Typ klein ist und hohe Zuweisungs Raten aufweist

Die zuvor beschriebene Regel für den Ziehpunkt enthält auch [F #-Daten Satz Typen](../language-reference/records.md). Beachten Sie die folgenden Datentypen und Funktionen, die Sie verarbeiten:

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

Dies ähnelt dem vorherigen tupelcode, aber dieses Mal verwendet das Beispiel Datensätze und eine Inline interne Funktion.

Wenn Sie diese Funktionen mit einem statistischen [Benchmarktool wie benchmarkdotnet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass `processStructPoint` fast 60% schneller ausgeführt wird und nichts auf dem verwalteten Heap zuweist.

#### <a name="consider-struct-discriminated-unions-when-the-data-type-is-small-with-high-allocation-rates"></a>Sie sollten strukturunterscheidungs-Unions in Erwägung gezogen werden, wenn der Datentyp klein ist und hohe

Die vorherigen Beobachtungen zur Leistung mit strukturtupeln und Datensätzen sind auch für [F #](../language-reference/discriminated-unions.md)-Unterscheidungs-Unions vorgesehen. Betrachten Sie folgenden Code:

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

Es ist üblich, bei der Domänen Modellierung eine diskriminierte Einzelfall-Unions wie diese zu definieren. Wenn Sie diese Funktionen mit einem statistischen [Benchmarktool wie benchmarkdotnet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass `structReverseName` ungefähr 25% schneller ist als `reverseName` bei kleinen Zeichen folgen. Bei großen Zeichen folgen werden beide ungefähr identisch sein. Daher ist es in diesem Fall immer empfehlenswert, eine Struktur zu verwenden. Wie bereits erwähnt, sollten Sie immer Messen und nicht auf Annahmen oder Intuitionen anwenden.

Obwohl im vorherigen Beispiel gezeigt wurde, dass eine strukturunterscheidungs-Union eine bessere Leistung erzielt hat, sind beim Modellieren einer Domäne häufig größere Unterscheidungs-Unions vorhanden. Größere Datentypen wie können nicht auch durchgeführt werden, wenn es sich um Strukturen handelt, die von den Vorgängen für Sie abhängig sind, da mehr Kopiervorgänge beteiligt sein könnten.

### <a name="functional-programming-and-mutation"></a>Funktionale Programmierung und Mutation

F #-Werte sind standardmäßig unveränderlich, sodass Sie bestimmte Klassen von Fehlern vermeiden können (insbesondere solche, die Parallelität und Parallelität betreffen). In bestimmten Fällen, um eine optimale (oder sogar sinnvolle) Effizienz der Ausführungszeit oder Speicher Belegungen zu erzielen, kann jedoch eine bestimmte arbeitsspanne am besten mithilfe einer direkten Mutation des Zustands implementiert werden. Dies ist in einer Opt-in-Basis mit F # mit dem- `mutable` Schlüsselwort möglich.

Die Verwendung von `mutable` in F # kann sich in Bezug auf die funktionale Reinheit widersprechen. Dies ist verständlich, aber die funktionale Reinheit überall kann mit den Leistungszielen in Konflikt stehen. Eine Gefährdung besteht darin, die Mutation so zu kapseln, dass Aufrufer nicht darauf achten müssen, was geschieht, wenn eine Funktion aufgerufen wird. Dies ermöglicht es Ihnen, eine funktionale Schnittstelle über eine mutations basierte Implementierung für Leistungs kritischen Code zu schreiben.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Umbruch von änderbaren Code in unveränderlichen Schnittstellen

Mit referenzieller Transparenz als Ziel ist es wichtig, Code zu schreiben, der den änderbaren Unterbauch von Leistungs kritischen Funktionen nicht verfügbar macht. Der folgende Code implementiert beispielsweise die- `Array.contains` Funktion in der F #-Kernbibliothek:

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

Wenn Sie diese Funktion mehrmals aufrufen, wird das zugrunde liegende Array nicht geändert, und es ist nicht erforderlich, dass Sie einen änderbaren Zustand bei der Nutzung beibehalten. Sie ist referenziell transparent, obwohl fast jede Codezeile darin eine Mutation verwendet.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>Sie sollten änderbare Daten in Klassen kapseln.

Im vorherigen Beispiel wurde eine einzelne Funktion verwendet, um Vorgänge mit veränderbaren Daten zu kapseln. Dies ist für komplexere Datensätze nicht immer ausreichend. Beachten Sie die folgenden Funktions Sätze:

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

Dieser Code ist leistungsfähig, macht aber die mutations basierte Datenstruktur verfügbar, die Aufrufer für die Wartung verantwortlich sind. Dies kann in einer Klasse ohne zugrunde liegende Member umschließt werden, die sich ändern können:

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` kapselt die zugrunde liegende mutations basierte Datenstruktur und erzwingt dadurch keine Aufrufer, um die zugrunde liegende Datenstruktur beizubehalten. Klassen sind eine leistungsstarke Möglichkeit, Daten und Routinen zu kapseln, die mutations basiert sind, ohne die Details für Aufrufer verfügbar zu machen.

#### <a name="prefer-let-mutable-to-reference-cells"></a>Bevorzugen des `let mutable` Verweises auf Zellen

Verweis Zellen können anstelle des Werts selbst den Verweis auf einen Wert darstellen. Obwohl Sie für Leistungs kritischen Code verwendet werden können, wird dies nicht empfohlen. Betrachten Sie das folgende Beispiel:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

Durch die Verwendung einer Referenzzelle wird nun der gesamte nachfolgende Code "verschmutzt", wobei die zugrunde liegenden Daten dereferenziert und neu referenziert werden müssen. Verwenden Sie stattdessen Folgendes `let mutable` :

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Abgesehen von der einzelnen Stelle der Mutation in der Mitte des Lambda-Ausdrucks kann der gesamte andere Code, der berührt, dies auf `acc` eine Weise tun, die sich nicht von der Verwendung eines Normal `let` gebundenen unveränderlichen Werts unterscheidet. Dadurch wird es einfacher, sich im Laufe der Zeit zu ändern.

## <a name="object-programming"></a>Objekt Programmierung

F # bietet vollständige Unterstützung für Objekte und objektorientierte Konzepte (OO). Obwohl viele OO-Konzepte leistungsstark und nützlich sind, sind nicht alle davon ideal zu verwenden. Die folgenden Listen bieten Anleitungen zu den Kategorien von OO-Features auf hoher Ebene.

**In vielen Situationen sollten Sie diese Features verwenden:**

* Punkt Notation ( `x.Length` )
* Instanzmember
* Implizite Konstruktoren
* Statische Member
* Indexer-Notation ( `arr.[x]` )
* Benannte und optionale Argumente
* Schnittstellen und Schnittstellen Implementierungen

**Erreichen Sie diese Features nicht zuerst, aber wenden Sie Sie mit Bedacht an, wenn Sie ein Problem lösen können:**

* Methodenüberladung
* Gekapselte änderbare Daten
* Operatoren für Typen
* Auto-Eigenschaften
* Implementieren von `IDisposable` und `IEnumerable`
* Typerweiterungen
* Ereignisse
* Strukturen
* Delegaten
* Enumerationen

**Vermeiden Sie diese Features im Allgemeinen, wenn Sie Sie nicht verwenden müssen:**

* Vererbungs basierte Typhierarchien und Implementierungs Vererbung
* Nullen und `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Komposition vor Vererbung bevorzugen

Die [Komposition über Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist eine lange Ausdrucksweise, der guter F #-Code entsprechen kann. Das Grundprinzip ist, dass Sie keine Basisklasse verfügbar machen und Aufrufer zwingen, von dieser Basisklasse zu erben, um die Funktionalität zu erhalten.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Verwenden von Objekt Ausdrücken zum Implementieren von Schnittstellen, wenn Sie keine Klasse benötigen

[Objekt Ausdrücke](../language-reference/object-expressions.md) ermöglichen es Ihnen, Schnittstellen im laufenden Betrieb zu implementieren, wobei die implementierte Schnittstelle an einen Wert gebunden wird, ohne dass dies innerhalb einer Klasse erforderlich ist. Dies ist praktisch, wenn Sie _nur_ die-Schnittstelle implementieren müssen und keine vollständige Klasse benötigen.

Hier ist beispielsweise der Code, der in [ionide](https://ionide.io/) ausgeführt wird, um eine Code Korrektur Aktion bereitzustellen, wenn Sie ein Symbol hinzugefügt haben, für das Sie keine- `open` Anweisung haben:

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

Da eine Klasse bei der Interaktion mit der Visual Studio Code-API nicht benötigt wird, sind Objekt Ausdrücke hierfür ein ideales Tool. Sie sind auch für Komponententests nützlich, wenn Sie eine Schnittstelle mit Testroutinen auf Ad-hoc-Weise auslagern möchten.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>Typabkürzungen zum Verkürzen von Signaturen in Erwägung gezogen

[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine bequeme Möglichkeit, einem anderen Typ eine Bezeichnung zuzuweisen, z. b. eine Funktions Signatur oder einen komplexeren Typ. Der folgende Alias weist z. b. eine Bezeichnung zu, die zum Definieren einer Berechnung mit [cntk](/cognitive-toolkit/), einer Deep Learning-Bibliothek, benötigt wird:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Der `Computation` Name ist eine bequeme Möglichkeit, jede Funktion anzugeben, die mit der Signatur übereinstimmt, die Sie Aliasing. Die Verwendung von typabkürzungen wie diesem ist praktisch und ermöglicht einen kompakteren Code.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Vermeiden Sie die Verwendung von typabkürzungen zur Darstellung Ihrer Domäne.

Obwohl typabkürzungen für die Angabe eines Namens an Funktions Signaturen geeignet sind, können Sie beim abkürzen anderer Typen verwirrend sein. Beachten Sie diese Abkürzung:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Dies kann auf verschiedene Arten verwirrend sein:

* `BufferSize` ist keine Abstraktion. Es ist nur ein anderer Name für eine ganze Zahl.
* Wenn `BufferSize` in einer öffentlichen API verfügbar gemacht wird, kann es leicht interpretiert werden, um mehr als nur zu bedeuten `int` . Im Allgemeinen verfügen Domänen Typen über mehrere Attribute und sind keine primitiven Typen wie `int` . Diese Abkürzung verstößt gegen diese Annahme.
* Die groß- `BufferSize` /Kleinschreibung von (PascalCase) impliziert, dass dieser Typ mehr Daten enthält.
* Dieser Alias bietet im Vergleich zur Bereitstellung eines benannten Arguments für eine Funktion keine bessere Übersichtlichkeit.
* Die Abkürzung wird in der kompilierten Il nicht angezeigt. Es handelt sich lediglich um eine ganze Zahl, und dieser Alias ist ein Kompilierzeit Konstrukt.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

Zusammenfassend ist der Fall, dass es sich bei den typabkürzungen um **keine** Abstraktionen für die Typen handelt, die Sie abkürzen. Im vorherigen Beispiel `BufferSize` ist nur ein `int` unter dem Cover, ohne zusätzliche Daten und keine Vorteile des Typsystems außer dem, was bereits vorhanden ist `int` .

Ein alternativer Ansatz für die Verwendung von typabkürzungen zur Darstellung einer Domäne ist die Verwendung von unitunterscheidungs-Unions. Das vorherige Beispiel kann wie folgt modelliert werden:

```fsharp
type BufferSize = BufferSize of int
```

Wenn Sie Code schreiben, der in Bezug auf `BufferSize` und den zugrunde liegenden Wert verhält, müssen Sie einen erstellen, anstatt eine beliebige ganze Zahl zu übergeben:

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

Dadurch wird die Wahrscheinlichkeit verringert, dass versehentlich eine beliebige Ganzzahl an die `send` Funktion übergeben wird, da der Aufrufer einen Typ erstellen muss `BufferSize` , um einen Wert zu schließen, bevor die Funktion aufgerufen wird.
