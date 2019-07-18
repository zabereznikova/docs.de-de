---
title: Threading-Modell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text on buttons [WPF], updating
- message processing [WPF], nested
- blocking operations [WPF]
- Common Language Runtime (CLR), locking mechanism
- locking mechanism of Common Language Runtime (CLR)
- threading model [WPF]
- Word [WPF], spelling checking
- button text [WPF], updating
- spelling checking in Word [WPF]
- asynchronous behavior [WPF], exposing
- nested message processing [WPF]
- reentrancy [WPF]
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
ms.openlocfilehash: c74d76cf7c216ed1d4d5c0741ed0ca4f651543e0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598626"
---
# <a name="threading-model"></a>Threading-Modell
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] soll Entwicklern bei Problemen mit Threading helfen. Als Ergebnis der meisten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Entwickler keine Schnittstelle schreiben, die mehr als einem Thread verwendet. Da Multithreadprogramme komplex und schwierig zu debuggen sind, sollten sie vermieden werden, wenn Singlethread-Lösungen vorhanden sind.  
  
 Ganz gleich, wie gut entworfen wurde, wird keine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Framework wird immer in der Lage, eine Singlethread-Lösung für jede Art von Problem bereitzustellen. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kommt dem nahe, aber es Situationen gibt, in denen mehrere Threads verbessern, weiterhin [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] -Reaktionsfähigkeit oder die Anwendungsleistung. In diesem Artikel werden zunächst einige Hintergrundinformationen angegeben, dann einige dieser Situationen beschrieben und am Ende einige Details auf niedriger Ebene besprochen.  

