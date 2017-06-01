---
title: "Consuming the Task-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, and TAP"
  - "asynchronous design patterns, .NET Framework"
  - "TAP, .NET Framework support for"
  - "Task-based Asynchronous Pattern, .NET Framework support for"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Consuming the Task-based Asynchronous Pattern
Wenn Sie das aufgabenbasierte asynchrone Muster \(TAP\) verwenden, um mit asynchronen Operationen zu arbeiten, können Sie Rückrufe verwenden, um ohne Blockierung eine Verzögerung zu erreichen.  Bei Aufgaben wird dies mit Methoden, z. B. <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=fullName>, erreicht.  Sprachbasierte Unterstützung asynchroner Vorgänge verbirgt Rückrufe, indem in der normalen Ablaufsteuerung auf asynchrone Vorgänge gewartet werden darf, und der vom Compiler generierte Code für die gleiche Unterstützung auf API\-Ebene bereitstellt.  
  
## Anhalten der Ausführung mit "Await"  
 Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], können Sie das [await](../Topic/await%20\(C%23%20Reference\).md)\-Schlüsselwort in C\# und [Await Operator](../Topic/Await%20Operator%20\(Visual%20Basic\).md) in Visual Basic verwenden, um <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601>\-Objekte asynchron zu erwarten.  Wenn Sie <xref:System.Threading.Tasks.Task> erwarten, ist der `await` Ausdruck vom Typ `void`.  Wenn Sie <xref:System.Threading.Tasks.Task%601> erwarten, ist der `await` Ausdruck vom Typ `TResult`.  Ein `await`\-Ausdruck muss im Text einer asynchronen Methode auftreten.  Weitere Informationen über die Unterstützung von C\# und Visual Basic in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] finden Sie in den Spezifikationen von C\# bzw. Visual Basic.  
  
 Die Wartefunktion installiert im Hintergrund einen Rückruf für die Aufgabe über eine Fortsetzung.  Mit diesem Rückruf wird die asynchrone Methode ab dem Zeitpunkt der Unterbrechung fortgesetzt.  Wenn die asynchrone Methode fortgesetzt wird und der Vorgang, auf den gewartet wurde, ein <xref:System.Threading.Tasks.Task%601> war und erfolgreich abgeschlossen wurde, wird sein `TResult` zurückgegeben.  Wenn der <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>, auf den gewartet wurde, im Zustand <xref:System.Threading.Tasks.TaskStatus> beendet wurde, wird eine <xref:System.OperationCanceledException>\-Ausnahme ausgelöst.  Wenn der <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>, auf den gewartet wurde, im Zustand <xref:System.Threading.Tasks.TaskStatus> beendet wurde, wird die Ausnahme ausgelöst, die den Fehler verursacht hat.  Eine `Task` kann infolge mehrerer Ausnahmen einen Fehler verursachen, aber nur eine dieser Ausnahmen wird weitergegeben.  Die <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName>\-Eigenschaft gibt jedoch eine Ausnahme <xref:System.AggregateException> zurück, die alle Fehler enthält.  
  
 Wenn ein Synchronisierungskontext \(<xref:System.Threading.SynchronizationContext>\-Objekt\) dem Thread zugeordnet ist, der die asynchrone Methode zum Zeitpunkt der Unterbrechung ausgeführt hat \(beispielsweise, wenn die Eigenschaft <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=fullName> nicht gleich `null` ist\), wird die asynchrone Methode auf diesem gleichen Synchronisierungskontext fortgesetzt, indem sie die <xref:System.Threading.SynchronizationContext.Post%2A>\-Methode des Kontexts verwendet.  Andernfalls verwendet sie den Taskplaner \(<xref:System.Threading.Tasks.TaskScheduler>\-Objekt\), der zum Zeitpunkt der Unterbrechung aktuell war.  In der Regel ist dies der standardmäßige Taskplaner \(<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=fullName>\), der auf den Threadpool abzielt.  Dieser Taskplaner bestimmt, ob der erwartete asynchrone Vorgang fortgesetzt werden soll, wo er abgeschlossen wurde, oder ob die Wiederaufnahme geplant werden soll.  Der Standardplaner lässt i. d. R. die Fortsetzung in dem Thread zu, in dem der Vorgang, auf den gewartet wurde, abgeschlossen wurde.  
  
 Beim Aufruf einer asynchronen Methode führt diese synchron den Text der Funktion bis zum ersten await\-Ausdruck für eine awaitable\-Instanz aus, die noch nicht abgeschlossen ist. An diesem Punkt kehrt der Aufruf zum Aufrufer zurück.  Wenn die asynchrone Methode nicht `void` zurückgibt, wird ein <xref:System.Threading.Tasks.Task>\- oder <xref:System.Threading.Tasks.Task%601>\-Objekt zurückgegeben, um die aktuelle Berechnung darzustellen.  Wenn in einer asynchronen Methode, die nicht void ist, eine return\-Anweisung auftritt oder wenn das Ende des Methodentexts erreicht wird, wird die Aufgabe im Endzustand <xref:System.Threading.Tasks.TaskStatus> abgeschlossen.  Wenn ein Ausnahmefehler das Steuerelement veranlasst, den Text der asynchronen Methode zu verlassen, endet die Aufgabe im Zustand <xref:System.Threading.Tasks.TaskStatus>.  Wenn diese Ausnahme eine <xref:System.OperationCanceledException> ist, endet die Aufgabe stattdessen im Zustand <xref:System.Threading.Tasks.TaskStatus>.  Auf diese Weise wird schließlich das Ergebnis oder die Ausnahme veröffentlicht.  
  
 Es gibt einige wichtige Variationen dieses Verhaltens.  Wenn eine Aufgabe zu dem Zeitpunkt, zu dem sie erwartet wurde, bereits abgeschlossen ist, wird die Steuerung nicht abgegeben, sondern die Ausführung der Funktion wird aus Leistungsgründen fortgesetzt.  Außerdem ist die Rückgabe an den ursprünglichen Kontext nicht immer das gewünschte Verhalten und kann geändert werden; dies wird im nächsten Abschnitt genauer beschrieben.  
  
