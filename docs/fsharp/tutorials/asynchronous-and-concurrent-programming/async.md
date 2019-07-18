---
title: Asynchrone Programmierung
description: Erfahren Sie, wie F# asynchrone Programmierung erfolgt über ein Programmiermodell auf Sprachebene, das einfach zu verwenden und natürlich für die Sprache ist.
ms.date: 06/20/2016
ms.openlocfilehash: 8cd7d7bcecabe8ea2c33a4787fe9ebbadd67fe67
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753595"
---
# <a name="async-programming-in-f"></a>Asynchrone Programmierung in F\#

> [!NOTE]
> In diesem Artikel wurden einige Ungenauigkeiten ermittelt.  Es wird erneut geschrieben wird.  Finden Sie unter [Problem #666](https://github.com/dotnet/docs/issues/666) Informationen zu den Änderungen.

Asynchrone Programmierung in F# erfolgt mit der ein Programmiermodell auf Sprachebene, das einfach zu verwenden und natürlich für die Sprache werden soll.

Den Kern der asynchronen Programmierung F# ist `Async<'T>`, eine Darstellung der Aufgaben, die ausgelöst werden kann, um im Hintergrund auszuführen, in denen `'T` ist entweder der zurückgegebene Typs über die spezielle `return` Schlüsselwort oder `unit` Wenn der asynchrone Workflow hat keine Ergebnisse zurückgegeben.

Das Schlüsselkonzept zu verstehen ist, wird der Typ des Ausdrucks, der einen asynchronen `Async<'T>`, dies ist lediglich ein _Spezifikation_ Arbeit in einem asynchronen Kontext ausgeführt werden. Es wird nicht ausgeführt, bis Sie explizit mit einem ab Funktionen beginnen (z. B. `Async.RunSynchronously`). Obwohl dies eine andere Weise angehen, Arbeit ist, im Endeffekt es recht einfach, in der Praxis.

Angenommen Sie, dass Sie den HTML-Code aus dotnetfoundation.org herunterladen, ohne den Hauptthread zu blockieren. Sie erreichen ihn wie folgt:

```fsharp
open System
open System.Net

let fetchHtmlAsync url =
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

Und das ist schon alles! Abgesehen von der Verwendung von `async`, `let!`, und `return`, dies ist lediglich um normale F# Code.

Es gibt einige syntaktische Konstrukte, die beachtet sollten werden:

* `let!` Bindet das Ergebnis einer Async-Ausdrucks (die auf einem anderen Kontext ausgeführt wird).
* `use!` funktioniert wie `let!`, aber die gebundenen Ressourcen frei, wenn sie den Gültigkeitsbereich verlässt.
* `do!` wird einen Async-Workflow "await" der nichts zurückgegeben wird nicht.
* `return` einfach gibt ein Ergebnis aus einem Async-Ausdruck zurück.
* `return!` Führt einen weiteren asynchronen Workflow aus, und gibt den Rückgabewert als Ergebnis zurück.

Darüber hinaus normalen `let`, `use`, und `do` Schlüsselwörter können zusammen mit die asynchronen Versionen verwendet werden, genauso wie in einer normalen-Funktion.

## <a name="how-to-start-async-code-in-f"></a>Starten Sie die Async-Code in F\#

Wie bereits erwähnt, ist Async-Code eine Spezifikation der Arbeit in einem anderen Kontext ausgeführt werden, die explizit gestartet werden muss. Hier sind zwei Hauptmethoden, um dies zu erreichen:

1. `Async.RunSynchronously` Startet einen asynchronen Workflow in einem anderen Thread und wartet auf das Ergebnis.

    ```fsharp
    open System
    open System.Net

    let fetchHtmlAsync url =
        async {
            let uri = Uri(url)
            use webClient = new WebClient()
            let! html = webClient.AsyncDownloadString(uri)
            return html
        }

    // Execution will pause until fetchHtmlAsync finishes
    let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

    // you actually have the result from fetchHtmlAsync now!
    printfn "%s" html
    ```

2. `Async.Start` Startet einen asynchronen Workflow in einem anderen Thread, und wird **nicht** wartet auf das Ergebnis.

    ```fsharp
    open System
    open System.Net

    let uploadDataAsync url data =
        async {
            let uri = Uri(url)
            use webClient = new WebClient()
            webClient.UploadStringAsync(uri, data)
        }

    let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

    // Execution will continue after calling this!
    Async.Start(workflow)

    printfn "%s" "uploadDataAsync is running in the background..."
    ```

Es gibt andere Möglichkeiten zum Starten einer Async-Workflows, die für spezifische Szenarien verfügbar. Sie werden beschrieben [in der Referenz zur asynchronen](https://msdn.microsoft.com/library/ee370232.aspx).

### <a name="a-note-on-threads"></a>Hinweis zur Threads

Der Ausdruck "in einem anderen Thread" erwähnt, aber es ist wichtig zu wissen, dass **Dies bedeutet nicht, asynchrone Workflows sind eine Fassade zum multithreading**. Der Workflow springt"tatsächlich" zwischen Threads, die sie für eine kleine Menge Zeit, nützliche Aufgaben der softwarecodeverwaltung. Wenn ein Async-Workflow effektiv "(z. B. beim Warten auf eines Netzwerkaufruf etwas zurückgegeben) wartet", wird jedem Thread aus, die sie zum Zeitpunkt der softwarecodeverwaltung wurde bis zum Wechseln Sie sinnvolle Arbeit für andere Aufgaben freigegeben. Dies ermöglicht die asynchrone Workflows im System nutzen können, die, das Sie so effektiv wie möglich ausgeführt, und stellt sie vor allem für e/a-Szenarien mit hohem Volumen stark.

## <a name="how-to-add-parallelism-to-async-code"></a>Gewusst wie: Hinzufügen von Parallelität in asynchronen Code

Manchmal kann müssen zum Ausführen von mehrere asynchrone Aufgaben parallel sammeln die Ergebnisse und Interpretieren sie in irgendeiner Form. `Async.Parallel` können Sie diesen Schritt ausführen, ohne dass der Task Parallel Library verwenden, die umzuwandelnde müssen dabei `Task<'T>` und `Async<'T>` Typen.

Das folgende Beispiel verwendet `Async.Parallel` zum Herunterladen des HTML-Codes aus vier beliebte Websites parallel warten Sie für diese Aufgaben abgeschlossen, und drucken Sie dann die HTML-Code der heruntergeladen wurde.

```fsharp
open System
open System.Net

let urlList =
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url =
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a>Wichtige Informationen und Hinweise

* Fügen Sie "Async" am Ende der Funktionen, die Sie nutzen werde

 Obwohl dies nur eine Benennungskonvention ist, z.B. API-Erkennbarkeit erleichtern. Insbesondere dann, wenn Sie synchrone und asynchrone Versionen der gleichen Routine verfügbar sind, ist es eine gute Idee, explizit angeben, die über den Namen asynchron ist.

* Hören Sie sich an den Compiler.

F#der Compiler ist sehr strenge, machen es nahezu unmöglich, etwas beunruhigend wie "Async" Code synchron ausgeführt. Wenn Sie über eine Warnung stammen, ist, die ein Zeichen dafür, dass der Code ausgeführt wird nicht wie Meinung, dass es klappt. Wenn Sie den Compiler glücklich machen können, wird Ihr Code in den meisten Fällen ausgeführt werden, wie erwartet.

## <a name="for-the-cvb-programmer-looking-into-f"></a>Für die C#/VB-Programmierer, die Suche in F\#

In diesem Abschnitt wird davon ausgegangen, Sie sind mit dem Async-Modell in C#/VB. Wenn Sie nicht, sind [für die asynchrone Programmierung in C# ](../../../csharp/async.md) ist ein Ausgangspunkt.

Es ist ein grundlegender Unterschied zwischen der C#/VB-Async-Modell und die F# asynchrone Modell.

Eine Funktion, die Gibt beim Aufruf einer `Task` oder `Task<'T>`, diesen Auftrag bereits mit Ausführung begonnen hat. Das zurückgegebene Handle stellt einen asynchronen bereits ausgeführten-Auftrag dar. Im Gegensatz dazu beim Aufruf einer asynchronen Funktion F#, `Async<'a>` zurückgegebenen stellt einen Auftrag die **generiert** an einem bestimmten Punkt. Verständnis dieses Modell ist leistungsstark, da dadurch für asynchronen Aufträge in F# miteinander verkettet werden einfacher, bedingt ausgeführt und mit feiner differenziert des Steuerelements gestartet werden.

Es gibt einige andere ähnlichkeiten und Unterschiede zu beachten.

### <a name="similarities"></a>Ähnlichkeiten

* `let!`, `use!`, und `do!` sind analog zu den `await` beim Aufrufen von eines Async-Auftrags innerhalb einer `async{ }` Block.

  Die drei Schlüsselwörter können nur verwendet werden, innerhalb einer `async { }` Block, ähnlich wie `await` kann nur aufgerufen werden, in eine `async` Methode. Kurz gesagt, `let!` ist für, wenn Sie möchten, erfassen und verwenden daher `use!` ist der gleiche aber etwas, deren Ressourcen bereinigt zu erhalten, müssen nachdem es verwendet wird, und `do!` ist, wenn Sie für einen asynchronen Workflow mit keinen Wert zurückgibt, um den Vorgang abzuschließen warten möchten Bevor Sie fortfahren.

* F#unterstützt Datenparallelität auf ähnliche Weise.

  Obwohl es sehr unterschiedlich arbeitet `Async.Parallel` entspricht `Task.WhenAll` für das Szenario möchten die Ergebnisse einer Reihe von asynchronen Aufträge aus, wenn alle abgeschlossen.

### <a name="differences"></a>Unterschiede

* Geschachtelte `let!` ist nicht zulässig, im Gegensatz zu geschachtelten `await`

  Im Gegensatz zu `await`, der unendlich geschachtelt werden kann `let!` kann nicht aus, und das Ergebnis gebunden werden, bevor Sie ihn in eine andere verwenden müssen `let!`, `do!`, oder `use!`.

* Unterstützung für den Abbruch ist in einfacher F# als in C#/VB.

  Unterstützen von Abbruch einer Aufgabe in der Mitte über die Ausführung in C#/VB erfordert die Prüfung der `IsCancellationRequested` -Eigenschaft oder Aufrufe `ThrowIfCancellationRequested()` auf eine `CancellationToken` -Objekt, das an die Async-Methode übergeben wird.

Im Gegensatz dazu F# asynchrone Workflows sind also ganz natürlich abgebrochen werden können. Abbruch ist ein einfacher dreistufigen Prozess.

1. Erstellen Sie einen neuen `CancellationTokenSource`.
2. Übergeben Sie ihn in eine Funktion ab.
3. Rufen Sie `Cancel` im Token.

Beispiel:

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }

let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

Und das ist schon alles!

## <a name="further-resources"></a>Weitere Ressourcen:

* [Asynchrone Workflows auf MSDN](https://msdn.microsoft.com/library/dd233250.aspx)
* [Asynchroner Sequenzen fürF#](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
* [F#Data-HTTP-Hilfsprogrammen](https://fsharp.github.io/FSharp.Data/library/Http.html)
