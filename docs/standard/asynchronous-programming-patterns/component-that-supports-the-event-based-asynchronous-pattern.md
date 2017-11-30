---
title: "Exemplarische Vorgehensweise: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Exemplarische Vorgehensweise: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt
Wenn Sie eine Klasse mit einigen Vorgängen, die merkliche Wartezeiten entstehen schreiben, in Betracht ziehen es asynchronen Funktionalität durch Implementieren der [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Komponente erstellen, die das ereignisbasierte asynchrone Muster implementiert wird. Er implementiert wird, mithilfe von Hilfsklassen aus dem <xref:System.ComponentModel?displayProperty=nameWithType> Namespace, der sicherstellt, dass die Komponente unter jedem beliebigen Anwendungsmodell ordnungsgemäß funktioniert, einschließlich [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Konsole und Windows Forms-Anwendungen. Diese Komponente ist außerdem mit ausführbar eine <xref:System.Windows.Forms.PropertyGrid> Steuerung und eine eigene benutzerdefinierte Designer.  
  
 Wenn Sie über sind, müssen Sie eine Anwendung, die Primzahlen asynchron berechnet. Die Anwendung wird eine Benutzeroberfläche (UI) des Hauptbenutzerthread und einen Thread für jede Berechnung Primzahl haben. Obwohl testen, ob eine große Anzahl ist Primzahlen kann eine spürbar Zeit dauern, der Hauptbenutzeroberflächen-Thread nicht unterbrochen wird, indem diese Verzögerung und das Formular werden während der Berechnung reaktionsfähig. Sie werden ausgeführt, wie viele Berechnungen wie gleichzeitig und selektiv gewünscht ausstehende Berechnungen "Abbrechen".  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen der Komponente  
  
-   Definieren von öffentlichen asynchrone Ereignisse und Delegaten  
  
-   Definieren von privaten Delegaten  
  
-   Implementieren öffentliche Ereignisse  
  
-   Implementieren der Abschlussmethode  
  
-   Implementieren der Workermethoden  
  
-   Implementieren von Start- und Cancel-Methode  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [wie: implementieren eine Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Erstellen der Komponente  
 Der erste Schritt ist zum Erstellen der Komponente, die das ereignisbasierte asynchrone Muster implementiert wird.  
  
#### <a name="to-create-the-component"></a>So erstellen Sie die Komponente  
  
-   Erstellen Sie eine Klasse namens `PrimeNumberCalculator` von erbt <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Definieren von öffentlichen asynchrone Ereignisse und Delegaten  
 Die Komponente kommuniziert mit Clients mithilfe von Ereignissen. Die *MethodName* `Completed` Ereignis benachrichtigt Clients, die bis zum Abschluss einer asynchronen Aufgabe und die *MethodName* `ProgressChanged` Ereignis informiert Clients über den Fortschritt einer asynchronen Aufgabe.  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>So definieren Sie asynchrone Ereignisse für Clients der Komponente  
  
1.  Importieren der <xref:System.Threading?displayProperty=nameWithType> und <xref:System.Collections.Specialized?displayProperty=nameWithType> Namespaces am Anfang der Datei.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  Bevor Sie die `PrimeNumberCalculator` Klassendefinition, deklarieren von Delegaten für Ereignisse von Status und den Abschluss.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  In der `PrimeNumberCalculator` Klassendefinition, deklarieren von Ereignissen für die Berichterstattung, Status und den Abschluss an Clients.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  Nach der `PrimeNumberCalculator` Klassendefinition, leiten Sie die `CalculatePrimeCompletedEventArgs` Klasse für die Berichterstattung im Rahmen jeder Ereignishandler des Clients für die Berechnung der `CalculatePrimeCompleted`.event. Zusätzlich zu den `AsyncCompletedEventArgs` Eigenschaften, diese Klasse ermöglicht es dem Client, um zu bestimmen, welche Zahl getestet wurde, gibt an, ob eine Primzahl ist und was der erste Divisor ist, wenn es keine Primzahl ist.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Checkpoint  
 An diesem Punkt können Sie die Komponente zu erstellen.  
  
#### <a name="to-test-your-component"></a>So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
     Sie erhalten zwei compilerwarnungen:  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Diese Warnungen werden im nächsten Abschnitt gelöscht werden.  
  
## <a name="defining-private-delegates"></a>Definieren von privaten Delegaten  
 Die asynchronen Aspekte der der `PrimeNumberCalculator` Komponente werden intern mit einem speziellen Delegaten genannt implementiert eine <xref:System.Threading.SendOrPostCallback>. Ein <xref:System.Threading.SendOrPostCallback> stellt eine Rückrufmethode, die auf führt eine <xref:System.Threading.ThreadPool> Thread. Die Rückrufmethode muss eine Signatur, die einen einzelnen Parameter vom Typ akzeptiert haben <xref:System.Object>, das bedeutet, dass Zustand zwischen Delegaten in einen Wrapperklasse übergeben müssen. Weitere Informationen finden Sie unter <xref:System.Threading.SendOrPostCallback>.  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Interne asynchrone Verhalten der Komponente zu implementieren:  
  
1.  Deklarieren und erstellen Sie die <xref:System.Threading.SendOrPostCallback> in delegiert die `PrimeNumberCalculator` Klasse. Erstellen der <xref:System.Threading.SendOrPostCallback> Objekte in eine Hilfsprogrammmethode, so genannte `InitializeDelegates`.  
  
     Sie benötigen zwei Delegaten: eine für die Statusmeldung an den Client, und eine für die Berichterstattung Abschluss an den Client.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  Rufen Sie die `InitializeDelegates` -Methode im Konstruktor der Komponente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  Deklarieren Sie einen Delegaten in der `PrimeNumberCalculator` -Klasse, die verarbeitet die eigentliche Arbeit, die asynchron ausgeführt werden. Dieser Delegat umschließt die Workermethode, die testet, ob eine Zahl eine Primzahl ist. Nimmt der Delegat einer <xref:System.ComponentModel.AsyncOperation> Parameter, der verwendet wird, um die Lebensdauer eines asynchronen Vorgangs nachzuverfolgen.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  Erstellen Sie eine Sammlung für die Verwaltung der Lebensdauer der ausstehende asynchrone Vorgänge. Der Client benötigt eine Möglichkeit zum Nachverfolgen von Vorgängen verwendet werden kann, wie sie ausgeführt und abgeschlossen werden, und diese Überwachung erfolgt durch, dass der Client ein eindeutiges Token oder ein Task-ID übergeben, wenn der Client die die asynchrone Methode aufruft. Die `PrimeNumberCalculator` Komponente muss Nachverfolgen von jedem Aufruf vom entsprechenden Aufruf die Task-ID zuordnen. Wenn der Client eine Aufgaben-ID übergibt, die nicht eindeutig ist, ist die `PrimeNumberCalculator` Komponente eine Ausnahme ausgelöst werden muss.  
  
     Die `PrimeNumberCalculator` Komponente der nachverfolgt Task-ID mithilfe einer speziellen Auflistungsklasse aufgerufen eine <xref:System.Collections.Specialized.HybridDictionary>. Erstellen Sie in der Klassendefinition ein <xref:System.Collections.Specialized.HybridDictionary> aufgerufen `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Implementieren öffentliche Ereignisse  
 Komponenten, die das ereignisbasierte asynchrone Muster implementieren, kommunizieren mit Clients mithilfe von Ereignissen. Diese Ereignisse werden im entsprechenden Thread anhand des aufgerufen der <xref:System.ComponentModel.AsyncOperation> Klasse.  
  
#### <a name="to-raise-events-to-your-components-clients"></a>Zum Auslösen von Ereignissen für die Komponente Clients:  
  
1.  Implementieren Sie die öffentlichen Ereignisse für die Berichterstattung an Clients. Sie benötigen ein Ereignis für die Berichterstattung ausgeführt und eine für die Berichterstattung Abschluss.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Implementieren der Abschlussmethode  
 Die Delegaten für den Abschluss wird die Methode, mit der das zugrunde liegende, Freethread-Verhalten für den asynchronen aufgerufen wird, wenn nach erfolgreichem Abschluss, Fehler oder Abbruch der asynchrone Vorgang beendet. Dieser Aufruf erfolgt auf einen beliebigen Thread.  
  
 Diese Methode ist, in denen der Client-Task-ID aus der internen Auflistung der eindeutigen Clienttokens entfernt wird. Diese Methode beendet die Lebensdauer für einen bestimmten asynchronen Vorgang auch durch Aufrufen der <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> Methode des entsprechenden <xref:System.ComponentModel.AsyncOperation>. Dieser Aufruf löst das Abschlussereignis in dem Thread, der für das Anwendungsmodell geeignet ist. Nach der <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> -Methode aufgerufen wird, wird diese Instanz von <xref:System.ComponentModel.AsyncOperation> nicht mehr verwendet werden können, und nachfolgende wird eine Ausnahme auslösen.  
  
 Die `CompletionMethod` Signatur muss alle Zustände enthalten sind, um das Ergebnis des asynchronen Vorgangs zu beschreiben. Er behält den Status für die Zahl, die von dieser bestimmten asynchronen Vorgang getestet wurde, ob die Anzahl Primzahlen und der Wert der ersten Divisors ist, wenn es sich nicht um eine Primzahl ist. Außerdem enthält Sie alle aufgetretenen Ausnahme, Status und die <xref:System.ComponentModel.AsyncOperation> dieser bestimmten Aufgabe entspricht.  
  
#### <a name="to-complete-an-asynchronous-operation"></a>So schließen Sie einen asynchronen Vorgang ab:  
  
-   Implementieren Sie die Abschlussmethode. Dauert die sechs Parameter an, die verwendet wird, zum Auffüllen einer `CalculatePrimeCompletedEventArgs` an den Client über des Clients zurückgegebenen `CalculatePrimeCompletedEventHandler`. Task-ID-Token des Clients aus der internen Auflistung entfernt, und beendet den asynchronen Vorgang Lebensdauer mit einem Aufruf von <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. Die <xref:System.ComponentModel.AsyncOperation> marshallt den Aufruf an den Thread oder Kontext, der für das Anwendungsmodell geeignet ist.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Checkpoint  
 An diesem Punkt können Sie die Komponente zu erstellen.  
  
#### <a name="to-test-your-component"></a>So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
     Sie erhalten eine compilerwarnung:  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Diese Warnung wird im nächsten Abschnitt aufgelöst werden.  
  
## <a name="implementing-the-worker-methods"></a>Implementieren der Workermethoden  
 Sie haben bisher implementiert den unterstützenden asynchronen Code für die `PrimeNumberCalculator` Komponente. Jetzt können Sie den Code zu implementieren, der die eigentliche Arbeit übernimmt. Implementieren Sie drei Methoden: `CalculateWorker`, `BuildPrimeNumberList`, und `IsPrime`. Zusammen `BuildPrimeNumberList` und `IsPrime` bilden einen bekannten Algorithmus die Sieb des Eratosthenes, mit der bestimmt, ob eine Zahl eine Primzahl ist durch die Primzahlen bis die Quadratwurzel der Anzahl der Tests zu suchen. Wenn keine Teiler von diesem Punkt gefunden werden, ist die Anzahl der Tests eine Primzahl.  
  
 Wenn diese Komponente für maximaler Effizienz geschrieben wurden, würde es alle die von verschiedenen Aufrufe für viele verschiedene ermittelt Primzahlen Denken Sie daran. Sie würden auch für triviale Teiler z. B. 2, 3 und 5 überprüfen. Der Zweck dieses Beispiels wird veranschaulicht wie zeitaufwändige Operationen können asynchron ausgeführt, allerdings damit diese Optimierungen für Sie als Übung übrig sind.  
  
 Die `CalculateWorker` Methode wird in einem Delegaten umschlossen und mit einem Aufruf von asynchron aufgerufen `BeginInvoke`.  
  
> [!NOTE]
>  Fortschrittsberichterstattung implementiert wird, der `BuildPrimeNumberList` Methode. Auf schnellen Computern `ProgressChanged` Ereignisse können in schneller Folge ausgelöst werden. Der Client-Thread, auf dem diese Ereignisse ausgelöst werden, muss diese Situation zu behandeln. Code für die Benutzeroberfläche mit Nachrichten überflutet und kann nicht rechtzeitig verarbeitet, möglicherweise hängenden Verhalten führt. Eine Beispiel-Benutzeroberfläche, die diese Situation behandelt, finden Sie unter [Vorgehensweise: Implementieren eines Clients des ereignisbasierten asynchronen Musters](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Um die Berechnung Primzahl asynchron ausgeführt werden soll:  
  
1.  Implementieren der `TaskCanceled` Utility-Methode. Dies überprüft die Auflistung der Lebensdauer für die angegebene Aufgaben-ID und gibt `true` Wenn Task-ID nicht gefunden wird.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  Implementieren Sie die `CalculateWorker`-Methode. Es werden zwei Parameter: eine Zahl ein, um zu testen, und eine <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  Implementieren Sie `BuildPrimeNumberList`. Es werden zwei Parameter: die Anzahl der zu testen, und ein <xref:System.ComponentModel.AsyncOperation>. Er verwendet die <xref:System.ComponentModel.AsyncOperation> zum Fortschritt und inkrementelle Ergebnisse. Dadurch wird sichergestellt, dass die Ereignishandler des Clients auf den richtigen Thread oder Kontext Anwendungsmodells aufgerufen werden. Wenn `BuildPrimeNumberList` eine Primzahl findet, es meldet dies als inkrementelle Ergebnis an den Client-Ereignishandler für das `ProgressChanged` Ereignis. Dies erfordert, dass eine Klasse abgeleitet <xref:System.ComponentModel.ProgressChangedEventArgs>namens `CalculatePrimeProgressChangedEventArgs`, die über eine hinzugefügte Eigenschaft mit dem Namen `LatestPrimeNumber`.  
  
     Die `BuildPrimeNumberList` Methodenaufrufe in regelmäßigen Abständen die `TaskCanceled` -Methode und wird beendet, wenn die-Methode zurückgibt `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  Implementieren Sie `IsPrime`. Es verwendet drei Parameter: eine Liste der bekannten Primzahlen, die Anzahl der zu testen und ein Output-Parameter für den ersten gefundenen Divisor. Wenn Sie die Liste der Primzahlen, bestimmt, ob die Anzahl der Tests eine Primzahl ist.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  Leiten Sie `CalculatePrimeProgressChangedEventArgs` aus <xref:System.ComponentModel.ProgressChangedEventArgs>. Diese Klasse ist notwendig, damit der Client-Ereignishandler für inkrementelle Ergebnisse meldet die `ProgressChanged` Ereignis. Es wurde eine zusätzliche Eigenschaft mit dem Namen `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Checkpoint  
 An diesem Punkt können Sie die Komponente zu erstellen.  
  
#### <a name="to-test-your-component"></a>So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
     Alle bleibt zu schreibenden sind die Methoden zum Starten und Abbrechen von asynchronen Operationen `CalculatePrimeAsync` und `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Implementieren die Start- und Cancel-Methode  
 Sie starten die Workermethode in einem eigenen Thread, durch den Aufruf `BeginInvoke` für den Delegaten, der ihn umschließt. Rufen Sie zum Verwalten der Lebensdauer für einen bestimmten asynchronen Vorgang, der <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> Methode für die <xref:System.ComponentModel.AsyncOperationManager> Hilfsklasse. Dies gibt eine <xref:System.ComponentModel.AsyncOperation>, die Aufrufe an die Ereignishandler des Clients an den richtigen Thread oder Kontext gemarshallt.  
  
 "Abbrechen" eine bestimmte ausstehenden Vorgang durch Aufrufen von <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> auf das entsprechende <xref:System.ComponentModel.AsyncOperation>. Damit wird beendet, diesen Vorgang und alle nachfolgenden Aufrufe der <xref:System.ComponentModel.AsyncOperation> wird eine Ausnahme ausgelöst.  
  
#### <a name="to-implement-start-and-cancel-functionality"></a>Zu Anfang zu implementieren und Cancel-Funktion:  
  
1.  Implementieren Sie die `CalculatePrimeAsync`-Methode. Stellen Sie sicher, dass der Client bereitgestellte Token (Task-ID) in Bezug auf alle Tokens der derzeit ausstehenden Aufgaben eindeutig ist. Wenn der Client ein nicht eindeutiges Token übergibt `CalculatePrimeAsync` löst eine Ausnahme aus. Andernfalls wird das Token die Task-ID-Sammlung hinzugefügt.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  Implementieren Sie die `CancelAsync`-Methode. Wenn die `taskId` Parameter in der token-Auflistung vorhanden ist, wird es entfernt. Dies verhindert, dass abgebrochene Aufgaben, die Ausführung nicht gestartet wurden. Wenn der Task ausgeführt wird, die `BuildPrimeNumberList` Methode beendet wird, wenn er erkennt, dass die Aufgaben-ID aus der Auflistung der Lebensdauer entfernt wurde.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Checkpoint  
 An diesem Punkt können Sie die Komponente zu erstellen.  
  
#### <a name="to-test-your-component"></a>So testen Sie die Komponente  
  
-   Kompilieren Sie die Komponente.  
  
 Die `PrimeNumberCalculator` Komponente ist jetzt vollständig und einsatzbereit.  
  
 Ein Beispiel für einen Client, der verwendet die `PrimeNumberCalculator` Komponente finden Sie unter [Vorgehensweise: Implementieren eines Clients des ereignisbasierten asynchronen Musters](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Nächste Schritte  
 In diesem Beispiel füllen, indem Sie schreiben `CalculatePrime`, das Äquivalent zu synchronen `CalculatePrimeAsync` Methode. Dies veranlasst den `PrimeNumberCalculator` Komponente vollständig kompatibel mit dem ereignisbasierten asynchronen Muster.  
  
 Sie können in diesem Beispiel verbessern, indem Sie die Liste der alle von der verschiedenen Aufrufe für viele verschiedene ermittelt Primzahlen beibehalten. Bei dieser Vorgehensweise profitieren jede Aufgabe von der Arbeit, die von vorherigen Tasks. Achten Sie darauf, dass Sie diese Liste mit Schutz `lock` Regionen, damit der Zugriff auf die Liste von verschiedenen Threads serialisiert wird.  
  
 Sie können auch in diesem Beispiel verbessern, indem Sie Tests für triviale Teiler, z. B. 2, 3 und 5.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [NICHT im BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
