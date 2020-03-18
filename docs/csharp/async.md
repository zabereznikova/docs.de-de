---
title: Asynchrone Programmierung – C#
description: Informationen zum asynchronen Programmiermodell auf C#-Sprachebene, das von .NET Core bereitgestellt wird.
author: cartermp
ms.date: 06/20/2016
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: 38d7c856e9a536db9ef26349175ad440a49f5fe2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713954"
---
# <a name="asynchronous-programming"></a>Asynchrone Programmierung

Wenn Sie E/A-gebundene Anforderungen (z.B. Daten aus einem Netzwerk anfordern oder auf eine Datenbank zugreifen) haben, sollten Sie asynchrone Programmierung verwenden.  Sie könnten auch CPU-gebundenen Code haben, z.B. eine teure Berechnung, bei der es sich auch um ein gutes Szenario zum Schreiben von asynchronem Code handelt.

C# bietet ein auf Sprachebene asynchrones Programmiermodell, das das Schreiben von asynchronem Code problemlos ermöglicht, ohne Rückrufe jonglieren oder eine Bibliothek bestätigen zu müssen, die Asynchronie unterstützt. Es folgt das so genannte [Aufgabenbasierte asynchrone Muster (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

## <a name="basic-overview-of-the-asynchronous-model"></a>Grundlegende Übersicht über das asynchrone Modell

Der Kern der asynchronen Programmierung sind die `Task`- und `Task<T>`-Objekte, die asynchrone Vorgänge modellieren.  Sie werden von den `async`- und `await`-Schlüsselwörtern unterstützt.  Das Modell ist in den meisten Fällen recht einfach:

Für E/A-gebundenen Code wenden Sie `await` auf einen Vorgang an, der `Task` oder `Task<T>` innerhalb einer `async`-Methode zurückgibt.

Für CPU-gebundenen Code wenden Sie `await` auf einen Vorgang an, der in einem Hintergrundthread mit der `Task.Run`-Methode gestartet wird.

Das Schlüsselwort `await` ist sozusagen der Zauberstab. Es übergibt die Steuerung an den Aufrufer der Methode, die `await` durchgeführt hat. Somit können Benutzeroberflächen letztendlich reaktionsfähig und Dienste elastisch werden.

Es gibt weitere Methoden als Ansatz für asynchronen Code als `async` und `await`, die im oben verknüpften TAP-Artikel beschriebenen sind, aber dieses Dokument konzentriert sich ab nun auf die Konstrukte auf Sprachebene.

### <a name="io-bound-example-downloading-data-from-a-web-service"></a>E/A-Beispiel: Herunterladen von Daten von einem Webdienst

Sie müssen möglicherweise einige Daten von einem Webdienst herunterladen, wenn auf eine Schaltfläche geklickt wird, möchten aber nicht den UI-Thread blockieren. Das kann einfach wie folgt erreicht werden:

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

Und das ist schon alles! Der Code gibt die Absicht (einige Daten asynchron herunterladen) an, ohne durch Interaktion mit Taskobjekten vereitelt zu werden.

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a>CPU-gebundenes Beispiel: Ausführen einer Berechnung eines Spiels

Angenommen, Sie schreiben ein mobiles Spiel, in dem ein Knopfdruck vielen Feinden auf dem Bildschirm Schaden zufügen könnte.  Das Durchführen der Schadensberechnung kann teuer sein, und sie auf dem UI-Thread durchzuführen, hält das Spiel scheinbar an, wenn die Berechnung ausgeführt wird!

Die beste Möglichkeit, dies zu verarbeiten, ist die Arbeit mit einen Hintergrundthread, der `Task.Run` verwendet, und `await` als Ergebnis hat.  Dadurch wird die Benutzeroberfläche nicht gestört, wenn die Berechnung durchgeführt wird.

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}

calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

