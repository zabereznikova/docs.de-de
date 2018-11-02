---
title: F#-Programmierung Konventionen
description: Erfahren Sie, allgemeine Richtlinien und Idiome, beim Schreiben von F#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: 21119b6d69e00f359104bfb6eab7681bdbfb8d78
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "49087387"
---
# <a name="f-coding-conventions"></a>F#-Programmierung Konventionen

Die folgenden Konventionen aus Erfahrung, die Arbeit mit großen F# formuliert werden Codebasen. Die [fünf Prinzipien guten F#-Code](index.md#five-principles-of-good-f-code) bilden die Grundlage jeder Empfehlung. Sie beziehen sich auf die [Entwurfsrichtlinien für F#-Komponente](component-design-guidelines.md), jedoch gelten für alle F#-Code, nicht nur Komponenten wie Bibliotheken.

## <a name="organizing-code"></a>Organisieren von code

F# bietet zwei bevorzugte Möglichkeiten, Code zu organisieren: Modulen und Namespaces. Diese sind ähnlich, aber Sie müssen die folgenden Unterschiede:

* Namespaces werden als .NET Namespaces kompiliert. Module werden als statische Klassen kompiliert.
* Namespaces sind immer oberste Ebene. Module können der obersten Ebene und in anderen Modulen geschachtelt sein.
* Namespaces können mehrere Dateien umfassen. Standardmodule nicht möglich.
* Module können mit ergänzt werden `[<RequireQualifiedAccess>]` und `[<AutoOpen>]`.

Die folgenden Richtlinien können Sie diese verwenden, um Ihren Code zu organisieren.

### <a name="prefer-namespaces-at-the-top-level"></a>Bevorzugen Sie Namespaces auf der obersten Ebene

Für jeden öffentlich nutzbar Code werden Namespaces Zugriffscode Modulen auf der obersten Ebene. Da sie als .NET Namespaces kompiliert werden, sind sie in c# genutzt, kein Problem.

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

Mit einem Modul auf oberster Ebene möglicherweise nicht angezeigt, unterschiedliche, wenn Sie nur von F#-aufgerufen, aber für C#-Verbraucher Aufrufer Ergebnissen möglicherweise überrascht sein, dass Sie zu qualifizieren `MyClass` mit der `MyCode` Modul.

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a>Sorgfältig anwenden. `[<AutoOpen>]`

Die `[<AutoOpen>]` Konstrukt kann den Bereich der verfügbaren Aufrufern verunreinigen, und die Antwort auf einen Ursprung ist "magische". Dies ist in der Regel nicht gut. Eine Ausnahme von dieser Regel ist die F#-Kernbibliothek selbst (obwohl dies auch etwas umstrittenen ist).

Es ist jedoch aus Gründen der benutzerfreundlichkeit, wenn Sie über Hilfsfunktionen für eine öffentliche API verfügen, die Sie zum Organisieren von separat über der öffentliche API möchten.

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

Dadurch können Sie sauber separate Implementierungsdetails aus der öffentlichen API einer Funktion ohne vollständig eine Hilfsprogramm jedes Mal zu qualifizieren Sie ihn aufrufen.

Darüber hinaus verfügbar gemacht, Erweiterungsmethoden und Ausdrucks-Generatoren auf Namespaceebene sauber ausgedrückt werden mit `[<AutoOpen>]`.

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a>Verwendung `[<RequireQualifiedAccess>]` jedes Mal, wenn Namen in Konflikt stehen können, oder Sie der Meinung sind, helfen Ihnen Lesbarkeit

Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifizierten. Z. B. die `Microsoft.FSharp.Collections.List` Modul verfügt über dieses Attribut.

Dies ist nützlich, wenn Funktionen und Werte im Modul Namen haben, die einen Konflikt mit den Namen in anderen Modulen wahrscheinlich sind. Qualifizierten Zugriff erfordern, kann erheblich die langfristige wartbarkeit und Evolvability einer Bibliothek erhöhen.

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a>Sortierung `open` Anweisungen topologisch

In F# wird die Reihenfolge der Deklarationen von Bedeutung ist, einschließlich mit `open` Anweisungen. Dies ist anders als bei c#, wobei die Auswirkungen der `using` und `using static` ist unabhängig von der Reihenfolge dieser Anweisungen in einer Datei.

