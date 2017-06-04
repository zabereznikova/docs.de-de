---
title: "Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF | Microsoft Docs"
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
  - "Interoperabilität [WPF], Win32"
  - "Meldungsschleifen [WPF]"
  - "Freigeben von Meldungsschleifen"
  - "Win32-Code, Freigeben von Meldungsschleifen"
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gemeinsame Verwendung von Nachrichtenschleifen zwischen Win32 und WPF
In diesem Thema erfahren Sie, wie Sie eine Nachrichtenschleife für die Interoperation mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] implementieren können, indem Sie entweder eine vorhandene Nachrichtenschleife in <xref:System.Windows.Threading.Dispatcher> verfügbar machen oder eine separate Nachrichtenschleife auf der [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Seite Ihres Codes für die Interoperation erstellen.  
  
## ComponentDispatcher und Nachrichtenschleifen  
 Ein normales Szenario für die Interoperation und die Unterstützung von Tastaturereignissen ist die Implementierung von <xref:System.Windows.Interop.IKeyboardInputSink> oder das Erstellen einer Unterklasse aus Klassen, die bereits <xref:System.Windows.Interop.IKeyboardInputSink> implementieren, wie zum Beispiel <xref:System.Windows.Interop.HwndSource> oder <xref:System.Windows.Interop.HwndHost>.  Durch die Unterstützung einer Tastatursenke werden jedoch möglicherweise nicht alle Ihre Anforderungen erfüllt, die beim Senden und Empfangen von Nachrichten über die Grenzen der Interoperation hinweg anfallen können.  Um die Anwendungsarchitektur mit Nachrichtenschleifen stärker zu formalisieren, stellt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] die <xref:System.Windows.Interop.ComponentDispatcher>\-Klasse bereit, die ein einfaches Protokoll, dem die Nachrichtenschleife folgen muss, definiert.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> ist eine statische Klasse, die mehrere Member verfügbar macht.  Der Anwendungsbereich der einzelnen Methoden ist implizit an den aufrufenden Thread gebunden.  Die Nachrichtenschleife muss einige dieser [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] zu einem bestimmten Zeitpunkt \(siehe nächster Abschnitt\) aufrufen.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> stellt Ereignisse bereit, die von anderen Komponenten wie der Tastatursenke überwacht \(abgehört\) werden können.  Die <xref:System.Windows.Threading.Dispatcher>\-Klasse ruft alle relevanten <xref:System.Windows.Interop.ComponentDispatcher>\-Methoden in der entsprechenden Reihenfolge auf.  Falls Sie Ihre eigene Nachrichtenschleife implementieren, müssen die <xref:System.Windows.Interop.ComponentDispatcher>\-Methoden auf ähnliche Weise durch Ihren Code aufgerufen werden.  
  
 Durch den Aufruf von <xref:System.Windows.Interop.ComponentDispatcher>\-Methoden für einen Thread werden nur die Ereignishandler ausgelöst, die für diesen Thread registriert wurden.  
  
## Schreiben von Nachrichtenschleifen  
 Die folgenden <xref:System.Windows.Interop.ComponentDispatcher>\-Member kommen zum Einsatz, wenn Sie Ihre eigene Nachrichtenschleife schreiben:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: Die Nachrichtenschleife sollte diesen Member aufrufen, um anzuzeigen, dass es sich um einen modalen Thread handelt.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: Die Nachrichtenschleife sollte diesen Member aufrufen, um anzuzeigen, dass der Thread wieder in einen Thread ohne Modus umgewandelt wurde.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: Die Nachrichtenschleife sollte dies aufrufen, um anzuzeigen, dass <xref:System.Windows.Interop.ComponentDispatcher> das<xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>\-Ereignis aufrufen soll.  <xref:System.Windows.Interop.ComponentDispatcher> löst <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> nicht aus, wenn <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> auf `true` festgelegt ist. Nachrichtenschleifen können jedoch <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> aufrufen, auch wenn <xref:System.Windows.Interop.ComponentDispatcher> im modalen Zustand nicht darauf reagieren kann.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: Die Nachrichtenschleife sollte diesen Member aufrufen, um anzuzeigen, dass eine neue Nachricht verfügbar ist.  Der Rückgabewert zeigt an, ob die Nachricht von einem Listener für ein <xref:System.Windows.Interop.ComponentDispatcher>\-Ereignis behandelt wurde.  Falls <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> als Antwort `true` \(behandelt\) zurückgibt, sollte der Dispatcher keine weiteren Aktionen hinsichtlich der Nachricht durchführen.  Falls der Rückgabewert `false` ist, muss der Verteiler zuerst die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Funktion `TranslateMessage` und dann `DispatchMessage` aufrufen.  
  