Das ist schon alles!  Dieser Code drückt die Absicht des click-Ereignisses der Schaltfläche sauber aus und benötigt kein manuelles Verwalten eines Hintergrundthreads. Dies geschieht in einer nicht blockierenden Art und Weise.

### <a name="what-happens-under-the-covers"></a>Was im Hintergrund geschieht

Es gibt viele bewegliche Bestandteile bei asynchronen Vorgängen.  Wenn Sie neugierig sind, was hinter den Kulissen von `Task` und `Task<T>` geschieht, dann lesen Sie den Artikel [Async im Detail](../standard/async-in-depth.md) für weitere Informationen.

Auf der C#-Seite transformiert der Compiler Ihren Code in einen Zustandsautomaten, der z.B. die Rückgabe der Ausführung protokolliert, wenn `await` erreicht wird, und das Fortsetzen der Ausführung, wenn ein Hintergrundauftrag abgeschlossen ist.

Für theorieinteressierte Benutzer: Dies ist eine Implementierung des [Promise-Modells der Asynchronie](https://en.wikipedia.org/wiki/Futures_and_promises).

## <a name="key-pieces-to-understand"></a>Wichtigste Bestandteile

* Async-Code kann für E/A-gebundenen und CPU-gebundene Code, aber für jedes Szenario anders verwendet werden.
* Async-Code verwendet die Konstrukte `Task<T>` und `Task`, die als Modell für Arbeit im Hintergrund verwendet werden können.
* Das `async`-Schlüsselwort wandelt eine Methode in eine asynchrone Methode um, mit der Sie das `await`-Schlüsselwort in ihrem Nachrichtentext verwenden können.
* Wenn das `await`-Schlüsselwort angewendet wird, hält es die aufrufende Methode an, und gibt die Steuerung wieder an den Aufrufer zurück, bis die Aufgabe abgeschlossen ist.
* `await` kann nur innerhalb einer Async-Methode verwendet werden.

## <a name="recognize-cpu-bound-and-io-bound-work"></a>Erkennen von CPU-gebundener und E/A-gebundener Arbeit

Die ersten beiden Beispiele dieser Anleitung zeigen, wie Sie `async` und `await` für E/A-gebundene und CPU-gebundene Arbeit verwenden können.  Der Schlüssel, den Sie erkennen können, wenn ein zu erledigender Auftrag E/A-gebunden oder CPU-gebunden ist, kann die Leistung Ihres Codes erheblich beeinträchtigen und möglicherweise zum Missbrauch bestimmter Konstrukte führen.

Hier sind zwei Fragen, die Sie stellen sollten, bevor Sie Code schreiben:

1. Wird Ihr Code auf etwas „warten“, z.B. auf Daten aus einer Datenbank?

    Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **E/A-gebunden**.

2. Wird Ihr Code eine umfangreiche Berechnung durchführen?

    Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **CPU-gebunden**.

Falls Ihre Arbeit **E/A-gebunden** ist, verwenden Sie `async` und `await` *ohne* `Task.Run`.  Sie *sollten nicht* die Task Parallel Library verwenden.  Der Grund dafür ist im Artikel [Async ausführlich](../standard/async-in-depth.md) dargestellt.

Falls Ihre Arbeit **CPU-gebunden** ist und Sie sich für Reaktionsfähigkeit interessieren, dann verwenden Sie `async` und `await`, aber übertragen Sie die Arbeit auf einen anderen Thread *mit* `Task.Run`.  Wenn die Arbeit für Parallelität und Konkurrenz geeignet ist, sollten Sie auch über die Verwendung der [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md) nachdenken.

Darüber hinaus sollten Sie immer die Ausführung Ihres Codes messen.  Sie könnten z.B. in eine Situation geraten, in der Ihre CPU-gebundene Arbeit im Vergleich zum Aufwand der Kontextwechsel beim Multithreading nicht kostspielig genug ist.  Jede Entscheidung hat Nachteile, und Sie sollten die Nachteile je nach Ihrer Situation auswählen.

## <a name="more-examples"></a>Weitere Beispiele

Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten, wie Sie asynchronen Code in C# schreiben können.  Diese decken einige andere Szenarios ab, auf die Sie möglicherweise stoßen.

### <a name="extracting-data-from-a-network"></a>Extrahieren von Daten aus einem Netzwerk

Dieser Ausschnitt lädt den HTML-Cod von der Homepage [www.dotnetfoundation.org](https://www.dotnetfoundation.org) herunter und zählt die Häufigkeit, mit der die Zeichenfolge „.NET“ im HTML-Code auftritt.  Er verwendet ASP.NET MVC zur Definition einer Webcontrollermethode, die diese Aufgabe ausführt, indem sie die Zahl zurückgibt.

> [!NOTE]
> Wenn Sie eine HTML-Analyse im Produktionscode durchführen möchten, nutzen Sie dafür nicht die regulären Ausdrücke. Verwenden Sie stattdessen eine Analysebibliothek.

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

Hier sehen Sie das gleiche Szenario, das für eine universelle Windows-App geschrieben wurde, die die gleiche Aufgabe ausführt, wenn auf eine Schaltfläche geklickt wird:

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://www.dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="waiting-for-multiple-tasks-to-complete"></a>Warten auf das Abschließen aller Aufgaben

Sie könnten sich in einer Situation befinden, in der Sie mehrere Daten gleichzeitig abrufen müssen.  Die `Task`-API enthält die Methoden `Task.WhenAll` und `Task.WhenAny`, mit denen Sie asynchronen Code schreiben können, der einen nicht blockierenden Wartevorgang für mehrere Hintergrundaufträge durchführt.

Dieses Beispiel zeigt, wie Sie einen `User`-Datensatz für einen Satz von `userId` nehmen könnten.

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();

    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

Hier sehen Sie eine weitere Möglichkeit, dies mithilfe von LINQ etwas präziser zu schreiben:

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

Obwohl es weniger Code ist, sollten Sie trotzdem vorsichtig sein, wenn Sie LINQ mit asynchronem Code mischen.  Da LINQ verzögerte (lazy) Ausführung verwendet, werden asynchrone Aufrufe nicht sofort ausgeführt, so wie in einer `foreach()`-Schleife, es sei denn, Sie erzwingen, dass die generierte Sequenz einen Aufruf von `.ToList()` oder `.ToArray()` durchläuft.

## <a name="important-info-and-advice"></a>Wichtige Informationen und Hinweise

Asynchrone Programmierung ist relativ einfach, es sind jedoch einige Details zu berücksichtigen, die unerwartetes Verhalten verhindern können.

* `async` **-Methoden benötigen ein Schlüsselwort**  `await`  **in Ihrem Textkörper, andernfalls erfolgt niemals eine Rückgabe!**

Berücksichtigen Sie dies.  Wenn `await` im Textkörper einer `async`-Methode nicht verwendet wird, generiert der C#-Compiler eine Warnung, aber der Code wird kompiliert und ausgeführt, als ob es sich um eine normale Methode handeln würde.  Beachten Sie, dass dies auch sehr ineffizient wäre, da der Zustandsautomat, der vom C#-Compiler für die asynchrone Methode generiert wurde, nichts erreichen würde.

* **Sie sollten „Async“ als Suffix für die Namen aller async-Methoden hinzufügen, die Sie schreiben.**

Dies ist die in .NET verwendete Konvention, mit der leichter zwischen synchronen und asynchronen Methoden unterschieden werden kann. Beachten Sie, dass bestimmte Methoden, die von Ihrem Code (z.B. Ereignishandler oder Webcontrollermethoden) nicht explizit aufgerufen werden, nicht unbedingt angewendet werden. Da diese von Ihrem Code nicht explizit aufgerufen werden, ist es nicht wichtig, ihre Namen explizit anzugeben.

* `async void` **sollte nur für Ereignishandler verwendet werden.**

`async void` ist die einzige Möglichkeit, mit der asynchrone Ereignishandler ausgeführt werden können, da Ereignisse keine Rückgabetypen haben (und somit `Task` und `Task<T>` nicht verwenden können). Jede andere Verwendung der `async void` folgt nicht dem TAP-Modell und kann schwierig zu verwenden sein, wie beispielsweise:

* Ausnahmen in einer `async void`-Methode können nicht außerhalb der Methode abgefangen werden.
* `async void`-Methoden sind sehr schwierig zu testen.
* `async void`-Methoden können große Nebeneffekte verursachen, wenn der Aufrufende nicht erwartet, dass sie asynchron sind.

* **Gehen Sie bei der Verwendung von asynchronen Lambdaausdrücken in LINQ-Ausdrücken sorgfältig vor**

Lambdaausdrücke in LINQ verwenden verzögerte Ausführung. Das bedeutet, dass Code zu einem Zeitpunkt ausgeführt werden kann, zu dem Sie es nicht erwarten. Die Einführung von blockierenden Aufgaben kann schnell zu einem Deadlock führen, wenn diese nicht ordnungsgemäß geschrieben werden. Darüber hinaus kann die Schachtelung von asynchronem Code die Ausführung des Codes erschweren. Async und LINQ sind leistungsstark, sollten aber so sorgfältig und genau wie möglich zusammen verwendet werden.

* **Schreiben Sie Code, der Aufgaben in einer nicht blockierenden Art und Weise erwartet**

Wenn Sie den aktuellen Thread blockieren, um auf den Abschluss einer Aufgabe zu warten, kann es zu Deadlocks und blockierten Kontextthreads kommen und wesentlich komplexere Fehlerbehandlung erfordern. Die folgende Tabelle enthält Anleitungen zum nicht-blockierenden Warten auf Aufgaben:

| Verwenden Sie... | Anstatt... | Wenn Sie dies tun möchten |
| --- | --- | --- |
| `await` | `Task.Wait` oder `Task.Result` | Abrufen des Ergebnisses einer Hintergrundaufgabe |
| `await Task.WhenAny` | `Task.WaitAny` | Warten auf das Abschließen einer Aufgabe |
| `await Task.WhenAll` | `Task.WaitAll` | Warten auf das Abschließen aller Aufgaben |
| `await Task.Delay` | `Thread.Sleep` | Warten auf einen Zeitraum |

* **Schreiben eines weniger statusbehafteten Codes**

Machen Sie sich nicht abhängig vom Zustand globaler Objekte oder der Ausführung bestimmter Methoden. Seien Sie stattdessen nur abhängig von Rückgabewerten der Methoden. Warum?

* Code wird leichter verständlich sein.
* Code wird leichter zu testen sein.
* Das Kombinieren von asynchronem und synchronem Code ist wesentlich einfacher.
* Racebedingungen können in der Regel ganz vermieden werden.
* Je nach Rückgabewerten ist das Koordinieren von asynchronem Code einfach.
* (Bonus) funktioniert hervorragend mit Abhängigkeitsinjektion.

Ein empfohlenes Ziel ist das vollständige oder nahezu vollständige Erreichen [referenzieller Transparenz](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in Ihrem Code. Dies führt zu einer sehr vorhersagbaren, getesteten und verwaltbaren Codebasis.

## <a name="other-resources"></a>Weitere Ressourcen

* [Async ausführlich](../standard/async-in-depth.md) enthält weitere Informationen zur Funktionsweise von Aufgaben.
* [Asynchrone Programmierung mit Async und Await (C#)](./programming-guide/concepts/async/index.md)
* Lucian Wischiks [sechs wichtige Tipps für Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) ist eine hervorragende Ressource für asynchrone Programmierung
