---
title: Windows Forms-und WPF-Interop-Eingabe Architektur
titleSuffix: ''
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
ms.openlocfilehash: f79971ba13691ccc36420e39696b7b8a46e5ce0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745048"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF
Die Interoperation zwischen dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] erfordert, dass beide Technologien über die entsprechende Tastatureingabe Verarbeitung verfügen. In diesem Thema wird beschrieben, wie diese Technologien Tastatur-und Nachrichtenverarbeitung implementieren, um eine reibungslose Interoperabilität in Hybrid Anwendungen zu ermöglichen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
- Nicht modante Formulare und Dialog Felder  
  
- WindowsFormsHost-Tastatur und Nachrichtenverarbeitung  
  
- ElementHost-Tastatur und Nachrichtenverarbeitung  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Nicht modante Formulare und Dialog Felder  
 Ruft die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>-Methode für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element auf, um ein nicht modalem Formular oder Dialogfeld aus einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung zu öffnen.  
  
 Ruft die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>-Methode für das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement auf, um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite in einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]basierten Anwendung zu öffnen.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost-Tastatur und Nachrichtenverarbeitung  
 Wenn Sie von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierten Anwendung gehostet werden, besteht [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Tastatur-und Nachrichtenverarbeitung aus folgendem:  
  
- Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Klasse ruft Nachrichten aus der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Message-Schleife ab, die von der <xref:System.Windows.Interop.ComponentDispatcher>-Klasse implementiert wird.  
  
- Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Klasse erstellt eine Ersatz [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Nachrichten Schleife, um sicherzustellen, dass die normale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Tastatur verarbeitet wird.  
  
- Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink> Schnittstelle zum Koordinieren der Fokus Verwaltung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelemente registrieren sich selbst und starten Ihre Nachrichten Schleifen.  
  
 In den folgenden Abschnitten werden diese Teile des Prozesses ausführlicher beschrieben.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Abrufen von Nachrichten aus der WPF-Nachrichten Schleife  
 Die <xref:System.Windows.Interop.ComponentDispatcher>-Klasse implementiert den Message Loop Manager für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Die <xref:System.Windows.Interop.ComponentDispatcher>-Klasse stellt Hooks bereit, damit externe Clients Nachrichten filtern können, bevor Sie von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verarbeitet werden.  
  
 Die Interoperation-Implementierung behandelt das <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>-Ereignis, das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelementen das Verarbeiten von Nachrichten vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen ermöglicht.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Ersatz Windows Forms Nachrichten Schleife  
 Standardmäßig enthält die <xref:System.Windows.Forms.Application?displayProperty=nameWithType>-Klasse die primäre Nachrichten Schleife für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Anwendungen. Während der Interoperation werden von der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Message-Schleife keine Nachrichten verarbeitet. Daher muss diese Logik reproduziert werden. Der Handler für das <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>-Ereignis führt die folgenden Schritte aus:  
  
1. Filtert die Nachricht mithilfe der <xref:System.Windows.Forms.IMessageFilter>-Schnittstelle.  
  
2. Ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>-Methode auf.  
  
3. Übersetzt und sendet die Nachricht, wenn dies erforderlich ist.  
  
4. Übergibt die Nachricht an das Hostingsteuerelement, wenn keine anderen Steuerelemente die Nachricht verarbeiten.  
  
### <a name="ikeyboardinputsink-implementation"></a>IKeyboardInputSink-Implementierung  
 Die Ersatz Nachrichten Schleife übernimmt die Tastatur Verwaltung. Daher ist die <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType>-Methode der einzige <xref:System.Windows.Interop.IKeyboardInputSink> Member, der eine Implementierung in der <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Klasse erfordert.  
  
 Standardmäßig gibt die <xref:System.Windows.Interop.HwndHost>-Klasse `false` für Ihre <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>-Implementierung zurück. Dadurch wird die Tabstopps von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement zu einem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement verhindert.  
  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType>-Methode führt die folgenden Schritte aus:  
  
1. Sucht das erste oder letzte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement, das im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement enthalten ist und das den Fokus erhalten kann. Die Auswahl des Steuer Elements hängt von den Traversale-Informationen ab.  
  
2. Legt den Fokus auf das-Steuerelement fest und gibt `true`zurück.  
  
3. Wenn kein Steuerelement den Fokus erhalten kann, wird `false`zurückgegeben.  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost-Registrierung  
 Wenn das Fenster Handle für ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement erstellt wird, ruft das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement eine interne statische Methode auf, die sein vorhanden sein für die Nachrichten Schleife registriert.  
  
 Während der Registrierung überprüft das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement die Nachrichten Schleife. Wenn die Nachrichten Schleife nicht gestartet wurde, wird der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>-Ereignishandler erstellt. Die Nachrichten Schleife wird ausgeführt, wenn der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> Ereignishandler angefügt wird.  
  
 Wenn das Fenster Handle zerstört wird, entfernt sich das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement selbst aus der Registrierung.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost-Tastatur und Nachrichtenverarbeitung  
 Wenn Sie von einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung gehostet werden, besteht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tastatur-und Nachrichtenverarbeitung aus folgendem:  
  
- <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>und <xref:System.Windows.Interop.IKeyboardInputSite> Schnittstellen Implementierungen.  
  
- Tabstopps und Pfeiltasten.  
  
- Befehlstasten und Dialogfeld Schlüssel.  
  
- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Accelerator-Verarbeitung.  
  
 In den folgenden Abschnitten werden diese Teile ausführlicher beschrieben.  
  
### <a name="interface-implementations"></a>Schnittstellen Implementierungen  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]werden Tastatur Meldungen an das Fenster Handle des Steuer Elements weitergeleitet, das den Fokus besitzt. Im <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement werden diese Nachrichten an das gehostete-Element weitergeleitet. Um dies zu erreichen, stellt das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement eine <xref:System.Windows.Interop.HwndSource>-Instanz bereit. Wenn das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement den Fokus besitzt, leitet die <xref:System.Windows.Interop.HwndSource> Instanz die meisten Tastatureingaben weiter, sodass Sie von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> Klasse verarbeitet werden kann.  
  
 Die <xref:System.Windows.Interop.HwndSource>-Klasse implementiert die-Schnittstellen <xref:System.Windows.Interop.IKeyboardInputSink> und <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
 Die Interoperation der Tastatur basiert darauf, dass die <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A>-Methode implementiert wird, um Tab-Taste und Pfeiltasten Eingaben zu verarbeiten, die den Fokus von gehosteten Elementen  
  
### <a name="tabbing-and-arrow-keys"></a>Tabstopps und Pfeiltasten  
 Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Auswahl Logik wird den <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>-und <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A>-Methoden zugeordnet, um die Tab-und Pfeiltasten Navigation zu implementieren. Wenn Sie die <xref:System.Windows.Forms.Integration.ElementHost.Select%2A>-Methode überschreiben, wird diese Zuordnung erreicht.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Befehlstasten und Dialog Feld Schlüssel  
 Um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die erste Gelegenheit zum Verarbeiten von Befehls Schlüsseln und Dialog Schlüsseln zu bieten, ist [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Befehls Vorverarbeitung mit der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>-Methode verbunden. Durch Überschreiben der <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> Methode werden die beiden Technologien verbunden.  
  
 Mit der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>-Methode können die gehosteten Elemente beliebige Schlüssel Nachrichten verarbeiten, z. b. WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN oder WM_SYSKEYUP, einschließlich Befehlstasten, z. b. Tab, Eingabe, ESC und Pfeiltasten. Wenn eine Schlüssel Nachricht nicht behandelt wird, wird Sie zur Verarbeitung an die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] übergeordnete Hierarchie gesendet.  
  
### <a name="accelerator-processing"></a>Accelerator-Verarbeitung  
 Damit Accelerators ordnungsgemäß verarbeitet werden können, muss die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Accelerator-Verarbeitung mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>-Klasse verbunden werden. Außerdem müssen alle WM_CHAR Meldungen ordnungsgemäß an gehostete Elemente weitergeleitet werden.  
  
 Da die Standard <xref:System.Windows.Interop.HwndSource> Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>-Methode `false`zurückgibt, werden WM_CHAR Meldungen mit der folgenden Logik verarbeitet:  
  
- Die <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType>-Methode wird überschrieben, um sicherzustellen, dass alle WM_CHAR Meldungen an gehostete Elemente weitergeleitet werden.  
  
- Wenn die Alt-Taste gedrückt wird, wird die Meldung WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] führt diese Nachricht nicht mit der <xref:System.Windows.Forms.Control.IsInputChar%2A>-Methode aus. Aus diesem Grund wird die <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>-Methode überschrieben, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> für eine registrierte Zugriffstaste abzufragen. Wenn eine registrierte Zugriffstaste gefunden wird, wird Sie von <xref:System.Windows.Input.AccessKeyManager> verarbeitet.  
  
- Wenn die Alt-Taste nicht gedrückt wird, verarbeitet die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager>-Klasse die nicht behandelte Eingabe. Wenn es sich bei der Eingabe um eine Zugriffstaste handelt, wird Sie vom <xref:System.Windows.Input.AccessKeyManager> verarbeitet. Das <xref:System.Windows.Input.InputManager.PostProcessInput> Ereignis wird für WM_CHAR Nachrichten behandelt, die nicht verarbeitet wurden.  
  
 Wenn der Benutzer die Alt-Taste drückt, werden visuelle Zugriffstasten Hinweise auf dem gesamten Formular angezeigt. Um dieses Verhalten zu unterstützen, empfangen alle <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente auf dem aktiven Formular WM_SYSKEYDOWN Nachrichten, unabhängig davon, welches Steuerelement den Fokus besitzt.  
  
 Nachrichten werden nur an <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente im aktiven Formular gesendet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