## ComponentDispatcher und bestehende Meldungsbehandlung  
 Die folgenden <xref:System.Windows.Interop.ComponentDispatcher>\-Member werden verwendet, wenn Sie auf die Nachrichtenschleife von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zurückgreifen.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: Gibt an, ob die Anwendung in den Modalzustand versetzt wurde \(zum Beispiel durch Push einer modalen Nachrichtenschleife\).  <xref:System.Windows.Interop.ComponentDispatcher> kann diesen Status verfolgen, weil die Klasse die <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>\-Aufrufe und die <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>\-Aufrufe der Nachrichtenschleife zählt.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>\-Ereignisse und <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>\-Ereignisse folgen den Standardregeln für Delegataufrufe.  Delegate werden in einer nicht vorgegebenen Reihenfolge aufgerufen, und es werden alle Delegate aufgerufen, selbst wenn die Nachricht vom ersten Delegat als behandelt gekennzeichnet wurde.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: Zeigt einen geeigneten Zeitpunkt für die effiziente Leerlaufverarbeitung an \(es gibt keine weiteren anstehenden Nachrichten für den Thread\).  <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> wird nicht ausgelöst, wenn der Thread modal ist.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: Wird für alle vom Nachrichtensystem verarbeiteten Nachrichten ausgelöst.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: Wird für alle Nachrichten ausgelöst, die im Zuge von <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> nicht behandelt wurden.  
  
 Eine Nachricht wird als behandelt angesehen, wenn im Anschluss an das <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>\-Ereignis oder das <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>\-Ereignis der per Referenz in den Ereignisdaten übergebene `handled`\-Parameter `true` ist.  Die Nachricht sollte von Ereignishandlern ignoriert werden, wenn `handled` den Wert `true` aufweist, da dies bedeutet, dass die Nachricht zuerst von einem anderen Handler behandelt wurde.  Die Nachricht wird möglicherweise von den Ereignishandlern für beide Ereignisse geändert.  Der Verteiler sollte die geänderte Nachricht und nicht die ursprüngliche, unbearbeitete Nachricht senden.   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> wird an alle Listener ausgeliefert, beabsichtigt ist in der Architektur jedoch, dass nur das Fenster auf oberster Ebene mit dem HWND, auf den die Nachrichten ausgerichtet waren, Code als Antwort auf die Nachricht aufruft.  
  
## Behandlung von ComponentDispatcher\-Ereignissen durch HwndSource  
 Falls es sich bei <xref:System.Windows.Interop.HwndSource> um ein Fenster auf oberster Ebene \(ohne übergeordneten HWND\) handelt, erfolgt die Registrierung bei <xref:System.Windows.Interop.ComponentDispatcher>.  Falls <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> ausgelöst wird und die Nachricht für <xref:System.Windows.Interop.HwndSource> oder untergeordnete Fenster bestimmt ist, ruft <xref:System.Windows.Interop.HwndSource> die Tastatursenkensequenz <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> auf.  
  
 Falls es sich bei <xref:System.Windows.Interop.HwndSource> nicht um ein Fenster auf oberster Ebene handelt \(das heißt, das Fenster verfügt über einen übergeordneten HWND\), findet keine Behandlung statt.  Die Behandlung wird nur vom Fenster auf oberster Ebene erwartet, und es wird im Rahmen der Interoperation vorausgesetzt, dass es ein Fenster auf oberster Ebene mit Tastatursenkenunterstützung gibt.  
  
 Falls <xref:System.Windows.Interop.HwndHost.WndProc%2A> für eine <xref:System.Windows.Interop.HwndSource> aufgerufen wird, ohne dass zuvor eine passende Tastatursenkenmethode aufgerufen wurde, empfängt Ihre Anwendung Tastaturereignisse der höheren Ebene wie zum Beispiel <xref:System.Windows.UIElement.KeyDown>.  Die Tastatursenkenmethoden werden jedoch eventuell nicht aufgerufen, wodurch erwünschte Funktionen des Tastatureingabemodells wie die Unterstützung von Zugriffstasten verhindert werden.  Dies kann vorkommen, wenn der entsprechende Thread auf dem <xref:System.Windows.Interop.ComponentDispatcher> nicht richtig von der Nachrichtenschleife benachrichtigt wurde oder wenn der übergeordnete HWND nicht die richtigen Tastatursenkenantworten aufgerufen hat.  
  
 Eine an die Tastatursenke gelieferte Nachricht wird unter Umständen nicht an den HWND gesendet, wenn Sie mit der <xref:System.Windows.Interop.HwndSource.AddHook%2A>\-Methode Hooks für diese Nachricht hinzugefügt haben.  Eventuell wurde die Nachricht direkt auf Nachrichtensystemebene behandelt und nicht an die `DispatchMessage`\-Funktion übergeben.  
  
## Siehe auch  
 <xref:System.Windows.Interop.ComponentDispatcher>   
 <xref:System.Windows.Interop.IKeyboardInputSink>   
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Threading\-Modell](../../../../docs/framework/wpf/advanced/threading-model.md)   
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)