### Konfigurieren der Unterbrechung und Wiederaufnahme mit Yield und ConfigureAwait  
 Einige Methoden bieten eine umfassendere Steuerung der Ausführung einer asynchronen Methode.  Beispielsweise können Sie die <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=fullName>\-Methode verwenden, um einen Übergabepunkt in die asynchrone Methode einzuführen:  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
  
```  
  
 Dies entspricht dem asynchronen Senden oder Planen in dem aktuellen Kontext.  
  
```csharp  
Task.Run(async  delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
  
```  
  
 Sie können auch die <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName>\-Methode verwenden, um bei einer asynchronen Methode eine bessere Kontrolle über Unterbrechung und Wiederaufnahme zu haben.  Wie standardmäßig den aktuellen Kontext zuvor erwähnt wird aufgezeichnet, als Unterbrechung einer asynchronen Methode wird, und dieser erfasste Kontext wird verwendet, um die Fortsetzung der asynchronen Methode nach Wiederaufnahme aufzurufen.  In vielen Fällen ist genau dies das gewünschte Verhalten.  In anderen Fällen interessieren Sie sich möglicherweise nicht für den Fortsetzungskontext und Sie können eine bessere Leistung erzielen, indem Sie solche Beiträge, die zurück auf den ursprünglichen Kontext verweisen, vermeiden.  Zu diesem Zweck kann mithilfe von <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=fullName> der Wartevorgang angewiesen werden, nicht den Kontext zu erfassen und diesen fortzusetzen, sondern die Ausführung dort fortzusetzen, wo der asynchrone Vorgang, auf den gewartet wird, abgeschlossen wurde:  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
  
```  
  
## Abbrechen eines asynchronen Vorgangs  
 Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellen TAP\-Methoden, die den Abbruch unterstützen, mindestens eine Überladung bereit, die ein Abbruchtoken akzeptiert \(<xref:System.Threading.CancellationToken>\-Objekt\).  
  
 Ein Abbruchtoken wird von einer Abbruchtokenquelle erstellt \(<xref:System.Threading.CancellationTokenSource>\-Objekt\).  Die <xref:System.Threading.CancellationTokenSource.Token%2A>\-Eigenschaft der Quelle gibt das Abbruchstoken zurück, das signalisiert wird, wenn die <xref:System.Threading.CancellationTokenSource.Cancel%2A>\-Methode der Quelle aufgerufen wird.  Wenn Sie beispielsweise eine einzelne Webseite herunterladen möchten und Sie möchten in der Lage sein, die Operation abzubrechen, erstellen Sie ein <xref:System.Threading.CancellationTokenSource>\-Objekt, übergeben Sie dessen Token an die TAP\-Methode und rufen Sie dann die <xref:System.Threading.CancellationTokenSource.Cancel%2A>\- Methode der Quelle auf, sobald Sie bereit sind, den Vorgang abzubrechen:  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
  
```  
  
 Um mehrere asynchrone Aufrufe abzubrechen, kann an alle Aufrufe das gleiche Token übergeben werden:  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
  
```  
  
 Oder Sie können das gleiche Token zu einer selektiven Teilmenge von Vorgängen übergeben:  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
  
```  
  
 Abbruchanforderungen können in jedem Thread initiiert werden.  
  
 Sie können den Wert <xref:System.Threading.CancellationToken.None%2A?displayProperty=fullName> an jede Methode übergeben, die ein Abbruchtoken akzeptiert, um anzugeben, dass der Abbruch nie angefordert wird.  Dadurch gibt die <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=fullName>\-Eigenschaft `false` zurück, und die aufgerufene Methode kann entsprechend optimieren.  Zu Testzwecken kann auch ein vorab abgebrochenes Abbruchstoken übergeben, das mit dem Konstruktor instanziiert wurde, der einen booleschen Wert akzeptiert, um anzugeben, ob das Token in einem bereits abgebrochenen oder in einem nicht abbrechbaren Zustand beginnen soll.  
  
 Dieser Ansatz zum Abbruch hat mehrere Vorteile:  
  
-   Sie können das gleiche Abbruchtoken an eine beliebige Anzahl von asynchronen und synchronen Vorgängen übergeben.  
  
-   Die gleiche Abbruchanforderung kann an eine beliebige Anzahl von Listenern weitergegeben werden.  
  
-   Der Entwickler des asynchronen APIs besitzt die völlige Kontrolle darüber, ob der Abbruch möglicherweise angefordert wird und wann er wirksam werden könnte.  
  
-   Der Code, der die API verwendet, kann die asynchronen Aufrufe, an die Abbruchanforderungen weitergegeben werden, selektiv bestimmen.  
  
## Überwachen des Status  
 Einige asynchrone Methoden machen den Status über eine Statusschnittstelle verfügbar, die an die asynchrone Methode übergeben wird.  Betrachten Sie beispielsweise eine Funktion, die asynchron eine Textzeichenfolge herunterlädt und währenddessen Statusupdates auslöst, die den Prozentsatz des bisher abgeschlossenen Downloads enthalten.  Eine solche Methode kann in einer Windows Presentation Foundation\-Anwendung \(WPF\) wie folgt genutzt werden:  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)    
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
## Verwenden der integrierten aufgabenbasierten Kombinatoren  
 Der <xref:System.Threading.Tasks>\-Namespace enthält mehrere Methoden für das Arbeiten mit Aufgaben und das Erstellen von Aufgaben.  
  
### Task.Run  
 Die <xref:System.Threading.Tasks.Task>\-Klasse enthält mehrere <xref:System.Threading.Tasks.Task.Run%2A>\-Methoden, die Sie leicht Arbeit als <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> an den Threadpool verteilen lassen, beispielsweise:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
  
```  
  
 Einige dieser <xref:System.Threading.Tasks.Task.Run%2A>\-Methoden, z. B. die <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName>\-Überladung, sind eine Kurzform der <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName>\-Methode.  Andere Überladungen jedoch, z. B. <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=fullName>, ermöglichen die Verwendung von await in der ausgelagerten Arbeit. Beispiel:  
  
```csharp  
public async  void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 Diese Überladungen sind mit der Verwendung der the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=fullName>\-Methode in Verbindung mit der <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>\-Erweiterungsmethode in der Task Parallel Library logisch äquivalent.  
  
### Task.FromResult  
 Verwenden Sie die <xref:System.Threading.Tasks.Task.FromResult%2A>\-Methode für Szenarien, in denen Daten möglicherweise bereits verfügbar sind und lediglich von einer Methode zurückgegeben werden müssen, die eine in einen <xref:System.Threading.Tasks.Task%601> umgewandelte Aufgabe zurückgibt.  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async  Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
  
```  
  
### Task.WhenAll  
 Verwenden Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A>\-Methode, um asynchron auf mehrere asynchrone Vorgänge zu warten, die als Aufgaben dargestellt werden.  Die Methode verfügt über mehrere Überladungen, die einen Satz nicht generischer Aufgaben oder einen nicht einheitlichen Satz generischer Aufgaben unterstützen \(z. B. asynchrones Warten auf mehrere Vorgänge, die void zurückgeben, oder asynchrones Warten auf mehrere einen Wert zurückgebende Methoden, wobei jeder Wert möglicherweise von einem anderen Typ ist\) sowie um einen einheitlichen Satz generischer Aufgaben zu unterstützen \(z. B. asynchrones Warten auf mehrere Methoden, die `TResult` zurückgeben\).  
  
 Wenn Sie beispielsweise E\-Mail\-Nachrichten an einigen Kunden senden möchten.  Sie können die Nachrichten überlappend versenden, damit Sie mit dem Senden einer Nachricht nicht warten müssen, bis die vorherige Sendung abgeschlossen ist.  Sie können auch herausfinden, wann die Sendevorgänge abgeschlossen sind und ob irgendwelche Fehler aufgetreten sind:  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
  
```  
  
 Dieser Code behandelt auftretende Ausnahmen nicht explizit. Stattdessen können Ausnahmen mit dem `await`\-Schlüsselwort in der aus <xref:System.Threading.Tasks.Task.WhenAll%2A> resultierenden Aufgabe weitergegeben werden.  Um die Ausnahmen zu behandeln, können Sie Code wie den Folgenden verwenden:  
  
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
  
 Schlägt in diesem Fall ein asynchroner Vorgang fehlt, werden alle Ausnahmen in einer <xref:System.AggregateException>\-Ausnahme konsolidiert, die im <xref:System.Threading.Tasks.Task> gespeichert wird, das von der <xref:System.Threading.Tasks.Task.WhenAll%2A>\-Methode zurückgegeben wird.  Mit dem `await`\-Schlüsselwort wird jedoch nur eine dieser Ausnahmen weitergegeben.  Wenn Sie alle Ausnahmen überprüfen möchten, können Sie den vorherigen Code wie folgt neu schreiben:  
  
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
  
 Betrachten Sie ein weiteres Beispiel für das asynchrone Herunterladen mehrerer Dateien aus dem Web.  In diesem Fall weisen alle asynchronen Vorgänge homogene Ergebnistypen auf, und der Zugriff auf die Ergebnisse ist einfach:  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 Sie können die gleichen Handhabungstechniken verwenden, die im vorherigen Szenario zur Rückgabe von Void erläutert wurde:  
  
```csharp  
Task [] asyncOps =   
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
  
### Task.WhenAny  
 Die <xref:System.Threading.Tasks.Task.WhenAny%2A>\-Methode wird verwendet, um asynchron auf mehrere asynchrone Vorgänge zu warten, die als abzuschließende Aufgaben dargestellt werden.  Diese Methode dient vier Hauptnutzungsfällen:  
  
-   Redundanz: Mehrmaliges Ausführen eines Vorgangs und Auswählen, der zuerst abgeschlossen wurde \(beispielsweise, Kontaktaufnahme mit mehreren Aktienkurswebdiensten, die alle ein einzelnes Ergebnis liefern, und Auswählen des am schnellsten das abgeschlossen ist\).  
  
-   Überlappung: Starten von mehreren Vorgängen und Warten auf, die alle abgeschlossen werden müssen, doch Verarbeiten der Vorgänge, sobald sie abgeschlossen sind.  
  
-   Einschränkung: Dürfend schließen zusätzliche Vorgänge als andere starten ab.  Dies ist eine Erweiterung des Szenarios mit Überlappung.  
  
-   Vorzeitiger Abbruch: Beispielsweise kann ein Vorgang, der von Aufgabe t1 dargestellt wird, in einer <xref:System.Threading.Tasks.Task.WhenAny%2A> \- Aufgabe mit einer anderen Aufgabe t2 gruppiert werden, und auf die Aufgabe warten. <xref:System.Threading.Tasks.Task.WhenAny%2A> Aufgabe t2 kann ein Timeout, einen Abbruch oder ein anderes Signal darstellen, das bewirkt, dass die <xref:System.Threading.Tasks.Task.WhenAny%2A>\-Aufgabe abgeschlossen wird, bevor t1 abgeschlossen ist.  
  
#### Redundanz  
 Nehmen wir einmal an, Sie möchten entscheiden, ob Sie eine Aktie kaufen.  Ihnen stehen mehrere vertrauenswürdige Webdienste für Aktienempfehlungen zur Verfügung, jedoch kann jeder dieser Dienste abhängig von der täglichen Last je nach Zeitpunkt recht langsam sein.  Sie können die <xref:System.Threading.Tasks.Task.WhenAny%2A>\-Methode verwenden, um eine Benachrichtigung zu erhalten, wenn ein Vorgang abgeschlossen ist:  
  
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
  
 Anders als bei <xref:System.Threading.Tasks.Task.WhenAll%2A>, das die Ergebnisse aller erfolgreich abgeschlossenen Aufgaben ohne Details zurückgibt, gibt <xref:System.Threading.Tasks.Task.WhenAny%2A> die Aufgabe zurück, die abgeschlossen wurde.  Wenn bei einer Aufgabe ein Fehler auftritt, ist es wichtig, zu wissen, dass der Fehler aufgetreten ist, und wenn eine Aufgabe folgt, ist es wichtig, zu wissen, welcher Aufgabe der Rückgabewert zugeordnet ist.  Daher müssen Sie auf das Ergebnis der zurückgegebenen Aufgabe zugreifen oder weiter erwarten sie, wie dieses Beispiel zeigt.  
  
 Wie bei <xref:System.Threading.Tasks.Task.WhenAll%2A> müssen Ausnahmen behandelt werden können.  Da Sie die abgeschlossene Aufgabe zurückerhalten haben, kann auf die zurückgegebene Aufgabe gewartet werden, damit Fehler weitergegeben und mit `try/catch` entsprechend behandelt werden, wie im folgenden Beispiel:  
  
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
  
 Auch wenn eine erste Aufgabe erfolgreich abgeschlossen wurde, können nachfolgende Aufgaben zu einem Fehler führen.  An diesem Punkt haben Sie mehrere Möglichkeiten zur Handhabung von Ausnahmen: Sie können warten, bis alle gestarteten Aufgaben abgeschlossen haben, in diesem Fall Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A>\-Methode verwenden oder Sie können entscheiden, dass alle Ausnahmen wichtig sind und protokolliert werden müssen.  Zu diesem Zweck können Fortsetzungen direkt genutzt werden, um eine Benachrichtigung zu empfangen, wenn Aufgaben asynchron abgeschlossen wurden:  
  
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
  
```  
private static async  void LogCompletionIfFailed(IEnumerable<Task> tasks)  
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
  
#### Überlappen  
 Angenommen, Sie laden Bilder aus dem Web herunter und verarbeiten jedes Bild \(beispielsweise indem Sie das Bild einem UI\-Steuerelement hinzufügen\).  Sie müssen die Verarbeitung auf dem UI\-Thread sequenziell ausführen, aber Sie sollten die Bilder so zeitgleich wie möglich herunterladen.  Außerdem sollten Sie mit dem Hinzufügen der Bilder zu der Benutzeroberfläche nicht warten, bis alle heruntergeladen sind, sondern die Bilder hinzufügen, sobald sie abgeschlossen sind:  
  
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
  
 Sie können auch eine Überlappung bei einem Szenario anwenden, das eine rechenintensive Verarbeitung auf <xref:System.Threading.ThreadPool> der heruntergeladenen Bilder einschließt; beispielsweise:  
  
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
  
#### Einschränkung  
 Betrachten Sie das Beispiel für Überlappung, mit dem Unterschied, dass der Benutzer so viele Bilder herunterlädt, dass die Downloads eingeschränkt werden müssen, indem z. B. nur eine bestimmte Anzahl von Downloads gleichzeitig erfolgen dürfen.  Zu diesem Zweck kann eine Teilmenge der asynchronen Vorgänge begonnen werden.  Wenn Vorgänge abgeschlossen sind, können an ihrer Stelle weitere Vorgänge begonnen werden.  
  
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
  
#### Vorzeitiger Abbruch  
 Angenommen, es wird asynchron auf den Abschluss eines Vorgangs gewartet, während gleichzeitig auf die Abbruchanforderung eines Benutzers \(z. B. der Benutzer hat auf die Schaltfläche Abbrechen geklickt\) reagiert werden kann.  Der folgende Code veranschaulicht dieses Szenario:  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async  void btnRun_Click(object sender, EventArgs e)  
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
  
private static async  Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
  
```  
  
 Mit dieser Implementierung wird die Benutzeroberfläche erneut aktiviert, sobald die Entscheidung für den Abbruch erfolgt, jedoch ohne die zugrunde liegenden asynchronen Vorgänge abzubrechen.  Eine Alternative ist das Abbrechen der ausstehenden Vorgänge, wenn die Entscheidung für den Abbruch erfolgt, die Benutzeroberfläche jedoch erst wieder zu aktivieren, wenn die Vorgänge tatsächlich abgeschlossen sind, möglicherweise weil sie aufgrund der Abbruchanforderung vorzeitig beendet werden:  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async  void btnRun_Click(object sender, EventArgs e)  
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
  
 Ein weiteres Beispiel eines frühen Abbruchs umfasst die <xref:System.Threading.Tasks.Task.WhenAny%2A>\-Methode in Verbindung mit der <xref:System.Threading.Tasks.Task.Delay%2A>\-Methode. Dies wird im nächsten Abschnitt erläutert.  
  
### Task.Delay  
 Wie weiter oben gezeigt, können mit der <xref:System.Threading.Tasks.Task.Delay%2A>\-Methode Pausen in die Ausführung einer asynchronen Methode eingefügt werden.  Dies ist für viele Arten von Funktionen hilfreich, z. B. für das Erstellen von Abrufschleifen und das Verzögern der Behandlung von Benutzereingaben für einen vordefinierten Zeitraum.  Die <xref:System.Threading.Tasks.Task.Delay%2A>\-Methode kann auch in Verbindung mit <xref:System.Threading.Tasks.Task.WhenAny%2A> hilfreich sein, um Timeouts für Wartevorgänge zu implementieren.  
  
 Wenn der Abschluss einer Aufgabe, die Teil eines größeren asynchronen Vorgangs \(z. B. eines ASP.NET\-Webdiensts\) ist, zu lange dauert, kann dies den größeren Vorgang beeinträchtigen, insbesondere wenn der Vorgang niemals abgeschlossen wird.  Darum ist es wichtig, das Warten auf einen asynchronen Vorgang bei Zeitüberschreitung beenden zu können.  Die synchronen Methoden <xref:System.Threading.Tasks.Task.Wait%2A>, <xref:System.Threading.Tasks.Task.%2A> WaitAll?qualifyHint=False&autoUpgrade=True und <xref:System.Threading.Tasks.Task.%2A> WaitAny?qualifyHint=False&autoUpgrade=True akzeptieren Timeoutwerte, die entsprechenden Methoden <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>\/<xref:System.Threading.Tasks.Task.WhenAny%2A> sowie die bereits erwähnten <xref:System.Threading.Tasks.Task.WhenAll%2A>\/<xref:System.Threading.Tasks.Task.WhenAny%2A>\-Methoden jedoch nicht.  Stattdessen kann zum Implementieren eines Timeouts <xref:System.Threading.Tasks.Task.Delay%2A> zusammen mit <xref:System.Threading.Tasks.Task.WhenAny%2A> verwendet werden.  
  
 Sie möchten beispielsweise in der UI\-Anwendung ein Bild herunterladen und die Benutzeroberfläche deaktivieren, während das Bild heruntergeladen wird.  Wenn der Download jedoch zu lange dauert, möchten Sie die Benutzeroberfläche wieder aktivieren und den Download verwerfen:  
  
```csharp  
public async  void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = “Timed out”;  
            var ignored = download.ContinueWith(  
                t => Trace(“Task finally completed”));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
 Dasselbe gilt für mehrere Downloads, da <xref:System.Threading.Tasks.Task.WhenAll%2A> eine Aufgabe zurückgibt:  
  
```csharp  
public async  void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = “Downloaded”;  
        }  
        else  
        {  
            status.Text = “Timed out”;  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
  
```  
  
## Erstellen von aufgabenbasierten Kombinatoren  
 Da eine Aufgabe in der Lage ist, einen asynchronen Vorgang vollständig darzustellen und synchrone sowie asynchrone Funktionen für die Verknüpfung mit dem Vorgang bereitzustellen, die Ergebnisse abzurufen usw., lassen sich hilfreiche Bibliotheken von Kombinatoren erstellen, mit denen Aufgaben zu größeren Mustern kombiniert werden.  Wie im vorherigen Abschnitt erläutert, enthält das .NET Framework verschiedene integrierte Kombinatoren. Sie können aber auch eigene erstellen.  Die folgenden Abschnitte enthalten einige Beispiele möglicher Kombinatormethoden und \- typen.  
  
### RetryOnFault  
 In vielen Situationen sollten Sie einen Vorgang erneut versuchen, wenn bei einem vorheriger Versuch ein Fehler aufgetreten ist.  Bei synchronem Code können Sie eine Hilfsmethode wie `RetryOnFault` im folgenden Beispiel verwenden, um dies zu erreichen:  
  
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
  
 Sie können eine fast identische Hilfsmethode erstellen, jedoch für synchrone Vorgänge mit dem TAP implementiert, sodass Aufgaben zurückgegeben werden:  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
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
  
 Sie können diesen Kombinator dann verwenden, um Wiederholungen in die Logik der Anwendung zu codieren, beispielsweise:  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
  
```  
  
 Sie können die `RetryOnFault`\-Funktion zusätzlich erweitern.  Beispielsweise kann die Funktion eine andere `Func<Task>` akzeptieren, die zwischen Wiederholungen aufgerufen wird, um zu bestimmen, wann der Vorgang erneut versucht werden soll; beispielsweise:  
  
```csharp  
public static async  Task<T> RetryOnFault<T>(  
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
  
 Sie könnten die Funktion dann wie folgt verwenden und eine Sekunde warten, bevor der Vorgang erneut versucht wird:  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
  
```  
  
### NeedOnlyOne  
 Manchmal wird Redundanz genutzt, um die Wartezeit eines Vorgangs und die Erfolgschancen zu verbessern.  Betrachten Sie mehrere Webdienste, die Aktienkurse bieten, aber zu verschiedenen Uhrzeiten und mit jeweils unterschiedlicher Qualität und Reaktionszeit.  Um diese Abweichungen zu verarbeiten, können Sie Anforderungen an alle Webdienste senden und sobald Sie eine Antwort von einem Webdienst erhalten, brechen Sie die verbleibenden Anforderungen ab.  Sie können eine Hilfsfunktion implementieren, um die Implementierung dieses allgemeinen Musters, mehrere Vorgänge zu starten, auf einen beliebigen dieser Vorgänge zu warten und die restlichen Vorgänge abzubrechen, zu vereinfachen.  Die `NeedOnlyOne`\-Funktion im folgenden Beispiel veranschaulicht dieses Szenario:  
  
```csharp  
public static async  Task<T> NeedOnlyOne(  
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
    ct => GetCurrentPriceFromServer1Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer2Async(“msft”, ct),  
    ct => GetCurrentPriceFromServer3Async(“msft”, ct));  
```  
  
### Überlappende Vorgänge  
 Wenn ein Überlappungsszenario mit der <xref:System.Threading.Tasks.Task.WhenAny%2A>\-Methode unterstützt wird und sehr große Sätze von Aufgaben verwendet werden, kann ein Leistungsproblem auftreten.  Jeder Aufruf von <xref:System.Threading.Tasks.Task.WhenAny%2A> ergibt eine Fortsetzung, die mit jeder Aufgabe registriert wird.  Für n Anzahl von Aufgaben, führt dieses zu O\(n2\) Fortsetzungen, die über die Lebensdauer des überlappenden Vorgangs erstellt werden.  Wenn Sie mit einem umfangreichen Satz von Aufgaben arbeiten, können Sie einen Kombinator \(`Interleaved` im folgenden Beispiel\) verwenden um das Leistungsproblem zu verweisen:  
  
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
  
 Dieser Kombinator kann dann verwendet werden, um die Ergebnisse der Aufgaben nach ihrem Abschluss zu verarbeiten, wie im folgenden Beispiel:  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### WhenAllOrFirstException  
 In bestimmten Scatter\-Gather\-Szenarien warten Sie auf alle Aufgaben in einem Satz, es sei denn, bei einer der Aufgaben tritt ein Fehler auf. In diesem Fall sollte das Warten beendet werden, sobald die Ausnahme auftritt.  Sie können das mit einer Kombinatormethode `WhenAllOrFirstException` wie im folgenden Beispiel erreichen:  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
  
```  
  
## Erstellen von aufgabenbasierten Datenstrukturen  
 Mit einer Datenstruktur in <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> lassen sich nicht nur benutzerdefinierte aufgabenbasierte Kombinatoren erstellen; da sie sowohl die Ergebnisse eines asynchronen Vorgangs als auch die erforderliche Synchronisierung darstellt, die mit dem Vorgang verknüpft werden soll, ist sie ein äußerst leistungsstarker Typ, der als Grundlage für die Erstellung benutzerdefinierter Datenstrukturen in asynchronen Szenarien verwendet werden kann.  
  
### AsyncCache  
 Ein wichtiger Aspekt einer Aufgabe ist, dass sie an mehrere Consumer ausgegeben werden kann, die alle auf sie warten können, Fortsetzungen bei ihr registrieren können, ihr Ergebnis oder Ausnahmen abrufen können \(im Fall von <xref:System.Threading.Tasks.Task%601>\) usw.  Aus diesem Grund eignen sich <xref:System.Threading.Tasks.Task> und <xref:System.Threading.Tasks.Task%601> perfekt zur Verwendung in einer Infrastruktur mit asynchroner Zwischenspeicherung.  Im folgenden Beispiel wird ein leistungsfähiger asynchroner Cache gezeigt, der auf <xref:System.Threading.Tasks.Task%601> basiert:  
  
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
  
 Die [AsyncCache \<TKey, TValue\>](http://go.microsoft.com/fwlink/p/?LinkId=251941)\-Klasse akzeptiert als Delegat für ihren Konstruktor eine Funktion, die `TKey` akzeptiert und <xref:System.Threading.Tasks.Task%601> zurückgibt.  Alle Werte aus dem Cache, auf die zuvor zugegriffen wurde, werden im internen Wörterbuch gespeichert. Dabei stellt `AsyncCache` sicher, dass nur eine Aufgabe pro Schlüssel generiert wird, auch bei gleichzeitigem Zugriff auf den Cache.  
  
 Beispielsweise können Sie einen Cache für heruntergeladene Webseiten erstellen:  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
  
```  
  
 Sie können diesen Cache in asynchronen Methoden dann verwenden, wenn Sie den Inhalt einer Webseite benötigen.  Die `AsyncCache`\- Klasse stellt sicher, dass so wenig Seiten wie möglich heruntergeladen werden, und speichert die Ergebnisse.  
  
```csharp  
private async  void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
  
```  
  
### AsyncProducerConsumerCollection  
 Aufgaben können auch zum Erstellen von Datenstrukturen für das Koordinieren von asynchronen Aktivitäten verwendet werden.  Betrachten Sie eines der klassischen parallelen Entwurfsmuster: Producer\-Consumer.  In diesem Muster generieren Producer Daten, die von Consumern verwendet werden, und die Producer und Consumer können parallel ausgeführt werden.  Beispielsweise verarbeitet der Consumer Element 1, das zuvor aus einem Producer generiert wurde, der jetzt Element 2. erzeugt. In dem Producer\-Consumer\-Muster wird immer benötigen Sie z eine Datenstruktur, um die Arbeit zu speichern, der von Producern erzeugten wird, damit die Consumer über neue Daten benachrichtigt werden können und sie finden, sofern verfügbar.  
  
 Die folgende einfache Datenstruktur wurde auf Grundlage von Aufgaben erstellt und ermöglicht die Verwendung von asynchronen Methoden als Producer und Consumer:  
  
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
  
 Mit dieser Datenstruktur können Sie beispielsweise folgenden Code schreiben:  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
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
  
 Der <xref:System.Threading.Tasks.Dataflow>\-Namespace enthält den <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>\-Typ, der auf ähnliche Weise verwendet werden kann, aber ohne einen benutzerdefinierten Auflistungstyp erstellen zu müssen:  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async  Task ConsumerAsync()  
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
>  Der <xref:System.Threading.Tasks.Dataflow>\-Namespace ist in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] über **NuGet** verfügbar.  Öffnen Sie zum Installieren der Assembly, die den <xref:System.Threading.Tasks.Dataflow>\-Namespace enthält, das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]. Wählen Sie im Menü Projekt die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem Paket Microsoft.Tpl.Dataflow.  
  
## Siehe auch  
 [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)   
 [Implementing the Task\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)   
 [Interop with Other Asynchronous Patterns and Types](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)