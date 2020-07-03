---
title: Verwenden des aufgabenbasierten asynchronen Musters
description: Hier erfahren Sie mehr über die Verwendung des aufgabenbasierten asynchronen Musters (Task-based Asynchronous Pattern, TAP) bei der Arbeit mit asynchronen Vorgängen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: f1a5070c106055b268d43751300d84269fed6a36
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85326002"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>Verwenden des aufgabenbasierten asynchronen Musters

Wenn Sie das aufgabenbasierte asynchrone Muster (TAP) verwenden, um mit asynchronen Vorgängen zu arbeiten, können Sie Rückrufe verwenden, um ein Warten ohne Blockierung zu erreichen.  Bei Tasks erfolgt dies durch Methoden wie <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Sprachbasierte Unterstützung asynchroner Vorgänge verbirgt Rückrufe, indem in der normalen Ablaufsteuerung auf asynchrone Vorgänge gewartet werden darf, und vom Compiler generierter Code bietet dieselbe Unterstützung auf API-Ebene.

## <a name="suspending-execution-with-await"></a>Anhalten der Ausführung mit „await“
 Ab .NET Framework 4.5 können Sie in C# das Schlüsselwort [await](../../csharp/language-reference/operators/await.md) und in Visual Basic den [Await-Operator](../../visual-basic/language-reference/operators/await-operator.md) verwenden, um asynchron auf Objekte vom Typ <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> zu warten. Wenn Sie eine <xref:System.Threading.Tasks.Task>-Klasse erwarten, ist der Ausdruck `await` vom Typ `void`. Wenn Sie eine <xref:System.Threading.Tasks.Task%601>-Klasse erwarten, ist der Ausdruck `await` vom Typ `TResult`. Ein `await`-Ausdruck muss im Text einer asynchronen Methode auftreten. Weitere Informationen zur Unterstützung von C# und Visual Basic in .NET Framework 4.5 finden Sie in den Spezifikationen für C# und Visual Basic.

 Die await-Funktionalität installiert im Hintergrund einen Rückruf für die Aufgabe, indem sie eine Fortsetzung verwendet.  Dieser Rückruf setzt die asynchrone Methode an dem Unterbrechungspunkt fort. Wenn die asynchrone Methode fortgesetzt wird und der Vorgang, auf den gewartet wurde, erfolgreich abgeschlossen wurde und <xref:System.Threading.Tasks.Task%601> war, wird `TResult` zurückgegeben.  Wenn die erwartete Klasse <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> im Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled> beendet wurde, wird eine <xref:System.OperationCanceledException>-Ausnahme ausgelöst.  Wenn die erwartete Klasse <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> im Zustand <xref:System.Threading.Tasks.TaskStatus.Faulted> beendet wurde, wird die für dessen fehlerhafte Ausführung verantwortliche Ausnahme ausgelöst. Ein `Task`-Objekt kann infolge mehrerer Ausnahmen einen Fehler verursachen, aber nur eine dieser Ausnahmen wird weitergegeben. Allerdings gibt die Eigenschaft <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> eine <xref:System.AggregateException>-Ausnahme zurück, die alle Fehler umfasst.

 Wenn ein Synchronisierungskontext (<xref:System.Threading.SynchronizationContext>-Objekt) mit dem Thread verknüpft wird, der zum Zeitpunkt der Unterbrechung die asynchrone Methode ausgeführt hat (z. B. wenn die Eigenschaft <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> nicht `null` ist), wird die asynchrone Methode für diesen Synchronisierungskontext mit der <xref:System.Threading.SynchronizationContext.Post%2A>-Methode des Kontexts fortgesetzt. Andernfalls greift sie auf den Taskplaner (<xref:System.Threading.Tasks.TaskScheduler>-Objekt) zurück, der zum Zeitpunkt der Unterbrechung aktuell war. Dies ist normalerweise der standardmäßige Taskplaner (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), der auf den Threadpool ausgerichtet ist. Dieser Taskplaner bestimmt, ob der erwartete asynchrone Vorgang fortgesetzt werden soll, wo er abgeschlossen wurde, oder ob die Wiederaufnahme geplant werden soll. Der Standardplaner lässt üblicherweise für die Fortsetzung zu, dass sie in dem Thread ausgeführt wird, in dem der erwartete Vorgang abgeschlossen wurde.

 Wenn eine asynchrone Methode aufgerufen wird, führt diese synchron den Hauptteil der Funktion bis zum ersten await-Ausdruck in einer await-fähigen Instanz aus, die noch nicht abgeschlossen ist. Dies ist der Punkt, an dem der Aufruf zum Aufrufer zurückkehrt. Wenn die asynchrone Methode nicht `void` zurückgibt, wird ein <xref:System.Threading.Tasks.Task>- oder <xref:System.Threading.Tasks.Task%601>-Objekt für die laufende Berechnung zurückgegeben. Wird in einer asynchronen Methode, die nicht „void“ zurückgibt, eine return-Anweisung gefunden oder das Ende des Methodentexts erreicht, wird der Task im <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>-Endzustand abgeschlossen. Wenn ein Ausnahmefehler bewirkt, dass die Steuerung den Text der asynchronen Methode verlässt, endet der Task im <xref:System.Threading.Tasks.TaskStatus.Faulted>-Zustand. Wenn es sich bei dieser Ausnahme um <xref:System.OperationCanceledException> handelt, endet der Task stattdessen im Zustand <xref:System.Threading.Tasks.TaskStatus.Canceled>. Auf diese Weise wird das Ergebnis oder die Ausnahme schließlich veröffentlicht.

 Es gibt mehrere wichtige Variationen dieses Verhalten.  Aus Leistungsgründen wird, wenn eine Aufgabe zu dem Zeitpunkt, zu dem sie erwartet wurde, bereits abgeschlossen ist, die Steuerung nicht abgegeben, sondern die Ausführung der Funktion fortgesetzt.  Außerdem ist eine Rückkehr zum ursprünglichen Kontext nicht immer das gewünschte Verhalten und kann geändert werden. Dies ist wird im nächsten Abschnitt genauer beschrieben.

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>Konfigurieren von Unterbrechung und Wiederaufnahme mit „Yield“ und „ConfigureAwait“
 Einige Methoden bieten eine weitergehende Steuerung der Ausführung einer asynchronen Methode. Beispielsweise können Sie mithilfe der <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType>-Methode einen Ertragspunkt in die asynchrone Methode einfügen:

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 Dies entspricht einem asynchronen Senden oder Planen zurück zum aktuellen Kontext.

