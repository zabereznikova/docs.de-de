---
title: Asynchrone Programmierung in F# erläutert werden.
description: Erfahren Sie, wie asynchrone Programmierung f# über ein Programmiermodell auf Sprachebene durchgeführt wird, die einfach zu verwenden und natürliche Sprache ist.
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: a3047b98637cb4b142f374a2a2b5e7270e850fd6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="async-programming-in-f"></a>Asynchrone Programmierung in F# erläutert werden. #

> [!NOTE]
> In diesem Artikel wurden einige Ungenauigkeiten ermittelt wurden.  Es wird erneut geschrieben wird.  Finden Sie unter [Problem #666](https://github.com/dotnet/docs/issues/666) Informationen zu den Änderungen.

Asynchrone Programmierung in f# kann über ein Sprachebene Programmiermodell soll eine einfach zu verwendende und natürliche Sprache durchgeführt werden.

Der Kern der asynchronen Programmierung in f# ist `Async<'T>`, eine Darstellung der Arbeit, die ausgelöst werden kann, um im Hintergrund auszuführen, in denen `'T` ist entweder der Typ, die über den besonderen zurückgegeben `return` Schlüsselwort oder `unit` Wenn des asynchronen Workflows keine Ergebnis zurückgeben.

Das grundlegende Konzept zu verstehen ist, dass ein asynchroner Ausdruckstyp `Async<'T>`, also lediglich ein _Spezifikation_ der Arbeit, die in einem asynchronen Kontext auszuführen. Es wird nicht ausgeführt, bis Sie explizit mit einem der ersten Funktionen beginnen (z. B. `Async.RunSynchronously`). Obwohl dies eine andere Art der Gedanken über die Aufgabe auszuführen ist, endet es ganz einfach in der Praxis wird.

Angenommen Sie, Sie möchten den HTML-Code aus dotnetfoundation.org heruntergeladen werden, ohne den Hauptthread zu blockieren. Sie erreichen sie wie folgt:

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

Und das ist schon alles! Abgesehen von der Verwendung von `async`, `let!`, und `return`, dies ist nur normale f#-Code.

Es gibt einige syntaktische Konstrukte, die Folgendes zu beachten sind:

*   `let!` Bindet das Ergebnis eines asynchronen-Ausdrucks (der auf einem anderen Kontext ausgeführt wird).
*   `use!` funktioniert Analog `let!`, aber die gebundenen Ressourcen verwirft, wenn sie den Gültigkeitsbereich verlässt.
*   `do!` wird einen asynchroner Workflow "await" die nichts zurückgibt.
*   `return` einfach gibt ein Ergebnis von einem asynchronen Ausdruck zurück.
*   `return!` eine andere Async-Workflow ausführt, und gibt den Rückgabewert als Ergebnis zurück.

Darüber hinaus normalen `let`, `use`, und `do` Schlüsselwörter können zusammen mit der asynchronen Versionen verwendet werden, so als in eine normale Funktion würden.

## <a name="how-to-start-async-code-in-f"></a>Zum Starten von asynchronem Code in F# erläutert werden. #

Wie bereits erwähnt, ist asynchronem Code eine Spezifikation der Arbeit, die in einem anderen Kontext auszuführen, der explizit gestartet werden muss. Hier sind zwei Hauptmethoden, um dies zu erreichen:

1.  `Async.RunSynchronously` Startet einen asynchronen Workflow in einem anderen Thread und "await" das Ergebnis.

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

2.  `Async.Start` Startet einen asynchronen Workflow in einem anderen Thread, und wird **nicht** "await" das Ergebnis.

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

Es gibt andere Möglichkeiten zum Starten einer Async-Workflows, die für spezifische Szenarien zur Verfügung. Sie werden beschrieben [in der Referenz zu asynchronen](https://msdn.microsoft.com/library/ee370232.aspx).

### <a name="a-note-on-threads"></a>Hinweis zu Threads

Der Ausdruck "in einem anderen Thread" erwähnten, aber es ist wichtig zu wissen, dass **Dies bedeutet nicht, dass asynchrone Workflows Fassade für sind multithreading**. Der Workflow springt"tatsächlich" zwischen Threads, die sie für eine kleine Menge von Zeit für sinnvolle Arbeit Kreditaufnahme. Wenn ein asynchroner Workflow effektiv "(z. B. das Warten auf eines Netzwerkaufruf etwas zurückgegeben) wartet", wird bis zu sinnvolle Arbeit wechseln möchten, auf ein anderes Element einen beliebigen Thread, die er zum Zeitpunkt Kreditaufnahme wurde freigegeben. Dies ermöglicht die asynchrone Workflows im System nutzen können, das sie so effektiv wie möglich ausgeführt, schreibt und Benutzerprozessen besonders starken für e/a-Szenarien mit hohem Volumen.

## <a name="how-to-add-parallelism-to-async-code"></a>Zum Hinzufügen von Parallelität zu asynchronem Code

In einigen Fällen möglicherweise müssen mehrere asynchrone Aufträge parallel auszuführenden erfassen ihre Ergebnisse und in irgendeiner Form zu interpretieren. `Async.Parallel` bietet die Möglichkeit, ohne die Task Parallel Library verwenden, denn diese enthalten würde umgewandelt werden müssen dazu `Task<'T>` und `Async<'T>` Typen.

Im folgende Beispiel wird verwenden `Async.Parallel` um den HTML-Code von vier beliebten Websites parallel heruntergeladen haben, warten Sie für diese Aufgaben abgeschlossen, und drucken Sie anschließend den HTML-Code die heruntergeladen wurde.

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

*   Fügen Sie "Async" am Ende alle Funktionen, die Sie nutzen können

 Obwohl dies nur eine Benennungskonvention ist, z. B. API Erkennbarkeit erleichtern. Insbesondere, wenn synchrone und asynchrone Versionen der gleichen Routine verfügbar sind, ist es eine gute Idee, um explizit anzugeben, die über den Namen asynchron ist.

*   Der Compiler hören!

 # Des Compilers ist sehr strenge, somit nahezu unmöglich, etwas beunruhigend wie "Async" Code synchron ausgeführt. Wenn Sie über eine Warnung stammen, ist, die ein Zeichen dafür, dass der Code ausgeführt wird nicht, wie Sie glauben, dass es sich bei wird. Wenn Sie den Compiler zufriedene vornehmen können, wird Ihr Code sehr wahrscheinlich ausgeführt, wie erwartet.

## <a name="for-the-cvb-programmer-looking-into-f"></a>Der C#/VB-Programmierer, die in f#-suchen #

In diesem Abschnitt wird vorausgesetzt, Sie bereits vertraut sind, mit dem Async-Modell in c# / VB dar. Wenn Sie nicht, sind [für die asynchrone Programmierung in c#](../../../csharp/async.md) ist ein Ausgangspunkt.

Es ist ein wesentlicher Unterschied zwischen der C#/VB Async und das f# Async-Modell.

Beim Aufrufen einer Funktion, die gibt eine `Task` oder `Task<'T>`, diesen Auftrag bereits mit Ausführung begonnen hat. Das zurückgegebene Handle stellt einen asynchronen bereits ausgeführten-Auftrag dar. Im Gegensatz dazu beim Aufruf einer Async-Funktion in F# erläutert werden, die `Async<'a>` zurückgegebene stellt einen Auftrag die **generiert** irgendwann. Grundlegendes zu diesem Modell ist leistungsstark, da für asynchronen Aufträge in F# erläutert werden, die miteinander verkettet werden können einfacher, bedingt ausgeführt und feiner differenziert des Steuerelements gestartet werden.

Es gibt einige ähnlichkeiten und Unterschiede zu beachten.

### <a name="similarities"></a>Ähnlichkeiten

*   `let!`, `use!`, und `do!` sind analog zu den `await` beim Aufrufen eines Async-Auftrags innerhalb einer `async{ }` Block.

 Die drei Schlüsselwörter können nur verwendet werden, innerhalb einer `async { }` Block, ähnlich wie beim `await` kann nur aufgerufen werden, in eine `async` Methode. Kurz gesagt, `let!` ist für, wenn Sie möchten, und ein Ergebnis `use!` ist der gleiche aber für ein Element, dessen Ressourcen bereinigt abrufen, müssen nachdem es verwendet wird, und `do!` kann, wenn Sie einen asynchronen Workflow mit keinen Wert zurückgibt, um den Vorgang abzuschließen warten möchten Bevor Sie fortfahren.

*   F# unterstützt Datenparallelität auf ähnliche Weise.

 Obwohl es sehr unterschiedlich arbeitet `Async.Parallel` entspricht `Task.WhenAll` für das Szenario für die Ergebnisse eines Satzes von asynchronen Aufträge endversatz, alle nach Beendigung.

### <a name="differences"></a>Unterschiede

*   Geschachtelte `let!` nicht zulässig ist, im Gegensatz zu geschachtelt `await`

 Im Gegensatz zu `await`, unbegrenzt lange, geschachtelte können `let!` kann nicht und muss das Ergebnis gebunden werden, bevor Sie ihn in eine andere verwenden `let!`, `do!`, oder `use!`.

*   Unterstützung für den Abbruch ist einfacher in f# als in c# / VB dar.

 Abbruch in der Mitte über seine Ausführung einer Aufgabe in C#/VB Unterstützung erfordert die Prüfung der `IsCancellationRequested` Eigenschaft oder das Aufrufen `ThrowIfCancellationRequested()` auf eine `CancellationToken` -Objekt, das an die asynchrone Methode übergeben wird.

Im Gegensatz dazu sind asynchrone Workflows [F#] natürlicher abgebrochen werden können. Abbruch ist ein einfacher dreistufigen Vorgang.

1.  Erstellen Sie einen neuen `CancellationTokenSource`.
2.  Übergeben Sie sie in einer Funktion ab.
3.  Rufen Sie `Cancel` auf dem Token.

Beispiel:

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

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

Und das ist schon alles!

## <a name="further-resources"></a>Weitere Ressourcen:

*   [Asynchrone Workflows auf MSDN](https://msdn.microsoft.com/library/dd233250.aspx)
*   [Asynchrone Sequenzen für [F#]](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [F#-Daten HTTP-Hilfsprogramme](https://fsharp.github.io/FSharp.Data/library/Http.html)
