---
title: Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: e1b96284d69645876d3e383beb03a2cc540d8b7b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731708"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
In diesem Thema wird beschrieben, wie eine Nachrichten Schleife für die Interoperation mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]implementiert wird, entweder mithilfe vorhandener Nachrichten Schleifen in <xref:System.Windows.Threading.Dispatcher> oder durch Erstellen einer separaten Nachrichten Schleife auf der Win32-Seite des Interoperation-Codes.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher und die Nachrichten Schleife  
 Ein normales Szenario für die Unterstützung von Interoperation und Tastatur Ereignissen besteht darin, <xref:System.Windows.Interop.IKeyboardInputSink>oder eine Unterklasse von Klassen zu implementieren, die bereits <xref:System.Windows.Interop.IKeyboardInputSink>implementiert haben, z. b. <xref:System.Windows.Interop.HwndSource> oder <xref:System.Windows.Interop.HwndHost>. Die Unterstützung von Tastatur senken adressiert jedoch nicht alle möglichen Nachrichten Schleifen Anforderungen, die Sie beim Senden und empfangen von Nachrichten über die Grenzen der Interoperabilität haben können. Um die Formalisierung einer Anwendungs Nachrichten Schleifen-Architektur zu unterstützen, stellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die <xref:System.Windows.Interop.ComponentDispatcher>-Klasse bereit, die ein einfaches Protokoll für eine Nachrichten Schleife definiert.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> ist eine statische Klasse, die mehrere Member verfügbar macht. Der Gültigkeitsbereich jeder Methode ist implizit an den aufrufenden Thread gebunden. Eine Nachrichten Schleife muss einige dieser APIs zu kritischen Zeiten (wie im nächsten Abschnitt definiert) aufruft.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> stellt Ereignisse bereit, die von anderen Komponenten (z. b. der Tastatur Senke) überwacht werden können. Die <xref:System.Windows.Threading.Dispatcher>-Klasse ruft alle geeigneten <xref:System.Windows.Interop.ComponentDispatcher> Methoden in einer entsprechenden Reihenfolge auf. Wenn Sie Ihre eigene Nachrichten Schleife implementieren, ist der Code für das Aufrufen von <xref:System.Windows.Interop.ComponentDispatcher> Methoden auf ähnliche Weise verantwortlich.  
  
 Wenn Sie <xref:System.Windows.Interop.ComponentDispatcher> Methoden in einem Thread aufrufen, werden nur Ereignishandler aufgerufen, die in diesem Thread registriert wurden.  
  
