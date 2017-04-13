---
title: "Eingabearchitektur f&#252;r die Interoperabilit&#228;t zwischen Windows Forms und WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ElementHost-Tastatur und -Meldungen"
  - "Eingabearchitektur [WPF-Interoperabilität]"
  - "Interoperabilität [WPF], Windows Forms"
  - "Tastaturinteroperation [WPF]"
  - "Meldungen [WPF]"
  - "Nicht modale Dialogfelder [WPF]"
  - "Nicht modale Formulare"
  - "Windows Forms [WPF], Interoperabilität mit"
  - "Windows Forms, WPF-Interoperation"
  - "WindowsFormsHost-Tastatur und -Meldungen"
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Eingabearchitektur f&#252;r die Interoperabilit&#228;t zwischen Windows Forms und WPF
Die Interoperation zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] erfordert, dass beide Technologien über die entsprechende Verarbeitung von Tastatureingaben verfügen.  In diesem Thema wird beschrieben, wie diese Technologien die Tastatur\- und Meldungsverarbeitung implementieren, um eine reibungslose Interoperation in hybriden Anwendungen zu ermöglichen.  
  
 Dieses Thema enthält folgende Unterabschnitte:  
  
-   Nicht modale Formulare und Dialogfelder  
  
-   Tastatur\- und Meldungsverarbeitung von WindowsFormsHost  
  
-   Tastatur\- und Meldungsverarbeitung von ElementHost  
  
## Nicht modale Formulare und Dialogfelder  
 Rufen Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>\-Methode für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element auf, um ein nicht modales Formular oder Dialogfeld aus einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendung zu öffnen.  
  
 Rufen Sie die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>\-Methode für das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement auf, um eine nicht modale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite in einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-basierten Anwendung zu öffnen.  
  
