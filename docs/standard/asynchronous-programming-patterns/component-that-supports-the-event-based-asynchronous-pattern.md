---
title: 'Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
ms.openlocfilehash: ef7363cd1c5161217fa4cf74dbfae9dee86fa76f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697739"
---
# <a name="how-to-implement-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt

Wenn Sie eine Klasse mit Vorgängen schreiben, die nennenswerte Verzögerungen verursachen können, sollten Sie die Klasse mit einer asynchronen Funktionalität ausstatten, indem Sie das ereignisbasierte asynchrone Muster implementieren. Informationen zu diesem Muster finden Sie unter [Übersicht über ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md).  
  
 Diese exemplarische Vorgehensweise veranschaulicht das Erstellen einer Komponente, die das ereignisbasierte asynchrone Muster implementiert. Dieses Muster wird mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace implementiert, wodurch eine einwandfreie Funktionsweise der Komponente unter jedem beliebigen Anwendungsmodell gewährleistet wird, z. B. ASP.NET, Konsolenanwendungen und Windows Forms-Anwendungen. Diese Komponente kann auch mit einem <xref:System.Windows.Forms.PropertyGrid>-Steuerelement und Ihren eigenen Designern gestaltet werden.  
  
 Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, verfügen Sie über eine Anwendung, die Primzahlen asynchron berechnet. Ihre Anwendung wird einen Thread für die Hauptbenutzeroberfläche und einen Thread für jede Primzahlenberechnung haben. Obwohl das Testen, ob eine große Zahl eine Primzahl ist, merklich Zeit in Anspruch nimmt, wird der Thread der Hauptbenutzeroberfläche nicht durch diese Verzögerung unterbrochen, und das Formular behält während der Berechnung seine Reaktionsfähigkeit. Sie können beliebig viele Berechnungen gleichzeitig ausführen und ausstehende Berechnungen selektiv abbrechen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
- Erstellen der Komponente  
  
- Definieren von öffentlichen asynchrone Ereignisse und Delegaten  
  
- Definieren von privaten Delegaten  
  
- Implementieren von öffentlichen Ereignissen  
  
- Implementieren der Abschlussmethode  
  
- Implementieren der Workermethoden  
  