## <a name="writing-message-loops"></a>Schreiben von Nachrichten Schleifen  
 Im folgenden finden Sie eine Prüfliste für <xref:System.Windows.Interop.ComponentDispatcher> Elemente, die Sie verwenden werden, wenn Sie eine eigene Nachrichten Schleife schreiben:  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: die Nachrichten Schleife sollte diese so angeben, dass der Thread modal ist.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: in der Nachrichten Schleife sollte diese aufgerufen werden, um anzugeben, dass der Thread auf einen nicht modalen Wert zurückgesetzt wurde.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: die Nachrichten Schleife sollte diese Methode angeben, um anzugeben, dass <xref:System.Windows.Interop.ComponentDispatcher> das <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> Ereignis aufzurufen. <xref:System.Windows.Interop.ComponentDispatcher> wird <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> nicht, wenn <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> `true`ist, aber Nachrichten Schleifen können auch <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> aufgerufen werden, auch wenn <xref:System.Windows.Interop.ComponentDispatcher> im modalen Zustand nicht darauf reagieren kann.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: die Nachrichten Schleife sollte diese zum angeben, dass eine neue Meldung verfügbar ist, aufgerufen werden. Der Rückgabewert gibt an, ob ein Listener für ein <xref:System.Windows.Interop.ComponentDispatcher> Ereignis die Nachricht verarbeitet hat. Wenn <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> `true` (behandelt) zurückgibt, sollte der Verteiler mit der Nachricht nichts weiter tun. Wenn der Rückgabewert `false`ist, wird erwartet, dass der Verteiler die Win32-Funktion `TranslateMessage`aufruft und dann `DispatchMessage`aufruft.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Verwenden von ComponentDispatcher und vorhandener Nachrichten Behandlung  
 Im folgenden finden Sie eine Prüfliste für <xref:System.Windows.Interop.ComponentDispatcher> Elemente, die Sie verwenden werden, wenn Sie sich auf die inhärente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Message-Schleife verlassen  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: Gibt zurück, ob die Anwendung modal ist (z. b. eine modale Nachrichten Schleife wurde per pushübertragung). <xref:System.Windows.Interop.ComponentDispatcher> können diesen Status nachverfolgen, weil die-Klasse die Anzahl von <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> und <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> aufrufen aus der Nachrichten Schleife beibehält.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> und <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> Ereignisse befolgen die Standardregeln für Delegatenaufrufe. Delegaten werden in einer nicht angegebenen Reihenfolge aufgerufen, und alle Delegaten werden auch dann aufgerufen, wenn der erste die Nachricht als behandelt kennzeichnet.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: gibt eine angemessene und effiziente Zeit für die Leerlauf Verarbeitung an (es sind keine weiteren ausstehenden Nachrichten für den Thread vorhanden). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> wird nicht ausgelöst, wenn der Thread modal ist.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: wird für alle Nachrichten ausgelöst, die von der Meldungs Pumpe verarbeitet werden.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: wird für alle Nachrichten ausgelöst, die während <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>nicht behandelt wurden.  
  
 Eine Nachricht wird als behandelt betrachtet, wenn nach dem <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> Ereignis oder <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> Ereignis der `handled` Parameter, der als Verweis in den Ereignisdaten übergeben wurde, `true`ist. Ereignishandler sollten die Meldung ignorieren, wenn `handled` `true`ist, da dies bedeutet, dass der andere Handler die Nachricht zuerst verarbeitet hat. Ereignishandler für beide Ereignisse können die Nachricht ändern. Der Verteiler sollte die geänderte Nachricht und nicht die ursprüngliche unveränderte Nachricht verteilen. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> wird an alle Listener übermittelt, aber die Architektur Absicht besteht darin, dass nur das Fenster der obersten Ebene, in dem das HWND enthalten ist, in dem die Nachrichten als Antwort auf die Nachricht Code aufrufen sollen.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Behandeln von ComponentDispatcher-Ereignissen durch HwndSource  
 Wenn die <xref:System.Windows.Interop.HwndSource> ein Fenster der obersten Ebene (kein übergeordnetes HWND) ist, wird Sie bei <xref:System.Windows.Interop.ComponentDispatcher>registriert. Wenn <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> ausgelöst wird und die Nachricht für die <xref:System.Windows.Interop.HwndSource> oder untergeordneten Fenster bestimmt ist, ruft <xref:System.Windows.Interop.HwndSource> deren <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A><xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> Tastatur Senk Sequenz auf.  
  
 Wenn es sich bei der <xref:System.Windows.Interop.HwndSource> nicht um ein Fenster der obersten Ebene handelt (hat ein übergeordnetes HWND), erfolgt keine Behandlung. Es wird davon ausgegangen, dass nur das Fenster der obersten Ebene die Verarbeitung durchführen soll, und es wird erwartet, dass ein Fenster der obersten Ebene mit Unterstützung für die Tastatur senken als Teil eines intervorgangs Szenarios ist.  
  
 Wenn <xref:System.Windows.Interop.HwndHost.WndProc%2A> auf einem <xref:System.Windows.Interop.HwndSource> aufgerufen wird, ohne dass eine entsprechende Tastatur Sink-Methode zuerst aufgerufen wird, empfängt Ihre Anwendung die Tastatur Ereignisse auf höherer Ebene, z. b. <xref:System.Windows.UIElement.KeyDown>. Es werden jedoch keine Methoden der Tastatur senken aufgerufen, die wünschenswert für das gewünschte Tastatureingabe Modell, wie z. b. die Zugriffsschlüssel Unterstützung, umgangen werden. Dies kann der Fall sein, weil die Nachrichten Schleife den relevanten Thread nicht ordnungsgemäß für die <xref:System.Windows.Interop.ComponentDispatcher>benachrichtigt hat oder weil das übergeordnete HWND nicht die richtigen Antworten auf die Tastatur Senke aufgerufen hat.  
  
 Eine Nachricht, die an die Tastatur Senke gesendet wird, wird möglicherweise nicht an das HWND gesendet, wenn Sie mit der <xref:System.Windows.Interop.HwndSource.AddHook%2A>-Methode Hooks für diese Nachricht hinzugefügt haben. Die Nachricht wurde möglicherweise direkt auf der nachrichtenpump Ebene verarbeitet und nicht an die `DispatchMessage` Funktion übermittelt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Threadmodell](threading-model.md)
- [Übersicht über die Eingabe](input-overview.md)