## Tastatur\- und Meldungsverarbeitung von WindowsFormsHost  
 Wenn die Tastatur\- und Meldungsverarbeitung von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] von einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendung gehostet wird, umfasst sie Folgendes:  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse ruft Meldungen von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Meldungsschleife ab, die von der <xref:System.Windows.Interop.ComponentDispatcher>\-Klasse implementiert wird.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse erstellt eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Ersatzmeldungsschleife, um die übliche [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Tastaturverarbeitung sicherzustellen.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink>\-Schnittstelle, um die Fokusverwaltung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu koordinieren.  
  
-   Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelemente registrieren sich und starten ihre Meldungsschleifen.  
  
 In den folgenden Abschnitten werden diese Teile des Vorgangs ausführlicher beschrieben.  
  
### Abrufen von Meldungen aus der WPF\-Meldungsschleife  
 Die <xref:System.Windows.Interop.ComponentDispatcher>\-Klasse implementiert den Meldungsschleifen\-Manager für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Die <xref:System.Windows.Interop.ComponentDispatcher>\-Klasse stellt Hooks bereit, damit externe Clients Meldungen filtern können, bevor sie von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verarbeitet werden.  
  
 Die Implementierung der Interoperation behandelt das <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>\-Ereignis, mit dem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente Meldungen vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelementen verarbeiten können.  
  
### Windows Forms\-Ersatzmeldungsschleife  
 Standardmäßig enthält die <xref:System.Windows.Forms.Application?displayProperty=fullName>\-Klasse die primäre Meldungsschleife für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Anwendungen.  Während der Interoperation verarbeitet die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Meldungsschleife keine Meldungen.  Deshalb muss diese Logik reproduziert werden.  Der Handler für das <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>\-Ereignis führt die folgenden Schritte aus:  
  
1.  Filtern der Meldung mithilfe der <xref:System.Windows.Forms.IMessageFilter>\-Schnittstelle.  
  
2.  Aufruf der <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName>\-Methode.  
  
3.  Übersetzen und Weiterleiten der Meldung, wenn erforderlich.  
  
4.  Übergeben der Meldung ans Hostingsteuerelement, wenn keine anderen Steuerelemente die Meldung verarbeiten.  
  
### IKeyboardInputSink\-Implementierung  
 Die Ersatzmeldungsschleife behandelt die Tastaturverwaltung.  Deshalb ist die <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName>\-Methode der einzige <xref:System.Windows.Interop.IKeyboardInputSink>\-Member, der eine Implementierung in der <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse erfordert.  
  
 Standardmäßig gibt die <xref:System.Windows.Interop.HwndHost>\-Klasse `false` für ihre <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>\-Implementierung zurück.  Dadurch wird das Wechseln mit der TAB\-TASTE von einem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement zu einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement verhindert.  
  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Implementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=fullName>\-Methode führt die folgenden Schritte aus:  
  
1.  Suchen des ersten oder letzten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelements, das im <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement enthalten ist und den Fokus erhalten kann.  Die Auswahl des Steuerelements hängt von Informationen zum Traversieren ab.  
  
2.  Festlegen des Fokus auf das Steuerelement und Rückgabe von `true`.  
  
3.  Rückgabe von `false`, wenn kein Steuerelement den Fokus erhalten kann.  
  
### WindowsFormsHost\-Registrierung  
 Wenn das Fensterhandle für ein <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement erstellt wird, ruft das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement eine interne statische Methode auf, die ihr Vorhandensein für die Meldungsschleife registriert.  
  
 Während der Registrierung untersucht das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement die Meldungsschleife.  Wenn die Meldungsschleife nicht gestartet wurde, wird der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>\-Ereignishandler erstellt.  Es wird angenommen, dass die Meldungsschleife ausgeführt wird, wenn der <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=fullName>\-Ereignishandler angefügt wird.  
  
 Wenn das Fensterhandle zerstört wird, entfernt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement sich aus der Registrierung.  
  
## Tastatur\- und Meldungsverarbeitung von ElementHost  
 Wenn die Tastatur\- und Meldungsverarbeitung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Anwendung gehostet wird, besteht sie aus Folgendem:  
  
-   Schnittstellenimplementierungen <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink> und <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
-   TAB\-TASTE und Pfeiltasten.  
  
-   Befehlstasten und Tastatureingaben im Dialogfeld.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Zugriffstastenverarbeitung.  
  
 In den folgenden Abschnitten werden diese Teile ausführlicher beschrieben.  
  
### Schnittstellenimplementierungen  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] werden Tastaturmeldungen zum Fensterhandle des Steuerelements weitergeleitet, das den Fokus besitzt.  Im <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement werden diese Meldungen zum gehosteten Element weitergeleitet.  Um dies zu erreichen, stellt das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement eine <xref:System.Windows.Interop.HwndSource>\-Instanz bereit.  Wenn das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement den Fokus besitzt, leitet die <xref:System.Windows.Interop.HwndSource>\-Instanz die meisten Tastatureingaben weiter, sodass sie von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager>\-Klasse verarbeitet werden können.  
  
 Die <xref:System.Windows.Interop.HwndSource>\-Klasse implementiert die <xref:System.Windows.Interop.IKeyboardInputSink>\-Schnittstelle und die <xref:System.Windows.Interop.IKeyboardInputSite>\-Schnittstelle.  
  
 Die Tastaturinteroperation hängt von der Implementierung der <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A>\-Methode ab, um die mittels TAB\-TASTE und Pfeiltasten vorgenommene Eingabe, die bewirkt, dass gehostete Elemente den Fokus verlieren, zu behandeln.  
  
### TAB\-TASTE und Pfeiltasten  
 Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Auswahllogik wird der <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>\-Methode und der <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A>\-Methode zugeordnet, um die Navigation mit der TAB\-TASTE und den Pfeiltasten zu implementieren.  Durch das Überschreiben der <xref:System.Windows.Forms.Integration.ElementHost.Select%2A>\-Methode wird diese Zuordnung erreicht.  
  
### Befehlstasten und Tastatureingaben im Dialogfeld.  
 Damit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die erste Möglichkeit erhält, Befehlstasten und Tastatureingaben im Dialogfeld zu verarbeiten, wird die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Befehlsvorverarbeitung mit der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>\-Methode verbunden.  Durch das Überschreiben der <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=fullName>\-Methode werden die zwei Technologien verbunden.  
  
 Mit der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>\-Methode können die gehosteten Elemente jede Tastenmeldung behandeln, z. B. WM\_KEYDOWN, WM\_KEYUP, WM\_SYSKEYDOWN oder WM\_SYSKEYUP, einschließlich Befehlstasten, z. B. TAB\-TASTE, EINGABETASTE, ESC\-TASTE und Pfeiltasten.  Wenn eine Tastenmeldung nicht behandelt wird, wird sie in der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Vorgängerhierarchie nach oben zur Behandlung gesendet.  
  
### Zugriffstastenverarbeitung  
 Um Zugriffstasten ordnungsgemäß zu verarbeiten, muss die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Zugriffstastenverarbeitung mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>\-Klasse verbunden werden.  Außerdem müssen alle WM\_CHAR\-Meldungen ordnungsgemäß zu gehosteten Elementen weitergeleitet werden.  
  
 Da die <xref:System.Windows.Interop.HwndSource>\-Standardimplementierung der <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>\-Methode `false` zurückgibt, werden WM\_CHAR\-Meldungen unter Verwendung der folgenden Logik verarbeitet:  
  
-   Die <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=fullName>\-Methode wird überschrieben, um sicherzustellen, dass alle WM\_CHAR\-Meldungen zu gehosteten Elementen weitergeleitet werden.  
  
-   Wenn die ALT\-TASTE gedrückt wird, lautet die Meldung WM\_SYSCHAR.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] führt keine Vorverarbeitung dieser Meldung durch die <xref:System.Windows.Forms.Control.IsInputChar%2A>\-Methode aus.  Deshalb wird die <xref:System.Windows.Forms.Control.ProcessMnemonic%2A>\-Methode überschrieben, um eine registrierte Zugriffstaste von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Input.AccessKeyManager> abzufragen.  Wenn eine registrierte Zugriffstaste gefunden wird, wird sie von <xref:System.Windows.Input.AccessKeyManager> verarbeitet.  
  
-   Wenn die ALT\-TASTE nicht gedrückt wird, wird die unbehandelte Eingabe von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Input.InputManager>\-Klasse verarbeitet.  Wenn die Eingabe eine Zugriffstaste ist, wird sie von <xref:System.Windows.Input.AccessKeyManager> verarbeitet.  Das <xref:System.Windows.Input.InputManager.PostProcessInput>\-Ereignis wird für WM\_CHAR\-Meldungen behandelt, die nicht verarbeitet wurden.  
  
 Wenn der Benutzer die ALT\-TASTE drückt, werden im ganzen Formular visuelle Hinweise für Zugriffstasten angezeigt.  Um dieses Verhalten zu unterstützen, erhalten alle <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelemente im aktiven Formular WM\_SYSKEYDOWN\-Meldungen, unabhängig davon, welches Steuerelement den Fokus besitzt.  
  
 Meldungen werden nur an <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelemente im aktiven Formular gesendet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>   
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)