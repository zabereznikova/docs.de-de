---
title: "Threading-Modell | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Text auf Schaltflächen, aktualisieren"
  - "Nachricht verarbeiten, geschachtelt"
  - "Blockierungsvorgänge"
  - "Dispatcher-Klasse"
  - "Sperrmechanismus Common Language Runtime (CLR)"
  - "Sperrmechanismus der Common Language Runtime (CLR)"
  - "Threadingmodell"
  - "DependencyObject-Klassen"
  - "Word, Rechtschreibprüfung"
  - "Schaltfläche Text aktualisieren"
  - "Rechtschreibprüfung in Word"
  - "asynchrones Verhalten verfügbar machen"
  - "DependencyObject-Klasse"
  - "Geschachtelte Meldungsverarbeitung"
  - "Dispatcher-Klassen"
  - "Wiedereintreten"
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Threading-Modell
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Dient zum Speichern der Entwickler aus den Problemen von threading. Folglich müssen die meisten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Entwickler müssen eine Schnittstelle zu schreiben, mehrere Threads verwendet. Da Multithreadprogramme komplex und schwierig zu debuggen sind, sollten sie vermieden werden, wenn Singlethread-Lösungen vorhanden sind.  
  
 Ganz gleich, wie gut entworfen, jedoch keine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Framework Lage, um eine Singlethread-Lösung für jede Art von Problem bereitzustellen.              [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]mithalten, aber es jedoch Situationen denkbar sind, in denen mehrere Threads verbessern [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Leistung Reaktionsfähigkeit oder Anwendung. Nach erörtert, dieses Dokument beschreibt einige dieser Situationen und dann endet mit einer Diskussion einige Details auf niedrigerer Ebene.  
  
   
  
> [!NOTE]
>  In diesem Thema wird erläutert, threading mithilfe der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> Methode zum asynchronen Aufrufen. Sie können auch asynchrone Aufrufe vornehmen, durch Aufrufen der <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> -Methode, die Nutzen einer <xref:System.Action> oder <xref:System.Func%601> als Parameter.  Die <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> -Methode gibt ein <xref:System.Windows.Threading.DispatcherOperation> oder <xref:System.Windows.Threading.DispatcherOperation%601>, die eine <xref:System.Windows.Threading.DispatcherOperation.Task%2A> Eigenschaft. Können Sie die `await` Schlüsselwort entweder mit der <xref:System.Windows.Threading.DispatcherOperation> oder mit dem zugehörigen <xref:System.Threading.Tasks.Task>. Synchrone warten möchten die <xref:System.Threading.Tasks.Task> zurückgegeben wird ein <xref:System.Windows.Threading.DispatcherOperation> oder <xref:System.Windows.Threading.DispatcherOperation%601>, rufen Sie die <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> -Erweiterungsmethode.  Aufrufen von <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> wird zu einem Deadlock führen. Weitere Informationen zur Verwendung einer <xref:System.Threading.Tasks.Task> zum Ausführen von asynchronen Vorgängen finden Sie unter Aufgabenparallelität.  Die <xref:System.Windows.Threading.Dispatcher.Invoke%2A> -Methode verfügt auch über Überladungen, die eine <xref:System.Action> oder <xref:System.Func%601> als Parameter.  Können Sie die <xref:System.Windows.Threading.Dispatcher.Invoke%2A> durch Übergabe eines Delegaten zu synchronen Methodenaufrufe <xref:System.Action> oder <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Übersicht und Verteiler  
 In der Regel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen beginnen mit zwei Threads: eine für die Behandlung von Rendering- und eine andere für die Verwaltung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Der Renderingthread läuft effektiv verborgen im Hintergrund während der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread Eingaben empfängt, Ereignisse behandelt, den Bildschirm zeichnet und Anwendungscode ausführt. Die meisten Anwendungen verwenden eine einzelne [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread, die zwar in manchen Situationen sollten Sie mehrere verwenden. Dies erläutert mit einem Beispiel weiter unten.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread stellt Arbeitsaufgaben in einem Objekt namens ein <xref:System.Windows.Threading.Dispatcher>. Die <xref:System.Windows.Threading.Dispatcher> wählt Arbeitsaufgaben nach Priorität und führt jede Aufgabe bis zum Abschluss.  Jede [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread müssen mindestens eine <xref:System.Windows.Threading.Dispatcher>, und jede <xref:System.Windows.Threading.Dispatcher> kann Arbeitsaufgaben in genau einem Thread ausführen.  
  
 Der Trick beim Erstellen von reaktionsfähigen und benutzerfreundliche besteht zum Maximieren der <xref:System.Windows.Threading.Dispatcher> Durchsatz von Arbeitsaufgaben klein zu halten. Diese Elemente veralten der <xref:System.Windows.Threading.Dispatcher> Warteschlange Verarbeitung warten. Jede spürbare Verzögerung zwischen Eingabe und Antwort kann einen Benutzer frustrierend sein.  
  
 Wie werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Applikationen big Vorgänge verarbeiten soll? Was geschieht, wenn Ihr Code Berechnung eine aufwändige oder Abfrage einer Datenbank auf einem Remoteserver muss? Die Antwort ist normalerweise der umfangreiche Vorgang in einen separaten Thread, sodass die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread frei, um auf Elemente in der Regel die <xref:System.Windows.Threading.Dispatcher> Warteschlange. Wenn der umfangreiche Vorgang abgeschlossen ist, meldet sie das Ergebnis an die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread für die Anzeige.  
  
 In der Vergangenheit [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] können [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nur von dem Thread den Zugriff auf Elemente, die sie erstellt wurden. Dies bedeutet, dass ein Hintergrundthread für eine lang ausgeführte Aufgabe ein Textfeld aktualisieren kann, wenn er abgeschlossen ist.                  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]tut dies, um die Datenintegrität sicherzustellen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Komponenten. Ein Listenfeld könnte merkwürdig aussehen, wenn sein Inhalt während des Zeichnens von einem Hintergrundthread aktualisiert wurden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verfügt über einen integrierten gegenseitigen Ausschluss-Mechanismus, der diese Koordination erzwingt. Die meisten Klassen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ableiten <xref:System.Windows.Threading.DispatcherObject>. Bei der Konstruktion einer <xref:System.Windows.Threading.DispatcherObject> speichert einen Verweis auf die <xref:System.Windows.Threading.Dispatcher> mit den derzeit ausgeführten Thread verknüpft. Im Endeffekt die <xref:System.Windows.Threading.DispatcherObject> ordnet dem Thread, der es erstellt. Während der Ausführung des Programms einer <xref:System.Windows.Threading.DispatcherObject> können rufen Sie den öffentlichen <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> Methode.                  <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> untersucht die <xref:System.Windows.Threading.Dispatcher> dem aktuellen Thread zugeordnet, und vergleicht ihn mit der <xref:System.Windows.Threading.Dispatcher> Referenz während der Konstruktion gespeichert. Wenn sie nicht übereinstimmen, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> löst eine Ausnahme aus.                  <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> am Anfang jeder Methode aufgerufen werden soll eine <xref:System.Windows.Threading.DispatcherObject>.  
  
 Wenn nur ein Thread ändern, kann die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], wie interagieren Hintergrundthreads mit dem Benutzer? Ein Hintergrundthread kann Fragen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread einen Vorgang in seinem Auftrag auszuführen. Dies geschieht durch Registrieren einer Arbeitsaufgabe mit der <xref:System.Windows.Threading.Dispatcher> von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Die <xref:System.Windows.Threading.Dispatcher> Klasse bietet zwei Methoden zum Registrieren von Arbeitsaufgaben: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> und <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Beide Methoden planen einen Delegaten für die Ausführung.                  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> ist ein synchroner Aufruf – d. h. es nicht erst zurückgegeben, wenn die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread tatsächlich die Ausführung des Delegaten beendet hat.                  <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> ist asynchron und kehrt sofort zurück.  
  
 Die <xref:System.Windows.Threading.Dispatcher> ordnet die Elemente in seiner Warteschlange nach Priorität. Es gibt zehn Ebenen, die angegeben werden können, wenn Sie ein Element hinzufügen die <xref:System.Windows.Threading.Dispatcher> Warteschlange. Diese Prioritäten werden beibehalten, der <xref:System.Windows.Threading.DispatcherPriority> Enumeration. Detaillierte Informationen über <xref:System.Windows.Threading.DispatcherPriority> Ebenen finden Sie in der [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] Dokumentation.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Threads in Aktion: Beispiele  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Ein Singlethread-Anwendung mit einer lang andauernde Berechnung  
 Die meisten [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] verbringen einen Großteil ihrer Zeit im Leerlauf, beim Warten auf Ereignisse, die in Reaktion auf Benutzerinteraktionen generiert werden. Mit eine sorgfältige Programmierung die Leerlaufzeit kann verwendet werden, konstruktiv, ohne die Reaktionsfähigkeit der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Threadmodell lässt nicht die Eingabe für einen Vorgang im Unterbrechen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Sie müssen daher sicher, dass zum Zurückgeben der <xref:System.Windows.Threading.Dispatcher> in regelmäßigen Abständen den Prozess ausstehende Eingabeereignisse, bevor sie veralten.  
  
 Betrachten Sie das folgende Beispiel:  
  
 ![Screenshot der Primzahlen](../../../../docs/framework/wpf/advanced/media/threadingprimenumberscreenshot.PNG "ThreadingPrimeNumberScreenShot")  
  
 Diese einfache Anwendung zählt nach oben von Primzahlen werden drei, gesucht. Klickt der Benutzer die **Start** Schaltfläche, um die Suche beginnt. Wenn das Programm eine Primzahl findet, wird die Benutzeroberfläche mit seiner Entdeckung aktualisiert. Zu jedem Zeitpunkt kann der Benutzer die Suche beenden.  
  
 Zwar einfach, endlos Primzahl Suche endlos, der einige Probleme bietet.  Wenn wir die gesamte Suche innerhalb der Click-Ereignishandler der Schaltfläche behandelt, würden wir nie geben die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread andere Ereignisse behandelt. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wäre nicht reagieren Eingabe-oder Prozess Nachrichten. Es würde nie neu gezeichnet und nie auf Mausklicks reagiert.  
  
 Wir konnten die Suche Primzahl in einem separaten Thread, aber dann müssten Synchronisierungsprobleme abgefangen. Mit einem Singlethread-Ansatz können wir die Bezeichnung, die die größte gefundene Primzahl auflistet, direkt aktualisieren.  
  
 Wenn die in verwaltbare Teile aufgeteilt wird, können wir in regelmäßigen Abständen zurück zu den <xref:System.Windows.Threading.Dispatcher> und Verarbeiten von Ereignissen. Wir erhalten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Gelegenheit, zu zeichnen und die Eingabe verarbeitet.  
  
 Ist die beste Möglichkeit, Verarbeitungszeit zwischen der Berechnung und der Ereignisbehandlung aufzuteilen Berechnung von der Verwaltung der <xref:System.Windows.Threading.Dispatcher>. Mithilfe der <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> -Methode, planen wir Primzahl checkt identisch, die in die Warteschlange [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Ereignisse entnommen werden. In unserem Beispiel planen wir nur eine einzelne Primzahl Überprüfung zu einem Zeitpunkt. Nach Abschluss der Überprüfung der Primzahl planen wir sofort die nächste Prüfung. Diese Überprüfung erfolgt, nachdem ausstehende [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] behandelt wurden.  
  
 ![Darstellung der Dispatcher-Warteschlange](../../../../docs/framework/wpf/advanced/media/threadingdispatcherqueue.PNG "ThreadingDispatcherQueue")  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)]führt die Rechtschreibprüfung mithilfe dieses Mechanismus. Die Rechtschreibprüfung ausgeführt wird, im Hintergrund in der Leerlaufzeit des der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Betrachten wir nun den Code.  
  
 Das folgende Beispiel zeigt den XAML-Code, der die Benutzeroberfläche erstellt.  
  
 [!code-xml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 Das folgende Beispiel zeigt den Code-Behind.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 Im folgenden Beispiel wird des ereignishandlers für das <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Neben dem Aktualisieren des Textes in der <xref:System.Windows.Controls.Button>, dieser Handler ist verantwortlich für die Planung der ersten Primzahl Überprüfung durch Hinzufügen ein Delegaten an die <xref:System.Windows.Threading.Dispatcher> Warteschlange. Nachdem dieser Ereignishandler seine Arbeit abgeschlossen hat die <xref:System.Windows.Threading.Dispatcher> wählt diesen Delegaten zur Ausführung.  
  
 Wie bereits erwähnt <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> ist die <xref:System.Windows.Threading.Dispatcher> Member, mit dem ein Delegat zur Ausführung geplant. In diesem Fall wählen wir die <xref:System.Windows.Threading.DispatcherPriority> Priorität. Die <xref:System.Windows.Threading.Dispatcher> führt diesen Delegaten nur dann, wenn keine wichtigen zu verarbeitenden Ereignisse.                          [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Reaktionsfähigkeit ist wichtiger als die Zahl Prüfung. Wir übergeben auch einen neuen Delegaten, der die Routine Anzahl überprüfen darstellt.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Diese Methode überprüft, ob die nächste ungerade Zahl eine Primzahl ist. Wenn Primzahl ist, aktualisiert die Methode direkt den `bigPrime` <xref:System.Windows.Controls.TextBlock> entsprechend seiner Entdeckung. Dies ist möglich, da die Berechnung im selben Thread ausgeführt wird, die zum Erstellen der Komponente verwendet wurde. Haben wir uns entschieden, einen separaten Thread für die Berechnung verwenden, müssten wir verwenden einen Synchronisierungsmechanismus komplizierteren, und führen das Update in der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Wir werden dies im folgenden dargestellt.  
  
 Den vollständigen Quellcode für dieses Beispiel finden Sie unter der [Single-Threaded Application with Long-Running Calculation Sample](http://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Behandeln einen blockierenden Vorgang mit einem Hintergrundthread  
 Behandlung von blockierenden Vorgänge in einer grafischen Anwendung kann schwierig sein. Wir möchten nicht blockierende Methoden von Ereignishandler aufrufen, da die Anwendung angezeigt werden, hängen. Verwenden wir einen eigenen Thread, um diese Vorgänge zu behandeln, aber wir haben eine Synchronisierung mit der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread auf, da direkt geändert werden kann die [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] vom Arbeitsthread aus. Verwenden wir <xref:System.Windows.Threading.Dispatcher.Invoke%2A> oder <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> einzufügende Delegaten in der <xref:System.Windows.Threading.Dispatcher> von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Letztlich werden diese Delegaten ausgeführt werden, mit der Berechtigung zum Ändern [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente.  
  
 In diesem Beispiel soll einen Remoteprozeduraufruf, der eine Wettervorhersage abrufen. Mithilfe eines separaten Arbeitsthreads dieser Aufruf ausgeführt, und planen wir eine Updatemethode in der <xref:System.Windows.Threading.Dispatcher> von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread, wenn wir fertig sind.  
  
 ![Wetter-Benutzeroberfläche Screenshot](../../../../docs/framework/wpf/advanced/media/threadingweatheruiscreenshot.png "ThreadingWeatherUIScreenShot")  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 Im folgenden sind einige Details, die beachtet werden.  
  
-   Erstellen den Ereignishandler der Schaltfläche  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 Wenn die Schaltfläche geklickt wird, werden wir die Uhr Zeichnung und Animation starten. Die Schaltfläche wird deaktiviert. Aufgerufen der `FetchWeatherFromServer` -Methode in einen neuen Thread und anschließend zurück, sodass die <xref:System.Windows.Threading.Dispatcher> Ereignisse verarbeiten, während auf die Wettervorhersage gewartet.  
  
-   Abrufen der Wettervorhersage  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Aus Gründen der Einfachheit, müssen wir nicht unbedingt alle Netzwerk-Code in diesem Beispiel. Stattdessen wird die Verzögerung des Netzwerkzugriffs durch Festlegen des neuen Threads für vier Sekunden in den Ruhezustand simulieren. In dieser Zeit wird der ursprüngliche [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread noch ausgeführt wird und auf Ereignisse reagiert. Um zu verdeutlichen, wir eine Animation ausgeführt wird, und minimieren und Maximieren weiterhin Schaltflächen auch funktionieren.  
  
 Wenn die Verzögerung beendet wird und die Wettervorhersagen zufällig ausgewählt wurden, ist es Zeit zum Bericht der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Wir erreichen dies durch einen Aufruf von Planung `UpdateUserInterface` in der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread mithilfe des betreffenden Threads <xref:System.Windows.Threading.Dispatcher>. Wir übergeben Sie eine Zeichenfolge, die das Wetter für diesen geplanten Methodenaufruf beschreibt.  
  
-   Aktualisieren der[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Wenn die <xref:System.Windows.Threading.Dispatcher> in der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread Zeit hat, führt er den geplanten Aufruf von `UpdateUserInterface`. Diese Methode hält die Uhranimation an und wählt ein Bild aus, um das Wetter zu beschreiben. Dieses Bild angezeigt und die Schaltfläche "Fetch Forecast" wiederhergestellt.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Mehrere Fenster, mehrere Threads  
 Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mehrere Fenster der obersten Ebene erforderlich. Es ist durchaus akzeptabel, dass ein Thread / <xref:System.Windows.Threading.Dispatcher> -Kombination mehrere Fenster verwaltet, aber mitunter eignen sich mehrere Threads besser funktionieren. Dies ist umso mehr, wenn die Möglichkeit besteht, dass eines der Fenster des Threads.  
  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]Explorer kann auf diese Weise. Jedes neue Explorer-Fenster gehört zum ursprünglichen Prozess wird, es jedoch von einem unabhängigen Thread gesteuert.  
  
 Mithilfe einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> Steuerelement, wir können Webseiten. Wir können problemlos erstellen eine einfache [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] ersetzen. Beginnen wir mit dem ein wichtiges Feature: die Möglichkeit, ein neues Explorerfenster zu öffnen. Wenn der Benutzer klickt "neue Fenster" Schaltfläche starten wir eine Kopie des Fensters in einem separaten Thread. Auf diese Weise wird nicht lange andauernden oder blockierende Vorgänge in eines der Fenster die anderen Fenstern sperren.  
  
 In Wirklichkeit hat das Browser-Modell ein eigene komplizierte Threadmodell. Sie haben wir uns entschieden, da es die meisten Leser vertraut sein sollten.  
  
 Das folgende Beispiel zeigt den Code.  
  
 [!code-xml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 Die folgenden threading Segmente des Codes sind die interessantesten in diesem Kontext:  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 Diese Methode wird aufgerufen, wenn das Fenster"neue" geklickt wird. Es wird einen neuer Thread erstellt und asynchron gestartet.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 Diese Methode ist der Ausgangspunkt für den neuen Thread. Wir erstellen ein neues Fenster von diesem Thread gesteuert.                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]erstellt automatisch eine neue <xref:System.Windows.Threading.Dispatcher> an den neuen Thread zu verwalten. Müssen wir tun, um das Fenster funktionsfähig ist, starten die <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Technische Details und Stolpersteine  
  
### <a name="writing-components-using-threading"></a>Schreiben von Komponenten mithilfe von Threading  
 Die [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] Developer's Guide Beschreibt ein Muster wie eine Komponente für ihre Clients asynchrones Verhalten verfügbar machen kann (siehe [Übersicht über ereignisbasierte asynchrone Muster](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Nehmen wir beispielsweise an, wir wollten Paket die `FetchWeatherFromServer` Methode in eine wieder verwendbare, nongraphical-Komponente. Nach dem Standard [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] Muster, würde dies ungefähr wie folgt aussehen.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync`würde eine der zuvor, wie z. B. das Erstellen eines Hintergrundthreads beschriebenen Techniken verwenden um die Arbeit asynchron den aufrufenden Thread nicht blockieren.  
  
 Eine der interessantesten Teile dieses Musters ist der Aufruf der *MethodName* `Completed` Methode auf dem gleichen Thread, der *MethodName* `Async` Methode mit dem begonnen. Könnte dazu verwenden Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] relativ einfach durch Speichern von <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>– aber dann die nongraphical Komponente kann nur verwendet werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clientanwendungen nicht in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] Programme.  
  
 Die <xref:System.Windows.Threading.DispatcherSynchronizationContext> Klasse erfüllt diese Anforderung, betrachten Sie es als eine vereinfachte Version des <xref:System.Windows.Threading.Dispatcher> funktioniert mit anderen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] konzipiert.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Geschachteltes verschieben  
 Manchmal ist es nicht möglich, vollständig zu Sperren der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Betrachten wir die <xref:System.Windows.MessageBox.Show%2A> Methode der <xref:System.Windows.MessageBox> Klasse.                          <xref:System.Windows.MessageBox.Show%2A> nicht zurückgegeben, bis der Benutzer die Schaltfläche "OK" klickt. Es wird, jedoch ein Fenster erstellt, die eine Meldungsschleife haben muss, um interaktiv sein. Während es für den Benutzer auf OK klicken, warten, reagiert das ursprüngliche Anwendungsfenster nicht auf Benutzereingaben. Es, jedoch weiterhin Paint-Meldungen zu verarbeiten. Das ursprüngliche Fenster zeichnet sich selbst beim verdeckt und dann angezeigt.  
  
 ![MessageBox mit einer Schaltfläche "OK"](../../../../docs/framework/wpf/advanced/media/threadingnestedpumping.png "ThreadingNestedPumping")  
  
 Einige Threads muss für das Meldungsfenster verantwortlich sein.                          [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]kann nur für das Meldungsfenster einen neuen Thread erstellen, aber dieser Thread wird in der Lage, die deaktivierten Elemente im ursprünglichen Fenster zu zeichnen (Beachten Sie die oben erwähnte wechselseitigen Ausschluss). Stattdessen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eine geschachtelte Nachricht System zur Verarbeitung verwendet. Die <xref:System.Windows.Threading.Dispatcher> -Klasse enthält eine besondere Methode namens <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, die aktuellen Ausführungspunkt einer Anwendung speichert eine neue Meldungsschleife beginnt. Nach Beendigung die geschachtelten Meldungsschleife Ausführung wird nach dem ursprünglichen <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> aufrufen.  
  
 In diesem Fall <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> behält den Programmkontext beim Aufruf von <xref:System.Windows.MessageBox>.                         <xref:System.Windows.MessageBox.Show%2A>, und beginnt eine neue Meldungsschleife, um das Hintergrundfenster und Eingaben für das Meldungsfenster zu behandeln. Wenn der Benutzer auf OK klickt und das Popupfenster, die geschachtelte Schleife beendet wird und das Steuerelement fortgesetzt, nach dem Aufruf von <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Veraltete Routingereignisse  
 Das System Routingereignis in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] benachrichtigt ganze Strukturen, wenn Ereignisse ausgelöst werden.  
  
 [!code-xml[InputOvw#ThreadingArticleStaticRoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 Wenn die linke Maustaste, über die Ellipse gedrückt wird `handler2` ausgeführt wird. Nach dem `handler2` nach Abschluss des Ereignisses übergeben die <xref:System.Windows.Controls.Canvas> -Objekt, das verwendet `handler1` verarbeitet. Dies geschieht nur, wenn `handler2` wird nicht explizit kennzeichnen das Ereignisobjekt als behandelt.  
  
 Es ist möglich, `handler2` wird sehr viel Zeit, die Verarbeitung dieses Ereignisses.                          `handler2`Verwenden Sie möglicherweise <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> um eine geschachtelte Meldungsschleife zu beginnen, Stunden zurückgegeben wird. Wenn `handler2` kennzeichnen Sie das Ereignis als behandelt, wenn die Meldungsschleife ist abgeschlossen ist, wird das Ereignis der Struktur nach oben übergeben, obwohl es sehr alt ist.  
  
### <a name="reentrancy-and-locking"></a>Reentranz und Sperrung  
 Der Sperrmechanismus der der [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] verhält sich nicht genau wie eine möglicherweise stellen Sie sich vor, dass sich einen Thread Vorgang beim Anfordern einer Sperre vollständig beendet werden soll. Der Thread weiterhin in Wirklichkeit aus empfangen und Verarbeiten von Nachrichten mit hoher Priorität. Dadurch Deadlocks zu vermeiden und Schnittstellen minimal reaktionsfähig, aber es führt die auch unscheinbare Fehler.  Der Großteil der Zeit, die Sie brauchen nichts dazu jedoch in den seltenen Fällen wissen (normalerweise im Zusammenhang mit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] fenstermeldungen oder COM-STA-Komponenten) Entwurfsalternativen möglich.  
  
 Die meisten Schnittstellen werden nicht auf Threadsicherheit Bedenken erstellt, da Entwickler bei Ihrer Arbeit, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nie durch mehrere Threads zugegriffen wird. In diesem Fall einzigen Thread environmental zu unerwarteten Zeiten ändern kann diese falsch verursacht, die Effekte der <xref:System.Windows.Threading.DispatcherObject> wechselseitigen Ausschlussmechanismus lösen soll. Betrachten Sie den folgenden Pseudocode aus:  
  
 ![Diagramm des Verkettungswiedereintritts](../../../../docs/framework/wpf/advanced/media/threadingreentrancy.png "ThreadingReentrancy")  
  
 In den meisten Fällen, die das richtige ist, aber manchmal in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , in denen solche unerwartete Reentranz wirklich zu Problemen führen kann. In diesem Fall Key gelegentlich [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Aufrufe <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, geändert wird, die die Lock-Anweisung für den Thread verwendet die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] frei von Eintrittsinvarianz Sperre anstelle des üblichen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] sperren.  
  
 Warum hat das [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Team auswählen dieses Verhalten? Es musste mit COM-STA-Objekten und der Finalization-Thread. Wenn ein Objekt mit Garbage Collection, ist seine `Finalize` -Methode für den dedizierten Finalizerthread ausgeführt wird nicht der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Und darin liegt das Problem, da ein COM-STA-Objekt, das erstellt wurde, auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread kann nur freigegeben werden, auf die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread. Die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] entspricht dem von einer <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (in diesem Fall mithilfe von Win32 `SendMessage`). Wenn Sie allerdings die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Thread ausgelastet ist, im Finalizer-Thread wurde unterbrochen, und das COM-STA-Objekt nicht verworfen werden, der einen Speicherverlust schwerwiegende erstellt. Damit der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Team die Notbremse Sperren wie gewünscht dazu.  
  
 Die Aufgabe für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist die Vermeidung von Eintrittsinvarianz ohne Wiedereinführung Speicherverlust, weshalb wir überall Eintrittsinvarianz nicht blockieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Singlethread-Anwendung mit Long-Running Calculation Sample](http://go.microsoft.com/fwlink/?LinkID=160038)