```csharp
Task.Run(async delegate
{
    for(int i=0; i<1000000; i++)
    {
        await Task.Yield(); // fork the continuation into a separate work item
        ...
    }
});
```

 Sie können auch die <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>-Methode verwenden, um eine bessere Kontrolle über die Unterbrechung und Wiederaufnahme in einer asynchronen Methode zu ermöglichen.  Wie bereits erwähnt wird der aktuelle Kontext standardmäßig zu dem Zeitpunkt festgehalten, zu dem eine asynchrone Methode unterbrochen wird, und der festgehaltene Kontext wird verwendet, um die Fortsetzung der asynchronen Methode bei Wiederaufnahme aufzurufen.  In vielen Fällen ist dies genau das von Ihnen gewünschte Verhalten.  In anderen Fällen ist Ihnen der Fortsetzungskontext möglicherweise egal, und Sie können eine bessere Leistung erzielen, indem Sie solche Rücksprünge zum ursprünglichen Kontext vermeiden.  Verwenden Sie hierfür die <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>-Methode, um den await-Vorgang anzuweisen, nicht den Kontext zu erfassen und mit diesem fortzusetzen, sondern die Ausführung dort fortzusetzen, wo der erwartete asynchrone Vorgang abgeschlossen wurde:

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a>Abbrechen eines asynchronen Vorgangs
 Ab .NET Framework 4 stellen TAP-Methoden, die das Abbrechen unterstützen, mindestens eine Überladung bereit, die ein Abbruchtoken akzeptiert (<xref:System.Threading.CancellationToken>-Objekt).

 Ein Abbruchtoken wird durch eine Abbruchtokenquelle erstellt (<xref:System.Threading.CancellationTokenSource>-Objekt).  Die <xref:System.Threading.CancellationTokenSource.Token%2A>-Eigenschaft der Quelle gibt das Abbruchtoken zurück, das beim Aufrufen der <xref:System.Threading.CancellationTokenSource.Cancel%2A>-Methode der Quelle signalisiert wird.  Wenn Sie beispielsweise eine einzelne Webseite herunterladen und in der Lage sein möchten, den Vorgang abzubrechen, erstellen Sie ein <xref:System.Threading.CancellationTokenSource>-Objekt, übergeben Sie dessen Token an die TAP-Methode, und rufen Sie dann die <xref:System.Threading.CancellationTokenSource.Cancel%2A>-Methode der Quelle auf, sobald Sie für den Abbruch des Vorgangs bereit sind:

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 Um mehrere asynchrone Aufrufe abzubrechen, können Sie dasselbe Token an alle Aufrufe übergeben:

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 Oder Sie können dasselbe Token an eine bestimmte Teilmenge von Vorgängen übergeben:

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 Abbruchanforderungen können aus jedem Thread initiiert werden.

 Sie können den Wert <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> an jede Methode übergeben, die ein Abbruchtoken akzeptiert, um anzugeben, dass es nie zum Anfordern eines Abbruchs kommen wird.  Dies führt dazu, dass die <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType>-Eigenschaft `false` zurückgibt, und die aufgerufene Methode kann entsprechend optimiert werden.  Zu Testzwecken können Sie auch ein vorab abgebrochenes Abbruchtoken übergeben, das mit dem Konstruktor instanziiert wurde, der einen booleschen Wert akzeptiert, um anzugeben, ob das Token in einem bereits abgebrochenen oder in einem nicht abbrechbaren Zustand beginnen soll.

 Dieser Ansatz für Abbrechen hat mehrere Vorteile:

- Sie können dasselbe Abbruchtoken an eine beliebige Anzahl von asynchronen und synchronen Vorgängen übergeben.

- Dieselbe Abbruchanforderung kann an eine beliebige Anzahl von Listenern weitergegeben werden.

- Ein Entwickler der asynchronen API hat die vollständige Kontrolle darüber, ob der Abbruch angefordert und wann er wirksam werden kann.

- Im Code, der die API verwendet, kann selektiv bestimmt werden, an welche asynchronen Aufrufe die Abbruchanforderungen weitergegeben werden.

## <a name="monitoring-progress"></a>Überwachen des Status
 Einige asynchrone Methoden machen den Status über eine Statusschnittstelle verfügbar, die an die asynchrone Methode übergeben wird.  Gehen Sie beispielsweise von einer Funktion aus, in der asynchron eine Textzeichenfolge heruntergeladen wird und währenddessen Statusupdates ausgelöst werden, die den Prozentsatz enthalten, bis zu dem der Download jeweils abgeschlossen ist.  Eine solche Methode kann in einer Windows Presentation Foundation-Anwendung (WPF) wie folgt genutzt werden:

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,
            new Progress<int>(p => pbDownloadProgress.Value = p));
    }
    finally { btnDownload.IsEnabled = true; }
}
```

<a name="combinators"></a>
## <a name="using-the-built-in-task-based-combinators"></a>Verwenden der integrierten aufgabenbasierten Kombinatoren
 Der <xref:System.Threading.Tasks>-Namespace enthält mehrere Methoden für das Erstellen von und Arbeiten mit Tasks.

### <a name="taskrun"></a>Task.Run
 Die <xref:System.Threading.Tasks.Task>-Klasse enthält mehrere <xref:System.Threading.Tasks.Task.Run%2A>-Methoden, mit denen Sie problemlos Arbeiten in Form von <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> an den Threadpool auslagern können. Beispiel:

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

 Einige dieser <xref:System.Threading.Tasks.Task.Run%2A>-Methoden wie die <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>-Überladung sind als Kurzform für die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode verfügbar.  Durch andere Überladungen wie <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> können Sie „await“ in der ausgelagerten Arbeit verwenden. Beispiel:

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

 Diese Überladungen sind logisch äquivalent zur Verwendung der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>-Methode in Verbindung mit der Erweiterungsmethode <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> in der Task Parallel Library.

### <a name="taskfromresult"></a>Task.FromResult
 Verwenden Sie die <xref:System.Threading.Tasks.Task.FromResult%2A>-Methode für Szenarien, in denen Daten möglicherweise bereits verfügbar sind und lediglich von einer Methode zurückgegeben werden müssen, die eine Aufgabe zurückgibt und sie in ein <xref:System.Threading.Tasks.Task%601>-Objekt übergibt:

```csharp
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

### <a name="taskwhenall"></a>Task.WhenAll
 Verwenden Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode, um asynchron auf mehrere asynchrone Vorgänge zu warten, die als Tasks dargestellt werden.  Die Methode hat mehrere Überladungen, die einen Satz nicht generischer Aufgaben oder einen nicht einheitlichen Satz generischer Aufgaben unterstützen (z. B. asynchrones Warten auf mehrere Vorgänge, die „void“ zurückgeben, oder asynchrones Warten auf mehrere Methoden mit Wertrückgabe, wobei jeder Wert möglicherweise einen anderen Typ hat) sowie einen einheitlichen Satz generischer Aufgaben unterstützen (z. B. asynchrones Warten auf mehrere Methoden, die `TResult` zurückgeben).

 Angenommen, Sie möchten E-Mail-Nachrichten an mehrere Kunden senden. Sie können die Nachrichten überlappend versenden, damit Sie nicht warten müssen, bis eine Nachricht abgeschlossen ist, bevor Sie die nächste Nachricht senden. Sie können auch ermitteln, wann die Sendevorgänge abgeschlossen sind und ob irgendwelche Fehler aufgetreten sind:

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 Dieser Code behandelt auftretende Ausnahmen nicht explizit, sondern ermöglicht es, Ausnahmen aus dem `await`-Vorgang für die resultierende Aufgabe aus <xref:System.Threading.Tasks.Task.WhenAll%2A> weiterzugeben.  Um Ausnahmen zu behandeln, können Sie Code wie den folgenden verwenden:

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```

 Wenn in diesem Fall ein Fehler bei asynchronen Vorgängen auftritt, werden sämtliche Ausnahmen in einer <xref:System.AggregateException>-Ausnahme konsolidiert, die in der von der <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode zurückgegebenen <xref:System.Threading.Tasks.Task>-Klasse gespeichert wird.  Über das `await`-Schlüsselwort wird jedoch nur eine dieser Ausnahmen weitergegeben.  Wenn Sie alle Ausnahmen auswerten möchten, können Sie den vorherigen Code wie folgt neu schreiben:

```csharp
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

 Betrachten Sie ein weiteres Beispiel für asynchrones Herunterladen mehrerer Dateien aus dem Web.  In diesem Fall haben alle asynchronen Vorgänge homogene Ergebnistypen, und der Zugriff auf die Ergebnisse ist einfach:

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 Sie können die gleichen Verarbeitungstechniken für Ausnahmen verwenden, die im vorherigen Szenario mit „void“-Rückgabe erläutert wurden:

