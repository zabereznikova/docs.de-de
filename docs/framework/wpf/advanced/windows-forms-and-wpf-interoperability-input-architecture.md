---
title: "Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a246a3297d212eabc31bf2ac9d000aeb56329d09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF
Interoperation zwischen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] erfordert, dass beide Technologien auf die entsprechende Tastenkombination Eingabeverarbeitung haben. In diesem Thema wird beschrieben, wie diese Technologien Tastatur und der Nachrichtenverarbeitung, die zum Aktivieren von smooth Interoperation in hybridanwendungen implementieren.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   Nicht modale Formularen und Dialogfeldern  
  
-   WindowsFormsHost-Tastatur und Verarbeitung von Nachrichten  
  
-   ElementHost-Tastatur und Verarbeitung von Nachrichten  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Nicht modale Formularen und Dialogfeldern  
 Rufen Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element um ein nicht modales Formular oder Dialogfeld Feld aus zu öffnen eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierten Anwendung.  
  
 Rufen Sie die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Methode auf die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement um einen ohne Modus zu öffnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf der Seite eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]--basierten Anwendung.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost-Tastatur und Verarbeitung von Nachrichten  
 Beim Hosten durch eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierende Anwendung, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Tastatur und der Meldung, die Verarbeitung besteht aus folgenden Komponenten:  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Klasse erhält Nachrichten von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Nachrichtenschleife, die durch implementiert wird die <xref:System.Windows.Interop.ComponentDispatcher> Klasse.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Klasse erstellt ein Ersatzzeichen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Nachrichtenschleife aus, um sicherzustellen, dass normale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Tastatur Verarbeitung erfolgt.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink> Schnittstelle zum Koordinieren der fokusverwaltung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelemente registrieren und starten Sie ihre Nachrichtenschleifen.  
  
 In den folgenden Abschnitten werden diese Teile des Prozesses im Detail beschrieben.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Abrufen von Nachrichten aus der WPF-Nachrichtenschleife  
 Die <xref:System.Windows.Interop.ComponentDispatcher> Klasse implementiert die Meldungsschleifen-Manager für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Die <xref:System.Windows.Interop.ComponentDispatcher> Klasse bietet Hooks damit externe Clients zum Filtern von Nachrichten vor dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verarbeitet sie.  
  
 Die Handles für die Interoperation zwischen der Implementierung der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> Ereignis, wodurch [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente zum Verarbeiten von Nachrichten vor dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Windows Forms-Nachrichtenschleife Ersatzzeichen  
 Wird standardmäßig die <xref:System.Windows.Forms.Application?displayProperty=nameWithType> Klasse enthält die primären Nachrichtenschleife für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendungen. Während der Interoperation die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Nachricht Schleife verarbeitet keine Nachrichten. Deshalb muss diese Logik reproduziert werden. Der Handler für das <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> Ereignis führt die folgenden Schritte aus:  
  
1.  Filtert die Nachricht mithilfe der <xref:System.Windows.Forms.IMessageFilter> Schnittstelle.  
  
2.  Ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> Methode.  
  
3.  Übersetzt, und die Nachricht sendet, wenn es erforderlich ist.  
  
4.  Übergibt die Nachricht an das hostende Steuerelement an, wenn keine weiteren Steuerelemente die Nachricht zu verarbeiten.  
  
### <a name="ikeyboardinputsink-implementation"></a>IKeyboardInputSink-Implementierung  
 Die Nachrichtenschleife Ersatzzeichen verarbeitet Tastatur Management. Aus diesem Grund die <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> Methode ist die einzige <xref:System.Windows.Interop.IKeyboardInputSink> Element, das eine Implementierung in erfordert die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Klasse.  
  
 Wird standardmäßig die <xref:System.Windows.Interop.HwndHost> zurück `false` für seine <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> Implementierung. Dies verhindert die TAB-Taste aus einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Steuerung an eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> Methode führt die folgenden Schritte aus:  
  
1.  Sucht das erste oder letzte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement, das enthalten ist das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement und den Fokus erhalten kann. Die Auswahl des Steuerelements abhängig von Durchlauf Informationen ab.  
  
2.  Legt den Fokus auf das Steuerelement und gibt `true`.  
  
3.  Gibt zurück, wenn kein Steuerelement den Fokus erhalten kann, `false`.  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost-Registrierung  
 Wenn das Fenster zu verarbeiten, um eine <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement erstellt, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement ruft eine interne statische Methode, die ihr Vorhandensein für das die Meldungsschleife registriert.  
  
 Während der Registrierung der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement untersucht die Meldungsschleife. Wenn die Nachrichtenschleife nicht gestartet wurde, die <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> -Ereignishandler erstellt wird. Die Nachrichtenschleife gilt beim Ausführen der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> Ereignishandler angefügt ist.  
  
 Wenn das Fensterhandle zerstört wird, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement selbst aus der Registrierung entfernt.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost-Tastatur und Verarbeitung von Nachrichten  
 Beim Hosten durch eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tastatur und der Meldung, die Verarbeitung besteht aus folgenden Komponenten:  
  
-   <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, und <xref:System.Windows.Interop.IKeyboardInputSite> schnittstellenimplementierungen.  
  
-   TAB-Taste und Tasten.  
  
-   Befehl Schlüssel und Tastatureingaben im Dialogfeld.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Accelerator-Verarbeitung.  
  
 In den folgenden Abschnitten werden diese Teile ausführlicher beschrieben.  
  
### <a name="interface-implementations"></a>Schnittstellenimplementierungen  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], Tastatur Nachrichten werden weitergeleitet, um das Fensterhandle des Steuerelements, das Fokus besitzt. In der <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement, diese Nachrichten zum gehosteten Element weitergeleitet werden. Um dies zu erreichen der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement verfügt über eine <xref:System.Windows.Interop.HwndSource> Instanz. Wenn die <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement den Fokus, hat die <xref:System.Windows.Interop.HwndSource> Instanz weiterleitet, die meisten Tastatur-, damit er von verarbeitet werden kann die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> Klasse.  
  
 Die <xref:System.Windows.Interop.HwndSource> -Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink> und <xref:System.Windows.Interop.IKeyboardInputSite> Schnittstellen.  
  
 Tastaturinteroperation hängt von der Implementierung der <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> Methode, um das Handle TAB-Taste und Pfeil Schlüssel Eingabe, die außerhalb des gehosteten Elemente Fokus.  
  
### <a name="tabbing-and-arrow-keys"></a>Tabstopptaste drücken und den Pfeiltasten  
 Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Auswahllogik zugeordnet ist die <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> und <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> Methoden zum Implementieren der TAB-Taste oder Schlüssel Navigation. Überschreiben der <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> Methode umfasst diese Zuordnung.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Befehl Schlüssel und Tastatureingaben im Dialogfeld  
 So erteilen Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die erste Gelegenheit zur Verarbeitung von Befehl Schlüssel und das Dialogfeld Schlüssel, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] vorverarbeitung Befehl verbunden ist, um die <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> Methode. Überschreiben der <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> verbindet die beiden Technologien.  
  
 Mit der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> -Methode, die gehosteten Elemente können alle tastenmeldung, z. B. WM_KEYDOWN, WM_SYSKEYDOWN, WM_KEYUP oder WM_SYSKEYUP, einschließlich Befehlstasten, z. B. Registerkarte, EINGABETASTE ESC und Pfeil behandeln. Wenn eine tastenmeldung nicht behandelt wird, wird er gesendet, wird die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Vorgänger Hierarchie für die Behandlung von.  
  
