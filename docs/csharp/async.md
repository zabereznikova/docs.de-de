---
title: Asynchrone Programmierung – C#
description: Informationen zum asynchronen Programmiermodell auf C#-Sprachebene, das von .NET Core bereitgestellt wird.
author: cartermp
ms.date: 05/20/2020
ms.technology: csharp-async
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.openlocfilehash: b5643dd7eddefebc9cbf922ff5cce75d72dee4dd
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100898"
---
# <a name="asynchronous-programming"></a>Asynchrone Programmierung

Wenn Sie E/A-gebundene Anforderungen haben (z. B. Daten aus einem Netzwerk anfordern, auf eine Datenbank zugreifen oder aus einem Dateisystem lesen oder hineinschreiben), sollten Sie asynchrone Programmierung verwenden. Sie könnten auch CPU-gebundenen Code haben, z.B. eine teure Berechnung, bei der es sich auch um ein gutes Szenario zum Schreiben von asynchronem Code handelt.

C# bietet ein auf Sprachebene asynchrones Programmiermodell, das das Schreiben von asynchronem Code problemlos ermöglicht, ohne Rückrufe jonglieren oder eine Bibliothek bestätigen zu müssen, die Asynchronie unterstützt. Es folgt das so genannte [Aufgabenbasierte asynchrone Muster (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

## <a name="overview-of-the-asynchronous-model"></a>Grundlegende Übersicht über das asynchrone Modell

Der Kern der asynchronen Programmierung sind die `Task`- und `Task<T>`-Objekte, die asynchrone Vorgänge modellieren. Sie werden von den `async`- und `await`-Schlüsselwörtern unterstützt. Das Modell ist in den meisten Fällen recht einfach:

- Für E/A-gebundenen Code erwarten Sie einen Vorgang, der einen `Task` oder `Task<T>` innerhalb einer `async`-Methode zurückgibt.
- Für CPU-gebundenen Code erwarten Sie einen Vorgang, der in einem Hintergrundthread mit der <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>-Methode gestartet wird.

Das Schlüsselwort `await` ist sozusagen der Zauberstab. Es übergibt die Steuerung an den Aufrufer der Methode, die `await` durchgeführt hat. Somit können Benutzeroberflächen letztendlich reaktionsfähig und Dienste elastisch werden. Obwohl es [Möglichkeiten gibt](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md), sich mit anderem asynchronem Code als `async` und `await` zu befassen, konzentriert sich dieser Artikel auf die Konstrukte auf Sprachebene.

### <a name="io-bound-example-download-data-from-a-web-service"></a>E/A-gebundenes Beispiel: Herunterladen von Daten von einem Webdienst

Sie müssen möglicherweise einige Daten von einem Webdienst herunterladen, wenn auf eine Schaltfläche geklickt wird, möchten aber nicht den UI-Thread blockieren. Das können Sie wie folgt erreichen:

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

Der Code gibt die Absicht (Daten asynchron herunterladen) an, ohne durch Interaktion mit `Task`-Objekten vereitelt zu werden.

### <a name="cpu-bound-example-perform-a-calculation-for-a-game"></a>CPU-gebundenes Beispiel: Ausführen einer Berechnung für ein Spiel

Angenommen, Sie schreiben ein mobiles Spiel, in dem ein Knopfdruck vielen Feinden auf dem Bildschirm Schaden zufügen könnte. Das Durchführen der Schadensberechnung kann teuer sein, und sie auf dem UI-Thread durchzuführen, hält das Spiel scheinbar an, wenn die Berechnung ausgeführt wird!

Die beste Möglichkeit ist, einen Hintergrundthread zu starten, der die Arbeit mit `Task.Run` erledigt, und das Ergebnis mit `await` zu erwarten. So wird die Benutzeroberfläche nicht gestört, wenn die Berechnung durchgeführt wird.

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
    // performs its work. The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