```csharp
Task<string> [] asyncOps =
    (from url in urls select DownloadStringAsync(url)).ToArray();
try
{
    string [] pages = await Task.WhenAll(asyncOps);
    ...
}
catch(Exception exc)
{
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

### <a name="taskwhenany"></a>Task.WhenAny
 Die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode können Sie verwenden, um asynchron auf nur einen von mehreren asynchrone Vorgängen zu warten, die als abzuschließende Tasks dargestellt werden.  Diese Methode ist für vier Hauptanwendungsfälle vorgesehen:

- Redundanz:  Mehrmaliges Ausführen eines Vorgangs und Auswählen desjenigen, der zuerst abgeschlossen wurde (beispielsweise Auswerten mehrerer Aktienkurswebdienste, die ein einzelnes Ergebnis liefern, und Auswählen des Diensts, der am schnellsten abgeschlossen ist).

- Überlappung:  Starten von mehreren Vorgängen und Warten, bis alle abgeschlossen sind, aber Verarbeiten der Vorgänge, sobald sie abgeschlossen sind.

- Einschränkung:  Zulassen, dass weitere Vorgänge gestartet werden, während andere abgeschlossen werden.  Dies ist eine Erweiterung des Szenarios mit Überlappung.

- Vorzeitiger Hashabbruch:  Ein von Task t1 dargestellter Vorgang kann in einem <xref:System.Threading.Tasks.Task.WhenAny%2A>-Task mit einem anderen Task t2 gruppiert werden, und Sie können auf den Task <xref:System.Threading.Tasks.Task.WhenAny%2A> warten. Task t2 könnte ein Timeout, einen Abbruch oder ein anderes Signal darstellen, das bewirkt, dass der <xref:System.Threading.Tasks.Task.WhenAny%2A>-Task abgeschlossen wird, bevor t1 abgeschlossen ist.

#### <a name="redundancy"></a>Redundanz
 Nehmen Sie einen Fall an, in dem Sie entscheiden möchten, ob Sie eine Aktie kaufen.  Ihnen stehen mehrere für Sie vertrauenswürdige Webdienste für Aktienempfehlungen zur Verfügung, jedoch kann jeder dieser Dienste abhängig von der täglichen Last je nach Zeitpunkt recht langsam sein.  Sie können die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um eine Benachrichtigung zu erhalten, wenn ein Vorgang abgeschlossen ist:

```csharp
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol),
    GetBuyRecommendation2Async(symbol),
    GetBuyRecommendation3Async(symbol)
};
Task<bool> recommendation = await Task.WhenAny(recommendations);
if (await recommendation) BuyStock(symbol);
```

 Im Gegensatz zur <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode, mit der die entpackten Ergebnisse aller erfolgreich abgeschlossenen Tasks zurückgegeben werden, gibt <xref:System.Threading.Tasks.Task.WhenAny%2A> den abgeschlossenen Task zurück. Ist eine Aufgabe fehlgeschlagen, ist es wichtig, zu wissen, dass sie fehlgeschlagen ist. Wenn eine Aufgabe erfolgreich, ist es ebenso wichtig, zu wissen, welcher Aufgabe der Rückgabewert zugeordnet ist.  Daher müssen Sie auf das Ergebnis der zurückgegebenen Aufgabe zugreifen oder weiter auf dieses warten, wie dieses Beispiel zeigt.

 Wie bei <xref:System.Threading.Tasks.Task.WhenAll%2A> müssen Sie Ausnahmen berücksichtigen können.  Da Sie die abgeschlossene Aufgabe zurückerhalten, können Sie die zurückgegebene Aufgabe über „await“ veranlassen, Fehler weiterzugeben, und `try/catch` verwenden, um die Fehler entsprechend zu behandeln. Beispiel:

```csharp
Task<bool> [] recommendations = …;
while(recommendations.Count > 0)
{
    Task<bool> recommendation = await Task.WhenAny(recommendations);
    try
    {
        if (await recommendation) BuyStock(symbol);
        break;
    }
    catch(WebException exc)
    {
        recommendations.Remove(recommendation);
    }
}
```

 Auch wenn eine erste Aufgabe erfolgreich abgeschlossen wurde, können in nachfolgenden Aufgaben Fehler auftreten.  An diesem Punkt können Sie zwischen mehreren Optionen zur Behandlung von Ausnahmen wählen:  Sie können warten, bis alle gestarteten Tasks abgeschlossen sind, und in diesem Fall können Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A>-Methode verwenden, oder Sie können entscheiden, dass alle Ausnahmen wichtig sind und protokolliert werden müssen.  Zu diesem Zweck können Sie Fortsetzungen verwenden, um eine Benachrichtigung zu empfangen, wenn Aufgaben asynchron abgeschlossen wurden:

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 oder:

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 oder sogar:

```csharp
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)
{
    foreach(var task in tasks)
    {
        try { await task; }
        catch(Exception exc) { Log(exc); }
    }
}
…
LogCompletionIfFailed(recommendations);
```

 Schließlich sollten Sie alle verbleibenden Vorgänge abbrechen:

```csharp
var cts = new CancellationTokenSource();
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol, cts.Token),
    GetBuyRecommendation2Async(symbol, cts.Token),
    GetBuyRecommendation3Async(symbol, cts.Token)
};