### <a name="accelerator-processing"></a>Accelerator-Verarbeitung  
 Zugriffstasten ordnungsgemäß verarbeiten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Accelerator Verarbeitung muss eine Verbindung mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> Klasse. Darüber hinaus müssen alle WM_CHAR Nachrichten richtig weitergeleitet gehostete Elemente.  
  
 Da der Standardwert <xref:System.Windows.Interop.HwndSource> Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> -Methode zurückkehrt `false`, WM_CHAR-Nachrichten verarbeitet werden, verwenden die folgende Logik:  
  
-   Die <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> Methode wird überschrieben, um sicherzustellen, dass alle WM_CHAR-Nachrichten an den gehosteten Elemente weitergeleitet werden.  
  
-   Wenn Sie die ALT-Taste gedrückt wird, wird die Meldung WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Diese Meldung über nicht zuvor verarbeitet die <xref:System.Windows.Forms.Control.IsInputChar%2A> Methode. Aus diesem Grund die <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> Methode wird überschrieben, abzufragende der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> für eine registrierte Zugriffstaste. Wenn eine registrierte Zugriffstaste gefunden wird, <xref:System.Windows.Input.AccessKeyManager> verarbeitet.  
  
-   Wenn Sie nicht die ALT-Taste gedrückt wird, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> Klasse verarbeitet, die nicht behandelte Eingabe. Wenn die Eingabe eine Zugriffstaste ist die <xref:System.Windows.Input.AccessKeyManager> verarbeitet. Die <xref:System.Windows.Input.InputManager.PostProcessInput> Ereignis behandelt wird, WM_CHAR-Nachrichten, die nicht verarbeitet wurden.  
  
 Wenn der Benutzer die ALT-Taste drückt, werden die Zugriffstaste visuellen Hinweise auf das gesamte Formular angezeigt. Um dieses Verhalten zu unterstützen alle <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente in das aktive Formular Empfangsnachrichten WM_SYSKEYDOWN, unabhängig davon, welche Steuerelement den Fokus hat.  
  
 Nachrichten werden nur für gesendet <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente in das aktive Formular.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