> [!NOTE]
>  In diesem Thema wird erläutert, threading mithilfe der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> Methode zum asynchronen Aufrufen. Sie können auch asynchrone Aufrufe vornehmen, durch den Aufruf der <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> -Methode, die nehmen ein <xref:System.Action> oder <xref:System.Func%601> als Parameter.  Die <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> Methode gibt eine <xref:System.Windows.Threading.DispatcherOperation> oder <xref:System.Windows.Threading.DispatcherOperation%601>, die eine <xref:System.Windows.Threading.DispatcherOperation.Task%2A> Eigenschaft. Können Sie die `await` -Schlüsselwort entweder mit der <xref:System.Windows.Threading.DispatcherOperation> oder mit dem zugehörigen <xref:System.Threading.Tasks.Task>. Wenn Sie synchron auf das <xref:System.Threading.Tasks.Task> warten müssen, das von <xref:System.Windows.Threading.DispatcherOperation> oder <xref:System.Windows.Threading.DispatcherOperation%601> zurückgegeben wird, rufen Sie die <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>-Erweiterungsmethode auf.  Aufrufen von <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> führt zu einem Deadlock. Weitere Informationen zur Verwendung einer <xref:System.Threading.Tasks.Task> zum Ausführen von asynchroner Vorgängen finden Sie unter Aufgabenparallelität.  Die <xref:System.Windows.Threading.Dispatcher.Invoke%2A> Methode verfügt auch über Überladungen, die eine <xref:System.Action> oder <xref:System.Func%601> als Parameter.  Sie können die <xref:System.Windows.Threading.Dispatcher.Invoke%2A> Methode zum Erstellen von synchronen Aufrufe durch Übergabe eines Delegaten <xref:System.Action> oder <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Übersicht und Verteiler  
 In der Regel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung beginnt mit zwei Threads: einer für das Rendering und einer für die Verwaltung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Das Renderingthread läuft effektiv verborgen im Hintergrund, während die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread Eingaben empfängt, behandelt Ereignisse, den Bildschirm zeichnet und Anwendungscode ausführt. Die meisten Anwendungen verwenden einen einzelnen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread, aber in einigen Situationen besser mehrere verwenden kann. Dies wird weiter unten mit einem Beispiel erläutert.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread stellt Arbeitsaufgaben in ein Objekt mit dem Namen einer <xref:System.Windows.Threading.Dispatcher>. Vom <xref:System.Windows.Threading.Dispatcher> werden Arbeitsaufgaben nach Priorität ausgewählt und jeweils vollständig ausgeführt.  Jede [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread muss über mindestens eine verfügen <xref:System.Windows.Threading.Dispatcher>, und jede <xref:System.Windows.Threading.Dispatcher> kann Arbeitsaufgaben in genau einem Thread ausführen.  
  
 Der Trick zum Erstellen von reaktionsfähigen und benutzerfreundlichen Anwendungen besteht darin zu maximieren der <xref:System.Windows.Threading.Dispatcher> Durchsatz, indem die Arbeitsaufgaben klein gehalten. Diese Elemente nicht veralten, wo der <xref:System.Windows.Threading.Dispatcher> Warteschlange, die Verarbeitung warten. Jede spürbare Verzögerung zwischen Eingabe und Antwort kann für einen Benutzer frustrierend sein.  
  
 Wie werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] soll, dass Anwendungen große Vorgänge verarbeiten? Was geschieht, wenn der Code eine aufwändige Berechnung beinhaltet oder eine Abfrage einer Datenbank auf einem Remoteserver ausführen muss? Die Antwort in der Regel ist, der umfangreiche Vorgang in einem eigenen Thread, wodurch die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread frei, um auf Elemente in der Regel die <xref:System.Windows.Threading.Dispatcher> Warteschlange. Wenn der umfangreiche Vorgang abgeschlossen ist, können sie melden, dass das Ergebnis an die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread für die Anzeige.  
  
 In der Vergangenheit [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ermöglicht [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nur von einem Thread den Zugriff auf Elemente, die sie erstellt wurden. Dies bedeutet, dass ein Hintergrundthread bei einer Aufgabe mit langer Laufzeit kein Textfeld aktualisieren kann, wenn er abgeschlossen ist. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ist diese Option, um die Integrität gewährleistet [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Komponenten. Ein Listenfeld könnte merkwürdig aussehen, wenn sein Inhalt während des Zeichnens von einem Hintergrundthread aktualisiert werden würde.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über einen integrierten gegenseitigen Ausschlussmechanismus, der diese Koordination erzwingt. Die meisten Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] abgeleitet <xref:System.Windows.Threading.DispatcherObject>. Während der Erstellung einer <xref:System.Windows.Threading.DispatcherObject> speichert einen Verweis auf die <xref:System.Windows.Threading.Dispatcher> mit dem aktuell ausgeführten Thread verknüpft. Faktisch sind die <xref:System.Windows.Threading.DispatcherObject> ordnet den Thread, der erstellt wird. Bei der programmausführung ein <xref:System.Windows.Threading.DispatcherObject> können rufen Sie den öffentlichen <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> Methode. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> überprüft die <xref:System.Windows.Threading.Dispatcher> den aktuellen Thread zugeordnet, und vergleicht ihn mit der <xref:System.Windows.Threading.Dispatcher> Referenz, die während der Konstruktion gespeichert. Wenn sie nicht übereinstimmen, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> löst eine Ausnahme aus. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> am Anfang jeder Methode aufgerufen werden soll eine <xref:System.Windows.Threading.DispatcherObject>.  
  
 Wenn nur ein Thread ändern, kann die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], wie interagieren Hintergrundthreads dann mit dem Benutzer? Ein Hintergrundthread lassen die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread zum Ausführen eines Vorgangs in dessen Auftrag aufzubauen. Dies geschieht durch Registrieren einer Arbeitsaufgabe mit der <xref:System.Windows.Threading.Dispatcher> von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Die <xref:System.Windows.Threading.Dispatcher> Klasse bietet zwei Methoden zum Registrieren von Arbeitsaufgaben: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> und <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Beide Methoden planen einen Delegaten für die Ausführung ein. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> ist ein synchroner Aufruf – d. h. die Rückgabe erst die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Threads tatsächlich beendet hat, den Delegaten ausführt. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> ist asynchron und gibt sofort zurück.  
  
 Die <xref:System.Windows.Threading.Dispatcher> sind die Elemente in seiner Warteschlange nach Priorität sortiert. Es gibt zehn Stufen, die beim Hinzufügen eines Elements angegeben werden können die <xref:System.Windows.Threading.Dispatcher> Warteschlange. Diese Prioritäten werden beibehalten, der <xref:System.Windows.Threading.DispatcherPriority> Enumeration. Detaillierte Informationen über <xref:System.Windows.Threading.DispatcherPriority> Ebenen finden Sie in der [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] Dokumentation.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Threads in Aktion: Die Beispiele  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Eine Singlethread-Anwendung mit einer Berechnung mit langer Laufzeit  
 Die meisten [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] verbringen einen Großteil ihrer Zeit im Leerlauf, beim Warten auf Ereignisse, die als Reaktion auf Benutzerinteraktionen generiert werden. Mit sorgfältiger Programmierung dieser Zeit im Leerlauf kann konstruktiv genutzt werden, ohne Auswirkungen auf die Reaktionsfähigkeit der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] threading-Modell nicht, dass eine Eingabe, um einen Vorgang im unterbrechen die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Dies bedeutet, dass Sie müssen Sie sicherstellen, dass zum Zurückgeben der <xref:System.Windows.Threading.Dispatcher> in regelmäßigen Abständen den Prozess ausstehende Eingabeereignisse, bevor sie veralten.  
  
 Betrachten Sie das folgende Beispiel:  
  
 ![Screenshot mit threading von Primzahlen.](./media/threading-model/threading-prime-numbers.png)  
  
 Diese einfache Anwendung zählt ab drei aufwärts und sucht dabei nach Primzahlen. Klickt der Benutzer die **starten** Schaltfläche, um die Suche beginnt. Wenn das Programm eine Primzahl findet, wird die Benutzeroberfläche mit dieser Entdeckung aktualisiert. Der Benutzer kann die Suche zu jedem Zeitpunkt beenden.  
  
 Obwohl es sich um eine einfache Anwendung handelt, könnte die Suche nach Primzahlen endlos fortgesetzt werden, was einige Probleme bereitet.  Wenn wir die gesamte Suche innerhalb der Click-Ereignishandler der Schaltfläche verarbeitet, würden wir nie geben die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread die Möglichkeit, andere Ereignisse zu verarbeiten. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nicht zur Reaktion auf Eingabe oder Prozess Nachrichten. Sie würde nie neu zeichnen und nie auf Mausklicks auf die Schaltflächen reagieren.  
  
 Wir könnten die Suche nach Primzahlen in einem separaten Thread ausführen, aber dann hätten wir Synchronisierungsprobleme. Mit einem Singlethread-Ansatz können wir die Bezeichnung, die die größte gefundene Primzahl auflistet, direkt aktualisieren.  
  
 Wenn der Task, der Berechnung in verwaltbare Teile aufgeteilt wird, können wir in regelmäßigen Abständen zurück zu den <xref:System.Windows.Threading.Dispatcher> und Verarbeiten von Ereignissen. Können wir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Gelegenheit, zu zeichnen und Eingaben zu verarbeiten.  
  
 Die beste Möglichkeit, Verarbeitungszeit auf Berechnung und Ereignisbehandlung aufzuteilen wird zum Verwalten der Berechnung von der die <xref:System.Windows.Threading.Dispatcher>. Mithilfe der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> -Methode, wir können primzahlüberprüfungen in identisch, die in die Warteschlange [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -Ereignisse stammen. In unserem Beispiel planen wir nur eine einzige Primzahlüberprüfung zu einem Zeitpunkt ein. Nach Abschluss der Primzahlüberprüfung planen wir sofort die nächste Überprüfung ein. Diese Überprüfung erfolgt erst, wenn ausstehende [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] behandelt wurden.  
  
 ![Screenshot mit der Dispatcher-Warteschlange.](./media/threading-model/threading-dispatcher-queue.png)  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] führt die Rechtschreibprüfung mithilfe dieses Mechanismus durch. Rechtschreibprüfung erfolgt im Hintergrund die Leerlaufzeit an, der über die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Sehen wir uns den Code an.  
  
 Das folgende Beispiel zeigt die XAML, die die Benutzeroberfläche erstellt.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 Im folgenden Beispiel wird das CodeBehind gezeigt.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 Das folgende Beispiel zeigt den Ereignishandler für die <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Neben dem Aktualisieren des Textes auf der <xref:System.Windows.Controls.Button>, dieser Handler ist verantwortlich für die Planung der ersten primzahlüberprüfung durch Hinzufügen eines Delegaten, der <xref:System.Windows.Threading.Dispatcher> Warteschlange. Manchmal, nachdem dieser Ereignishandler seine Arbeit abgeschlossen hat die <xref:System.Windows.Threading.Dispatcher> dieses Delegaten für die Ausführung auswählen.  
  
 Wie bereits erwähnt <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> ist die <xref:System.Windows.Threading.Dispatcher> Member verwendet, um einen Delegaten für die Ausführung planen. In diesem Fall wählen wir die <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> Priorität. Die <xref:System.Windows.Threading.Dispatcher> führt diesen Delegaten nur, wenn keine wichtigen Ereignisse zu verarbeiten. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Reaktionsfähigkeit ist wichtiger als die Zahlenüberprüfung. Wir übergeben auch einen neuen Delegaten, der die Zahlenüberprüfungsroutine darstellt.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Diese Methode überprüft, ob die nächste ungerade Zahl eine Primzahl ist. Wenn sie eine Primzahl ist, aktualisiert die Methode direkt die `bigPrime` <xref:System.Windows.Controls.TextBlock> entsprechend. Dies ist möglich, da die Berechnung im selben Thread ausgeführt wird, der für die Erstellung der Komponente verwendet wurde. Hatten wir uns entschieden, einen separaten Thread für die Berechnung verwendet, müssten wir einen komplizierteren Synchronisierungsmechanismus verwenden, und führen Sie das Update in der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Wir werden diese Situation im Folgenden zeigen.  
  
 Den vollständigen Quellcode für dieses Beispiel, finden Sie unter den [Single-Threaded Application with Long-Running Calculation Sample](https://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Behandeln eines blockierenden Vorgangs mit einem Hintergrundthread  
 Die Behandlung von blockierenden Vorgängen in einer grafischen Anwendung kann schwierig sein. Wir wollen keine blockierenden Methoden von Ereignishandlern aufrufen, da die Anwendung sonst scheinbar einfriert. Wir können einen separaten Thread verwenden, um diese Vorgänge zu behandeln, aber wenn wir fertig sind, haben wir zum Synchronisieren mit der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread auf, da wir nicht direkt ändern können die [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] vom Arbeitsthread aus. Wir können <xref:System.Windows.Threading.Dispatcher.Invoke%2A> oder <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> zum Einfügen von Delegaten in der <xref:System.Windows.Threading.Dispatcher> von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Schließlich werden diese Delegaten ausgeführt werden, mit der Berechtigung zum Ändern der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente.  
  
 In diesem Beispiel simulieren wir einen Remoteprozeduraufruf, der eine Wettervorhersage abruft. Wir verwenden einen separaten Arbeitsthread aus, um die Ausführung dieses Aufrufs und planen wir eine Updatemethode in der <xref:System.Windows.Threading.Dispatcher> von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Threads ein, wenn wir fertig sind.  
  
 ![Screenshot mit dem Wetter-UI.](./media/threading-model/threading-weather-ui.png)  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 Im Folgenden sind einige der Details aufgeführt, die beachtet werden sollten.  
  
- Erstellen des Schaltflächenhandlers  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 Wenn auf die Schaltfläche geklickt wird, wird die Uhr-Zeichnung angezeigt, und wir beginnen mit der Animation. Die Schaltfläche wird deaktiviert. Rufen wir die `FetchWeatherFromServer` -Methode in einen neuen Thread und anschließend zurück, sodass die <xref:System.Windows.Threading.Dispatcher> zum Verarbeiten von Ereignissen während wir auf die Wettervorhersage warten.  
  
- Abrufen der Wettervorhersage  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Aus Gründen der Einfachheit verwenden wir in diesem Beispiel keinen Netzwerk-Code. Stattdessen simulieren wir die Verzögerung des Netzwerkzugriffs, indem wir den neuen Thread für vier Sekunden in den Ruhezustand versetzen. In dieser Zeit wird die ursprüngliche [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread noch ausgeführt wird und auf Ereignisse reagieren. Um dies zu zeigen, führen wir eine Animation weiterhin aus, und die Schaltflächen „Minimieren“ und „Maximieren“ funktionieren ebenfalls weiterhin.  
  
 Wenn die Verzögerung beendet, und wir die Wettervorhersage zufällig ausgewählt haben, ist es Zeit, zurückzumelden der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Wir erreichen dies durch Planen eines Aufrufs von `UpdateUserInterface` in die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread mithilfe des betreffenden Threads <xref:System.Windows.Threading.Dispatcher>. Wir übergeben eine Zeichenfolge, die das Wetter beschreibt, an diesen eingeplanten Methodenaufruf.  
  
- Aktualisieren der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Wenn die <xref:System.Windows.Threading.Dispatcher> in die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread Zeit hat, führt er den eingeplanten Aufruf von `UpdateUserInterface`. Diese Methode hält die Uhr-Animation an und wählt ein Bild aus, um das Wetter zu beschreiben. Sie zeigt dieses Bild an und stellt die Schaltfläche „fetch forecast“ (Wettervorhersage abrufen) wieder her.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Mehrere Fenster, mehrere Threads  
 Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen erfordern mehrere Fenster von der obersten Ebene. Es ist durchaus akzeptabel, dass ein Thread /<xref:System.Windows.Threading.Dispatcher> Tastenkombination, um mehrere Fenster verwaltet, aber manchmal mehrere Threads besser funktionieren. Dies trifft besonders zu, wenn die Möglichkeit besteht, dass eines der Fenster den Thread für sich beansprucht.  
  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Explorer funktioniert auf diese Weise. Jedes neue Explorer-Fenster gehört zum ursprünglichen Prozess, wird jedoch unter der Kontrolle eines unabhängigen Threads erstellt.  
  
 Mithilfe einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> -Steuerelement, können wir Webseiten anzeigen. Wir können problemlos erstellen eine einfache [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] ersetzen. Wir beginnen mit einer wichtigen Funktion, und zwar der Möglichkeit, ein neues Explorerfenster zu öffnen. Wenn der Benutzer auf die Schaltfläche „Neues Fenster“ klickt, starten wir eine Kopie des Fensters in einem separaten Thread. Auf diese Weise sperren lange andauernde oder blockierende Vorgänge in einem der Fenster nicht alle anderen Fenster.  
  
 In Wirklichkeit verfügt das Webbrowser-Modell über ein eigenes kompliziertes Threadingmodell. Wir haben uns dafür entschieden, da die meisten Leser damit vertraut sein sollten.  
  
 Im folgenden Beispiel wird der Code angezeigt.  
  
 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 Die folgenden Threadingsegmente dieses Codes sind für uns in diesem Kontext am interessantesten:  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 Diese Methode wird aufgerufen, wenn die Schaltfläche „Neues Fenster“ angeklickt wird. Sie erstellt einen neuen Thread und startet diesen asynchron.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 Diese Methode ist der Ausgangspunkt für den neuen Thread. Wir erstellen ein neues Fenster unter der Kontrolle dieses Threads. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erstellt automatisch eine neue <xref:System.Windows.Threading.Dispatcher> um den neuen Thread zu verwalten. Alles, was wir tun, um das Fenster funktionsfähig ist, starten Sie den <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Technische Details und Stolpersteine  
  
### <a name="writing-components-using-threading"></a>Schreiben von Komponenten mithilfe von Threading  
 Microsoft .NET Framework Developer's Guide Beschreibt ein Muster wie eine Komponente asynchrones Verhalten für die Clients verfügbar machen kann (siehe [Übersicht über ereignisbasierte asynchrone Muster](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Nehmen wir beispielsweise an, wir wollten zum Packen der `FetchWeatherFromServer` Methode in eine wiederverwendbare, nichtgrafische Komponente. Nach dem standardmäßigen Microsoft .NET Framework-Muster würde dies etwa wie folgt aussehen.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` würde eine der zuvor beschriebenen Techniken wie z.B. das Erstellen eines Hintergrundthreads verwenden, um die Arbeit asynchron auszuführen und den aufrufenden Thread nicht zu blockieren.  
  
 Einer der wichtigsten Teile dieses Musters ist der Aufruf der *MethodName* `Completed` Methode auf dem gleichen Thread, der Namen der *MethodName* `Async` Methode damit beginnt, mit. Könnte dazu verwenden Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] relativ einfach erreichen, indem Sie speichern <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>– klicken Sie dann die nichtgrafische Komponente kann nur verwendet werden, aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen nicht in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] Programme.  
  
 Der <xref:System.Windows.Threading.DispatcherSynchronizationContext> -Klasse erfüllt diese Anforderung — betrachten Sie sie als eine vereinfachte Version der <xref:System.Windows.Threading.Dispatcher> dieses Produkt funktioniert mit anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] auch Frameworks.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Geschachtelte Verteilung  
 Manchmal ist es nicht möglich, völlig gesperrt ist, bis die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Betrachten wir die <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse. <xref:System.Windows.MessageBox.Show%2A> Gibt nicht zurück, bis der Benutzer die Schaltfläche "OK" klickt. Es wird jedoch ein Fenster erstellt, das über eine Meldungsschleife verfügen muss, um interaktiv zu sein. Während wir warten, bis der Benutzer auf „OK“ klickt, reagiert das ursprüngliche Anwendungsfenster nicht auf Benutzereingaben. Es verarbeitet jedoch weiterhin Paint-Meldungen. Das ursprüngliche Fenster zeichnet sich selbst neu, wenn es verdeckt war und dann wieder angezeigt wird.  
  
 ![Screenshot, der eine MessageBox mit Schaltfläche "OK" anzeigt](./media/threading-model/threading-message-loop.png)  
  
 Ein Thread muss für das Meldungsfenster zuständig sein. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] könnte einen neuen Thread nur für das Meldungsfenster erstellen, aber dieser Thread wäre nicht in der Lage, die deaktivierten Elemente im ursprünglichen Fenster zu zeichnen (beachten Sie den bereits erwähnten gegenseitigen Ausschluss). Stattdessen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein geschachteltes meldungsverarbeitungssystem. Die <xref:System.Windows.Threading.Dispatcher> Klasse enthält eine spezielle Methode namens <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, dem aktuellen Ausführungspunkt in einer Anwendung speichert eine neue Meldungsschleife beginnt. Nach Abschluss die geschachtelten Meldungsschleife Ausführung fortgesetzt wird, nach dem ursprünglichen <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> aufrufen.  
  
 In diesem Fall <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> behält den Programmkontext beim Aufruf <xref:System.Windows.MessageBox>.<xref:System.Windows.MessageBox.Show%2A>, und beginnt eine neue Meldungsschleife, um das Hintergrundfenster und Eingaben für das Meldungsfenster zu behandeln. Wenn der Benutzer auf OK klickt und das Popupfenster löscht, die geschachtelte Schleife beendet und die Steuerung wird nach dem Aufruf von <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Veraltete Routingereignisse  
 Das Routingereignissystem in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] benachrichtigt ganze Strukturen, wenn Ereignisse ausgelöst werden.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 Wenn die linke Maustaste, über die Ellipse gedrückt wird, `handler2` ausgeführt wird. Nach dem `handler2` beendet ist ist, das Ereignis wird an übergeben, die <xref:System.Windows.Controls.Canvas> -Objekt, das verwendet `handler1` , sie zu verarbeiten. Dies geschieht nur, wenn `handler2` ist nicht explizit Mark stattdessen das Ereignis als behandelt.  
  
 Es ist möglich, `handler2` wird sehr viel Zeit, die dieses Ereignis zu verarbeiten. `handler2` Verwenden Sie möglicherweise <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> um eine geschachtelte Meldungsschleife zu beginnen, die keinen Stunden zurückgibt. Wenn `handler2` nicht kennzeichnet das Ereignis als behandelt, wenn diese Meldungsschleife ist abgeschlossen, wird das Ereignis der Struktur nach oben übergeben, obwohl es sehr alt ist.  
  
