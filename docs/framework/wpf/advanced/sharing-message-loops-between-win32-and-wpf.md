---
title: Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 6ee440d91bf241949923074dfd5163a49cfd9979
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740964"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
In diesem Thema wird beschrieben, wie eine Nachrichtenschleife für die Interoperation mit implementieren [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], entweder durch Nutzung vorhandener message Loop-Präsenz im <xref:System.Windows.Threading.Dispatcher> oder erstellen eine separate Nachrichtenschleife für den [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] -Seite der interoperation Code.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher und der Nachrichtenschleife  
 Ein normales Szenario für die Unterstützung von Interoperabilität und Tastatur zu implementieren ist <xref:System.Windows.Interop.IKeyboardInputSink>, oder um eine Unterklasse von Klassen, die bereits implementieren <xref:System.Windows.Interop.IKeyboardInputSink>, z. B. <xref:System.Windows.Interop.HwndSource> oder <xref:System.Windows.Interop.HwndHost>. Tastaturunterstützung für die Senke behandelt jedoch nicht alle möglichen Nachrichten Schleife Anforderungen, die Sie möglicherweise beim Senden und Empfangen von Nachrichten über die Grenzen der interoperation. Um eine Nachricht Anwendungsarchitektur, zu formalisieren [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet die <xref:System.Windows.Interop.ComponentDispatcher> Klasse, die für eine Meldungsschleife, führen ein einfaches Protokoll definiert.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> ist eine statische Klasse, die mehrere Elemente verfügbar macht. Der Bereich der einzelnen Methoden ist implizit an den aufrufenden Thread gebunden. Eine Nachrichtenschleife muss aufgerufen werden, einige davon [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] in kritischen Zeiten (wie im nächsten Abschnitt definiert).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> bietet Ereignisse, denen anderen Komponenten (z. B. die Tastatursenke) überwachen können. Die <xref:System.Windows.Threading.Dispatcher> -Klasse ruft die entsprechende <xref:System.Windows.Interop.ComponentDispatcher> Methoden in der entsprechenden Reihenfolge. Der Code ist verantwortlich für den Aufruf, wenn Sie Ihre eigene Nachrichtenschleife implementieren, <xref:System.Windows.Interop.ComponentDispatcher> Methoden auf ähnliche Weise.  
  
 Aufrufen von <xref:System.Windows.Interop.ComponentDispatcher> rufen Methoden für einen Thread nur Ereignishandler, die auf diesem Thread registriert wurden.  
  
## <a name="writing-message-loops"></a>Schreiben von Nachrichtenschleifen  
 Im folgenden finden Sie eine Prüfliste der <xref:System.Windows.Interop.ComponentDispatcher> Member verwendet werden, wenn Sie eigene Meldungsschleife schreiben:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: die Nachrichtenschleife sollte aufrufen, um anzugeben, dass der Thread modal ist.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: die Nachrichtenschleife sollte aufrufen, um anzugeben, dass der Thread auf diesen zurückgesetzt wurde.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: die Nachrichtenschleife sollte aufrufen, um anzugeben, dass <xref:System.Windows.Interop.ComponentDispatcher> auslösen soll die <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> Ereignis. <xref:System.Windows.Interop.ComponentDispatcher> löst keinen <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> Wenn <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> ist `true`, aber Nachrichtenschleifen aufrufen können <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> selbst wenn <xref:System.Windows.Interop.ComponentDispatcher> nicht auf das er im modalen Zustand versetzt.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: die Nachrichtenschleife sollte aufrufen, um anzugeben, dass eine neue Nachricht verfügbar ist. Der Rückgabewert gibt an, ob ein Listener auf einem <xref:System.Windows.Interop.ComponentDispatcher> Ereignis die Meldung verarbeitet wurde. Wenn <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> gibt `true` (behandelt), der Verteiler sollte keine weiteren Aktionen mit der Meldung. Wenn der Rückgabewert ist `false`, der Verteiler zum Aufrufen der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion `TranslateMessage`, rufen Sie anschließend `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>ComponentDispatcher und bestehende Nachrichtenverarbeitung  
 Im folgenden finden Sie eine Prüfliste der <xref:System.Windows.Interop.ComponentDispatcher> Elemente verwendet werden, wenn Sie auf den inhärenten verlassen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Nachrichtenschleife.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: Gibt zurück, ob die Anwendung modale versetzt wurde (z. B. eine modale Meldung-Schleife wurde übertragen). <xref:System.Windows.Interop.ComponentDispatcher> kann diesen Status verfolgen, da die Klasse die Anzahl der verwaltet <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> und <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> Aufrufe von der Nachrichtenschleife.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> und <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> Ereignisse folgen die Standardregeln für den Delegaten aufrufen. Delegaten werden in einer nicht vorgegebenen Reihenfolge aufgerufen, und alle Delegaten aufgerufen, selbst wenn das erste Abonnement die Nachricht markiert, als behandelt.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: Gibt an, eine geeignete und wirksame-Zeit für die Verarbeitung im Leerlauf befindet, (es sind keine weiteren ausstehenden Nachrichten für den Thread). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> wird nicht ausgelöst werden, wenn der Thread modal ist.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: wird ausgelöst, für alle Nachrichten, die die Meldungsverteilschleife verarbeitet.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: wird ausgelöst, für alle Nachrichten, die während der nicht behandelt wurden <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Eine Nachricht gilt als behandelt Wenn Sie nach einer der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> Ereignis oder <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> -Ereignis, das `handled` in den Ereignisdaten als Verweis übergebener Parameter ist `true`. Ereignishandler sollte die Meldung ignorieren, wenn `handled` ist `true`, da das bedeutet, dass der Handler für verschiedene verarbeitet die Nachricht zuerst. Beide Ereignisse Ereignishandler können die Nachricht zu ändern. Der Verteiler sollte es sich um die geänderte Nachricht und nicht die ursprüngliche unveränderte Nachricht senden. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> wird an alle Listener, aber die Architektur Absicht übermittelt wird, die nur die Fenster der obersten Ebene mit dem HWND, an dem die Nachrichten, die als Ziel müssen Code als Reaktion auf die Nachricht aufrufen.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Wie behandelt HwndSource ComponentDispatcher-Ereignisse  
 Wenn die <xref:System.Windows.Interop.HwndSource> ist ein Fenster der obersten Ebene (keine übergeordneten HWND), erfolgt die Registrierung bei <xref:System.Windows.Interop.ComponentDispatcher>. Wenn <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> ausgelöst wird, und wenn die Nachricht vorgesehen ist die <xref:System.Windows.Interop.HwndSource> oder untergeordneten Fenster <xref:System.Windows.Interop.HwndSource> Aufrufe der <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> Senke Sequenz der Tastatur.  
  
 Wenn die <xref:System.Windows.Interop.HwndSource> ist es sich nicht um ein Fenster der obersten Ebene (verfügt über einen übergeordneten HWND), es werden keine Verarbeitung. Nur die Fenster der obersten Ebene muss die Verarbeitung ist, und es wird erwartet ein Fenster auf oberster Ebene mit tastaturunterstützung-Senke als Teil jeder Interoperationsszenarios.  
  
 Wenn <xref:System.Windows.Interop.HwndHost.WndProc%2A> auf eine <xref:System.Windows.Interop.HwndSource> wird aufgerufen, ohne eine entsprechende Tastenkombination Senke Methode zuerst aufgerufen wird, empfängt die Anwendung die Tastaturereignisse der höheren Ebene wie z. B. <xref:System.Windows.UIElement.KeyDown>. Jedoch werden keine Tastatur Senke-Methoden aufgerufen werden, die wünschenswert Tastatur Eingabemodell-Funktionen wie Unterstützung von Zugriffstasten umgeht. Dies kann passieren, wenn die Meldungsschleife nicht richtig den entsprechenden Thread auf benachrichtigt wurde die <xref:System.Windows.Interop.ComponentDispatcher>, oder das HWND des übergeordneten nicht die richtige Senke Tastaturantworten aufgerufen hat.  
  
 Eine Nachricht, die auf der Tastatursenke geht möglicherweise nicht an das HWND gesendet werden, wenn Sie mithilfe von Hooks für diese Nachricht hinzugefügt der <xref:System.Windows.Interop.HwndSource.AddHook%2A> Methode. Die Nachricht möglicherweise behandelt wurden auf Nachrichtenebene für die Datapump direkt und nicht übermittelt werden, um die `DispatchMessage` Funktion.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
- [Threadmodell](../../../../docs/framework/wpf/advanced/threading-model.md)
- [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
