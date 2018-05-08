---
title: Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 35a908cc26e6b70c9acd8732521837f2b20eaf5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
In diesem Thema wird beschrieben, wie eine Nachrichtenschleife für die Zusammenarbeit mit implementieren [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], entweder mithilfe der vorhandenen Nachricht Schleife Datenanzeige im <xref:System.Windows.Threading.Dispatcher> oder erstellen eine separate Nachrichtenschleife auf die [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] des Codes interoperation Seite.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher und die Nachrichtenschleife  
 Für die Unterstützung von Interoperation und ein normales Szenario besteht darin zu implementieren <xref:System.Windows.Interop.IKeyboardInputSink>, oder Unterklassen von Klassen, die bereits implementiert <xref:System.Windows.Interop.IKeyboardInputSink>, wie z. B. <xref:System.Windows.Interop.HwndSource> oder <xref:System.Windows.Interop.HwndHost>. Allerdings befasst Senke Tastaturfunktionen alle möglichen Schleife Anforderungen sich nicht, die Sie möglicherweise beim Senden und Empfangen von Nachrichten über die Grenzen der interoperation. Um formalisieren Nachricht Anwendungsarchitektur, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet die <xref:System.Windows.Interop.ComponentDispatcher> Klasse, die ein einfaches Protokoll für eine Nachrichtenschleife anzuwendendes definiert.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> ist eine statische Klasse, die mehrere Member verfügbar macht. Der Bereich der einzelnen Methoden ist implizit an den aufrufenden Thread gebunden. Eine Nachrichtenschleife muss aufgerufen werden, einige davon [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] in kritischen Zeiten (wie im nächsten Abschnitt definiert).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> bietet Ereignisse, denen andere Komponenten (z. B. die Tastatursenke) überwachen können. Die <xref:System.Windows.Threading.Dispatcher> -Klasse ruft die entsprechende <xref:System.Windows.Interop.ComponentDispatcher> Methoden in der entsprechenden Reihenfolge. Der Code ist verantwortlich für das aufrufen, wenn Sie Ihre eigene Nachrichtenschleife implementieren, <xref:System.Windows.Interop.ComponentDispatcher> Methoden auf ähnliche Weise.  
  
 Aufrufen von <xref:System.Windows.Interop.ComponentDispatcher> rufen Methoden auf einen Thread nur Ereignishandler, die in diesem Thread registriert wurden.  
  