Task<bool> recommendation = await Task.WhenAny(recommendations);
cts.Cancel();
if (await recommendation) BuyStock(symbol);
```

#### <a name="interleaving"></a>Überlappen
 Angenommen, Sie laden Bilder aus dem Web herunter und verarbeiten jedes Bild (beispielsweise Hinzufügen des jeweiligen Bilds zu einem UI-Steuerelement). Sie verarbeiten die Images sequenziell im UI-Thread, möchten die Images aber so zeitgleich wie möglich herunterladen. Außerdem möchten Sie mit dem Hinzufügen der Bilder zur Benutzeroberfläche nicht warten, bis sie alle heruntergeladen sind. Sie möchten sie stattdessen hinzufügen, wenn sie fertig sind.

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

 Sie können auch Überlappung in einem Szenario anwenden, das eine rechenintensive Verarbeitung im <xref:System.Threading.ThreadPool> der heruntergeladenen Bilder bedingt. Beispiel:

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)
         .ContinueWith(t => ConvertImage(t.Result)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

#### <a name="throttling"></a>Einschränkung
 Nehmen Sie das Beispiel für Überlappung mit dem Unterschied, dass der Benutzer so viele Bilder herunterlädt, dass die Downloads eingeschränkt werden müssen. Dazu möchte Sie z. B. so vorgehen, dass nur eine bestimmte Anzahl von Downloads gleichzeitig erfolgen darf. Um dies zu erreichen, können Sie eine Teilmenge der asynchronen Vorgänge starten.  Sobald Vorgänge abgeschlossen sind, können an derer Stelle weitere Vorgänge starten:

```csharp
const int CONCURRENCY_LEVEL = 15;
Uri [] urls = …;
int nextIndex = 0;
var imageTasks = new List<Task<Bitmap>>();
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)
{
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
    nextIndex++;
}

while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch(Exception exc) { Log(exc); }

    if (nextIndex < urls.Length)
    {
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
        nextIndex++;
    }
}
```

#### <a name="early-bailout"></a>Vorzeitiger Abbruch
 Nehmen Sie an, es wird asynchron auf den Abschluss eines Vorgangs gewartet, während gleichzeitig auf die Abbruchanforderung eines Benutzers (der Benutzer hat z. B. auf die Schaltfläche „Abbrechen“ geklickt) reagiert wird. Der folgende Code veranschaulicht dieses Szenario:

```csharp
private CancellationTokenSource m_cts;

public void btnCancel_Click(object sender, EventArgs e)
{
    if (m_cts != null) m_cts.Cancel();
}

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();
    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        if (imageDownload.IsCompleted)
        {
            Bitmap image = await imageDownload;
            panel.AddImage(image);
        }
        else imageDownload.ContinueWith(t => Log(t));
    }
    finally { btnRun.Enabled = true; }
}