In F# können Elemente in einem Bereich geöffnet Shadowing für andere bereits vorhanden. Dies bedeutet, dass diese Neuordnung `open` Anweisungen können die Bedeutung des Codes ändern. Als Ergebnis jeden beliebigen aller sortieren `open` Anweisungen (z. B. alphanumerisch) wird im Allgemeinen nicht empfohlen, damit ein anderes Verhalten zu generieren, die Sie möglicherweise erwarten.

Stattdessen empfehlen wir, dass Sie diese sortieren [topologisch](https://en.wikipedia.org/wiki/Topological_sorting); sortieren, also Ihr `open` Anweisungen in der Reihenfolge, in der _Ebenen_ des Systems definiert sind. Alphanumerische in Schichten topologische Sortierung durchführen kann ebenfalls berücksichtigt werden.

Als Beispiel ist hier die topologische Sortierung für die F#-Compiler öffentliche API-Datei:

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

Beachten Sie, ein Zeilenumbruch topologische Ebenen, wobei jede Ebene danach alphanumerisch sortiert wird getrennt. Dieser organisiert Code ordnungsgemäß ohne shadowing versehentlich Werte.

## <a name="use-classes-to-contain-values-that-have-side-effects"></a>Verwenden Sie Klassen, um die Werte enthalten, die Nebeneffekte haben

Es gibt viele Male, wenn Nebeneffekte, wie Sie einen Kontext für eine Datenbank oder andere Remoteressource instanziieren initialisieren einen Wert haben kann. Es ist verlockend, beispielsweise in einem Modul zu initialisieren, und in nachfolgenden Funktionen verwenden:

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

Dies ist häufig keine gute Idee für verschiedene Gründe haben:

Zunächst wird die Anwendungskonfiguration in der Codebasis mit abgelegt `dep1` und `dep2`. Dies ist schwer in verwalten, dass die größeren Codebasen befindet.

Zweitens werden statisch initialisierte Daten darf keine Werte enthalten, die nicht threadsicher sind, wenn die Komponente selbst mehrere Threads verwendet wird. Dies wird eindeutig durch verletzt `dep3`.

Schließlich werden Initialisierung des Moduls in einem statischen Konstruktor für die gesamte Kompilationseinheit kompiliert. Wenn ein Fehler bei der wertinitialisierung von Let gebundenen in diesem Modul auftritt, manifestiert es als ein `TypeInitializationException` , die dann für die gesamte Lebensdauer der Anwendung zwischengespeichert wird. Dies kann nur schwer zu diagnostizieren sein. Es ist in der Regel eine innere Ausnahme, der Sie versuchen können, verständlich, aber wenn keine vorhanden ist, besteht keine Information darüber was die Ursache ist.

Stattdessen verwenden Sie eine einfache Klasse einfach, die Abhängigkeiten enthalten soll:

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

Dies ermöglicht Folgendes:

1. Überträgt alle abhängigen Zustand die API selbst.
2. Konfiguration kann nun außerhalb der API erfolgen.
3. Fehler bei der Initialisierung für abhängige Werte können nicht als manifest wahrscheinlich eine `TypeInitializationException`.
4. Die API ist jetzt einfacher zu testen.

## <a name="error-management"></a>Fehlerverwaltung

Fehlerverwaltung in großen Systemen ist ein komplexer und facettenreichen Unterfangen, und es sind keine Silver Aufzählungszeichen Ihrer Systeme zu gewährleisten, sind fehlertolerant und Verhalten sich auch. Die folgenden Richtlinien sollten bei der Navigation von dieser schwierig Speicherplatz hilfreich.

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a>Darstellen Sie Fehlerfälle und ungültigen Status in Ihrer Domäne systeminterne Typen

Mit [Unterscheidungs-Unions](../language-reference/discriminated-unions.md), F# gibt Ihnen die Möglichkeit, fehlerhafte Programmstatus in Ihrem Typsystem darstellen. Zum Beispiel:

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

In diesem Fall stehen drei bekannte Methoden, die bucht Geld von einem Bankkonto ausfallen können. Jeder Fehlerfall des Typs dargestellt wird und daher behandelt werden kann sicher in der gesamten Anwendung.

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

Im Allgemeinen, wenn Sie die verschiedenen Möglichkeiten modellieren können, dass etwas kann **fehlschlagen** in Ihrer Domäne, klicken Sie dann Fehlerbehandlungscode ist nicht mehr als behandelt etwas müssen Sie zusätzlich zum normalen Programmablauf behandeln. Es ist einfach ein Bestandteil der normalen Programmablauf und nicht als **außergewöhnliche**. Es gibt zwei Hauptvorteile sprechen für diese:

1. Es ist einfacher zu verwalten wie Ihre Domäne im Laufe der Zeit ändert.
2. Fehler werden einfacher Komponententests unterziehen.

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a>Verwenden Sie Ausnahmen aus, wenn der Fehler nicht mit Typen dargestellt werden kann

Nicht alle Fehler können in einer Problemdomäne dargestellt werden. Diese Art von Fehlern werden *außergewöhnliche* Natur, daher die Möglichkeit, auslösen und Abfangen von Ausnahmen in F#.

Zunächst wird empfohlen, Sie lesen die [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md). Diese gelten auch für F#.

Im Rahmen der Auslösen von Ausnahmen in F# verfügbar mit die wichtigen Konstrukten sollten in der folgenden Reihenfolge ihrer Priorität berücksichtigt werden:

| Funktion | Syntax | Zweck |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | Löst eine `System.ArgumentNullException` mit dem angegebenen Argumentnamen. |
| `invalidArg` | `invalidArg "argumentName" "message"` | Löst eine `System.ArgumentException` mit einem angegebenen Argumentnamen und Nachricht. |
| `invalidOp` | `invalidOp "message"` | Löst eine `System.InvalidOperationException` mit der angegebenen Meldung. |
|`raise`| `raise (ExceptionType("message"))` | Allgemeinen Mechanismus zum Auslösen von Ausnahmen. |
| `failwith` | `failwith "message"` | Löst eine `System.Exception` mit der angegebenen Meldung. |
| `failwithf` | `failwithf "format string" argForFormatString` | Löst eine `System.Exception` mit der Meldung hängt von der Formatzeichenfolge und ihre Eingaben. |

Verwendung `nullArg`, `invalidArg` und `invalidOp` als Mechanismus zum Auslösen `ArgumentNullException`, `ArgumentException` und `InvalidOperationException` bei Bedarf.

Die `failwith` und `failwithf` Funktionen sollten im Allgemeinen vermieden werden, da sie auf die Basis lösen `Exception` eingeben, nicht für eine bestimmte Ausnahme. Gemäß der [Ausnahme Entwurfsrichtlinien](../../standard/design-guidelines/exceptions.md), spezifischere Ausnahmen auslösen, wenn möglich werden sollen.

### <a name="using-exception-handling-syntax"></a>Mithilfe der Syntax der Behandlung von Ausnahmen

F# unterstützt Muster für die Ausnahme über die `try...with` Syntax:

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

Abgleichen von Funktionen bei einer Ausnahme mit dem Mustervergleich ausführen werden etwas schwieriger, wenn Sie den Code für eine übersichtlichere möchten. Eine solche Möglichkeit hierzu ist die Verwendung [mit aktiven Mustern](../language-reference/active-patterns.md) als Mittel zur Funktion für ein Fehler bei einer Ausnahme selbst um. Beispielsweise können Sie eine API nutzen, die, wenn es eine Ausnahme auslöst, wertvollen Informationen in die Ausnahmemetadaten einschließt. Das Aufheben dieses Zustands eines nützlicher Wert im Text die abgefangene Ausnahme in das aktive Muster und zurückgeben, dass der Wert in einigen Situationen hilfreich sein kann.

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a>Verwenden Sie keine monadische Fehlerbehandlung um Ausnahmen zu ersetzen.

Ausnahmen werden als etwas Taboo bei der funktionalen Programmierung betrachtet. In der Tat verletzen Ausnahmen Reinheit, daher ist es sicher ist, die sie nicht-ziemlich funktionale berücksichtigen. Dies ignoriert jedoch die Realität, in dem Code ausgeführt werden muss, und dieser Laufzeit, Fehler auftreten können. Schreiben Sie Code in der Regel auf der Annahme, dass die meisten Informationen weder reine noch insgesamt, sodass unliebsame überraschungen Ausbleiben minimiert werden.

Es ist wichtig, die folgenden Stärken/Kernaspekte von Ausnahmen in Bezug auf die Relevanz und die Eignung in der .NET Common Language Runtime und sprachübergreifende-Ökosystem als Ganzes zu berücksichtigen:

1. Sie enthalten ausführliche Diagnoseinformationen, die sehr hilfreich ist, wenn ein Problem zu debuggen.
2. Sie sind durch die Common Language Runtime und anderen .NET-Sprachen gut verstanden.
3. Sie können zu verringern erheblich im Vergleich mit Code, der eine Methode zum verlässt *vermeiden* Ausnahmen durch die Implementierung einer Teilmenge der ihre Semantik auf Ad-hoc-Basis.

Dieser dritte Punkt ist wichtig. Fehler beim Verwenden von Ausnahmen kann beim Umgang mit Strukturen wie folgt bei nicht trivialen komplexe Operationen ausführen führen:

```fsharp
Result<Result<MyType, string>, string list>
```

Dies kann problemlos zu instabilem Code z. B. einen Musterabgleich für "stringly typisierte" Fehler führen:

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

Darüber hinaus kann es verlockend sein, eine Ausnahme aus, in dem Wunsch nach einer "einfachen"-Funktion zu behalten, die ein "nützlicher" zurückgibt:

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

Leider `tryReadAllText` können zahlreiche basierte auf einer Vielzahl von Aufgaben, die in einem Dateisystem auftreten können Ausnahmen auslösen, und dieser Code verwirft sofort jegliche Informationen darüber, was tatsächlich in Ihrer Umgebung nicht in Ordnung sein kann. Wenn Sie diesen Code mit einem Ergebnistyp ersetzen, sind Sie an der Analyse des "stringly typisierte" Fehler:

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

Und das Ausnahmeobjekt selbst in die `Error` Konstruktor nur erzwingt, dass Sie den Typ der Ausnahme an der Aufrufsite und nicht in der Funktion ordnungsgemäß behandeln. Dadurch effektiv erstellt geprüften Ausnahmen, die bekanntermaßen für den Umgang mit als einer API-Aufrufer unfun sind.

Eine gute Alternative zu den obigen Beispielen ist zum Abfangen von *bestimmte* Ausnahmen und Return keinen sinnvollen Wert im Kontext dieser Ausnahme. Wenn Sie ändern die `tryReadAllText` funktioniert wie folgt `None` hat mehr Bedeutung:

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

Statt als ein Catch-All funktioniert, wird diese Funktion jetzt ordnungsgemäß den Fall handhaben, eine Datei wurde nicht gefunden und eine Rückgabe, Bedeutung zuweisen. Dieser Rückgabewert kann zu diesem Fehlerfall bei der nicht verwerfen alle Kontextinformationen oder erzwingen Aufrufe an einen Fall verarbeiten, die möglicherweise nicht relevant ist an diesem Punkt im Code zuordnen.

Typen wie `Result<'Success, 'Error>` eignen sich für grundlegende Vorgänge, in dem sie geschachtelt sind nicht und optionale F#-Typen sind ideal für darstellen, wenn etwas entweder zurückgeben könnte *etwas* oder *nichts*. Sie sind kein Ersatz für Ausnahmen, allerdings und sollte nicht versuchen, Ersetzen von Ausnahmen verwendet werden. Stattdessen sollten sie mit Bedacht auf Aspekte der Adresse der Ausnahme und die Richtlinie für die Verwaltung in die entsprechenden Methoden angewendet werden.

## <a name="partial-application-and-point-free-programming"></a>Teilweise Anwendung "und" Punkt-free-Programmierung

F# unterstützt partielle Anwendung, und daher verschiedene Arten der Programmierung in einem Punkt-free-Stil. Dies kann für die Wiederverwendung von Code in einem Modul oder die Implementierung von etwas von Vorteil sein, aber es wird in der Regel nicht öffentlich verfügbar machen. Im Allgemeinen kann Point-free-Programmierung keine Tugend an und für sich selbst, und eine erhebliche Hürde für cognitive für Personen, die nicht in der Formatvorlage befinden werden.

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a>Verwenden Sie teilweise Anwendung und in öffentlichen APIs currying nicht

Mit kleinen Ausnahme kann die Verwendung von teilweise Anwendung von öffentlichen APIs für Benutzer verwirrend sein. In der Regel `let`-gebundenen Werte in F#-Code sind **Werte**, nicht **Funktionswerte**. Miteinander kombinieren, Werte und Werte von Funktionen kann dazu führen, speichern eine kleine Anzahl von Codezeilen im Austausch gegen einiges an cognitive Mehraufwand, insbesondere dann, wenn Sie z. B. mit Operatoren kombiniert `>>` um Funktionen zu erstellen.

### <a name="consider-the-tooling-implications-for-point-free-programming"></a>Betrachten Sie die Auswirkungen auf die Tools für Punkt-free-Programmierung

Funktionen mit Currying ihre Argumente nicht beschriftet. Dies hat Auswirkungen auf die Tools. Beachten Sie die folgenden zwei Funktionen:

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

Beide sind gültige Funktionen, aber `funcWithApplication` ist eine Funktion, mit Currying. Wenn Sie über ihre Typen in einem Editor bewegen, wird Folgendes angezeigt:

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

An der Aufrufsite QuickInfos in Tools wie Visual Studio nicht erhalten Sie aussagekräftige Informationen, welche die `string` und `int` Eingabetypen tatsächlich darstellen.

Punkt-free-Code wie auftreten `funcWithApplication` , die öffentlich nutzbar ist, es wird empfohlen, eine vollständige η-Erweiterung, damit Tools wählen Sie aussagekräftige Namen für die Argumente an bis kann.

Darüber hinaus kann Punkt fehlerfreien Code zu debuggen, wenn nicht sogar unmöglich schwierig sein. Tools zum Debuggen communitywerte nutzen, um Namen gebunden (z. B. `let` Bindungen), damit Sie während der Ausführung Zwischenwerte Ausführung überprüfen können. Wenn im Code keine Werte, um zu überprüfen, aber es gibt noch nichts zu debuggen. In Zukunft weiterentwickeln kann debugging-Tools, um diese Werte, die anhand der zuvor ausgeführten Pfade zu synthetisieren, aber es ist nicht ratsam, Ihre Suchergebnisse auf allerhöchstem *potenzielle* Debugfunktionen.

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a>Betrachten Sie teilweise Anwendung als Verfahren, um interne Codebausteine zu reduzieren.

Im Gegensatz zum vorherigen Punkt handelt ist teilweise Anwendung ein hervorragendes Tool zum Reduzieren der Codebaustein in einer Anwendung oder die umfassendere Interna einer API. Es kann für Komponententests, die die Implementierung komplizierter-APIs, in denen Codebausteine zu handhaben ist häufig hilfreich sein. Beispielsweise der folgende Code zeigt, wie Sie erreichen können, welche die meisten verfügbaren Mockframeworks erhalten Sie ohne eine externe Abhängigkeit auf solch einem Framework, und einen zugehörigen erfahren, dass Individual-API.

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

Komponententests `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` ist einfach:

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

Teilweise Anwendung `doTransaction` Objekt mit einem mocking Kontext können Sie die Funktion in allen Komponententests aufrufen, ohne jedes Mal einen simulierte Kontext zu erstellen:

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

Dieses Verfahren sollten nicht universell angewendet werden, Ihre gesamte Codebasis, aber es ist eine gute Möglichkeit zur Reduzierung von Codebausteine für komplizierte-Interna und Komponententests, die die Interna.

## <a name="access-control"></a>Zugriffssteuerung

F# weist mehrere Optionen für [Zugriffssteuerung](../language-reference/access-control.md), geerbt vom, was in der .NET Runtime verfügbar ist. Diese sind nicht nur für Typen verwendet werden – Sie können sie für Funktionen zu.

* Lieber nicht`public` Typen und Member, bis Sie sie öffentlich nutzbar sein benötigen. Dies minimiert ebenfalls, welche Consumer-Paar.
* Sich bemühen, behalten Sie alle Hilfsfunktionen `private`.
* Betrachten Sie die Verwendung von `[<AutoOpen>]` für ein Modul private Hilfsfunktionen, wenn sie zahlreiche sind.

## <a name="type-inference-and-generics"></a>Typrückschluss und Generika

Typrückschluss können Sie über die Eingabe viele häufig speichern. Und automatische Verallgemeinerung in F#-Compiler können Sie generischen Code mit fast kein zusätzlicher Aufwand ihrerseits zu schreiben. Diese Funktionen sind jedoch nicht universell gut.

* Betrachten Sie die Argumentnamen mit expliziter Typen in öffentlichen APIs, die Bezeichnung, und verlassen Sie sich nicht auf den Typrückschluss für diese.

    Der Grund dafür ist, dass **Sie** muss in der Form Ihrer API, die nicht der Compiler-Steuerelement. Obwohl der Compiler sehr gut an das Ableiten von Typen für Sie tun kann, ist es möglich, dass die Form Ihrer API-Änderung, wenn die standardbibliotheksinternen Elementen, denen in diesem Fall verwendet die Typen geändert wurden. Dies ist möglicherweise erwünscht, aber in eine grundlegende Änderung der API, die downstreamconsumer klicken Sie dann für den Umgang mit fast absoluter Sicherheit führt. Stattdessen, wenn Sie explizit die Form der öffentlichen API steuern, dann können Sie diese Änderungen steuern. In DDD-Terminologie kann dies als eine Anti-Corruption-Ebene aufgefasst werden.

* Beachten Sie, sodass einen aussagekräftigen Namen zu Ihrer generischen Argumente.

    Es sei denn, Sie tatsächlich generischen Code, der nicht spezifisch für eine bestimmte Domäne ist schreiben, können ein aussagekräftigen Namen andere Programmierer verstehen der Domäne, die sie gerade arbeiten. Beispielsweise einen Typparameter, die mit dem Namen `'Document` in den Kontext für die Interaktion mit einem Dokument Datenbank ist es klarer, dass generische Dokumenttypen können, von der Funktion oder ein Element akzeptiert werden mit dem Sie arbeiten.

* Erwägen Sie die Benennung von generischen Typparametern mit PascalCase.

    Dies ist die allgemeine Vorgehensweise Dinge in .NET ist die Verwendung von PascalCase anstelle von Snake_case oder CamelCase empfohlen.

Schließlich ist automatische Verallgemeinerung nicht immer ein Segen für Personen gedacht, die F#- oder einer großen Codebasis. Mithilfe von Komponenten, die generisch sind ist cognitive Aufwand. Wenn automatisch darüber hinaus die generalisierte Funktionen werden nicht verwendet, mit verschiedenen Eingabetypen (Let nur, wenn sie z. B. verwendet werden sollen), dann keinen echten Vorteil, sie generisch zu diesem Zeitpunkt. Berücksichtigen Sie immer, wenn der Code, den Sie schreiben tatsächlich profitieren von der generischen.

## <a name="performance"></a>Leistung

F#-Werte sind unveränderlich, standardmäßig die Ihnen ermöglicht, bestimmte Klassen von Fehlern (insbesondere die im Zusammenhang mit Parallelität und Konkurrenz) zu vermeiden. Allerdings kann in bestimmten Fällen um eine optimale (oder sogar sinnvoll) Effizienz Ausführungszeit oder speicherbelegungen, eine Spanne der Arbeit am besten implementiert werden mithilfe des direktes Veränderung des Zustands. Dies ist möglich, in einer Basis Opt-in mit F# mit der `mutable` Schlüsselwort.

Allerdings verwenden der `mutable` in F# echtzeiteinschränkungen funktionale Reinheit fühlen. Dies ist in Ordnung, wenn Sie anpassen, dass die Erwartungen Reinheit zu [referenzieller Transparenz](https://en.wikipedia.org/wiki/Referential_transparency). Referenzieller Transparenz - nicht Reinheit – ist das Ziel beim Schreiben von F#-Funktionen. Dadurch können Sie eine funktionsfähige-Schnittstelle über eine Mutation-basierte Implementierung für die Leistung kritischen Code zu schreiben.

### <a name="wrap-mutable-code-in-immutable-interfaces"></a>Umschließen Sie änderbare Code in der unveränderlichen Schnittstellen

Mit referenzieller Transparenz als Ziel ist es wichtig, Code schreiben, der nicht die änderbare Tiefen des leistungskritischen Funktionen verfügbar macht. Das folgende Codebeispiel implementiert die `Array.contains` Funktion in der F#-Kernbibliothek:

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

Das Aufrufen dieser Funktion mehrmals ändert sich nicht auf das zugrunde liegende Array, noch ist es erforderlich, veränderlichen Zustand in Ihre Verwendung zu verwalten. Es ist Referenziell transparent, obwohl nahezu jede Codezeile darin Mutation verwendet.

### <a name="consider-encapsulating-mutable-data-in-classes"></a>Beachten Sie, änderbare Daten in Klassen kapseln

Im vorherige Beispiel verwendet eine einzelne Funktion, um Vorgänge mit änderbare Daten zu kapseln. Dies ist nicht immer ausreichend für komplexere Sätze von Daten. Beachten Sie die folgenden Sätze von Funktionen aus:

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

Macht die Mutation basierende Datenstruktur, dass Aufrufer für die Verwaltung zuständig sind, aber dieser Code ist leistungsfähig. Dies kann innerhalb einer Klasse ohne zugrunde liegende Member umbrochen werden, die geändert werden können:

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

`Closure1Table` Kapselt die zugrunde liegende Mutation basierende Data-Struktur, wodurch nicht erzwungen, Aufrufe an die zugrunde liegende Datenstruktur zu verwalten. Klassen sind eine leistungsstarke Möglichkeit zum Kapseln von Daten und Routinen, die Mutation-basiert sind, ohne die Details für Aufrufer verfügbar zu machen.

### <a name="prefer-let-mutable-to-reference-cells"></a>Bevorzugen `let mutable` zu Referenzzellen

Referenzzellen sind eine Möglichkeit, den Verweis auf einen Wert anstatt den Wert selbst darstellen. Obwohl sie für leistungskritische Code verwendet werden können, werden sie in der Regel nicht empfohlen. Betrachten Sie das folgende Beispiel:

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

Die Verwendung von einer Referenzzelle jetzt Täuschung"" alle nachfolgenden Code zu von dereferenziert und erneut auf die zugrunde liegenden Daten verweisen. Erwägen Sie stattdessen `let mutable`:

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

Abgesehen von der einzige Punkt der Veränderung in der Mitte der Lambda-Ausdruck, alle anderen Code, der berührt `acc` dazu in einer Weise, die nicht für die Verwendung einer normalen unterscheidet `let`-unveränderlichen Wert gebunden. Dies wird im Laufe der Zeit ändern erleichtern.

## <a name="object-programming"></a>Objektprogrammierung

F# bietet vollständige Unterstützung für Objekte und Konzepte für objektorientierte (OO). Obwohl viele OO-Konzepte leistungsfähig und nützlich sind, sind nicht alle von ihnen erzielen Sie, wenn verwenden. Die folgenden Listen bieten Anleitungen für die Kategorien von OO-Funktionen auf hoher Ebene.

**Sollten Sie diese Funktionen in vielen Situationen verwenden:**

* Punktierte Schreibweise (`x.Length`)
* Instanzmember
* Implizite Konstruktoren
* Statische Member
* Indexers (`arr.[x]`)
* Benannte und optionale Argumente
* Schnittstellen und schnittstellenimplementierungen

**Greifen Sie nicht zuerst für diese Funktionen zu, jedoch mit Umsicht anzuwenden Sie, wenn sie zur Lösung eines Problems sind:**

* Methodenüberladung
* Gekapselten änderbaren Daten
* Operatoren für Typen
* Auto-Eigenschaften
* Implementieren von `IDisposable` und `IEnumerable`
* Erweiterungen des Typs
* Ereignisse
* Strukturen
* Delegaten
* Enumerationen

**Vermeiden Sie diese Funktionen in der Regel, es sei denn, Sie sie verwenden müssen:**

* Vererbung basierende Typenhierarchien und von implementierungsvererbung
* NULL-Werte und `Unchecked.defaultof<_>`

### <a name="prefer-composition-over-inheritance"></a>Vererbung Komposition vorziehen

[Aufbau im Laufe der Vererbung](https://en.wikipedia.org/wiki/Composition_over_inheritance) ist eine langfristige Vorgehensweise, die guter F#-Code entsprechen kann. Das grundlegende Prinzip ist, dass Sie nicht verfügbar eine Basisklasse machen und Erzwingen von Aufrufern das erben von dieser Basisklasse um Funktionen zu erhalten.

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a>Verwenden Sie Object-Ausdrücke, um Schnittstellen zu implementieren, wenn Sie eine Klasse nicht

[Objektausdrücke](../language-reference/object-expressions.md) die implementierte Schnittstelle können Sie zum Implementieren von Schnittstellen dynamisch an einen Wert ohne dafür innerhalb einer Klasse gebunden. Dies ist praktisch, insbesondere dann, wenn Sie _nur_ müssen die Schnittstelle implementieren und müssen nicht für eine vollständige Klasse.

Beispielsweise sieht der Code, der ausgeführt wird, in [Ionide](http://ionide.io/) eine Korrektur Codeaktion bereitstellen, wenn Sie ein Symbol hinzugefügt haben, die Sie besitzen eine `open` -Anweisung für:

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

Da bei der Interaktion mit der Visual Studio Code-API, keine Notwendigkeit für eine Klasse besteht, sind Object-Ausdrücke ein ideales Tool dafür. Sie sind auch nützlich für Komponententests bereit, wenn Sie eine Schnittstelle mit Test-Routinen in einer ad-hoc-Weise stub werden sollen.

## <a name="type-abbreviations"></a>Typabkürzungen

[Typabkürzungen](../language-reference/type-abbreviations.md) sind eine einfache Möglichkeit zum Zuweisen einer Bezeichnung in einen anderen Typ, z. B. einer Funktionssignatur oder einen komplexen Typ. Der folgende Alias weist z. B. eine Bezeichnung, was erforderlich ist, definieren Sie eine Berechnung mit [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), ein Deep learning-Bibliothek:

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

Die `Computation` Name ist eine bequeme Möglichkeit, eine Funktion anzugeben, die der Signatur entspricht, es ist Aliasing. Typabkürzungen wie folgt verwenden, ist praktisch und kompaktere Code ermöglicht.

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a>Vermeiden Sie die Verwendung von Typabkürzungen zur Darstellung von Ihrer Domäne

Obwohl Typabkürzungen praktisch für das Festlegen einer Bezeichnung für Funktionssignaturen sind, können sie verwirrend sein, wenn abkürzen, von anderen Typen. Betrachten Sie diese Abkürzung aus:

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

Dies kann auf verschiedene Weise verwirrend sein:

* `BufferSize` ist keine Abstraktion. Es ist nur ein anderer Name für eine ganze Zahl.
* Wenn `BufferSize` verfügbar gemacht wird in eine öffentliche API nutzen, es kann leicht falsch interpretiert werden, um mehr als nur bedeutet, dass `int`. Im Allgemeinen Domänentypen mehrere Attribute werden und nicht primitive Typen wie `int`. Diese Abkürzung verstößt gegen diese Annahme.
* Die Schreibweise von `BufferSize` (PascalCase) bedeutet, dass es sich bei diesem Typ mehr Daten enthält.
* Dieser Alias bietet keine Verwaltungsaufgabe, die im Vergleich mit der Bereitstellung eines benannten Arguments an eine Funktion.
* Die Abkürzung wird nicht in die kompilierte IL-manifest; Es ist nur eine ganze Zahl ein, und dieser Alias ist ein Konstrukt während der Kompilierung.

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

Zusammenfassung der Fehlers mit Typabkürzungen ist, dass sie **nicht** Abstraktionen, die Typen, die sie mit der sind abkürzen von. Im vorherigen Beispiel `BufferSize` ist einfach ein `int` mit keine zusätzlichen Daten, und alle Vorteile aus das Typensystem neben dem, was im Hintergrund `int` bereits verfügt.