## <a name="writing-message-loops"></a>Schreiben von Nachrichtenschleifen  
 Im folgenden finden Sie eine Prüfliste der <xref:System.Windows.Interop.ComponentDispatcher> Member verwendet wird, wenn Sie Ihre eigene Nachrichtenschleife schreiben:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: die Nachrichtenschleife sollte aufrufen, um anzugeben, dass der Thread modal ist.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: die Nachrichtenschleife sollte rufen Sie diese Option, um anzugeben, dass der Thread auf diesen zurückgesetzt wurde.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: die Nachrichtenschleife sollte rufen Sie diese Option, um anzugeben, dass <xref:System.Windows.Interop.ComponentDispatcher> auslösen soll die <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> Ereignis. <xref:System.Windows.Interop.ComponentDispatcher> löst keine <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> Wenn <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> ist `true`, aber möglicherweise Nachrichtenschleifen aufrufen auswählen <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> selbst wenn <xref:System.Windows.Interop.ComponentDispatcher> nicht auf das er im modalen Zustand.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: die Nachrichtenschleife sollte aufrufen, um anzugeben, dass eine neue Nachricht verfügbar ist. Der Rückgabewert gibt an, ob ein Listener einen <xref:System.Windows.Interop.ComponentDispatcher> Ereignis behandelt, die Nachricht. Wenn <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> gibt `true` (behandelt), der Verteiler sollte keine weiteren Aktionen mit der Meldung. Wenn der Rückgabewert ist `false`, wird erwartet, dass der Verteiler rufen die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion `TranslateMessage`, rufen Sie anschließend `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>ComponentDispatcher und bestehende Meldungsbehandlung  
 Im folgenden finden Sie eine Prüfliste der <xref:System.Windows.Interop.ComponentDispatcher> Elemente verwendet werden, wenn Sie auf den inhärenten verlassen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Nachrichtenschleife.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: Gibt zurück, ob die Anwendung modale verlassen hat (z. B. eine modale Nachrichtenschleife verfügt über ein Push ausgeführt wurde). <xref:System.Windows.Interop.ComponentDispatcher> Dieser Status kann nachverfolgt werden, da die Klasse die Anzahl der verwaltet <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> und <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> aufrufen, die von der Nachrichtenschleife.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> und <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> Ereignisse folgen die Standardregeln für das Delegieren von aufrufen. Delegaten werden in einer nicht angegebenen Reihenfolge aufgerufen, und alle Delegaten werden aufgerufen, auch wenn das erste Schema die Nachricht markiert, als behandelt.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: Gibt an eine geeignete und effiziente Verarbeitung im Leerlauf befindet, führen Sie (es gibt keine ausstehenden Nachrichten für den Thread). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> wird nicht ausgelöst werden, wenn der Thread modal ist.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: für alle Nachrichten, die von die Meldungsverteilschleife verarbeitet ausgelöst.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: für alle Nachrichten, die nicht während der behandelt wurden ausgelöst <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Eine Nachricht gilt als behandelt If nach der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> Ereignis oder <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> Ereignis, das `handled` in Ereignisdaten als Verweis übergebener Parameter ist `true`. Ereignishandler sollte die Meldung ignorieren, wenn `handled` ist `true`, da das bedeutet, dass die unterschiedliche Handler behandelt die Nachricht zuerst. Ereignishandler auf beide Ereignisse können die Nachricht zu ändern. Der Verteiler sollte die geänderte Nachricht und nicht die ursprüngliche unveränderte Nachricht senden. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> alle Listener, aber die architektonische Absicht übermittelt wird, die nur die Fenster der obersten Ebene mit dem HWND, an dem die gerichteten Nachrichten sollten Code als Antwort auf die Nachricht aufrufen.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Wie behandelt HwndSource ComponentDispatcher-Ereignisse  
 Wenn die <xref:System.Windows.Interop.HwndSource> ist ein Fenster der obersten Ebene (kein übergeordnetes Element HWND), wird folglich mit <xref:System.Windows.Interop.ComponentDispatcher>. Wenn <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> ausgelöst wird, und wenn die Nachricht vorgesehen ist die <xref:System.Windows.Interop.HwndSource> oder untergeordneten Fenster <xref:System.Windows.Interop.HwndSource> Aufrufe der <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> Tastatur Senke Sequenz.  
  
 Wenn die <xref:System.Windows.Interop.HwndSource> ist ein Fenster der obersten Ebene (verfügt über einen übergeordneten HWND), werden keine Verarbeitung. Nur die Fenster auf oberster Ebene ist, führen Sie die Behandlung erwartet, und es muss ein Fenster auf oberster Ebene mit Unterstützung für die Senke Tastatur als Teil jeder interoperation Szenario sein.  
  
 Wenn <xref:System.Windows.Interop.HwndHost.WndProc%2A> auf eine <xref:System.Windows.Interop.HwndSource> wird aufgerufen, ohne eine entsprechende Tastenkombination Senke Methode zuerst aufgerufen wird, empfängt die Anwendung Tastaturereignisse der höheren Ebene wie z. B. <xref:System.Windows.UIElement.KeyDown>. Allerdings werden keine Tastatur Senke Methoden die umgeht wünschenswert Eingabemodell Tastaturfunktionen z. B. Unterstützung von Zugriffstasten aufgerufen. Dies kann passieren, wenn die Nachrichtenschleife nicht richtig des relevanten Threads auf benachrichtigt wurde die <xref:System.Windows.Interop.ComponentDispatcher>, oder weil das übergeordnete Element HWND nicht die richtige Tastatur Senke Antworten aufgerufen hat.  
  
 Eine Meldung, die auf der Tastatursenke geht möglicherweise nicht an das HWND gesendet werden, wenn Sie zuvor hinzugefügt haben, Hooks für diese Nachricht mithilfe der <xref:System.Windows.Interop.HwndSource.AddHook%2A> Methode. Möglicherweise wurde die Nachricht auf Nachrichtenebene für die Datapump direkt und nicht übermittelt werden, um behandelt die `DispatchMessage` Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.ComponentDispatcher>  
 <xref:System.Windows.Interop.IKeyboardInputSink>  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Threadmodell](../../../../docs/framework/wpf/advanced/threading-model.md)  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
