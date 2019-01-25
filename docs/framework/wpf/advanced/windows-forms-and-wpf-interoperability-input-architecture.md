---
title: Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF
ms.date: 03/30/2017
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
ms.openlocfilehash: 9c19e09d1b72bbee48f101904647146a467cc8d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736233"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF
Interoperation zwischen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] erfordert, dass beide Technologien auf die entsprechende Tastenkombination Eingabeverarbeitung ist. Dieses Thema beschreibt die Implementierung dieser Technologies Tastatur- und Nachrichtenverarbeitung statt, um reibungslose Zusammenarbeit in hybridanwendungen zu ermöglichen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   Nicht modale Formulare und Dialogfelder  
  
-   WindowsFormsHost-Tastatur und Verarbeitung von Nachrichten  
  
-   ElementHost-Tastatur und Verarbeitung von Nachrichten  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Nicht modale Formulare und Dialogfelder  
 Rufen Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element, ein nicht modales Formular oder Dialogfeld Öffnen Sie im eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierten Anwendung.  
  
 Rufen Sie die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Methode für die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement ein ohne Modus geöffnet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf der Seite eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]--basierten Anwendung.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost-Tastatur und Verarbeitung von Nachrichten  
 Beim Hosten durch eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierende Anwendung [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Tastatur und der Meldung, die Verarbeitung umfasst Folgendes:  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Klasse erhält Nachrichten von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Meldungsschleife, die von implementiert ist die <xref:System.Windows.Interop.ComponentDispatcher> Klasse.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Klasse erstellt ein Ersatzzeichen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Meldungsschleife, um sicherzustellen, dass normale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Tastatur Verarbeitung erfolgt.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink> Schnittstelle zum Koordinieren der fokusverwaltung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelemente registrieren sich selbst, und starten Sie ihre Nachrichtenschleifen.  
  
 In den folgenden Abschnitten werden diese Teile des Prozesses im Detail beschrieben.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Abrufen von Nachrichten aus der WPF-Nachrichtenschleife  
 Die <xref:System.Windows.Interop.ComponentDispatcher> -Klasse implementiert die Meldungs-Schleife-Manager für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Die <xref:System.Windows.Interop.ComponentDispatcher> Klasse bietet Hooks, damit externe Clients zum Filtern von Nachrichten vor dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verarbeitet.  
  
 Die Handles interoperations-Implementierung der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> -Ereignis, das kann [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente zum Verarbeiten von Nachrichten vor dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Ersatzzeichen Windows Forms-Nachrichtenschleife  
 In der Standardeinstellung die <xref:System.Windows.Forms.Application?displayProperty=nameWithType> -Klasse enthält die primäre Meldungsschleife für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendungen. Bei der Zusammenarbeit die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Nachricht, die Schleife verarbeitet keine Nachrichten. Aus diesem Grund muss diese Logik reproduziert werden. Der Handler für die <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> Ereignis führt die folgenden Schritte aus:  
  
1.  Filtert die Nachricht mithilfe der <xref:System.Windows.Forms.IMessageFilter> Schnittstelle.  
  
2.  Ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> Methode.  
  
3.  Übersetzt, und die Nachricht sendet, wenn dies erforderlich ist.  
  
4.  Übergibt die Nachricht an das hosting-Steuerelement, wenn keine anderen Steuerelementen die Nachricht zu verarbeiten.  
  
### <a name="ikeyboardinputsink-implementation"></a>IKeyboardInputSink-Implementierung  
 Die Nachrichtenschleife Ersatzzeichen übernimmt Tastatur. Aus diesem Grund die <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> Methode ist die einzige <xref:System.Windows.Interop.IKeyboardInputSink> Member, die eine Implementierung in erfordert die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Klasse.  
  
 In der Standardeinstellung die <xref:System.Windows.Interop.HwndHost> -Klasse gibt `false` für seine <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> Implementierung. Dies verhindert die TAB-Taste aus einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Steuerung an eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> Methode führt die folgenden Schritte aus:  
  
1.  Sucht das erste oder letzte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] von befindlichen Steuerelement ausgehend, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement und die Fokus erhalten kann. Die Auswahl des Steuerelements, die Traversierung Informationen abhängig ist.  
  
2.  Legt den Fokus auf das Steuerelement und gibt `true`.  
  
3.  Gibt zurück, wenn kein Steuerelement den Fokus erhalten kann, `false`.  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost-Registrierung  
 Wenn das Fensterhandle für ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement wird erstellt, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement ruft eine interne, statische Methode, die ihr Vorhandensein für die Nachrichtenschleife registriert.  
  
 Während der Registrierung der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement untersucht die Meldungsschleife. Wenn die Meldungsschleife nicht gestartet wurde, die <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> -Ereignishandler wird erstellt. Die Nachrichtenschleife gilt beim Ausführen der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> Ereignishandler angefügt wird.  
  
 Wenn das Handle des Fensters zerstört wird, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement entfernt selbst aus der Registrierung.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost-Tastatur und Verarbeitung von Nachrichten  
 Wenn Sie gehostet eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tastatur und der Meldung, die Verarbeitung umfasst die folgenden:  
  
-   <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, und <xref:System.Windows.Interop.IKeyboardInputSite> schnittstellenimplementierungen.  
  
-   TAB-Taste und unten-Tasten.  
  
-   Befehl Schlüssel und Tastatureingaben im Dialogfeld.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Accelerator-Verarbeitung.  
  
 In den folgenden Abschnitten werden diese Teile im Detail beschrieben.  
  
### <a name="interface-implementations"></a>Schnittstellenimplementierungen  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], tastaturnachrichten weitergeleitet werden, auf das Fensterhandle des Steuerelements, das Fokus besitzt. In der <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement, diese Nachrichten werden an das gehostete Element weitergeleitet. Zu diesem Zweck die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement bietet eine <xref:System.Windows.Interop.HwndSource> Instanz. Wenn die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement den Fokus hat, die <xref:System.Windows.Interop.HwndSource> Instanz weiterleitet, die meisten Tastatureingaben, damit es von verarbeitet werden, kann die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> Klasse.  
  
 Die <xref:System.Windows.Interop.HwndSource> -Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink> und <xref:System.Windows.Interop.IKeyboardInputSite> Schnittstellen.  
  
 Tastaturinteroperation zum Implementieren der <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> Methode, um das Handle TAB-Taste und Pfeil nach Schlüssel, Eingabe, die der Fokus gehostete Elemente.  
  
### <a name="tabbing-and-arrow-keys"></a>Tabstopptaste drücken und den Pfeiltasten  
 Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Auswahllogik zugeordnet ist die <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> und <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> Methoden zum Implementieren der TAB-Taste oder Schlüssel Navigation. Überschreiben der <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> Methode wird diese Zuordnung erreicht.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Befehlsschlüssel und Tastatureingaben im Dialogfeld  
 Gerne [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] der ersten Gelegenheit zur Verarbeitung von Befehlsschlüssel und Dialogfeld-Schlüssel, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] vorverarbeitung Befehl verbunden ist, um die <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> Methode. Überschreiben der <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> Methode verbindet die beiden Technologien.  
  
 Mit der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> -Methode, die gehosteten Elemente können alle tastenmeldung, z. B. WM_KEYDOWN, WM_SYSKEYDOWN, WM_KEYUP oder WM_SYSKEYUP, einschließlich der Befehl, z. B. Registerkarte, geben Sie, ESC-Taste, und der Pfeiltasten behandeln. Wenn eine tastenmeldung nicht behandelt wird, wird es gesendet, wird die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] übergeordnete Hierarchie für die Behandlung.  
  
