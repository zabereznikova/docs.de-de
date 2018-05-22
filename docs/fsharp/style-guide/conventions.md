---
title: Codekonventionen [F#]
description: Erfahren Sie allgemeine Richtlinien und Idiome beim Schreiben von F#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: adb2189540496046ccf6e392bd45807860e13520
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="f-coding-conventions"></a>Codekonventionen [F#]

Die folgenden Konventionen werden aus Erfahrung mit großen f# formuliert Codebasen. Die [fünf Prinzipien der gute f#-Code](index.md#five-principles-of-good-f-code) sind die Grundlage für jede Empfehlung. Sie beziehen sich auf die [f# Komponente Entwurfsrichtlinien](component-design-guidelines.md), jedoch gelten für alle f#-Code, nicht nur Komponenten wie Bibliotheken.

## <a name="organizing-code"></a>Organisieren von code

F# bietet zwei Hauptmethoden zum Organisieren von Code: Module und Namespaces. Diese sind ähnlich, aber Sie müssen die folgenden Unterschiede:

* Namespaces werden als .NET Namespaces kompiliert. Module werden als statische Klassen kompiliert.
* Namespaces sind immer der obersten Ebene. Module können auf der obersten Ebene und in anderen Modulen geschachtelt werden.
* Namespaces können mehrere Dateien umfassen. Module können nicht.
* Module können mit ergänzt werden `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`.

Die folgenden Richtlinien können Sie diese verwenden, um Ihren Code zu organisieren.

### <a name="prefer-namespaces-at-the-top-level"></a>Bevorzugen Sie Namespaces auf der obersten Ebene

Für jeden öffentlich nutzbar Code sind Namespaces bietet, Module, die auf der obersten Ebene. Da sie als .NET Namespaces kompiliert werden, sind sie kann von c# mit kein Problem.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Mithilfe der obersten Ebene treten möglicherweise anders aus, wenn Sie nur vom F#-aufgerufen, aber für C#-Consumern, können Aufrufer Katastrophenfall qualifizieren überrascht werden `MyClass` mit der `MyCode` Modul.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Sorgfältig anwenden `[<AutoOpen>]`

Die `[<AutoOpen>]` Konstrukt kann dadurch den Rahmen, was für Aufrufer verfügbar ist, und die Antwort auf etwas Ursprung ist "magische". Dies ist im Allgemeinen nicht empfehlenswert. Eine Ausnahme von dieser Regel wird die F#-Kernbibliothek selbst (obwohl dies auch etwas kontroverse ist).

Es ist jedoch zur Vereinfachung, wenn Sie Hilfsfunktionen für eine öffentliche API verfügen, die Sie separat von diesem öffentliche API organisieren möchten.

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

Dadurch können Sie von der öffentlichen API einer Funktion ordnungsgemäß separate Implementierungsdetails ohne vollständig eine Hilfsprogramm jedes Mal zu qualifizieren Sie ihn aufrufen.

Darüber hinaus Verfügbarmachen von Erweiterungsmethoden und Ausdrucks-Generatoren auf Namespaceebene ausgedrückt werden kann problemlos mit `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Verwendung `[<RequireQualifiedAccess>]` sichern können einen Konflikt mit Namen, und es unterstützt die Lesbarkeit der Meinung

Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifiziert. Z. B. die `Microsoft.FSharp.Collections.List` -Modul ist dieses Attribut.

Dies ist hilfreich, wenn Funktionen und Werte im Modul Namen haben, die wahrscheinlich einen Konflikt mit Namen in anderen Modulen ausgeführt werden. Einen qualifizierten Zugriff erfordern, kann erheblich die langfristige Verwaltbarkeit und die Evolvability einer Bibliothek erhöhen.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Sortieren `open` Anweisungen topologisch

In F# erläutert werden, die Reihenfolge der Deklarationen ist von Belang, einschließlich mit `open` Anweisungen. Dies ist anders als bei c#, wobei die Auswirkung der `using` und `using static` ist unabhängig von der Reihenfolge der diese Anweisungen in einer Datei.

In F# erläutert werden da Elemente, die in den Gültigkeitsbereich einer geöffnet zu überschatten, können vorhandene andere bereits. Dies bedeutet, dass dieser neuanordnung `open` alter-Anweisungen können die Bedeutung des Codes. Folglich sortieren alphanumerisch (oder pseudorandomly) wird im Allgemeinen nicht empfohlen, damit Sie sich im Verhalten etwas generieren, die Sie möglicherweise erwarten.

Stattdessen empfehlen wir, dass sie zu sortieren [topologisch](https://en.wikipedia.org/wiki/Topological_sorting); d. h. sortieren Ihre `open` Anweisungen in der Reihenfolge, in der _Ebenen_ Ihres Systems definiert sind. Auf diese Weise alphanumerische Sortierung in verschiedene topologische Ebenen kann ebenfalls berücksichtigt werden.

Als Beispiel sieht die topologische Sortierung für die F#-Compiler öffentliche API-Datei:

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

Beachten Sie, dass ein Zeilenumbruch topologische Ebenen mit jeder Ebene, die zu sortierenden alphanumerisch anschließend trennt. Diese werden ordnungsgemäß Code ohne versehentlich shadowing Werte organisiert.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Verwenden Sie Klassen, um die Werte enthalten, die Nebeneffekte haben

Es gibt viele Male Wenn Nebeneffekte, wie einen Kontext auf eine Datenbank oder andere Remoteressource instanziieren initialisieren einen Wert aufweisen kann. Es ist verlockend, u. a. in einem Modul zu initialisieren und in nachfolgenden Funktionen verwenden:

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"
    let dep3 = Random().Next() // Random is not thread-safe

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

Dies ist häufig nicht sinnvoll, Gründen:

Zunächst erleichtert die-API selbst auf gemeinsam verwendete Zustände angewiesen. Z. B. mehrere aufrufenden Threads möglicherweise den Zugriff auf die `dep3` Wert (und es ist nicht threadsicher). Zweitens, legt die Anwendungskonfiguration ab, in die Codebase selbst. Dies ist schwer zu verwalten, größere CodeBase.

Schließlich wird Initialisierung des Moduls in einem statischen Konstruktor für die gesamte Kompilationseinheit kompiliert. Wenn ein Fehler bei der Initialisierung der Let-Grenzwert in diesem Modul auftritt, Manifeste als eine `TypeInitializationException` , klicken Sie dann für die gesamte Lebensdauer der Anwendung zwischengespeichert wird. Dies kann nur schwer zu diagnostizieren sein. In der Regel eine innere Ausnahme, der Sie versuchen, zu dem Grund besteht, aber wenn keine vorhanden ist, besteht keine mitteilen, was die Ursache ist.

Verwenden Sie eine einfache Klasse stattdessen nur zum Speichern von Abhängigkeiten:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Dies ermöglicht Folgendes:

1. Betätigen alle abhängigen Status außerhalb der API selbst.
2. Konfiguration kann nun außerhalb der API erfolgen.
3. Fehler bei der Initialisierung für abhängige Werte können nicht als manifest wahrscheinlich eine `TypeInitializationException`.
4. Die API ist jetzt einfacher zu testen.

## <a name="error-management"></a>Fehlerverwaltung

Fehlerverwaltung in großen Systemen ist ein komplexer und vor-Unterfangen, und es sind keine Silber Nummerierung in Ihr System sichergestellt werden fehlertolerante und Verhalten sich auch. Die folgenden Richtlinien bieten Anleitungen zum Navigieren in dieser schwierig Speicherplatz.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Darstellen Sie Sonderfälle und ungültigen Status in Ihrer Domäne systeminterne Typen

Mit [Unterscheidungs-Unions](../language-reference/discriminated-unions.md), f# bietet Ihnen die Möglichkeit, fehlerhafte Programmstatus in Ihrem Typsystem darstellen. Zum Beispiel:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In diesem Fall stehen drei bekannte Methoden, die das Abbuchen von Geld von einem Bankkonto ausgeführt werden kann. Jeder Fehlerfall des Typs dargestellt wird und daher behandelt werden kann sicher in der gesamten Anwendung.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

Im Allgemeinen, wenn Sie die verschiedenen Möglichkeiten modellieren können, dass etwas kann **fehlschlagen** in Ihrer Domäne, klicken Sie dann Fehlerbehandlungscode ist nicht mehr als behandelt etwas müssen Sie zusätzlich zum normalen Programmablauf behandeln. Es ist einfach ein Bestandteil der normalen Programmablauf und nicht als **herausragende**. Es gibt zwei Hauptvorteile dieser:

1. Es ist einfacher zu verwalten, während Ihre Domäne im Zeitverlauf ändert.
2. Für diesen Fehler sind einfacher zu Komponententest.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Verwenden Sie Ausnahmen aus, wenn der Fehler mit Typen dargestellt werden kann

Nicht alle Fehler können in einer Problemdomäne dargestellt werden. Diese Art von Fehlern werden *herausragende* Natur, daher die Möglichkeit, auslösen und Abfangen von Ausnahmen in F# erläutert werden.

Zunächst wird empfohlen, dass Sie Lesen der [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md). Diese gelten auch für f#.

In f# verfügbar im Rahmen der Auslösen von Ausnahmen mit die wichtigen Konstrukten sollten in der folgenden Reihenfolge der Priorität berücksichtigt werden:

| Funktion | Syntax | Zweck |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Löst ein `System.ArgumentNullException` mit dem angegebenen Argumentnamen. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Löst ein `System.ArgumentException` mit einem angegebenen Argumentnamen und die Nachricht. |
| `invalidOp` | `invalidOp "message"` | Löst ein `System.InvalidOperationException` mit der angegebenen Meldung. |
|`raise`| `raise (ExceptionType("message"))` | Allgemeine Mechanismus zum Auslösen von Ausnahmen. |
| `failwith` | `failwith "message"` | Löst ein `System.Exception` mit der angegebenen Meldung. |
| `failwithf` | `failwithf "format string" argForFormatString` | Löst ein `System.Exception` mit einer Meldung durch die Formatzeichenfolge und ihre Eingaben bestimmt. |

Verwendung `nullArg`, `invalidArg` und `invalidOp` als Mechanismus zum lösen `ArgumentNullException`, `ArgumentException` und `InvalidOperationException` gegebenenfalls.

Die `failwith` und `failwithf` Funktionen sollten im Allgemeinen vermieden werden, da sie die Basis auslösen `Exception` eingeben, nicht für eine bestimmte Ausnahme. Gemäß der [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md), finden Sie spezifischere Ausnahmen auslösen, sofern möglich werden sollen.

### <a name="using-exception-handling-syntax"></a>Mithilfe der Ausnahmebehandlung-syntax

F# unterstützt Ausnahme Muster über die `try...with` Syntax:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Abstimmen von Funktionen zur Ausführung eine Ausnahme mit dem Mustervergleich ausführen werden etwas komplizierter, wenn Sie den Code bereinigen aufbewahren möchten. Eine solche Möglichkeit in diesem Fall ist die Verwendung [mit aktiven Mustern](../language-reference/active-patterns.md) als Mittel zum Funktion für den Fehlerfall eines mit einer Ausnahme selbst umgebenden. Beispielsweise können Sie eine API nutzen, die, wenn er eine Ausnahme auslöst, wertvollen Informationen in den Ausnahmemetadaten umschließt. Entpacken einen nützlichsten Wert im Text der Ausnahme aufgezeichnete in das aktive Muster und zurückgeben, dass der Wert in einigen Situationen hilfreich sein kann.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Verwenden Sie keine monadische Fehlerbehandlung um Ausnahmen zu ersetzen.

Ausnahmen werden als etwas Taboo bei der funktionalen Programmierung betrachtet. In der Tat verletzen Ausnahmen Reinheit, sodass sie nicht ganz funktionale berücksichtigt werden kann. Allerdings wird dadurch die Realität, in dem Code ausgeführt werden muss, und dieser Fehler können auftreten, Laufzeit ignoriert. Schreiben Sie Code in der Regel auf der Annahme, dass die meisten Dinge reinen weder total minimieren, unerfreuliche überraschungen sind.

Es ist wichtig, die folgenden Core Stärken/Aspekte von Ausnahmen im Hinblick auf ihre Relevanz und Eignung in der .NET Common Language Runtime und das sprachübergreifende Ökosystem als Ganzes zu berücksichtigen:

1. Sie enthalten detaillierte Diagnoseinformationen, die sehr hilfreich ist, wenn ein Problem debuggen.
2. Durch die Common Language Runtime und anderen gut verständlich sind.
3. Reduzierung der erhebliche Textbaustein im Vergleich zu Code, der eine Methode zum verlässt *vermeiden* Ausnahmen durch die Implementierung einer Teilmenge der ihre Semantik auf Ad-hoc-Basis.

Diese dritte Punkt ist wichtig. Für nicht trivialen komplexe Operationen ausführen kann wegen eines Fehlers beim Verwenden von Ausnahmen beim Umgang mit Datenstrukturen, z. B. Dies führen:

```fsharp
Result<Result<MyType, string>, string list>
```

Dies kann problemlos zu instabilen Code wie einen Mustervergleich für "stringly typisierte" Fehler führen:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Darüber hinaus kann es sein verlockend, jede Ausnahme in der Wunsch nach einer Funktion "einfache" behalten, die ein "nützlicher" zurückgibt:

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Leider `tryReadAllText` kann zahlreiche basierte auf einer Vielzahl von Vorgängen, die in einem Dateisystem durchgeführt kann Ausnahmen auslösen, und dieser Code verwirft sofort jegliche Informationen, was tatsächlich in Ihrer Umgebung falschen passiert werden kann. Wenn Sie diesen Code mit einem Ergebnistyp ersetzen, können Sie zurück zur Analyse des "stringly typisierte" Fehler:

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

Und platziert das Ausnahmeobjekt selbst in die `Error` Konstruktor nur erzwingt, dass Sie den Ausnahmetyp an der Aufrufsite anstatt in die Funktion ordnungsgemäß behandeln. Dadurch effektiv erstellt überprüfte Ausnahmen, die für den Umgang mit als Aufrufer einer API offenkundig unfun sind.

Eine gute Alternative zur in den Beispielen oben wird zum Abfangen von *bestimmte* Ausnahmen und der Rückgabewert keinen sinnvollen Wert im Kontext der diese Ausnahme. Wenn Sie ändern die `tryReadAllText` -Funktion wie folgt `None` hat mehr Bedeutung:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Anstelle von funktioniert wie eine sammelfehlermeldung, ausführt diese Funktion jetzt ordnungsgemäß die Groß-/Kleinschreibung, wenn eine Datei wurde nicht gefunden, und weisen Sie diesem Bedeutung eine Rückgabe. Dieser Rückgabewert kann diese auftretender Fehler beim Zuordnen nicht verwerfen alle Kontextinformationen oder Erzwingen der Aufrufer für den Umgang mit einem Fall, die möglicherweise nicht relevant ist an diesem Punkt im Code.

Typen wie `Result<'Success, 'Error>` eignen sich für Standardvorgänge, in dem sie geschachtelt sind nicht, und optionale f#-Typen sind ideal für die Darstellung etwas entweder möglich *etwas* oder *nichts*. Sie sind kein Ersatz für Ausnahmen, jedoch und sollte nicht in einem Versuch zum Ersetzen von Ausnahmen verwendet werden. Stattdessen sollten sie Umsicht Adresse bestimmte Aspekte der Ausnahme und die Richtlinie für die Verwaltung targeted angewendet werden.

## <a name="partial-application-and-point-free-programming"></a>Teilweise Anwendung und frei von Punkt-Programmierung

F# unterstützt teilweise Anwendung, und somit auf verschiedene Arten der Programmierung in einem Format mit Punkt freizugeben. Dies kann für die Wiederverwendung von Code in einem Modul oder die Implementierung von etwas von Vorteil sein, allerdings handelt es sich im Allgemeinen nicht etwas, um die öffentlich verfügbar zu machen. Im Allgemeinen Punkt frei Programmierung ist ein Vorteil, dass es in und von sich selbst und kann ein großes cognitive Hindernis für Personen, die im entsprechenden Stil nicht mehr über sind hinzufügen.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Verwenden Sie keine teilweise Anwendung und in öffentlichen APIs currying

Mit wenig Ausnahme kann die Verwendung der partiellen Anwendung von öffentlichen APIs für den Consumer verwirrend sein. In der Regel `let`-gebundenen Werte in f#-Code sind **Werte**, nicht **Funktion Werte**. Vermischen von Werten und Funktionswerten kann dazu führen, speichern eine kleine Anzahl von Codezeilen für relativ viel cognitive Mehraufwand, insbesondere dann, wenn Sie z. B. mit Operatoren kombiniert `>>` um Funktionen zu erstellen.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Betrachten Sie die Auswirkungen auf die Tools für die Programmierung Punkt frei

Funktionen mit Currying ihre Argumente nicht beschriftet. Dies hat Auswirkungen auf die Tools. Betrachten Sie die folgenden zwei Funktionen:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Beide sind gültige Funktionen jedoch `funcWithApplication` ist eine Funktion, mit Currying. Wenn Sie ihre Typen in einem Editor zeigen, wird Folgendes angezeigt:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

An der Aufrufsite QuickInfos in Tools wie Visual Studio nicht erhalten Sie aussagekräftige Informationen, was die `string` und `int` Eingabetypen tatsächlich darstellen.

Treten Punkt frei Code wie `funcWithApplication` öffentlich nutzbar ist, es wird empfohlen, einen vollständigen η-Erweiterung vornehmen, sodass Tools wählen Sie aussagekräftige Namen für die Argumente an bis kann.

Darüber hinaus kann Debugcode Punkt frei, wenn nicht sogar unmöglich schwierig sein. Tools zum Debuggen basieren auf Werte, die an den Namen gebunden (z. B. `let` Bindungen), um Sie in der Mitte Zwischenwerte durch die Ausführung überprüfen. Wenn der Code keine Werte überprüfen aufweist, wird nichts zu debuggen. In der Zukunft Debugtools weiterentwickelt kann, um diese Werte basierend auf der zuvor ausgeführten Pfade zu synthetisieren, aber es ist nicht ratsam, Ihre Suchergebnisse auf hedge *potenzielle* Funktionalität Debuggen.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Betrachten Sie teilweise Anwendung als eine Technik zum Reduzieren der internen Textbaustein

Im Gegensatz zu vorherigen Punkt ist teilweise Anwendung ein traumhaftes Tool zur Reduzierung der Textbaustein innerhalb einer Anwendung oder die tieferen Besonderheiten der API. Es kann für die Implementierung der etwas komplizierteren APIs, wobei Textbaustein häufig einen Bereich mit den für den Umgang mit ist für die Komponententests hilfreich sein. Z. B. der folgende Code zeigt, wie Sie erreichen können, welche die meisten Mockframeworks Ihnen ohne externe Abhängigkeit solches Framework und einer verknüpften erfahren, dass die API Werk.

Betrachten Sie beispielsweise die folgende Lösung Topografie aus:

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

`ImplementationLogic.fsproj` Code kann z. B. verfügbar machen:

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

UnitTests `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` ist einfach:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Anwenden von teilweise `doTransaction` Objekt mit einem mocking Kontext können Sie die Funktion in allen Komponententests aufrufen, ohne einen mocked Kontext jedes Mal erstellen:

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

Dieses Verfahren sollten auf die gesamte Codebase nicht universell angewendet, aber es ist eine gute Möglichkeit, Textbausteine für komplizierte Besonderheiten und diese Mechanismen für die Komponententests zu reduzieren.

## <a name="access-control"></a>Zugriffssteuerung

F#-verfügt über mehrere Optionen für [Zugriffssteuerung](../language-reference/access-control.md), geerbt vom was in der .NET Common Language Runtime verfügbar ist. Diese sind nicht nur für Typen verwendet werden – verwenden sie für Funktionen zu.

* Bevorzugen nicht-`public` Typen und Member, bis Sie öffentlich werden benötigt. Dadurch wird minimiert auch, welche Consumer-Paar an
* Bemühen, behalten Sie alle Hilfsfunktionen `private`.
* Betrachten Sie die Verwendung von `[<AutoOpen>]` auf eine private Hilfsfunktionen, wenn zahlreiche versetzten-Modul.

## <a name="type-inference-and-generics"></a>Typrückschluss und Generika

Typrückschluss sparen Sie viel Textbaustein eingeben. Und automatische Verallgemeinerung in f#-Compiler können Sie allgemeineren Code mit fast keine zusätzlichen Aufwand ihrerseits zu schreiben. Diese Funktionen sind jedoch nicht universell gut.

* Betrachten Sie beschriften Argumentnamen mit expliziten Typen in öffentlichen APIs und verlassen Sie sich nicht auf den Typrückschluss für diesen.

    Der Grund dafür ist, dass **Sie** Kontrolle über die Form von Ihrer API, die nicht vom Compiler werden sollte. Obwohl der Compiler sehr gut an Ableiten von Typen für Sie ausführen kann, ist es möglich, dass die Form der API ändern, wenn die Mechanismen, die auf basiert Typen geändert wurden. Dies kann sein, was Sie möchten, aber Befehlsbeispiel führt zu einer Änderung der wichtige-API, für die downstreamconsumer dann für den Umgang mit. Stattdessen, wenn Sie die Form des Ihre öffentliche API explizit steuern, dann können Sie diese Änderungen steuern. DDD ausgedrückt kann dies als eine Schicht Anti-Beschädigung betrachtet werden.

* Nennen Sie einen aussagekräftigen Namen zu Ihrer generischen Argumenten.

    Es sei denn, Sie tatsächlich generischen Code, der nicht spezifisch für eine bestimmte Domäne ist schreiben, können ein aussagekräftigen Namen andere Programmierer verstehen die Domäne, in dem sie arbeiten. Beispielsweise einen Typparameter mit dem Namen `'Document` im Kontext der Interaktion mit einem Dokument Datenbank erleichtert klarer, dass generische Dokumenttypen können, von der Funktion oder einen Member akzeptiert werden mit dem Sie arbeiten.

* Erwägen Sie die Benennung der generische Typparameter mit "PascalCase".

    Dies ist die allgemeine Möglichkeit, die Aktionen in .NET, daher wird empfohlen, dass die Verwendung von "PascalCase" anstatt Snake_case oder camelCase ändern möchten.

Schließlich ist automatische Verallgemeinerung nicht immer ein Segen für Personen, die F#- oder einer großen Codebasis nicht vertraut sind. Bei der Verwendung von Komponenten, die generisch sind ist cognitive Aufwand. Wenn automatisch darüber hinaus die generalisierte Funktionen werden nicht mit verschiedenen Eingabetypen (Let allein, wenn sie z. B. verwendet werden soll) verwendet, wird keine echte Vorteil diese generischen zu diesem Zeitpunkt wird. In Betracht gezogen Sie, wenn der Code, den Sie schreiben tatsächlich nicht generischen profitieren.

## <a name="performance"></a>Leistung

F#-Werte sind unveränderlich ist, wird standardmäßig die Ihnen ermöglicht, bestimmte Klassen von Fehlern (insbesondere die im Zusammenhang mit Parallelität und Parallelität) zu vermeiden. Allerdings kann in bestimmten Fällen um eine optimale (oder sogar sinnvoll) Effizienz Ausführungszeit oder speicherbelegungen zu erzielen eine Spanne der Arbeit am besten implementiert werden mithilfe von direkten Mutation des Status. Dies ist möglich, in ein Opt-in-Basis mit f# mit dem `mutable` Schlüsselwort.

Allerdings verwenden der `mutable` in f# entwurfsseitig funktionale Reinheit fühlen. Dies ist in Ordnung, wenn Sie Erwartungen aus Reinheit zum Anpassen [referenzielle Transparenz](https://en.wikipedia.org/wiki/Referential_transparency). Referenzielle Transparenz - nicht Reinheit - ist Endziel es beim Schreiben von f#-Funktionen. Dadurch können Sie eine funktionsfähige Schnittstelle über einer Mutation-basierten Implementierung für Leistung wichtigen Code zu schreiben.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Umschließen Sie änderbare Code unveränderlichen Schnittstellen

Mit referenziellen Transparenz als Ziel ist es wichtig, Code zu schreiben, die nicht die änderbare Tiefen leistungskritischen Funktionen zur Verfügung stellt. Z. B. der folgende code implementiert die `Array.contains` -Funktion in der f#-Kernbibliothek:

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

Das Aufrufen dieser Funktion mehrmals ändert sich nicht auf das zugrunde liegende Array, noch ist es erforderlich, alle änderbaren Zustand in Ihre Verwendung beibehalten. Es ist Referenziell transparent, obwohl fast jede Codezeile darin Mutation verwendet.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>Betrachten Sie änderbare Daten in Klassen kapseln

Im vorherige Beispiel verwendet eine einzelne Funktion, um Vorgänge mithilfe änderbare Daten kapseln. Dies ist nicht immer ausreichend für komplexe Datenmengen. Betrachten Sie die folgenden Sätze von Funktionen aus:

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

Dieser Code ist leistungsfähiger, aber macht die Mutation basierende Datenstruktur, dass Aufrufer für die Verwaltung zuständig sind. Dies kann innerhalb einer Klasse ohne zugrunde liegende Member umbrochen werden, die geändert werden kann:

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

`Closure1Table` Kapselt die zugrunde liegende Mutation kennwortbasierten Datenschutzdienst-Struktur, nicht erzwingen Aufrufer auf die zugrunde liegende Datenstruktur zu verwalten. Klassen sind eine leistungsfähige Möglichkeit zum Kapseln von Daten und Routinen, die Mutation-basiert sind, ohne die Details für Aufrufer verfügbar zu machen.

### <a name="prefer-let-mutable-to-reference-cells"></a>Bevorzugen `let mutable` zu Referenzzellen

Referenzzellen sind eine Möglichkeit, den Verweis auf einen Wert anstatt den Wert selbst darstellen. Obwohl sie für leistungskritische Code verwendet werden können, werden sie im Allgemeinen nicht empfohlen. Betrachten Sie das folgende Beispiel:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

Die Verwendung von einer Referenzzelle Täuschung"" alle nachfolgenden Code zu dereferenzieren und verweisen auf die zugrunde liegenden Daten erneut. Erwägen Sie stattdessen `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Abgesehen von den einzelnen Fehlerpunkt Mutation in der Mitte der Lambda-Ausdruck, alle anderen Code, der berührt `acc` können dies in einer Weise, die nicht für die Verwendung einer normalen unterscheidet tun `let`-unveränderlichen Wert gebunden. Dies wird im Laufe der Zeit ändern vereinfachen.

## <a name="object-programming"></a>Objekt-Programmierung

F# bietet vollständige Unterstützung für Objekte und Konzepte für objektorientierte (OO). Obwohl viele OO Konzepte leistungsstarke und nützlich sind, sind nicht alle von ihnen sich perfekt für verwenden. Die folgenden Listen bieten Anleitungen zu den Kategorien von OO Funktionen auf hoher Ebene.

**Sollten Sie diese Funktionen in vielen Situationen verwenden:**

* Punktnotation (`x.Length`)
* Instanzmember
* Implizite Konstruktoren
* Statische Member
* Indexer-Notation (`arr.[x]`)
* Benannte und optionale Argumente
* Schnittstellen und schnittstellenimplementierungen

**Erreichen Sie nicht zuerst für diese Funktionen, aber Umsicht anzuwenden Sie, wenn sie zur Lösung eines Problems sind:**

* Methodenüberladung
* Gekapselten änderbaren Daten
* Operatoren auf Typen
* Auto-Eigenschaften
* Implementieren von `IDisposable` und `IEnumerable`
* Typerweiterungen
* Ereignisse
* Strukturen
* Delegaten
* Enumerationen

**Vermeiden Sie diese Funktionen in der Regel, sofern Sie sie verwenden müssen:**

* Vererbung basierende Typenhierarchien und implementierungsvererbung
* NULL-Werte und `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Ziehen Sie Komposition Vererbung

[Komposition über Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist ein langjähriges-Idiom, die gute f#-Code entsprechen kann. Fundamentales Prinzip ist, sollten nicht verfügbar eine Basisklasse machen und zum Erzwingen von Aufrufern das erben von dieser Basisklasse, Funktionalität zu erhalten.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Verwenden Sie Objektausdrücke, um Schnittstellen zu implementieren, wenn Sie eine Klasse benötigen

[Objektausdrücke](../language-reference/object-expressions.md) ermöglichen es Ihnen, im Handumdrehen Schnittstellen implementieren die implementierte Schnittstelle auf einen Wert binden, ohne dass dazu innerhalb einer Klasse. Dies ist zweckmäßig, insbesondere dann, wenn Sie _nur_ müssen die Schnittstelle implementieren und keine Notwendigkeit für eine vollständige-Klasse.

Hier ist z. B. der Code, der ausgeführt wird, in [Ionide](http://ionide.io/) eine Update-Codeaktion bereitstellen, wenn Sie ein Symbol hinzugefügt haben, die Sie besitzen eine `open` -Anweisung:

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

Da bei der Interaktion mit den Visual Studio Code-API, keine Notwendigkeit für eine Klasse besteht, sind Objektausdrücke ein ideales Tool dafür. Sie sind auch nützlich für Komponententests bereit, wenn Sie, eine Schnittstelle mit Test-Routinen in einer ad-hoc-Weise stub möchten.

## <a name="type-abbreviations"></a>Typabkürzungen

[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine einfache Möglichkeit, einen anderen Typ, z. B. einer Funktionssignatur oder ein komplexer Typ eine Bezeichnung zuweisen. Beispielsweise weist der folgende Alias eine Bezeichnung, was erforderlich ist, um eine Berechnung mit definieren [CNTK](https://www.microsoft.com/cognitive-toolkit/), eine umfassende learning-Bibliothek:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Die `Computation` Name ist eine einfache Möglichkeit, eine beliebige Funktion anzumerken, die der Signatur entspricht, es handelt sich um Aliasing. Typabkürzungen wie folgt mit ist sehr nützlich und kompaktere Code ermöglicht.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Vermeiden Sie die Verwendung von Typabkürzungen zur Darstellung Ihrer Domänenstatus

Obwohl Typabkürzungen praktisch für die Vergabe eines Namens für die Funktionssignaturen sind, können sie verwirrend sein, wenn abkürzen von anderen Typen von. Betrachten Sie diese Abkürzung aus:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Dies kann auf verschiedene Weise verwirrend sein:

* `BufferSize` ist nicht abstrakt. Es ist einfach einen anderen Namen für eine ganze Zahl.
* Wenn `BufferSize` verfügbar gemacht wird in eine öffentliche API es kann problemlos falsch interpretiert werden, um mehr als nur bedeuten, dass `int`. Im Allgemeinen Domänentypen haben Sie mehrere Attribute werden und sind nicht primitive Typen wie `int`. Diese Abkürzung verstößt gegen diese Annahme.
* Die Groß-/Kleinschreibung von `BufferSize` ("PascalCase") gibt an, dass dieser Typ mehr Daten enthält.
* Dieser Alias bietet höhere Klarheit im Vergleich mit dem Ziel eines benannten Arguments an eine Funktion nicht.
* Die Abkürzung wird nicht in die kompilierte IL manifest; Es ist nur eine ganze Zahl, und dieser Alias ist ein Konstrukt Zeitpunkt der Kompilierung.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

Im Grunde ist der Dateneingabe mit Typabkürzungen sind **nicht** Abstraktionen über die Typen, die sie sind abkürzen von. Im vorherigen Beispiel `BufferSize` lediglich ein `int` mit keine zusätzlichen Daten noch keine Vorteile aus dem Typsystem neben dem, was im Hintergrund `int` bereits hat.
