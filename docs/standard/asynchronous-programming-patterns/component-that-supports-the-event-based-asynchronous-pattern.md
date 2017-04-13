---
title: "Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern | Microsoft Docs"
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
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern
Wenn Sie eine Klasse mit Operationen schreiben, durch die nennenswerte Verzögerungen auftreten können, sollten Sie sie mit einer asynchronen Funktionalität ausstatten, indem Sie die unter [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) beschriebenen Schritte implementieren.  
  
 Diese exemplarische Vorgehensweise veranschaulicht das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert.  Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=fullName>\-Namespace implementiert, was eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell, einschließlich [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Konsolenanwendungen und Anwendungen von Windows Forms, gewährleistet.  Diese Komponente ist auch mit einem <xref:System.Windows.Forms.PropertyGrid>\-Steuerelement und den eigenen benutzerdefinierten Designern ausführbar.  
  
 Nach dem Implementieren steht Ihnen eine Komponente zur Verfügung, die Primzahlen asynchron berechnet.  Die Anwendung ist mit einem Haupthread der Benutzeroberfläche \(UI\) und einem Thread für jede einzelne Primzahlenberechnung ausgestattet.  Obwohl die Primzahlenberechnung mitunter sehr zeitaufwändig ist, wird der Hauptthread der Benutzeroberfläche durch diese Verzögerung nicht unterbrochen. Die Reaktivität der Benutzeroberfläche bleibt erhalten.  Sie können daher beliebig viele Berechnungen gleichzeitig ausführen und ausstehende Berechnungen wahlweise abbrechen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen der Komponente  
  
-   Definieren von öffentlichen, asynchronen Ereignissen und Delegaten  
  
-   Definieren von privaten Delegaten  
  
-   Implementieren von öffentlichen Ereignissen  
  
-   Implementieren der Abschlussmethode  
  
-   Implementieren der Workermethoden  
  
-   Implementieren der Start\-Methode und der Cancel\-Methode  
  
 Informationen zum Kopieren des in diesem Thema behandelten Codes als einzelne Auflistung finden Sie unter [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## Erstellen der Komponente  
 Der erste Schritt besteht darin, eine Komponente zu erstellen, die das ereignisbasierte asynchrone Entwurfsmuster implementiert.  
  
#### So erstellen Sie die Komponente  
  
-   Erstellen Sie eine Klasse mit dem Namen `PrimeNumberCalculator`, die von <xref:System.ComponentModel.Component> erbt.  
  
## Definieren von öffentlichen, asynchronen Ereignissen und Delegaten  
 Die Komponente kommuniziert mit den Clients mithilfe von Ereignissen.  Die Clients erhalten vom *MethodName*`Completed`\-Ereignis den Abschluss einer asynchronen Aufgabe, und *Methodennamen*`ProgressChanged` das Ereignis informiert Clients über den Status einer asynchronen Aufgabe.  
  
#### So definieren Sie asynchrone Ereignisse für Clients der Komponente:  
  
1.  Importieren Sie den <xref:System.Threading?displayProperty=fullName>\-Namespace und den <xref:System.Collections.Specialized?displayProperty=fullName>\-Namespace am Anfang der Datei.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  Deklarieren Sie vor der Definition der  `PrimeNumberCalculator` \-Klasse Delegaten für Fortschritts\- und Abschlussereignisse.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  Deklarieren Sie während der Definition der  `PrimeNumberCalculator` \-Klasse Ereignisse, die an die Clients Status und Abschluss melden.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  Leiten Sie nach der Definition der  `PrimeNumberCalculator` \-Klasse die  `CalculatePrimeCompletedEventArgs` \-Klasse ab, die den Ereignishandler des Clients für das `CalculatePrimeCompleted`\-Ereignis über das Ergebnis jeder Berechnung informiert.  Neben den `AsyncCompletedEventArgs`\-Eigenschaften kann der Client mittels dieser Klasse feststellen, welche Zahl getestet wurde, ob es sich um eine Primzahl handelt und, falls keine Primzahl vorliegt, wie der erste Divisor lautet.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## Checkpoint  
 An diesem Punkt können Sie die Komponente erstellen.  
  
#### So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
     Sie empfangen daraufhin zwei Compiler\-Warnungen:  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Diese Warnungen werden im nächsten Abschnitt gelöscht.  
  
## Definieren von privaten Delegaten  
 Die asynchronen Aspekte der  `PrimeNumberCalculator` \-Komponente werden intern mit einem gesonderten, als <xref:System.Threading.SendOrPostCallback> bekannten Delegaten implementiert.  Ein <xref:System.Threading.SendOrPostCallback> stellt eine Rückrufmethode dar, die in einem <xref:System.Threading.ThreadPool>\-Thread ausgeführt wird.  Die Rückrufmethode muss über eine Signatur verfügen, die einen einzelnen Parameter des Typs <xref:System.Object> übernimmt. Dies bedeutet, dass Sie an Delegaten in einer Wrapperklasse Zustand übergeben müssen.  Weitere Informationen finden Sie unter <xref:System.Threading.SendOrPostCallback>.  
  
#### So implementieren Sie das interne asynchrone Verhalten der Komponente:  
  
1.  Deklarieren und erzeugen Sie die <xref:System.Threading.SendOrPostCallback>\-Delegaten in der  `PrimeNumberCalculator` \-Klasse.  Erstellen Sie die <xref:System.Threading.SendOrPostCallback>\-Objekte in einer Dienstprogrammmethode mit dem Namen  `InitializeDelegates`.  
  
     Sie benötigen zwei Delegate: einen für den Statusbericht an den Client, den anderen für die Abschlussmeldung an den Client.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  Rufen Sie die `InitializeDelegates`\-Methode im Konstruktor der Komponente auf.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  Deklarieren Sie einen Delegaten in der `PrimeNumberCalculator`\-Klasse, der die eigentliche, asynchron zu verrichtende Arbeit erledigt.  Dieser Delegat umschließt die Workermethode, die eine Zahl auf ihre Primzahleigenschaft testet.  Der Delegat übernimmt einen <xref:System.ComponentModel.AsyncOperation>\-Parameter, mit dem dann die Lebensdauer der asynchronen Operation verfolgt wird.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  Erstellen Sie zum Verwalten der Lebensdauer ausstehender, asynchroner Operationen eine Auflistung.  Der Client muss auf eine bestimmte Art und Weise die Operationen bei Ausführung und Abschluss verfolgen. Dieses Verfolgen geschieht so, dass der Client beim Aufrufen der asynchronen Methode ein eindeutiges Token bzw. eine eindeutige Aufgaben\-ID übergibt.  Jeder Aufruf muss von der `PrimeNumberCalculator`\-Komponente durch Zuordnen der Aufgaben\-ID zum entsprechenden Aufruf verfolgt werden.  Wenn der Client eine nicht eindeutige Aufgaben\-ID übergibt, muss die `PrimeNumberCalculator`\-Komponente eine Ausnahme auslösen.  
  
     Die `PrimeNumberCalculator`\-Komponente verfolgt die Aufgaben\-ID mithilfe einer gesonderte Auflistungsklasse, die <xref:System.Collections.Specialized.HybridDictionary> genannt wird.  Erstellen Sie beim Definieren der Klasse eine <xref:System.Collections.Specialized.HybridDictionary> mit dem Namen  `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## Implementieren von öffentlichen Ereignissen  
 Komponenten, die das ereignisbasierte asynchrone Muster implementieren, kommunizieren mit den Clients über Ereignisse.  Diese Ereignisse werden im entsprechenden Thread mithilfe der <xref:System.ComponentModel.AsyncOperation>\-Klasse aufgerufen.  
  
#### So lösen Sie Ereignisse zu den Clients der Komponente aus:  
  
1.  Implementieren Sie öffentliche Ereignisse für die Benachrichtigung von Clients.  Sie benötigen ein Ereignis für die Statusmeldung und ein Ereignis für die Abschlussmeldung.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## Implementieren der Abschlussmethode  
 Der Abschlussdelegat ist die Methode, die vom zugrunde liegenden asynchronen Verhalten mit freiem Thread dann aufgerufen wird, wenn die asynchrone Operation aufgrund eines erfolgreichen Abschlusses, eines Fehlers oder aber eines Abbruchs beendet wird.  Ein solcher Aufruf wird in einem beliebigen Thread vollzogen.  
  
 Die Methode dient dazu, die Aufgaben\-ID aus der internen Auflistung der eindeutigen Clienttokens zu entfernen.  Die Methode beendet auch die Lebensdauer einer einzelnen asynchronen Operation durch Aufrufen der <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>\-Methode für die entsprechende <xref:System.ComponentModel.AsyncOperation>.  Dieser Aufruf löst das Abschlussereignis in dem Thread aus, der für das Anwendungsmodell geeignet ist.  Nach dem Aufrufen der <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>\-Methode kann diese Instanz der <xref:System.ComponentModel.AsyncOperation> nicht länger verwendet werden, sodass nachfolgende Verwendungsversuche eine Ausnahme auslösen.  
  
 Die `CompletionMethod`\-Signatur muss alle Zustände enthalten, die notwendig sind, um das Ergebnis der asynchronen Operation zu beschreiben.  Diese Klasse speichert den Zustand für die Zahl, die von dieser asynchronen Operation getestet wurde, und sie gibt an, ob die Zahl eine Primzahl ist. Wenn es sich nicht um eine Primzahl handelt, gibt die Klasse den ersten Divisor an.  Zusätzlich speichert die Klasse den Zustand jeder aufgetretenen Ausnahme sowie die <xref:System.ComponentModel.AsyncOperation>, die dieser Aufgabe entspricht.  
  
#### So schließen Sie eine asynchrone Operation ab:  
  
-   Implementieren Sie die Abschlussmethode.  Sie nimmt sechs Parameter an, mit denen sie ein  `CalculatePrimeCompletedEventArgs` auffüllt, das durch den  `CalculatePrimeCompletedEventHandler` des Clients an den Client zurückgegeben wird.  Die Methode entfernt das Token bzw. die Aufgaben\-ID des Clients aus der internen Auflistung und beendet die Lebensdauer der asynchronen Methode durch Aufrufen von <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>.  Die <xref:System.ComponentModel.AsyncOperation> führt das Marshalling des Aufrufs an den auf das Anwendungsmodell passenden Thread oder Kontext aus.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## Checkpoint  
 An diesem Punkt können Sie die Komponente erstellen.  
  
#### So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
     Sie empfangen eine Compilerwarnung:  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Diese Warnung wird im nächsten Abschnitt aufgelöst.  
  
## Implementieren der Workermethoden  
 Sie haben bereits den unterstützenden asynchronen Code für die `PrimeNumberCalculator`\-Komponente implementiert.  Jetzt können Sie den Code für die eigentliche Arbeit implementieren.  Sie implementieren drei Methoden: `CalculateWorker`,  `BuildPrimeNumberList` und `IsPrime`.  `BuildPrimeNumberList` und `IsPrime` bilden zusammen einen bekannten Algorithmus, das Sieb des Eratosthenes, mit dem eine Zahl auf ihre Primzahleigenschaft hin untersucht wird, indem aus einem bestimmten Zahlenbereich alle Primzahlen bis zur Quadratwurzel der untersuchten Zahl ermittelt werden.  Wenn bis zu diesem Punkt keine Primteiler gefunden werden, dann handelt es sich bei der getesteten Zahl um eine Primzahl.  
  
 Falls diese Komponente geschrieben wäre, um größtmögliche Effizienz zu erzielen, würden alle von verschiedenen Aufrufen für viele verschiedene Testzahlen ermittelten Primzahlen abrufbar sein.  Die Komponente würde auch auf einfache Primteiler wie 2, 3 und 5 prüfen.  Ziel dieses Beispieles ist es zu zeigen, wie zeitaufwändig asynchron ausgeführte Operationen sein können. Daher sollen Ihnen diese Optimierungen als Übung dienen.  
  
 Die `CalculateWorker`\-Methode wird mit einem Delegaten umschlossen und mit einem Aufruf von `BeginInvoke` asynchron aufgerufen.  
  
> [!NOTE]
>  Die Fortschrittsberichterstellung wird in der `BuildPrimeNumberList`\-Methode implementiert.  Auf schnellen Computern können `ProgressChanged`\-Ereignisse in schneller Folge ausgelöst werden.  Der Clientthread, anhand dessen diese Ereignisse ausgelöst werden, muss mit dieser Situation umgehen können.  Der Code für die Benutzeroberfläche wird möglicherweise mit Meldungen überschwemmt und kann nicht darauf reagieren, was zu einem absturzähnlichen Verhalten führt.  Eine Beispielbenutzeroberfläche, die mit dieser Situation zurechtkommt, finden Sie unter [How to: Implement a Client of the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
#### So führen Sie die Primzahlenberechnung asynchron aus:  
  
1.  Implementieren Sie die `TaskCanceled`\-Dienstprogrammmethode.  Diese überprüft die Auflistung der Aufgabenlebensdauer für die angegebene Aufgaben\-ID und gibt `true` zurück, wenn die Aufgaben\-ID nicht gefunden wurde.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  Implementieren Sie die `CalculateWorker`\-Methode.  Es werden zwei Parameter angenommen: eine Testzahl und eine <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  Sie können `BuildPrimeNumberList` implementieren.  Es werden zwei Parameter übernommen: die Testzahl und eine <xref:System.ComponentModel.AsyncOperation>.  Es wird die <xref:System.ComponentModel.AsyncOperation> verwendet, um Status und inkrementelle Ergebnisse zu melden.  Damit wird sichergestellt, dass die Ereignishandler des Clients in dem auf das Anwendungsmodell passenden Thread oder Kontext aufgerufen werden.  Wenn `BuildPrimeNumberList` eine Primzahl ermittelt, wird dies in Form eines inkrementellen Ergebnisses an den für das `ProgressChanged`\-Ereignis bestimmten Ereignishandler des Clients gemeldet.  Dies erfordert eine von <xref:System.ComponentModel.ProgressChangedEventArgs> abgeleitete Klasse namens `CalculatePrimeProgressChangedEventArgs`, die über eine hinzugefügte Eigenschaft mit dem Namen `LatestPrimeNumber` verfügt.  
  
     Die `BuildPrimeNumberList`\-Methode ruft auch periodisch die `TaskCanceled`\-Methode auf und endet, wenn die Methode `true` zurückgibt.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  Sie können `IsPrime` implementieren.  Übernommen werden drei Parameter: eine Liste bekannter Primzahlen, die Testzahl und ein Ausgabeparameter für den ersten gefundenen Divisor.  Anhand der Liste mit den Primzahlen wird die Testzahl auf ihre Primzahleigenschaft hin überprüft.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  Leiten Sie `CalculatePrimeProgressChangedEventArgs` von <xref:System.ComponentModel.ProgressChangedEventArgs> ab.  Diese Klasse ist für das Melden von inkrementellen Ergebnissen an die für das `ProgressChanged`\-Ereignis vorgesehenen Ereignishandler des Clients erforderlich.  Die Klasse verfügt über eine zusätzliche Eigenschaft mit dem Namen `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## Checkpoint  
 An diesem Punkt können Sie die Komponente erstellen.  
  
#### So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
     Nun sind lediglich noch die Methoden zum Starten und Abbrechen von asynchronen Operationen zu schreiben, und zwar die `CalculatePrimeAsync`\-Methode und die `CancelAsync`\-Methode.  
  
## Implementieren der Start\-Methode und der Cancel\-Methode  
 Sie starten die Workermethode in deren Thread durch Aufrufen von `BeginInvoke` für den Delegaten, mit dem diese Methode umschlossen ist.  Zum Verwalten der Lebensdauer einer bestimmten, asynchronen Operation rufen Sie die <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>\-Methode für die <xref:System.ComponentModel.AsyncOperationManager>\-Hilfsklasse auf.  Daraufhin wird eine <xref:System.ComponentModel.AsyncOperation> zurückgegeben, die das Marshalling von Aufrufen von Ereignishandlern des Clients an den entsprechenden Thread oder Kontext vornimmt.  
  
 Sie brechen eine einzelne ausstehende Operation so ab, indem Sie <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> für die entsprechende <xref:System.ComponentModel.AsyncOperation> aufrufen.  Damit wird diese Operation beendet, und alle nachfolgenden Aufrufe der <xref:System.ComponentModel.AsyncOperation> lösen eine Ausnahme aus.  
  
#### So implementieren Sie die Start\-Funktion und die Cancel\-Funktion:  
  
1.  Implementieren Sie die `CalculatePrimeAsync`\-Methode.  Stellen Sie sicher, dass das Token bzw. die Aufgaben\-ID eindeutig ist, und zwar im Hinblick auf alle Tokens der aktuell ausstehenden Aufgaben.  Wenn der Client ein nicht eindeutiges Token übergibt, dann wird von `CalculatePrimeAsync` eine Ausnahme ausgelöst.  Andernfalls wird das Token der Aufgaben\-ID\-Auflistung hinzugefügt.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  Implementieren Sie die `CancelAsync`\-Methode.  Wenn der `taskId`\-Parameter in der Token\-Auflistung vorhanden ist, wird er entfernt.  Dadurch werden abgebrochene Aufgaben, die nicht gestartet wurden, nicht ausgeführt.  Wenn die Aufgabe ausgeführt wird, wird die `BuildPrimeNumberList`\-Methode beendet, wenn sie feststellt, dass die Aufgaben\-ID aus der Auflistung der Lebensdauer entfernt wurde.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## Checkpoint  
 An diesem Punkt können Sie die Komponente erstellen.  
  
#### So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
 Die  `PrimeNumberCalculator` \-Komponente ist nun vollständig und einsatzbereit.  
  
 Ein Beispiel für einen Client, der die `PrimeNumberCalculator`\-Komponente verwendet, finden Sie unter [How to: Implement a Client of the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## Nächste Schritte  
 Sie können dieses Beispiel ausfüllen, indem Sie `CalculatePrime`, das synchrone Äquivalent der `CalculatePrimeAsync`\-Methode, schreiben.  Hiermit erreichen Sie, dass die `PrimeNumberCalculator`\-Komponente für das ereignisbasierte asynchrone Muster uneingeschränkt tauglich ist.  
  
 Sie können das Beispiel noch verbessern, indem Sie die Liste der aus der Menge der verschiedenen Testzahlen per Aufruf ermittelten Primzahlen speichern.  Mit dieser Vorgehensweise kann jede Aufgabe von zuvor ausgeführten Aufgaben profitieren.  Schützen Sie die Liste mit `lock`\-Bereichen, damit der Zugriff auf die Liste durch verschiedene Threads serialisiert wird.  
  
 Sie können das Beispiel auch verbessern, indem Sie auf einfache Primteiler wie 2, 3 und 5 testen lassen.  
  
## Siehe auch  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/de-de/c731a50c-09c1-4468-9646-54c86b75d269)   
 [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)