### <a name="accelerator-processing"></a>Accelerator-Verarbeitung  
 Accelerators ordnungsgemäß verarbeiten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Accelerator Verarbeitung muss eine Verbindung mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> Klasse. Darüber hinaus müssen alle WM_CHAR-Nachrichten korrekt weitergeleitet werden, Elemente gehostet.  
  
 Da der Standardwert <xref:System.Windows.Interop.HwndSource> Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> Methodenrückgabe `false`, WM_CHAR-Nachrichten verarbeitet werden, mit der folgenden Logik:  
  
-   Die <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> Methode wird überschrieben, um sicherzustellen, dass alle WM_CHAR-Nachrichten an die gehosteten Elemente weitergeleitet werden.  
  
-   Wenn die ALT-Taste gedrückt wird, ist die Nachricht WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Diese Nachricht über nicht zuvor verarbeitet die <xref:System.Windows.Forms.Control.IsInputChar%2A> Methode. Aus diesem Grund die <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> Methode wird überschrieben, Abfrage die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> für registrierten Zugriffstaste. Wenn eine registrierte Zugriffstaste gefunden wird, <xref:System.Windows.Input.AccessKeyManager> verarbeitet.  
  
-   Wenn die ALT-Taste nicht gedrückt wird, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> Klasse verarbeitet, die nicht behandelte Eingabe. Wenn die Eingabe einer Zugriffstaste, ist die <xref:System.Windows.Input.AccessKeyManager> verarbeitet. Die <xref:System.Windows.Input.InputManager.PostProcessInput> -Ereignis behanelt WM_CHAR-Nachrichten, die nicht verarbeitet wurden.  
  
 Wenn der Benutzer die ALT-Taste drückt, werden die Zugriffstaste visuelle Hinweise auf das gesamte Formular angezeigt. Um dieses Verhalten zu unterstützen alle <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente im aktiven Formular erhalten Nachrichten von WM_SYSKEYDOWN, unabhängig davon, welches Steuerelement den Fokus hat.  
  
 Nachrichten werden nur gesendet, <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente im aktiven Formular.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
