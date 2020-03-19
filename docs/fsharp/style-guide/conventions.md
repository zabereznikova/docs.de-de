---
title: Codekonventionen für F#
description: Lernen Sie allgemeine Richtlinien und Idiome beim Schreiben von F-Code.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401148"
---
# <a name="f-coding-conventions"></a>Codekonventionen für F#

Die folgenden Konventionen basieren auf der Erfahrung in der Arbeit mit großen F-Codebases. Die [fünf Prinzipien des guten F-Codes](index.md#five-principles-of-good-f-code) sind die Grundlage jeder Empfehlung. Sie beziehen sich auf die Richtlinien für den Entwurf von [F-Komponenten](component-design-guidelines.md), sind jedoch für jeden F-Code anwendbar, nicht nur für Komponenten wie Bibliotheken.

## <a name="organizing-code"></a>Organisieren von Code

Es gibt zwei primäre Möglichkeiten, Code zu organisieren: Module und Namespaces. Diese sind ähnlich, weisen jedoch die folgenden Unterschiede auf:

* Namespaces werden als .NET-Namespaces kompiliert. Module werden als statische Klassen kompiliert.
* Namespaces sind immer oberste Ebene. Module können auf der obersten Ebene sein und in anderen Modulen verschachtelt sein.
* Namespaces können mehrere Dateien umfassen. Module können dies nicht.
* Module können mit `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`dekoriert werden.

Die folgenden Richtlinien helfen Ihnen, diese zum Organisieren des Codes zu verwenden.

### <a name="prefer-namespaces-at-the-top-level"></a>Bevorzugen Sie Namespaces auf der obersten Ebene

Für alle öffentlich-beschaffenen Codes sind Namespaces Modulen auf der obersten Ebene vorziehend. Da sie als .NET-Namespaces kompiliert werden, sind sie ohne Probleme aus C-Code verbrauchsfähig.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Die Verwendung eines Moduls der obersten Ebene scheint möglicherweise nicht anders zu sein, wenn es nur `MyClass` von `MyCode` F-Dateien aufgerufen wird, aber für C-Verbraucher können Anrufer überrascht sein, wenn sie sich für das Modul qualifizieren müssen.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Sorgfältig anwenden`[<AutoOpen>]`

Das `[<AutoOpen>]` Konstrukt kann den Umfang dessen verschmutzen, was Anrufern zur Verfügung steht, und die Antwort darauf, woher etwas kommt, ist "Magisch". Das ist nicht gut. Eine Ausnahme von dieser Regel ist die F-Core-Bibliothek selbst (obwohl diese Tatsache auch etwas umstritten ist).

Es ist jedoch eine Bequemlichkeit, wenn Sie über Hilfsfunktionen für eine öffentliche API verfügen, die Sie getrennt von dieser öffentlichen API organisieren möchten.

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

Auf diese Weise können Sie Implementierungsdetails sauber von der öffentlichen API einer Funktion trennen, ohne einen Helfer bei jedem Aufruf vollständig qualifizieren zu müssen.

Darüber hinaus kann das Aussetzen von Erweiterungsmethoden und Ausdrucksgeneratoren auf Namespaceebene mit ordentlich ausgedrückt `[<AutoOpen>]`werden.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Verwenden `[<RequireQualifiedAccess>]` Sie immer dann, wenn Namen in Konflikt geraten könnten oder Sie das Gefühl haben, dass dies bei der Lesbarkeit hilft

Das `[<RequireQualifiedAccess>]` Hinzufügen des Attributs zu einem Modul weist darauf hin, dass das Modul möglicherweise nicht geöffnet wird und dass Verweise auf die Elemente des Moduls einen expliziten qualifizierten Zugriff erfordern. Das `Microsoft.FSharp.Collections.List` Modul verfügt beispielsweise über dieses Attribut.

Dies ist nützlich, wenn Funktionen und Werte im Modul Namen haben, die wahrscheinlich mit Namen in anderen Modulen in Konflikt stehen. Der Erfordernis eines qualifizierten Zugriffs kann die langfristige Wartbarkeit und Evolvierbarkeit einer Bibliothek erheblich erhöhen.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Sortieren `open` von Anweisungen topologisch

In f- ist die Reihenfolge der `open` Erklärungen wichtig, auch mit Erklärungen. Dies ist anders als bei `using` `using static` C, wo die Wirkung dieser Anweisungen in einer Datei unabhängig ist und unabhängig ist.

Elemente, die in einen Bereich geöffnet werden, können andere bereits vorhandene Elemente in F-Bereich überschatten. Dies bedeutet, `open` dass das Neuanordnen von Anweisungen die Bedeutung von Code ändern könnte. Daher wird keine beliebige Sortierung aller `open` Anweisungen (z. B. alphanumerisch) empfohlen, damit Sie nicht ein anderes Verhalten generieren, das Sie möglicherweise erwarten.

Stattdessen empfehlen wir, dass Sie sie [topologisch](https://en.wikipedia.org/wiki/Topological_sorting)sortieren; Das heißt, `open` ordnen Sie Ihre Anweisungen in der Reihenfolge an, in der _Ebenen_ Ihres Systems definiert sind. Die alphanumerische Sortierung innerhalb verschiedener topologischer Schichten kann ebenfalls in Betracht gezogen werden.

Hier ist z. B. die topologische Sortierung für die öffentliche API-Datei des F-Compilerdiensts:

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

Beachten Sie, dass ein Zeilenumbruch topologische Layer trennt, wobei jede Ebene anschließend alphanumerisch sortiert wird. Dadurch wird Code sauber organisiert, ohne versehentlich Werte zu beschatten.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Verwenden von Klassen zum Enthalten von Werten mit Nebenwirkungen

Es gibt viele Male, in denen das Initialisieren eines Werts Nebenwirkungen haben kann, z. B. das Instanziieren eines Kontexts in einer Datenbank oder einer anderen Remoteressource. Es ist verlockend, solche Dinge in einem Modul zu initialisieren und in nachfolgenden Funktionen zu verwenden:

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

Dies ist oft eine schlechte Idee aus einigen Gründen:

Zuerst wird die Anwendungskonfiguration in `dep1` die `dep2`Codebasis mit und übertragen. Dies ist in größeren Codebasen nur schwer zu verwalten.

Zweitens sollten statisch initialisierte Daten keine Werte enthalten, die nicht threadsicher sind, wenn die Komponente selbst mehrere Threads verwendet. Dies wird `dep3`eindeutig durch verletzt.

Schließlich wird die Modulinitialisierung in einen statischen Konstruktor für die gesamte Kompilierungseinheit kompiliert. Wenn in diesem Modul ein Fehler bei der let-bound-Wertinitialisierung auftritt, manifestiert er sich als ein, `TypeInitializationException` der dann für die gesamte Lebensdauer der Anwendung zwischengespeichert wird. Dies kann schwierig zu diagnostizieren sein. Es gibt in der Regel eine innere Ausnahme, über die Sie versuchen können, zu denken, aber wenn es nicht gibt, dann gibt es keine Aussage darüber, was die Ursache ist.

Verwenden Sie stattdessen einfach eine einfache Klasse, um Abhängigkeiten zu halten:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Dies ermöglicht Folgendes:

1. Durch Pushen eines abhängigen Status außerhalb der API selbst.
2. Die Konfiguration kann nun außerhalb der API erfolgen.
3. Fehler bei der Initialisierung für abhängige `TypeInitializationException`Werte werden sich wahrscheinlich nicht als manifestieren.
4. Die API ist jetzt einfacher zu testen.

## <a name="error-management"></a>Fehlerverwaltung

Fehlermanagement in großen Systemen ist ein komplexes und nuanciertes Unterfangen, und es gibt keine silbernen Kugeln, um sicherzustellen, dass Ihre Systeme fehlertolerant sind und sich gut verhalten. Die folgenden Richtlinien sollten Anleitungen für die Navigation in diesem schwierigen Bereich bieten.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Stellen Sie Fehlerfälle und ungültigen Status in Typen dar, die Ihrer Domäne innewohnen

Mit Diskriminierten Unions können Sie mit ["Diskriminierte Unions"](../language-reference/discriminated-unions.md)einen fehlerhaften Programmstatus in Ihrem Typsystem darstellen. Beispiel:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In diesem Fall gibt es drei bekannte Möglichkeiten, wie das Abheben von Geld von einem Bankkonto fehlschlagen kann. Jeder Fehlerfall wird im Typ dargestellt und kann somit im gesamten Programm sicher behandelt werden.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

Wenn Sie im Allgemeinen die verschiedenen Möglichkeiten modellieren können, wie etwas in Ihrer Domäne **fehlschlagen** kann, wird Fehlerbehandlungscode nicht mehr als etwas behandelt, mit dem Sie sich zusätzlich zum regulären Programmfluss befassen müssen. Es ist einfach ein Teil des normalen Programmflusses und nicht als **außergewöhnlich**betrachtet. Dies hat zwei Hauptvorteile:

1. Es ist einfacher zu verwalten, wenn sich Ihre Domäne im Laufe der Zeit ändert.
2. Fehlerfälle sind einfacher zu einheitstest.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Ausnahmen verwenden, wenn Fehler nicht mit Typen dargestellt werden können

Nicht alle Fehler können in einer Problemdomäne dargestellt werden. Diese Art von Fehlern sind *außergewöhnlich,* daher die Fähigkeit, Ausnahmen in F zu erhöhen und zu fangen.

Zunächst wird empfohlen, die Richtlinien für den [Ausnahmeentwurf](../../standard/design-guidelines/exceptions.md)zu lesen. Diese gelten auch für die F-Datei.

Die wichtigsten Konstrukte, die für das Auslösen von Ausnahmen in F-Code verfügbar sind, sollten in der folgenden Reihenfolge der Präferenz betrachtet werden:

| Funktion | Syntax | Zweck |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Löst `System.ArgumentNullException` a mit dem angegebenen Argumentnamen aus. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Löst `System.ArgumentException` eine mit einem angegebenen Argumentnamen und einer angegebenen Nachricht aus. |
| `invalidOp` | `invalidOp "message"` | Löst `System.InvalidOperationException` eine mit der angegebenen Nachricht aus. |
|`raise`| `raise (ExceptionType("message"))` | Allzweckmechanismus zum Auslösen von Ausnahmen. |
| `failwith` | `failwith "message"` | Löst `System.Exception` eine mit der angegebenen Nachricht aus. |
| `failwithf` | `failwithf "format string" argForFormatString` | Löst `System.Exception` eine mit einer Nachricht aus, die durch die Formatzeichenfolge und ihre Eingaben bestimmt wird. |

Verwenden `nullArg` `invalidArg` Sie `invalidOp` , und `ArgumentNullException`als `ArgumentException` `InvalidOperationException` Mechanismus zum Auslösen von , und ggf..

Die `failwith` `failwithf` und Funktionen sollten im Allgemeinen vermieden `Exception` werden, da sie den Basistyp und keine bestimmte Ausnahme auslösen. Gemäß den Richtlinien für den [Ausnahmeentwurf](../../standard/design-guidelines/exceptions.md)möchten Sie, wenn möglich, spezifischere Ausnahmen auslösen.

### <a name="using-exception-handling-syntax"></a>Verwenden der Syntax für die Ausnahmebehandlung

Über die `try...with` Syntax unterstützt F- Ausnahmemuster:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Das Abgleichen der Funktionalität, die angesichts einer Ausnahme mit dem Musterabgleich durchgeführt werden soll, kann etwas schwierig sein, wenn Sie den Code sauber halten möchten. Eine möglichkeit, dies zu behandeln, besteht darin, [aktive Muster](../language-reference/active-patterns.md) als Mittel zu verwenden, um Funktionen zu gruppieren, die einen Fehlerfall mit einer Ausnahme selbst umgeben. Sie können z. B. eine API verwenden, die beim Auslösen einer Ausnahme wertvolle Informationen in die Ausnahmemetadaten einschließt. Das Entpacken eines nützlichen Werts im Körper der erfassten Ausnahme innerhalb des aktiven Musters und das Zurückgeben dieses Werts kann in einigen Situationen hilfreich sein.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Verwenden Sie keine monadische Fehlerbehandlung, um Ausnahmen zu ersetzen

Ausnahmen werden in der funktionalen Programmierung als etwas tabu angesehen. In der Tat, Ausnahmen verletzen Reinheit, so ist es sicher, sie nicht ganz funktionsfähig zu betrachten. Dadurch wird jedoch die Realität ignoriert, wo Code ausgeführt werden muss, und dass Laufzeitfehler auftreten können. Im Allgemeinen schreiben Sie Code unter der Annahme, dass die meisten Dinge weder rein noch vollständig sind, um unangenehme Überraschungen zu minimieren.

Es ist wichtig, die folgenden Kernstärken/Aspekte von Ausnahmen in Bezug auf ihre Relevanz und Angemessenheit im .NET-Laufzeit- und sprachübergreifenden Ökosystem als Ganzes zu berücksichtigen:

1. Sie enthalten detaillierte Diagnoseinformationen, was beim Debuggen eines Problems sehr hilfreich ist.
2. Sie werden von der Laufzeit und anderen .NET-Sprachen gut verstanden.
3. Sie können im Vergleich zu Code, der aus dem Weg geht, um Ausnahmen zu *vermeiden,* signifikante Bausteine reduzieren, indem sie eine Teilmenge ihrer Semantik ad hoc implementieren.

Dieser dritte Punkt ist von entscheidender Bedeutung. Bei nicht trivialen komplexen Vorgängen kann die Nichtverwendung von Ausnahmen zu Strukturen wie diesen führen:

```fsharp
Result<Result<MyType, string>, string list>
```

Was leicht zu fragilem Code wie Musterabgleich bei "stringly-typed"-Fehlern führen kann:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Darüber hinaus kann es verlockend sein, jede Ausnahme in dem Wunsch nach einer "einfachen" Funktion zu schlucken, die einen "niceren" Typ zurückgibt:

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Leider `tryReadAllText` können zahlreiche Ausnahmen auf der Grundlage der unzähligen Dinge, die auf einem Dateisystem passieren können, auslösen, und dieser Code verwirft alle Informationen darüber, was in Ihrer Umgebung tatsächlich schief gehen könnte. Wenn Sie diesen Code durch einen Ergebnistyp ersetzen, kehren Sie zur Analyse der Fehlermeldung "stringly-typed" zurück:

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

Und das Platzieren des `Error` Ausnahmeobjekts selbst im Konstruktor zwingt Sie nur, den Ausnahmetyp an der Aufrufsite und nicht in der Funktion ordnungsgemäß zu behandeln. Dadurch werden effektiv geprüfte Ausnahmen erstellt, die als Aufrufer einer API notorisch unlustig sind.

Eine gute Alternative zu den obigen Beispielen besteht darin, *bestimmte* Ausnahmen abzufangen und im Kontext dieser Ausnahme einen aussagekräftigen Wert zurückzugeben. Wenn Sie `tryReadAllText` die Funktion `None` wie folgt ändern, hat mehr Bedeutung:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Anstatt als Catch-All zu fungieren, wird diese Funktion nun den Fall richtig behandeln, wenn eine Datei nicht gefunden wurde, und diese Bedeutung einer Rückgabe zuweisen. Dieser Rückgabewert kann diesem Fehlerfall zugeordnet werden, ohne Kontextinformationen zu verwerfen oder Aufrufer zu zwingen, sich mit einem Fall zu befassen, der an diesem Punkt des Codes möglicherweise nicht relevant ist.

Typen, `Result<'Success, 'Error>` z. B. eignen sich für grundlegende Vorgänge, bei denen sie nicht geschachtelt sind, und optionale Typen von F- sind perfekt zum Darstellen, wenn etwas *etwas* oder *nichts*zurückgeben könnte. Sie ersetzen jedoch keine Ausnahmen und sollten nicht verwendet werden, um Ausnahmen zu ersetzen. Vielmehr sollten sie mit Bedacht angewendet werden, um bestimmte Aspekte der Ausnahme- und Fehlerverwaltungspolitik gezielt anzugehen.

## <a name="partial-application-and-point-free-programming"></a>Teilanwendung und punktfreie Programmierung

Die Datei unterstützt die partielle Anwendung und damit verschiedene Möglichkeiten, punktfrei zu programmieren. Dies kann für die Wiederverwendung von Code innerhalb eines Moduls oder die Implementierung von etwas von Vorteil sein, aber es ist nicht etwas, das öffentlich verfügbar gemacht werden kann. Im Allgemeinen ist punktfreie Programmierung keine Tugend an sich und kann eine signifikante kognitive Barriere für Menschen hinzufügen, die nicht in den Stil eingetaucht sind.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Verwenden Sie keine partielle Anwendung und Currying in öffentlichen APIs

Mit wenig Ausnahme kann die Verwendung von Partizipasten in öffentlichen APIs für Verbraucher verwirrend sein. In `let`der Regel sind -gebundene Werte im F-Code **Werte,** keine **Funktionswerte**. Das Zusammenführen von Werten und Funktionswerten kann dazu führen, dass eine kleine Anzahl von Codezeilen `>>` im Austausch für einen ziemlich enerbierten kognitiven Overhead gespeichert wird, insbesondere wenn sie mit Operatoren kombiniert werden, die z. B. Funktionen erstellen.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Berücksichtigen Sie die Auswirkungen auf die Werkzeugerstellung für die punktfreie Programmierung

Curried-Funktionen kennzeichnen ihre Argumente nicht. Dies hat Auswirkungen auf die Werkzeugisierung. Berücksichtigen Sie die folgenden beiden Funktionen:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Beide sind gültige `funcWithApplication` Funktionen, sind jedoch eine Curry-Funktion. Wenn Sie den Mauszeiger über ihre Typen in einem Editor bewegen, sehen Sie dies:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

Auf der Aufrufsite geben Tooltips in Tools wie Visual Studio keine `string` aussagekräftigen Informationen darüber, was die Eingabetypen `int` tatsächlich darstellen.

Wenn Sie punktfreien Code `funcWithApplication` wie diesen öffentlich verbrauchsfähig begegnen, wird empfohlen, eine vollständige Erweiterung von ,,,"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

Darüber hinaus kann das Debuggen von punktfreiem Code eine Herausforderung, wenn nicht gar unmöglich sein. Debugtools basieren auf Werten, die an `let` Namen gebunden sind (z. B. Bindungen), sodass Sie Zwischenwerte während der Ausführung überprüfen können. Wenn der Code keine Werte zum Überprüfen hat, gibt es nichts zu debuggen. In Zukunft können sich Debugging-Tools weiterentwickeln, um diese Werte basierend auf zuvor ausgeführten Pfaden zu synthetisieren, aber es ist keine gute Idee, Ihre Wetten auf *potenzielle* Debugging-Funktionalität abzusichern.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Betrachten Sie die partielle Anwendung als eine Technik, um interne Boilerplate zu reduzieren

Im Gegensatz zum vorherigen Punkt ist die Partielle Anwendung ein wunderbares Werkzeug zur Reduzierung von Boilerplate innerhalb einer Anwendung oder der tieferen Innenräume einer API. Es kann hilfreich sein, wenn Komponenten die Implementierung komplizierterer APIs testen, bei denen die Bausteine oft ein Schmerz sind. Der folgende Code zeigt beispielsweise, wie Sie das erreichen können, was Ihnen die meisten Mocking-Frameworks bieten, ohne eine externe Abhängigkeit von einem solchen Framework zu übernehmen und eine zugehörige maßgeschneiderte API zu erlernen.

Betrachten Sie beispielsweise die folgende Lösungstopographie:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj`kann Code verfügbar machen, z. B.:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

Komponententests `Transactions.doTransaction` `ImplementationLogic.Tests.fsproj` in sind einfach:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Wenn `doTransaction` Sie teilweise mit einem Mocking-Kontextobjekt angewendet werden, können Sie die Funktion in allen Komponententests aufrufen, ohne jedes Mal einen simulierten Kontext erstellen zu müssen:

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

Diese Technik sollte nicht universell auf Ihre gesamte Codebasis angewendet werden, aber es ist eine gute Möglichkeit, Boilerplate für komplizierte Interna und Komponententests dieser Interna zu reduzieren.

## <a name="access-control"></a>Zugriffssteuerung

Die Option ["F"](../language-reference/access-control.md)verfügt über mehrere Optionen für die Zugriffssteuerung , die von dem geerbt wurde, was in der .NET-Laufzeit verfügbar ist. Diese sind nicht nur für Typen nutzbar - Sie können sie auch für Funktionen verwenden.

* Bevorzugen Sie`public` Nicht-Typen und Member, bis Sie sie öffentlich verbrauchsfähig sein müssen. Dies minimiert auch, was Verbraucher paaren.
* Bemühen Sie sich, `private`alle Helfer-Funktionalität zu behalten .
* Erwägen Sie `[<AutoOpen>]` die Verwendung auf einem privaten Modul von Hilfsfunktionen, wenn sie zahlreich werden.

## <a name="type-inference-and-generics"></a>Typrückschluss und Generika

Typrückschluss kann Sie vor der Eingabe einer Menge Von Boilerplate sparen. Und die automatische Verallgemeinerung im F-Compiler kann Ihnen helfen, mehr generischen Code zu schreiben, ohne dass Sie sich mehr Mühe geben. Diese Eigenschaften sind jedoch nicht allgemein gut.

* Erwägen Sie die Beschriftung von Argumentnamen mit expliziten Typen in öffentlichen APIs, und verlassen Sie sich hierzu nicht auf Typrückschluss.

    Der Grund dafür ist, dass **Sie** die Kontrolle über die Form Ihrer API haben sollten, nicht über den Compiler. Obwohl der Compiler beim Ableiten von Typen für Sie eine gute Arbeit leisten kann, ist es möglich, die Form der API zu ändern, wenn die internen Typen geändert wurden. Das mag Das sein, was Sie wollen, aber es wird mit ziemlicher Sicherheit zu einer bahnbrechenden API-Änderung führen, mit der sich nachgeschaltete Verbraucher dann auseinandersetzen müssen. Wenn Sie stattdessen explizit die Form Ihrer öffentlichen API steuern, können Sie diese brechenden Änderungen steuern. In DDD-Begriffen kann dies als Anti-Korruptions-Schicht betrachtet werden.

* Erwägen Sie, Ihren allgemeinen Argumenten einen aussagekräftigen Namen zu geben.

    Wenn Sie keinen wirklich generischen Code schreiben, der nicht spezifisch für eine bestimmte Domäne ist, kann ein aussagekräftiger Name anderen Programmierern helfen, die Domäne zu verstehen, in der sie arbeiten. Ein Typparameter, der `'Document` im Kontext der Interaktion mit einer Dokumentdatenbank benannt ist, macht beispielsweise deutlicher, dass generische Dokumenttypen von der Funktion oder dem Member akzeptiert werden können, mit dem Bzw. der Sie arbeiten.

* Erwägen Sie, generische Typparameter mit PascalCase zu benennen.

    Dies ist die allgemeine Vorgehensweise in .NET, daher wird empfohlen, PascalCase anstelle von snake_case oder camelCase zu verwenden.

Schließlich ist die automatische Verallgemeinerung nicht immer ein Segen für Personen, die neu in der F-Datei oder einer großen Codebasis sind. Die Verwendung von generischen Komponenten ist ein kognitiver Overhead. Wenn automatisch verallgemeinerte Funktionen nicht mit unterschiedlichen Eingabetypen verwendet werden (geschweige denn, wenn sie als solche verwendet werden sollen), dann besteht kein wirklicher Vorteil dafür, dass sie zu diesem Zeitpunkt generisch sind. Berücksichtigen Sie immer, ob der Code, den Sie schreiben, tatsächlich davon profitiert, generisch zu sein.

## <a name="performance"></a>Leistung

### <a name="prefer-structs-for-small-data-types"></a>Bevorzugen von Strukturen für kleine Datentypen

Die Verwendung von Strukturen (auch Als Werttypen bezeichnet) kann häufig zu einer höheren Leistung für einige Codes führen, da die Zuweisung von Objekten in der Regel vermieden wird. Strukturen sind jedoch nicht immer eine "Go faster"-Schaltfläche: Wenn die Größe der Daten in einer Struktur 16 Byte überschreitet, kann das Kopieren der Daten oft zu mehr CPU-Zeit führen als mit einem Referenztyp.

Um zu bestimmen, ob Sie eine Struktur verwenden sollten, beachten Sie die folgenden Bedingungen:

- Wenn die Größe Ihrer Daten 16 Byte oder kleiner ist.
- Wenn sich wahrscheinlich viele dieser Datentypen in einem laufenden Programm im Arbeitsspeicher befinden.

Wenn die erste Bedingung zutrifft, sollten Sie in der Regel eine Struktur verwenden. Wenn beides zutrifft, sollten Sie fast immer eine Struktur verwenden. Es kann einige Fälle geben, in denen die vorherigen Bedingungen gelten, aber die Verwendung einer Struktur ist nicht besser oder schlechter als die Verwendung eines Referenztyps, aber sie sind wahrscheinlich selten. Es ist wichtig, immer zu messen, wenn Sie Änderungen wie diese vornehmen, aber nicht auf Annahme oder Intuition zu arbeiten.

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a>Bevorzugen Sie Struktur-Tuples beim Gruppieren kleiner Werttypen

Berücksichtigen Sie die folgenden beiden Funktionen:

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

Wenn Sie diese Funktionen mit einem statistischen Benchmarking-Tool wie [BenchmarkDotNet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass die Funktion, die `runWithStructTuple` Struktur-Tuuples verwendet, 40% schneller läuft und keinen Speicher zuweist.

Diese Ergebnisse sind jedoch nicht immer in Ihrem eigenen Code der Fall. Wenn Sie eine `inline`Funktion als markieren, erhält Code, der Referenz-Tupeln verwendet, möglicherweise einige zusätzliche Optimierungen, oder Code, der zugewiesen würde, könnte einfach nicht mehr optimiert werden. Sie sollten immer Ergebnisse messen, wenn es um Leistung geht, und niemals auf der Grundlage von Annahme oder Intuition arbeiten.

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a>Bevorzugen von Strukturdatensätzen, wenn der Datentyp klein ist

Die oben beschriebene Faustregel gilt auch für [die Datensatztypen](../language-reference/records.md)von F. Berücksichtigen Sie die folgenden Datentypen und Funktionen, die sie verarbeiten:

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

Dies ähnelt dem vorherigen Tupelcode, aber dieses Mal verwendet das Beispiel Datensätze und eine inline innere Funktion.

Wenn Sie diese Funktionen mit einem statistischen Benchmarking-Tool wie `processStructPoint` [BenchmarkDotNet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass fast 60% schneller läuft und nichts auf dem verwalteten Heap zuordnet.

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a>Bevorzugen Sie strukturierte diskriminierte Gewerkschaften, wenn der Datentyp klein ist

Die bisherigen Beobachtungen zur Leistung mit Strukturtupeln und Aufzeichnungen gilt auch für [die F-Diskriminierten Unions](../language-reference/discriminated-unions.md). Betrachten Sie folgenden Code:

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

Es ist üblich, einzelne diskriminierte Unions wie diese für die Domänenmodellierung zu definieren. Wenn Sie diese Funktionen mit einem statistischen Benchmarking-Tool wie [BenchmarkDotNet](https://benchmarkdotnet.org/)vergleichen, werden Sie feststellen, dass das `structReverseName` etwa 25% schneller läuft als `reverseName` bei kleinen Strings. Bei großen Zeichenfolgen führen beide ungefähr gleich aus. In diesem Fall ist es also immer vorzuziehen, eine Struktur zu verwenden. Wie bereits erwähnt, messen und arbeiten sie nicht auf Annahmen oder Intuition.

Obwohl das vorangegangene Beispiel zeigte, dass eine strukturdiskriminierte Union eine bessere Leistung erbracht hat, ist es üblich, größere diskriminierte Unions zu haben, wenn sie eine Domäne modellieren. Größere Datentypen wie dieser funktionieren möglicherweise nicht so gut, wenn es sich um Strukturen handelt, die von den Vorgängen abhängen, da mehr Kopieren beteiligt sein könnte.

### <a name="functional-programming-and-mutation"></a>Funktionelle Programmierung und Mutation

Die F-Werte sind standardmäßig unveränderlich, sodass Sie bestimmte Klassen von Fehlern vermeiden können (insbesondere solche, die Parallelität und Parallelität betreffen). In bestimmten Fällen kann jedoch eine Arbeitsspanne am besten mithilfe einer ortsansässigen Mutation des Zustands implementiert werden, um eine optimale (oder sogar angemessene) Effizienz der Ausführungszeit oder speicherzuweisungen zu erreichen. Dies ist in einer Opt-in-Basis `mutable` mit dem Schlüsselwort F' möglich.

Die `mutable` Verwendung von in F' kann sich im Widerspruch zur funktionellen Reinheit anfühlen. Das ist verständlich, aber funktionale Reinheit kann überall im Widerspruch zu Leistungszielen stehen. Ein Kompromiss besteht darin, Mutationen so zu kapseln, dass Anrufer sich nicht darum kümmern müssen, was passiert, wenn sie eine Funktion aufrufen. Auf diese Weise können Sie eine funktionale Schnittstelle über eine mutationsbasierte Implementierung für leistungskritischen Code schreiben.

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Wrap-veränderlichen Code in unveränderlichen Schnittstellen

Unter dem Ziel der referenziellen Transparenz ist es wichtig, Code zu schreiben, der den veränderlichen Unterbauch leistungskritischer Funktionen nicht verfügbar macht. Der folgende Code implementiert z. B. die `Array.contains` Funktion in der Kernbibliothek von F.:

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

Wenn Sie diese Funktion mehrmals aufrufen, wird das zugrunde liegende Array nicht geändert, und Es erfordert auch nicht, dass Sie einen veränderlichen Zustand beibehalten, um es zu verwenden. Es ist referenziell transparent, obwohl fast jede Codezeile darin Mutation verwendet.

#### <a name="consider-encapsulating-mutable-data-in-classes"></a>Erwägen Sie das Einkapseln veränderbarer Daten in Klassen

Im vorherigen Beispiel wurde eine einzelne Funktion verwendet, um Vorgänge mithilfe veränderbarer Daten zu kapseln. Dies reicht nicht immer für komplexere Datensätze aus. Berücksichtigen Sie die folgenden Funktionssätze:

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

Dieser Code ist performant, macht jedoch die mutationsbasierte Datenstruktur verfügbar, für deren Wartung Aufrufer verantwortlich sind. Dies kann innerhalb einer Klasse ohne zugrunde liegende Member eingeschlossen werden, die sich ändern können:

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

`Closure1Table`Kapselt die zugrunde liegende mutationsbasierte Datenstruktur, wodurch Aufrufer nicht gezwungen werden, die zugrunde liegende Datenstruktur beizubehalten. Klassen sind eine leistungsstarke Möglichkeit, Daten und Routinen zu kapseln, die mutationsbasiert sind, ohne die Details Aufrufern offenzulegen.

#### <a name="prefer-let-mutable-to-reference-cells"></a>Bevorzugen `let mutable` Sie Referenzzellen

Referenzzellen sind eine Möglichkeit, den Verweis auf einen Wert und nicht den Wert selbst darzustellen. Obwohl sie für leistungskritischen Code verwendet werden können, werden sie nicht empfohlen. Betrachten Sie das folgenden Beispiel:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

Die Verwendung einer Referenzzelle "verschmutzt" nun den gesamten nachfolgenden Code mit dem Dereferenzieren und erneuten Referenzieren der zugrunde liegenden Daten. Betrachten Sie `let mutable`stattdessen:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Abgesehen vom einzelnen Mutationspunkt in der Mitte des Lambda-Ausdrucks kann jeder andere Code, der `acc` berührt, `let`dies auf eine Weise tun, die sich nicht von der Verwendung eines normalen unveränderlichen Wertes unterscheidet. Dies wird es einfacher, im Laufe der Zeit zu ändern.

## <a name="object-programming"></a>Objektprogrammierung

Die vollständige Unterstützung von Objekten und objektorientierten Konzepten (OO) ist von F- unterstützt. Obwohl viele OO-Konzepte leistungsstark und nützlich sind, sind nicht alle ideal zu bedienen. Die folgenden Listen bieten Anleitungen zu Kategorien von OO-Funktionen auf hoher Ebene.

**Erwägen Sie die Verwendung dieser Funktionen in vielen Situationen:**

* Punktnotation`x.Length`( )
* Instanzmitglieder
* Implizite Konstruktoren
* Statische Member
* Indexernotation`arr.[x]`( )
* Benannte und optionale Argumente
* Schnittstellen und Schnittstellenimplementierungen

**Greifen Sie nicht zuerst nach diesen Funktionen, sondern wenden Sie sie mit Bedacht an, wenn sie bequem sind, um ein Problem zu lösen:**

* Methodenüberladung
* Gekapselte veränderbare Daten
* Operatoren für Typen
* Autoeigenschaften
* Umsetzung `IDisposable` und`IEnumerable`
* Typerweiterungen
* Events
* Strukturen
* Delegaten
* Enumerationen

**Vermeiden Sie diese Funktionen im Allgemeinen, es sei denn, Sie müssen sie verwenden:**

* Vererbungsbasierte Typhierarchien und Implementierungsvererbung
* Nullen und`Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Komposition vor Vererbung bevorzugen

[Die Komposition über die Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist ein langjähriges Idiom, an das sich guter F-Code halten kann. Das Grundprinzip besteht darin, dass Sie keine Basisklasse verfügbar machen und Aufrufer zwingen sollten, von dieser Basisklasse zu erben, um Funktionalität zu erhalten.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Verwenden von Objektausdrücken zum Implementieren von Schnittstellen, wenn Sie keine Klasse benötigen

[Mit Objektausdrücken](../language-reference/object-expressions.md) können Sie Schnittstellen spontan implementieren und die implementierte Schnittstelle an einen Wert binden, ohne dass dies innerhalb einer Klasse erforderlich ist. Dies ist praktisch, vor allem, wenn Sie _nur_ die Schnittstelle implementieren müssen und keine vollständige Klasse benötigen.

Hier ist z. B. der Code, der in [Ionide](http://ionide.io/) ausgeführt wird, um eine Codefixaktion bereitzustellen, wenn Sie ein Symbol hinzugefügt haben, für das Sie keine `open` Anweisung haben:

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

Da bei der Interaktion mit der Visual Studio-Code-API keine Klasse erforderlich ist, sind Objektausdrücke ein ideales Tool dafür. Sie sind auch für Komponententests nützlich, wenn Sie eine Schnittstelle mit Testroutinen ad hoc ausblenden möchten.

## <a name="consider-type-abbreviations-to-shorten-signatures"></a>Typabkürzungen in Betracht ziehen, um Signaturen zu kürzen

[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine bequeme Möglichkeit, eine Bezeichnung einem anderen Typ zuzuweisen, z. B. einer Funktionssignatur oder einem komplexeren Typ. Der folgende Alias weist z. B. eine Bezeichnung dem zu, was zum Definieren einer Berechnung mit [CNTK](https://docs.microsoft.com/cognitive-toolkit/), einer Deep Learning-Bibliothek, erforderlich ist:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Der `Computation` Name ist eine bequeme Möglichkeit, jede Funktion zu bezeichnen, die mit der Signatur übereinstimmt, die mit dem Aliasnamen übereinstimmt. Die Verwendung von Typabkürzungen wie dieser ist praktisch und ermöglicht prägnanteren Code.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Vermeiden Sie die Verwendung von Typabkürzungen zur Darstellung Ihrer Domäne

Obwohl Typabkürzungen für die Angabe eines Namens für Funktionssignaturen praktisch sind, können sie verwirrend sein, wenn andere Typen abgekürzt werden. Betrachten Sie diese Abkürzung:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Dies kann auf verschiedene Arten verwirrend sein:

* `BufferSize`ist keine Abstraktion; es ist nur ein anderer Name für eine ganze Zahl.
* Wenn `BufferSize` sie in einer öffentlichen API verfügbar gemacht wird, `int`kann sie leicht falsch interpretiert werden, um mehr als nur zu bedeuten. Im Allgemeinen weisen Domänentypen mehrere Attribute auf sich `int`ab und sind keine primitiven Typen wie . Diese Abkürzung verstößt gegen diese Annahme.
* Das Gehäuse `BufferSize` von (PascalCase) impliziert, dass dieser Typ mehr Daten enthält.
* Dieser Alias bietet keine größere Klarheit im Vergleich zur Bereitstellung eines benannten Arguments für eine Funktion.
* Die Abkürzung manifestiert sich nicht in kompilierter IL; Es ist nur eine ganze Zahl und dieser Alias ist ein Kompilierungszeitkonstrukt.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

Zusammenfassend lässt sich sagen, dass die Falle bei Typabkürzungen darin besteht, dass sie **keine** Abstraktionen über die Typen sind, die sie abkürzen. Im vorherigen Beispiel `BufferSize` ist `int` nur eine unter den Abdeckungen, ohne zusätzliche Daten, `int` noch irgendwelche Vorteile aus dem Typsystem abgesehen von dem, was bereits hat.

Ein alternativer Ansatz zur Verwendung von Typabkürzungen zur Darstellung einer Domäne besteht darin, diskriminierte Unions in einzelfalldurchfällen zu verwenden. Das vorherige Beispiel kann wie folgt modelliert werden:

```fsharp
type BufferSize = BufferSize of int
```

Wenn Sie Code schreiben, `BufferSize` der in Bezug auf und den zugrunde liegenden Wert arbeitet, müssen Sie einen erstellen, anstatt eine beliebige ganze Zahl zu übergeben:

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

Dies verringert die Wahrscheinlichkeit, dass eine `send` beliebige ganze Zahl versehentlich an `BufferSize` die Funktion übergeben wird, da der Aufrufer einen Typ erstellen muss, um einen Wert umzuschließen, bevor er die Funktion aufruft.