### <a name="reentrancy-and-locking"></a>Wiedereintritt und Sperrung  
 Der Mechanismus zum Sperren von der [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] verhält Sie sich nicht genau wie man sich vorstellen könnte; man könnte erwarten, dass einen Thread beim Anfordern einer Sperre den Vorgang vollständig beendet. In Wirklichkeit empfängt und verarbeitet der Thread weiterhin Meldungen mit hoher Priorität. Dadurch können Deadlocks vermieden und Schnittstellen minimal reaktionsfähig gemacht werden, aber dadurch können auch schwer erkennbare Fehler entstehen.  Der Großteil der Zeit nicht alles wissen, dass zu diesem, aber in seltenen Fällen müssen (normalerweise im Zusammenhang mit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] fenstermeldungen oder COM-STA-Komponenten) Entwurfsalternativen infrage.  
  
 Die meisten Schnittstellen werden nicht mit der im Hinblick auf Threadsicherheit erstellt, da Entwickler bei Ihrer Arbeit, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nie durch mehrere Threads zugegriffen wird. In diesem Fall ist der Singlethread Umweltbelastung zu unerwarteten Zeiten ändern kann diese falsch verursacht, die Auswirkungen der <xref:System.Windows.Threading.DispatcherObject> soll gegenseitige Ausschlussmechanismus um zu lösen. Betrachten Sie den folgenden Pseudocode:  
  
 ![Diagramm, das threading Eintrittsinvarianz angezeigt wird. ](./media/threading-model/threading-reentrancy.png "ThreadingReentrancy")  
  
 In den meisten Fällen das ist richtig, aber es gibt Situationen, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , in denen solch ein unerwarteter Wiedereintritt kann wirklich zu Problemen führen. In diesem Fall zu bestimmten Zeiten, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Aufrufe <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, welche Änderungen die sperranweisung für diesen Thread so die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Sperre Wiedereintritt anstatt der üblichen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Sperre.  
  
 Warum wurde die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Team dieses Verhalten entschieden? Dies hatte mit COM-STA-Objekten und dem Finalizerthread zu tun. Wenn ein Objekt mit Garbage Collection, ist die `Finalize` -Methode nicht auf dem dedizierten Finalizerthread ausgeführt wird die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Und darin liegt das Problem, da eine COM-STA-Objekt, das erstellt wurde, auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread kann nur freigegeben werden, auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] entspricht einem <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (in diesem Fall von Win32 `SendMessage`). Wenn Sie allerdings die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread ausgelastet ist, der Finalizer-Thread wurde unterbrochen, und das COM-STA-Objekt nicht verworfen werden, die einen schwerwiegenden Speicherverlust erstellt. Daher [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Team für diesen Aufruf entschieden, damit Sperren wie gewünscht dies der Fall.  
  
 Die Aufgabe für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besteht darin, unerwarteten Wiedereintritt zu verhindern, ohne Speicherverlust zu, weshalb wir Wiedereintritt nicht überall blockieren.  
  
## <a name="see-also"></a>Siehe auch

- [Single-Threaded Application with Long-Running Calculation Sample (Singlethread-Anwendung mit Beispiel für Berechnung mit langer Laufzeit)](https://go.microsoft.com/fwlink/?LinkID=160038)