- Implementieren von Methoden zum Starten und Abbrechen  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter [Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Erstellen der Komponente  

 Der erste Schritt besteht darin, die Komponente zu erstellen, die das ereignisbasierte asynchrone Muster implementiert.  
  
### <a name="to-create-the-component"></a>So erstellen Sie die Komponente  
  
- Erstellen Sie eine Klasse namens `PrimeNumberCalculator`, die von <xref:System.ComponentModel.Component> erbt.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Definieren von öffentlichen asynchrone Ereignisse und Delegaten  

 Die Komponente kommuniziert mit Clients mithilfe von Ereignissen. Das Ereignis _MethodName_**Completed** warnt Clients bei Abschluss eines asynchronen Tasks, und das Ereignis _MethodName_**ProgressChanged** informiert Clients über den Fortschritt eines asynchronen Tasks.  
  
### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>So definieren Sie asynchrone Ereignisse für Clients der Komponente  
  
1. Importieren Sie die Namespaces <xref:System.Threading?displayProperty=nameWithType> und <xref:System.Collections.Specialized?displayProperty=nameWithType> am Anfang der Datei.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#11)]  
  
2. Deklarieren Sie vor der Klassendefinition `PrimeNumberCalculator` Delegate für Fortschritts- und Abschlussereignisse.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#7)]  
  
3. Deklarieren Sie in der Klassendefinition `PrimeNumberCalculator` Ereignisse, um Clients über Fortschritt und Abschluss zu informieren.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#8)]  
  
4. Leiten Sie nach der Klassendefinition `PrimeNumberCalculator` die Klasse `CalculatePrimeCompletedEventArgs` ab, um den Ereignishandler des Clients über die Ergebnisse jeder Berechnung für das `CalculatePrimeCompleted`.event zu informieren. Zusätzlich zu den `AsyncCompletedEventArgs`-Eigenschaften bietet diese Klasse dem Client die Möglichkeit, die getesteten Zahlen, ob diese Primzahlen sind und deren ersten Divisor, wenn es keine Primzahl ist, zu ermitteln.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Checkpoint  

 An diesem Punkt können Sie die Komponente erstellen.  
  
### <a name="to-test-your-component"></a>So testen Sie Ihre Komponente  
  
- Kompilieren Sie die Komponente.  
  
     Sie erhalten zwei Compilerwarnungen:  
  
    ```console  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Diese Warnungen werden im nächsten Abschnitt gelöscht.  
  
## <a name="defining-private-delegates"></a>Definieren von privaten Delegaten  

 Die asynchronen Aspekte der Komponente `PrimeNumberCalculator` werden intern mit einem speziellen Delegaten, dem sogenannten <xref:System.Threading.SendOrPostCallback>, implementiert. Ein <xref:System.Threading.SendOrPostCallback> stellt eine Rückrufmethode dar, die für einen <xref:System.Threading.ThreadPool>-Thread ausgeführt wird. Die Rückrufmethode muss über eine Signatur verfügen, die einen einzelnen Parameter vom Typ <xref:System.Object> enthält, was bedeutet, dass Sie den Status zwischen Delegaten in einer Wrapperklasse übergeben müssen. Weitere Informationen finden Sie unter <xref:System.Threading.SendOrPostCallback>.  
  
### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>So implementieren Sie internes asynchrones Verhalten der Komponente  
  
1. Deklarieren und erstellen Sie die <xref:System.Threading.SendOrPostCallback>-Delegate in der Klasse `PrimeNumberCalculator`. Erstellen Sie die <xref:System.Threading.SendOrPostCallback>-Objekte in der Hilfsprogrammmethode `InitializeDelegates`.  
  
     Sie benötigen zwei Delegate: einen, um dem Client den Fortschritt, und einen, um dem Client den Abschluss zu melden.  

     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#20)]  
  
2. Rufen Sie die `InitializeDelegates`-Methode im Konstruktor der Komponente auf.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#21)]  
  
3. Deklarieren Sie einen Delegaten in der Klasse `PrimeNumberCalculator`, der die eigentliche, asynchron auszuführende Arbeit übernimmt. Dieser Delegat umschließt die Workermethode, die testet, ob eine Zahl eine Primzahl ist. Der Delegat nutzt einen <xref:System.ComponentModel.AsyncOperation>-Parameter, mit dem die Lebensdauer des asynchronen Vorgangs verfolgt wird.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#22)]  
  
4. Erstellen Sie eine Auflistung, um die Lebensdauer ausstehender asynchroner Vorgänge zu verwalten. Der Client muss die Möglichkeit haben, Vorgänge zu verfolgen, während sie ausgeführt und abgeschlossen werden. Diese Verfolgung erfolgt dadurch, dass der Client ein eindeutiges Token oder eine Task-ID übergeben muss, sobald er die asynchrone Methode aufruft. Die Komponente `PrimeNumberCalculator` muss jeden Aufruf verfolgen, indem sie die Task-ID mit dem entsprechenden Aufruf verknüpft. Wenn der Client eine Task-ID übergibt, die nicht eindeutig ist, muss die Komponente `PrimeNumberCalculator` eine Ausnahme auslösen.  
  
     Die Komponente `PrimeNumberCalculator` verfolgt die Task-ID mithilfe der speziellen Auflistungsklasse <xref:System.Collections.Specialized.HybridDictionary>. Erstellen Sie in der Klassendefinition ein <xref:System.Collections.Specialized.HybridDictionary> namens `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Implementieren von öffentlichen Ereignissen  

 Komponenten, die das ereignisbasierte asynchrone Muster implementieren, kommunizieren mit Clients mithilfe von Ereignissen. Diese Ereignisse werden auf dem richtigen Thread mithilfe der Klasse <xref:System.ComponentModel.AsyncOperation> aufgerufen.  
  
### <a name="to-raise-events-to-your-components-clients"></a>So lösen Sie Ereignisse für die Komponente Ihres Clients aus  
  
1. Implementieren Sie öffentliche Ereignisse für die Meldung an Clients. Sie benötigen ein Ereignis, um den Fortschritt, und eins, um den Abschluss zu melden.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Implementieren der Abschlussmethode  

 Der Abschlussdelegat ist die Methode, die das zugrundeliegende asynchrone Verhalten mit dem Threadingmodell „Free“ aufruft, sobald der asynchrone Vorgang durch erfolgreichen Abschluss, Fehler oder Abbruch beendet wird. Dieser Aufruf erfolgt auf einen beliebigen Thread.  
  
 Bei dieser Methode wird die Task-ID des Clients aus der internen Auflistung eindeutiger Clienttoken entfernt. Diese Methode beendet auch die Lebensdauer eines bestimmten asynchronen Vorgangs, indem die Methode <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> für den entsprechenden <xref:System.ComponentModel.AsyncOperation> aufgerufen wird. Dieser Aufruf löst das Abschlussereignis für den Thread aus, der für das Anwendungsmodell geeignet ist. Nach dem Aufruf der Methode <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> kann diese Instanz von <xref:System.ComponentModel.AsyncOperation> nicht mehr verwendet werden, und alle nachfolgenden Verwendungsversuche werden eine Ausnahme auslösen.  
  
 Die Signatur `CompletionMethod` muss alle Zustände enthalten, die erforderlich sind, um das Ergebnis des asynchronen Vorgangs zu beschreiben. Sie umfasst den Zustand für die Zahl, für die mit diesem bestimmten asynchronen Vorgang geprüft wurde, ob sie eine Primzahl ist, und den Wert ihres ersten Divisors, wenn es sich nicht um eine Primzahl handelt. Außerdem enthält Sie den Zustand, der alle aufgetretenen Ausnahmen beschreibt, und die entsprechende <xref:System.ComponentModel.AsyncOperation> für diesen bestimmten Task.  
  
### <a name="to-complete-an-asynchronous-operation"></a>So schließen Sie einen asynchronen Vorgang ab  
  
- Implementieren Sie die Abschlussmethode. Sie nutzt sechs Parameter, die zum Ausfüllen von `CalculatePrimeCompletedEventArgs` verwendet werden, welches durch den `CalculatePrimeCompletedEventHandler` des Clients an den Client zurückgegeben wird. Das Task-ID-Token des Clients wird aus der internen Auflistung entfernt, und die Lebensdauer des asynchronen Vorgangs wird mit einem Aufruf von <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> beendet. <xref:System.ComponentModel.AsyncOperation> marshallt den Aufruf des Threads bzw. des Kontexts, der für das Anwendungsmodell geeignet ist.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Checkpoint  

 An diesem Punkt können Sie die Komponente erstellen.  
  
### <a name="to-test-your-component"></a>So testen Sie Ihre Komponente  
  
- Kompilieren Sie die Komponente.  
  
     Sie erhalten eine Compilerwarnung:  
  
    ```console  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Diese Warnung wird im nächsten Abschnitt aufgelöst.  
  
## <a name="implementing-the-worker-methods"></a>Implementieren der Workermethoden  

 Bisher haben Sie den unterstützenden asynchronen Code für die Komponente `PrimeNumberCalculator` implementiert. Jetzt können Sie den Code implementieren, der die eigentliche Arbeit übernimmt. Sie implementieren drei Methoden: `CalculateWorker`, `BuildPrimeNumberList` und `IsPrime`. Zusammen umfassen `BuildPrimeNumberList` und `IsPrime` einen bekannten Algorithmus namens „Sieb des Eratosthenes“, der bestimmt, ob eine Zahl eine Primzahl ist, indem er alle Primzahlen bis zur Quadratwurzel der Testzahl findet. Wenn keine Divisoren bis dahin gefunden werden, ist die zu testende Zahl eine Primzahl.  
  
 Wenn diese Komponente für maximale Effizienz geschrieben würde, würde sie alle Primzahlen speichern, die durch verschiedene Aufrufe für verschiedene Testzahlen entdeckt wurden. Zudem würde sie auch triviale Divisoren wie 2, 3 und 5 überprüfen. In diesem Beispiel soll demonstriert werden, wie zeitaufwendige Vorgänge asynchron ausgeführt werden können, sodass diese Optimierungen als Übung für Sie belassen werden.  
  
 Die `CalculateWorker`-Methode wird von einem Delegaten umschlossen und mit einem Aufruf von `BeginInvoke` asynchron aufgerufen.  
  
> [!NOTE]
> Die Fortschrittsmeldung wird in der `BuildPrimeNumberList`-Methode implementiert. Auf schnellen Computern können `ProgressChanged`-Ereignisse in rascher Folge ausgelöst werden. Der Clientthread, für den diese Ereignisse ausgelöst werden, muss diese Situation verarbeiten können. Der Code der Benutzeroberfläche erhält möglicherweise eine Flut von Meldungen, die er nicht bewältigen kann, sodass keine Reaktion mehr erfolgt. Ein Beispiel für eine Benutzeroberfläche in einer solchen Situation finden Sie unter [Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>So führen Sie die asynchrone Berechnung der Primzahl aus  
  
1. Implementieren Sie die Hilfsprogrammmethode `TaskCanceled`. Diese überprüft die Auflistung der Tasklebensdauer für die angegebene Task-ID und gibt `true` zurück, wenn die Task-ID nicht gefunden wird.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#32)]  
  
2. Implementieren Sie die `CalculateWorker`-Methode. Es werden zwei Parameter akzeptiert: eine zu testende Zahl und eine <xref:System.ComponentModel.AsyncOperation>-Klasse.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#27)]  
  
3. Implementieren Sie `BuildPrimeNumberList`. Es werden zwei Parameter akzeptiert: die zu testende Zahl und eine <xref:System.ComponentModel.AsyncOperation>-Klasse. Die <xref:System.ComponentModel.AsyncOperation>-Klasse wird verwendet, um den Fortschritt und inkrementelle Ergebnisse zu melden. Dadurch wird sichergestellt, dass die Ereignishandler des Clients für den richtigen Thread oder Kontext für das Anwendungsmodell aufgerufen werden. Wenn `BuildPrimeNumberList` eine Primzahl findet, wird dies als inkrementelles Ergebnis an den Clientereignishandler für das `ProgressChanged`-Ereignis weitergegeben. Dies erfordert eine von <xref:System.ComponentModel.ProgressChangedEventArgs> abgeleitete Klasse namens `CalculatePrimeProgressChangedEventArgs`, die über eine hinzugefügte Eigenschaft mit der Bezeichnung `LatestPrimeNumber` verfügt.  
  
     Die `BuildPrimeNumberList`-Methode ruft in regelmäßigen Abständen die `TaskCanceled`-Methode auf und wird beendet, wenn die Methode `true` zurückgibt.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#5)]  
  
4. Implementieren Sie `IsPrime`. Es werden drei Parameter akzeptiert: eine Liste der bekannten Primzahlen, die zu testende Zahl und ein Ausgabeparameter für den ersten gefundenen Divisor. Anhand der vorliegenden Primzahlenliste wird ermittelt, ob es sich bei der zu testenden Zahl um eine Primzahl handelt.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#28)]  
  
5. Leiten Sie `CalculatePrimeProgressChangedEventArgs` aus <xref:System.ComponentModel.ProgressChangedEventArgs> ab. Diese Klasse ist notwendig, damit der Clientereignishandler für das `ProgressChanged`-Ereignis über inkrementelle Ergebnisse informiert wird. Sie verfügt über eine zusätzliche Eigenschaft namens `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Checkpoint  

 An diesem Punkt können Sie die Komponente erstellen.  
  
### <a name="to-test-your-component"></a>So testen Sie Ihre Komponente  
  
- Kompilieren Sie die Komponente.  
  
     Was nun noch geschrieben werden muss, sind die Methoden zum Starten und Abbrechen der asynchronen Vorgänge `CalculatePrimeAsync` und `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Implementieren von Methoden zum Starten und Abbrechen  

 Sie starten die Workermethode auf ihrem eigenen Thread, indem Sie `BeginInvoke` über den Delegaten aufrufen, der sie umschließt. Um die Lebensdauer eines bestimmten asynchronen Vorgangs zu verwalten, rufen Sie die <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>-Methode für die Hilfsprogrammklasse <xref:System.ComponentModel.AsyncOperationManager> auf. Dadurch wird eine <xref:System.ComponentModel.AsyncOperation>-Klasse zurückgegeben, die Aufrufe für den Ereignishandler des Clients zum richtigen Thread oder Kontext marshallt.  
  
 Sie brechen einen bestimmten ausstehenden Vorgang ab, indem Sie <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> für die entsprechende <xref:System.ComponentModel.AsyncOperation>-Klasse aufrufen. Dadurch wird dieser Vorgang beendet, und alle nachfolgenden Aufrufe für <xref:System.ComponentModel.AsyncOperation> werden eine Ausnahme auslösen.  
  
### <a name="to-implement-start-and-cancel-functionality"></a>So implementieren Sie die Funktionen zum Starten und Abbrechen  
  
1. Implementieren Sie die `CalculatePrimeAsync`-Methode. Stellen Sie sicher, dass das vom Client bereitgestellte Token (Task-ID) in Bezug auf alle Tokens der derzeit ausstehenden Tasks eindeutig ist. Wenn der Client ein nicht eindeutiges Token übergibt, löst `CalculatePrimeAsync` eine Ausnahme aus. Andernfalls wird das Token zur Task-ID-Auflistung hinzugefügt.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#3)]  
  
2. Implementieren Sie die `CancelAsync`-Methode. Wenn der `taskId`-Parameter in der Tokenauflistung vorhanden ist, wird er entfernt. Dies verhindert, dass noch nicht ausgeführte Tasks abgebrochen werden. Wenn der Task ausgeführt wird, wird er durch die `BuildPrimeNumberList`-Methode beendet, sobald diese erkennt, dass die Task-ID aus der Auflistung der Lebensdauer entfernt wurde.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Checkpoint  

 An diesem Punkt können Sie die Komponente erstellen.  
  
### <a name="to-test-your-component"></a>So testen Sie Ihre Komponente  
  
- Kompilieren Sie die Komponente.  
  
 Die `PrimeNumberCalculator`-Komponente ist jetzt vollständig und einsatzbereit.  
  
 Ein Beispiel für einen Client, der die `PrimeNumberCalculator`-Komponente verwendet, finden Sie unter [Gewusst wie: Implementieren eines Clients des ereignisbasierten asynchronen Musters](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Nächste Schritte  

 Sie können dieses Beispiel ausfüllen, indem Sie `CalculatePrime` schreiben. Dies ist das synchrone Äquivalent der `CalculatePrimeAsync`-Methode. So wird die `PrimeNumberCalculator`-Komponente vollständig kompatibel mit dem ereignisbasierten asynchronen Muster.  
  
 Sie können dieses Beispiel verbessern, indem Sie die Liste aller Primzahlen beibehalten, die durch verschiedene Aufrufe für verschiedene Testzahlen entdeckt wurden. Mit diesem Ansatz profitiert jeder Task von der Arbeit früherer Tasks. Achten Sie darauf, diese Liste mit `lock`-Regionen zu schützen, damit der Zugriff auf die Liste durch verschiedene Threads serialisiert wird.  
  
 Außerdem können Sie dieses Beispiel auch verbessern, indem Sie auf triviale Divisoren wie 2, 3 und 5 testen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](event-based-asynchronous-pattern-overview.md)
- [Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))](event-based-asynchronous-pattern-eap.md)