private static async Task UntilCompletionOrCancellation(
    Task asyncOp, CancellationToken ct)
{
    var tcs = new TaskCompletionSource<bool>();
    using(ct.Register(() => tcs.TrySetResult(true)))
        await Task.WhenAny(asyncOp, tcs.Task);
    return asyncOp;
}
```

 Mit dieser Implementierung wird die Benutzeroberfläche erneut aktiviert, sobald die Entscheidung für den Abbruch erfolgt ist, aber die zugrundeliegenden asynchronen Vorgänge werden nicht abgebrochen. Eine weitere Alternative ist das Abbrechen der ausstehenden Vorgänge, wenn die Entscheidung für den Abbruch erfolgt ist, aber mit dem erneuten Aktivieren der Benutzeroberfläche zu warten, bis die Vorgänge abgeschlossen sind, möglicherweise weil sie wegen der Abbruchanforderung vorzeitig zu beenden sind:

```csharp
private CancellationTokenSource m_cts;

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();

    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        Bitmap image = await imageDownload;
        panel.AddImage(image);
    }
    catch(OperationCanceledException) {}
    finally { btnRun.Enabled = true; }
}
```

 Ein weiteres Beispiel für einen vorzeitigen Hashabbruch betrifft die Verwendung der <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode in Verbindung mit der <xref:System.Threading.Tasks.Task.Delay%2A>-Methode, wie im nächsten Abschnitt erläutert wird.

### <a name="taskdelay"></a>Task.Delay
 Mit der <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>-Methode können Sie Pausen in die Ausführung einer asynchronen Methode einfügen.  Dies ist für viele Arten von Funktionalität nützlich, z. B. für das Erstellen von Abrufschleifen und das Verzögern der Behandlung von Benutzereingaben für einen vordefinierten Zeitraum.  Die <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>-Methode kann in Kombination mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> zudem nützlich sein, um Timeouts bei Wartevorgängen zu implementieren.

 Dauert das Abschließen einer Aufgabe, die Teil eines größeren asynchronen Vorgangs (z. B. eines ASP.NET-Webdiensts) ist, zu lange, kann der Gesamtvorgang beeinträchtigt werden, insbesondere wenn die Aufgabe niemals abgeschlossen wird.  Darum ist es wichtig, das Warten auf einen asynchronen Vorgang bei Timeouts (Zeitüberschreitungen) beenden zu können.  Die synchronen Methoden <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> akzeptieren Timeoutwerte, nicht aber die entsprechenden <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>- und die zuvor erwähnten <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>-Methoden.  Stattdessen können Sie <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in Kombination verwenden, um ein Timeout zu implementieren.

 Nehmen Sie beispielsweise an, Sie möchten in der UI-Anwendung ein Bild herunterladen und die Benutzeroberfläche deaktivieren, während das Bild heruntergeladen wird. Wenn der Download jedoch zu lange dauert, möchten Sie die Benutzeroberfläche wieder aktivieren und den Download verwerfen:

```csharp
public async void btnDownload_Click(object sender, EventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap> download = GetBitmapAsync(url);
        if (download == await Task.WhenAny(download, Task.Delay(3000)))
        {
            Bitmap bmp = await download;
            pictureBox.Image = bmp;
            status.Text = "Downloaded";
        }
        else
        {
            pictureBox.Image = null;
            status.Text = "Timed out";
            var ignored = download.ContinueWith(
                t => Trace("Task finally completed"));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

 Dasselbe gilt auch für mehrere Downloads, da <xref:System.Threading.Tasks.Task.WhenAll%2A> einen Task zurückgibt:

```csharp
public async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap[]> downloads =
            Task.WhenAll(from url in urls select GetBitmapAsync(url));
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))
        {
            foreach(var bmp in downloads) panel.AddImage(bmp);
            status.Text = "Downloaded";
        }
        else
        {
            status.Text = "Timed out";
            downloads.ContinueWith(t => Log(t));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

## <a name="building-task-based-combinators"></a>Erstellen von aufgabenbasierten Kombinatoren
 Da eine Aufgabe in der Lage ist, einen asynchronen Vorgang vollständig darzustellen und synchrone sowie asynchrone Funktionalitäten zum Verknüpfen mit dem Vorgang bereitzustellen, dessen Ergebnisse abzurufen usw., lassen sich nützliche Bibliotheken von Kombinatoren erstellen, mit denen Aufgaben zu größeren Mustern kombiniert werden.  Wie im vorherigen Abschnitt erläutert, enthält .NET Framework verschiedene integrierte Kombinatoren. Sie können aber auch eigene Kombinatoren erstellen. Die folgenden Abschnitte enthalten einige Beispiele möglicher Kombinatormethoden und - typen.

### <a name="retryonfault"></a>RetryOnFault
 In vielen Situationen möchten Sie wahrscheinlich einen Vorgang erneut versuchen, wenn ein vorheriger Versuch fehlgeschlagen ist.  Bei synchronem Code können Sie eine Hilfsmethode verwenden, etwa `RetryOnFault` im folgenden Beispiel, um dies zu erreichen:

```csharp
public static T RetryOnFault<T>(
    Func<T> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return function(); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 Eine fast identische Hilfsmethode können Sie für asynchrone Vorgänge erstellen, die mit TAP implementiert sind und daher Aufgaben zurückgeben:

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 Sie können diesen Kombinator dann verwenden, um Wiederholungen in der Logik der Anwendung zu codieren. Beispiel:

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 Sie könnten die `RetryOnFault`-Funktion zusätzlich erweitern. Beispielsweise könnte die Funktion eine weitere `Func<Task>` akzeptieren, die zwischen Wiederholungen aufgerufen wird, um zu bestimmen, wann der Vorgang erneut versucht werden soll. Beispiel:

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
        await retryWhen().ConfigureAwait(false);
    }
    return default(T);
}
```

 Sie könnten die Funktion dann wie folgt verwenden, damit eine Sekunde gewartet wird, bevor der Vorgang erneut versucht wird:

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a>NeedOnlyOne
 Gelegentlich können Sie Redundanz verwenden, um die Latenz eines Vorgangs und die Erfolgschancen zu verbessern.  Betrachten Sie mehrere Webdienste, die Aktienkurse bereitstellen, aber zu unterschiedlichen Uhrzeiten kann jeder Dienst unterschiedliche Qualität und Reaktionszeiten bieten.  Um mit diesen Abweichungen umzugehen, können Sie Anforderungen an alle Webdienste senden, und sobald Sie eine Antwort von einem Dienst erhalten haben, die verbleibenden Anforderungen abbrechen.  Sie können eine Hilfsfunktion implementieren, um die Implementierung dieses allgemeinen Musters zu vereinfachen, bei dem mehrere Vorgänge gestartet werden, gewartet wird, bis einer abgeschlossen ist, und dann die restlichen Vorgänge abgebrochen werden. Die `NeedOnlyOne`-Funktion im folgenden Beispiel veranschaulicht dieses Szenario:

```csharp
public static async Task<T> NeedOnlyOne(
    params Func<CancellationToken,Task<T>> [] functions)
{
    var cts = new CancellationTokenSource();
    var tasks = (from function in functions
                 select function(cts.Token)).ToArray();
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);
    cts.Cancel();
    foreach(var task in tasks)
    {
        var ignored = task.ContinueWith(
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);
    }
    return completed;
}
```

 Sie können diese Funktion dann wie folgt verwenden:

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a>Überlappende Vorgänge
 Wenn Sie mit großen Taskgruppen arbeiten und die <xref:System.Threading.Tasks.Task.WhenAny%2A>-Methode verwenden, um ein Überlappungsszenario zu unterstützen, kann ein Leistungsproblem auftreten. Jeder Aufruf von <xref:System.Threading.Tasks.Task.WhenAny%2A> führt dazu, dass mit jedem Task eine Fortsetzung registriert wird. Für N als Anzahl von Aufgaben führt dieses zu O(N<sup>2</sup>) Fortsetzungen, die über die Lebensdauer des überlappenden Vorgangs erstellt werden. Wenn Sie mit einer großen Menge von Aufgaben arbeiten, können Sie einen Combinator (im folgenden Beispiel `Interleaved`) verwenden, um das Leistungsproblem zu beheben:

```csharp
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)
{
    var inputTasks = tasks.ToList();
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)
                   select new TaskCompletionSource<T>()).ToList();
    int nextTaskIndex = -1;
    foreach (var inputTask in inputTasks)
    {
        inputTask.ContinueWith(completed =>
        {
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];
            if (completed.IsFaulted)
                source.TrySetException(completed.Exception.InnerExceptions);
            else if (completed.IsCanceled)
                source.TrySetCanceled();
            else
                source.TrySetResult(completed.Result);
        }, CancellationToken.None,
           TaskContinuationOptions.ExecuteSynchronously,
           TaskScheduler.Default);
    }
    return from source in sources
           select source.Task;
}
```

 Diesen Kombinator können Sie dann verwenden, um die Ergebnisse von Aufgaben zu verarbeiten, nachdem sie abgeschlossen sind. Beispiel:

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a>WhenAllOrFirstException
 In bestimmten Scatter-Gather-Szenarien möchten Sie möglicherweise auf alle Aufgaben in einem Satz warten, es sei denn, bei einer dieser Aufgaben tritt ein Fehler auf. In diesem Fall soll das Warten beendet werden, sobald die Ausnahme auftritt.  Sie können das mit einer Kombinatormethode erreichen, etwa `WhenAllOrFirstException` im folgenden Beispiel:

```csharp
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)
{
    var inputs = tasks.ToList();
    var ce = new CountdownEvent(inputs.Count);
    var tcs = new TaskCompletionSource<T[]>();

    Action<Task> onCompleted = (Task completed) =>
    {
        if (completed.IsFaulted)
            tcs.TrySetException(completed.Exception.InnerExceptions);
        if (ce.Signal() && !tcs.Task.IsCompleted)
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());
    };

    foreach (var t in inputs) t.ContinueWith(onCompleted);
    return tcs.Task;
}
```

## <a name="building-task-based-data-structures"></a>Erstellen von aufgabenbasierten Datenstrukturen
 Zusätzlich zur Möglichkeit, benutzerdefinierte taskbasierte Kombinatoren zu erstellen, ist eine Datenstruktur, die in <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> verwendet wird und sowohl die Ergebnisse eines asynchronen Vorgangs als auch die erforderliche mit dem Vorgang zu verknüpfende Synchronisierung darstellt, ein leistungsstarker Typ. Aus diesem können benutzerdefinierte Datenstrukturen erstellt werden, die für den Einsatz in asynchronen Szenarios bestimmt sind.

### <a name="asynccache"></a>AsyncCache
 Ein wichtiger Aspekt eines Tasks besteht darin, dass dieser an mehrere Consumer ausgegeben werden kann, die u.a. alle auf diesen warten, Fortsetzungen bei diesem registrieren und dessen Ergebnis oder dessen Ausnahmen abrufen können (im Fall von <xref:System.Threading.Tasks.Task%601>).  Aufgrund dessen sind <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> ideal für die Verwendung in einer asynchronen Cachinginfrastruktur geeignet.  Im folgenden Beispiel wird ein kleiner, aber leistungsstarker asynchroner Cache gezeigt, der auf <xref:System.Threading.Tasks.Task%601> basiert:

```csharp
public class AsyncCache<TKey, TValue>
{
    private readonly Func<TKey, Task<TValue>> _valueFactory;
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;

    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)
    {
        if (valueFactory == null) throw new ArgumentNullException("loader");
        _valueFactory = valueFactory;
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();
    }

    public Task<TValue> this[TKey key]
    {
        get
        {
            if (key == null) throw new ArgumentNullException("key");
            return _map.GetOrAdd(key, toAdd =>
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;
        }
    }
}
```

 Die [AsyncCache\<TKey,TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/)-Klasse akzeptiert als Delegaten für ihren Konstruktor eine Funktion, die `TKey` übernimmt und <xref:System.Threading.Tasks.Task%601> zurückgibt.  Alle Werte aus dem Cache, auf die zuvor zugegriffen wurde, werden im internen Wörterbuch gespeichert, und `AsyncCache` stellt sicher, dass nur eine Aufgabe pro Schlüssel generiert wird, selbst wenn gleichzeitig auf den Cache zugegriffen wird.

 Sie können z. B. einen Cache für heruntergeladene Webseiten erstellen:

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 Anschließend können Sie diesen Cache in asynchronen Methoden verwenden, wenn Sie den Inhalt einer Webseite benötigen. Die `AsyncCache`-Klasse stellt sicher, dass so wenig Seiten wie möglich heruntergeladen werden, und speichert die Ergebnisse zwischen.

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtContents.Text = await m_webPages["https://www.microsoft.com"];
    }
    finally { btnDownload.IsEnabled = true; }
}
```