Dieser Code drückt die Absicht des click-Ereignisses der Schaltfläche sauber aus und benötigt kein manuelles Verwalten eines Hintergrundthreads. Dies geschieht in einer nicht blockierenden Art und Weise.

### <a name="what-happens-under-the-covers"></a>Was im Hintergrund geschieht

Es gibt viele bewegliche Bestandteile bei asynchronen Vorgängen. Wenn Sie neugierig sind, was hinter den Kulissen von `Task` und `Task<T>` geschieht, dann lesen Sie den Artikel [Async im Detail](../standard/async-in-depth.md).

Auf der C#-Seite transformiert der Compiler Ihren Code in einen Zustandsautomaten, der z.B. die Rückgabe der Ausführung protokolliert, wenn `await` erreicht wird, und das Fortsetzen der Ausführung, wenn ein Hintergrundauftrag abgeschlossen ist.

Für theorieinteressierte Benutzer: Dies ist eine Implementierung des [Promise-Modells der Asynchronie](https://en.wikipedia.org/wiki/Futures_and_promises).

## <a name="key-pieces-to-understand"></a>Wichtigste Bestandteile

* Async-Code kann für E/A-gebundenen und CPU-gebundene Code, aber für jedes Szenario anders verwendet werden.
* Async-Code verwendet die Konstrukte `Task<T>` und `Task`, die als Modell für Arbeit im Hintergrund verwendet werden können.
* Das `async`-Schlüsselwort wandelt eine Methode in eine asynchrone Methode um, mit der Sie das `await`-Schlüsselwort in ihrem Nachrichtentext verwenden können.
* Wenn das `await`-Schlüsselwort angewendet wird, hält es die aufrufende Methode an, und gibt die Steuerung wieder an den Aufrufer zurück, bis die Aufgabe abgeschlossen ist.
* `await` kann nur innerhalb einer Async-Methode verwendet werden.

## <a name="recognize-cpu-bound-and-io-bound-work"></a>Erkennen von CPU-gebundener und E/A-gebundener Arbeit

Die ersten beiden Beispiele dieser Anleitung zeigen, wie Sie `async` und `await` für E/A-gebundene und CPU-gebundene Arbeit verwenden können. Der Schlüssel, den Sie erkennen können, wenn ein zu erledigender Auftrag E/A-gebunden oder CPU-gebunden ist, kann die Leistung Ihres Codes erheblich beeinträchtigen und möglicherweise zum Missbrauch bestimmter Konstrukte führen.

Hier sind zwei Fragen, die Sie stellen sollten, bevor Sie Code schreiben:

1. Wird Ihr Code auf etwas „warten“, z.B. auf Daten aus einer Datenbank?

   Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **E/A-gebunden**.

1. Wird Ihr Code eine umfangreiche Berechnung durchführen?

   Wenn Ihre Antwort „Ja“ lautet, ist Ihre Arbeit **CPU-gebunden**.

Falls Ihre Arbeit **E/A-gebunden** ist, verwenden Sie `async` und `await` *ohne* `Task.Run`. Sie *sollten nicht* die Task Parallel Library verwenden. Der Grund dafür wird in [Async ausführlich](../standard/async-in-depth.md) dargelegt.

Falls Ihre Arbeit **CPU-gebunden** ist und Sie sich für Reaktionsfähigkeit interessieren, dann verwenden Sie `async` und `await`, aber übertragen Sie die Arbeit *mit* `Task.Run` auf einen anderen Thread. Wenn die Arbeit für Parallelität und Konkurrenz geeignet ist, erwägen Sie auch die Verwendung der [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).

Darüber hinaus sollten Sie immer die Ausführung Ihres Codes messen. Sie könnten z.B. in eine Situation geraten, in der Ihre CPU-gebundene Arbeit im Vergleich zum Aufwand der Kontextwechsel beim Multithreading nicht kostspielig genug ist. Jede Entscheidung hat Nachteile, und Sie sollten die Nachteile je nach Ihrer Situation auswählen.

## <a name="more-examples"></a>Weitere Beispiele

Die folgenden Beispiele veranschaulichen verschiedene Möglichkeiten, wie Sie asynchronen Code in C# schreiben können. Diese decken einige andere Szenarios ab, auf die Sie möglicherweise stoßen.

### <a name="extract-data-from-a-network"></a>Extrahieren von Daten aus einem Netzwerk

Dieser Ausschnitt lädt den HTML-Code von der Homepage <https://dotnetfoundation.org> herunter und zählt, wie oft die Zeichenfolge „.NET“ darin vorkommt. Er verwendet ASP.NET zur Definition einer Web-API-Controllermethode, die diesen Task ausführt und die Zahl zurückgibt.

> [!NOTE]
> Wenn Sie eine HTML-Analyse im Produktionscode durchführen möchten, nutzen Sie dafür nicht die regulären Ausdrücke. Verwenden Sie stattdessen eine Analysebibliothek.

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet, Route("DotNetCount")]
public async Task<int> GetDotNetCount()
{
    // Suspends GetDotNetCount() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

Hier sehen Sie das gleiche Szenario, das für eine universelle Windows-App geschrieben wurde, die die gleiche Aufgabe ausführt, wenn auf eine Schaltfläche geklickt wird:

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void OnSeeTheDotNetsButtonClick(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends OnSeeTheDotNetsButtonClick(), returning control to its caller.
    // This is what allows the app to be responsive and not block the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="wait-for-multiple-tasks-to-complete"></a>Warten auf das Abschließen mehrerer Tasks

Sie könnten sich in einer Situation befinden, in der Sie mehrere Daten gleichzeitig abrufen müssen. Die `Task`-API enthält die Methoden <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, mit denen Sie asynchronen Code schreiben können, der einen nicht blockierenden Wartevorgang für mehrere Hintergrundaufträge durchführt.

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

Hier sehen Sie eine weitere Möglichkeit, dies mithilfe von LINQ präziser zu schreiben:

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

Obwohl es weniger Code ist, sollten Sie trotzdem vorsichtig sein, wenn Sie LINQ mit asynchronem Code mischen. Da LINQ verzögerte (lazy) Ausführung verwendet, werden asynchrone Aufrufe nicht sofort ausgeführt, so wie in einer `foreach`-Schleife, es sei denn, Sie erzwingen, dass die generierte Sequenz einen Aufruf von `.ToList()` oder `.ToArray()` durchläuft.

## <a name="important-info-and-advice"></a>Wichtige Informationen und Hinweise

Bei asynchroner Programmierung sind einige Details zu berücksichtigen, die unerwartetes Verhalten verhindern können.

* `async` **-Methoden benötigen ein Schlüsselwort**  `await`  **in Ihrem Textkörper, andernfalls erfolgt niemals eine Rückgabe!**

  Berücksichtigen Sie dies. Wenn `await` nicht im Textkörper einer `async`-Methode verwendet wird, generiert der C#-Compiler eine Warnung, aber der Code wird kompiliert und ausgeführt, als ob es sich um eine normale Methode handeln würde. Dies ist unglaublich ineffizient, da der Zustandsautomat, der vom C#-Compiler für die asynchrone Methode generiert wird, nichts erreicht.

* **Sie sollten „Async“ als Suffix für die Namen aller async-Methoden hinzufügen, die Sie schreiben.**

Mit dieser in .NET verwendeten Konvention kann leichter zwischen synchronen und asynchronen Methoden unterschieden werden. Bestimmte, von Ihrem Code nicht explizit aufgerufene Methoden (z. B. Ereignishandler oder Webcontrollermethoden) werden nicht unbedingt angewendet. Da sie von Ihrem Code nicht explizit aufgerufen werden, ist es nicht wichtig, ihre Namen explizit anzugeben.

* `async void` **sollte nur für Ereignishandler verwendet werden.**

`async void` ist die einzige Möglichkeit, mit der asynchrone Ereignishandler ausgeführt werden können, da Ereignisse keine Rückgabetypen haben (und somit `Task` und `Task<T>` nicht verwenden können). Jede andere Verwendung der `async void` folgt nicht dem TAP-Modell und kann schwierig zu verwenden sein, wie beispielsweise:

* Ausnahmen in einer `async void`-Methode können nicht außerhalb der Methode abgefangen werden.
* `async void`-Methoden sind schwierig zu testen.
* `async void`-Methoden können schlechte Nebeneffekte verursachen, wenn der Aufrufende nicht erwartet, dass sie asynchron sind.

* **Gehen Sie bei der Verwendung von asynchronen Lambdaausdrücken in LINQ-Ausdrücken sorgfältig vor**

Lambdaausdrücke in LINQ verwenden verzögerte Ausführung. Das bedeutet, dass Code zu einem Zeitpunkt ausgeführt werden kann, zu dem Sie es nicht erwarten. Die Einführung von blockierenden Aufgaben kann schnell zu einem Deadlock führen, wenn diese nicht ordnungsgemäß geschrieben werden. Darüber hinaus kann die Schachtelung von asynchronem Code die Ausführung des Codes erschweren. Async und LINQ sind leistungsstark, sollten aber so sorgfältig und genau wie möglich zusammen verwendet werden.

* **Schreiben Sie Code, der Aufgaben in einer nicht blockierenden Art und Weise erwartet**

Wenn Sie den aktuellen Thread blockieren, um auf den Abschluss eines `Task` zu warten, können Deadlocks und Blockierungen von Kontextthreads auftreten und komplexere Fehlerbehandlung kann erforderlich sein. Die folgende Tabelle enthält Anleitungen zum nicht-blockierenden Warten auf Tasks:

| Verwenden Sie...          | Anstatt...           | Wenn Sie dies tun möchten...                 |
|----------------------|------------------------------|--------------------------------------------|
| `await`              | `Task.Wait` oder `Task.Result` | Abrufen des Ergebnisses einer Hintergrundaufgabe |
| `await Task.WhenAny` | `Task.WaitAny`               | Warten auf das Abschließen einer Aufgabe           |
| `await Task.WhenAll` | `Task.WaitAll`               | Warten auf das Abschließen aller Aufgaben          |
| `await Task.Delay`   | `Thread.Sleep`               | Warten auf einen Zeitraum               |

* **Verwenden Sie ggf.** `ValueTask` **.**

Das Zurückgeben eines `Task`-Objekts von asynchronen Methoden kann Leistungsengpässe in bestimmten Pfaden verursachen. `Task` ist ein Verweistyp, seine Verwendung bedeutet also das Zuordnen eines Objekts. In Fällen, in denen eine mit dem `async`-Modifizierer deklarierte Methode ein zwischengespeichertes Ergebnis zurückgibt oder synchron abschließt, können die zusätzlichen Zuordnungen viel Zeit bei der Ausführung kritischer Codeabschnitte kosten. Es kann kostspielig werden, wenn diese Zuordnungen in engen Schleifen auftreten. Weitere Informationen finden Sie unter [Generalisierte asynchrone Rückgabetypen](whats-new/csharp-7.md#generalized-async-return-types).

* **Verwenden Sie ggf.** `ConfigureAwait(false)`.

Eine häufige Frage ist: „Wann sollte ich die <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType>-Methode verwenden?“. Die Methode ermöglicht einer `Task`-Instanz, ihren Awaiter zu konfigurieren. Dies ist ein wichtiger Aspekt, und die falsche Festlegung kann möglicherweise Auswirkungen auf die Leistung und sogar Deadlocks zur Folge haben. Weitere Informationen zu `ConfigureAwait` finden Sie im [ConfigureAwait-FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq).

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