### <a name="asyncproducerconsumercollection"></a>AsyncProducerConsumerCollection
 Sie können Aufgaben auch verwenden, um Datenstrukturen für das Koordinieren von asynchronen Aktivitäten zu erstellen.  Betrachten Sie eines der klassischen parallelen Entwurfsmuster: Producer/Consumer.  In diesem Muster generieren Producer Daten, die von Consumern verwendet werden, und die Producer und Consumer können parallel ausgeführt werden. Beispielsweise verarbeitet der Consumer Element 1, das zuvor von einem Producer generiert wurde, der jetzt Element 2 erzeugt.  Für das Producer/Consumer-Muster benötigen Sie immer eine Datenstruktur, um die Arbeit zu speichern, die von Producern erzeugt wurde, damit die Consumer über neue Daten benachrichtigt werden und diese finden können, wenn sie verfügbar sind.

 Es folgt eine einfache Datenstruktur, die auf Aufgaben aufsetzt und es für asynchrone Methoden ermöglicht, als Producer und Consumer verwendet zu werden:

```csharp
public class AsyncProducerConsumerCollection<T>
{
    private readonly Queue<T> m_collection = new Queue<T>();
    private readonly Queue<TaskCompletionSource<T>> m_waiting =
        new Queue<TaskCompletionSource<T>>();

    public void Add(T item)
    {
        TaskCompletionSource<T> tcs = null;
        lock (m_collection)
        {
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();
            else m_collection.Enqueue(item);
        }
        if (tcs != null) tcs.TrySetResult(item);
    }

    public Task<T> Take()
    {
        lock (m_collection)
        {
            if (m_collection.Count > 0)
            {
                return Task.FromResult(m_collection.Dequeue());
            }
            else
            {
                var tcs = new TaskCompletionSource<T>();
                m_waiting.Enqueue(tcs);
                return tcs.Task;
            }
        }
    }
}
```

 Wenn diese Datenstruktur vorhanden ist, können Sie Code schreiben, der wie der folgende Code aussieht:

```csharp
private static AsyncProducerConsumerCollection<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.Take();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Add(data);
}
```

Der Namespace <xref:System.Threading.Tasks.Dataflow> enthält den Typ <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, den Sie auf ähnliche Weise verwenden können, bei dem Sie jedoch keinen benutzerdefinierten Auflistungstyp erstellen müssen:

```csharp
private static BufferBlock<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.ReceiveAsync();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Post(data);
}
```

> [!NOTE]
> Der Namespace <xref:System.Threading.Tasks.Dataflow> ist in .NET Framework 4.5 über **NuGet** verfügbar. Zum Installieren der Assembly, die den <xref:System.Threading.Tasks.Dataflow>-Namespace enthält, öffnen Sie Ihr Projekt in Visual Studio, wählen **NuGet-Pakete verwalten** aus dem Menü „Projekt“ und suchen anschließend online nach dem Microsoft.Tpl.Dataflow-Paket.

## <a name="see-also"></a>Siehe auch

- [Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](task-based-asynchronous-pattern-tap.md)
- [Implementieren des aufgabenbasierten asynchronen Entwurfsmusters](implementing-the-task-based-asynchronous-pattern.md)
- [Interoperabilität mit anderen asynchronen Mustern und Typen](interop-with-other-asynchronous-patterns-and-types.md)
