---
title: "Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF | Microsoft Docs"
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
  - "Hosten eines Win32-Steuerelements in WPF"
  - "Win32-Code, WPF-Interoperation"
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit.  Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Code betrieben haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung wieder zu verwenden, anstatt ihn vollständig neu zu schreiben.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet ein einfaches Verfahren zum Hosten eines [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fensters auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite.  
  
 Dieses Thema führt Sie durch eine Anwendung, [Beispiel für das Hosten eines Win32\-Listenfeld\-Steuerelements in Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkID=159998), die ein [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Listenfeldsteuerelement hostet.  Dieses allgemeine Verfahren kann für das Hosten beliebiger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster erweitert werden.  
  
   
  
<a name="requirements"></a>   
## Anforderungen  
 In diesem Thema wird davon ausgegangen, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung und [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programmierung vertraut sind.  Eine Einführung in die Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung finden Sie unter [Erste Schritte](../../../../docs/framework/wpf/getting-started/index.md).  Eine Einführung in die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programmierung finden Sie in zahlreichen Büchern zu diesem Thema, insbesondere in *Windows\-Programmierung* von Charles Petzold.  
  
 Da das Beispiel für dieses Thema in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] implementiert wurde, werden die [!INCLUDE[TLA#tla_pinvoke](../../../../includes/tlasharptla-pinvoke-md.md)] für den Zugriff auf die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] verwendet.  Grundkenntnisse in [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] sind hilfreich, aber keine Voraussetzung.  
  
> [!NOTE]
>  Dieses Thema enthält eine Reihe von Codebeispielen aus dem genannten Beispiel.  Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt.  Den vollständigen Code können Sie unter [Beispiel für das Hosten eines Win32\-Listenfeld\-Steuerelements in Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkID=159998) abrufen oder dort einsehen.  
  
<a name="basic_procedure"></a>   
## Das grundlegende Verfahren  
 Dieser Abschnitt umfasst das grundlegende Verfahren zum Hosten eines [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fensters auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite.  In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Das grundlegende Hostingverfahren verläuft wie folgt:  
  
1.  Implementieren Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite, um das Fenster zu hosten.  Eine Möglichkeit ist das Erstellen eines <xref:System.Windows.Controls.Border>\-Elements, um einen Abschnitt der Seite für das gehostete Fenster zu reservieren.  
  
2.  Implementieren Sie eine Klasse, um das Steuerelement zu hosten, das von <xref:System.Windows.Interop.HwndHost> erbt.  
  
3.  Überschreiben Sie in dieser Klasse den <xref:System.Windows.Interop.HwndHost>\-Klassenmember <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Erstellen Sie das gehostete Fenster als untergeordnetes Element des Fensters, das die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite enthält.  Obwohl es bei der herkömmlichen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung nicht explizit verwendet werden muss, stellt die Hostingseite ein Fenster mit einem Handle \(HWND\) dar.  Sie erhalten das HWND der Seite durch den `hwndParent`\-Parameter der <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>\-Methode.  Das gehostete Fenster sollte als untergeordnetes Element von diesem HWND erstellt werden.  
  
5.  Sobald Sie das Hostfenster erstellt haben, geben Sie das HWND des gehosteten Fensters zurück.  Wenn Sie ein oder mehrere [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Steuerelemente hosten möchten, erstellen Sie in der Regel ein Hostfenster als untergeordnetes Element des HWND und machen die Steuerelemente zu untergeordneten Elementen dieses Hostfensters.  Durch Umschließen der Steuerelemente mit einem Hostfenster kann die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite Benachrichtigungen von den Steuerelementen erhalten. Dabei geht es um bestimmte Probleme von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] im Zusammenhang mit Benachrichtigungen über die HWND\-Grenze hinweg.  
  
6.  Verarbeiten Sie ausgewählte Meldungen, die an das Hostfenster gesendet wurden, z. B. Benachrichtigungen von untergeordneten Steuerelementen.  Hierfür gibt es zwei Möglichkeiten.  
  
    -   Wenn Sie Meldungen bevorzugt in der Hostingklasse verarbeiten, überschreiben Sie die <xref:System.Windows.Interop.HwndHost.WndProc%2A>\-Methode der <xref:System.Windows.Interop.HwndHost>\-Klasse.  
  
    -   Sollen die Meldungen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verarbeitet werden, verarbeiten Sie das <xref:System.Windows.Interop.HwndHost.MessageHook>\-Ereignis der <xref:System.Windows.Interop.HwndHost>\-Klasse im Code\-Behind.  Dieses Ereignis tritt für jede Meldung auf, die vom gehosteten Fenster empfangen wird.  Wenn Sie diese Option auswählen, müssen Sie <xref:System.Windows.Interop.HwndHost.WndProc%2A> zwar immer noch überschreiben, benötigen jedoch nur eine minimale Implementierung.  
  
7.  Überschreiben Sie die <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>\-Methode und <xref:System.Windows.Interop.HwndHost.WndProc%2A>\-Methode von <xref:System.Windows.Interop.HwndHost>.  Sie müssen diese Methoden überschreiben, um dem <xref:System.Windows.Interop.HwndHost>\-Vertrag zu entsprechen, aber müssen u. U. nur eine minimale Implementierung bereitstellen.  
  
8.  Erstellen Sie in der Code\-Behind\-Datei eine Instanz der Hostingklasse des Steuerelements, und machen Sie diese zu einem untergeordneten Element des <xref:System.Windows.Controls.Border>\-Elements, das das Fenster hosten soll.  
  
9. Kommunizieren Sie mit dem gehosteten Fenster, indem Sie [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]\-Meldungen dorthin senden und Meldungen der untergeordneten Fenster verarbeiten, z. B. Benachrichtigungen von Steuerelementen.  
  
<a name="page_layout"></a>   
## Implementieren des Seitenlayouts  
 Das Layout für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite, die das ListBox\-Steuerelement hostet, besteht aus zwei Bereichen.  Auf der linken Seite werden verschiedene [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente gehostet, die eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] bereitstellen, mit der Sie das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Steuerelement bearbeiten können.  In der rechten oberen Ecke der Seite befindet sich ein quadratischer Bereich für das gehostete ListBox\-Steuerelement.  
  
 Der Code zum Implementieren dieses Layouts ist ganz einfach.  Das Stammelement entspricht <xref:System.Windows.Controls.DockPanel> mit zwei untergeordneten Elementen.  Das erste ist ein <xref:System.Windows.Controls.Border>\-Element, das das ListBox\-Steuerelement hostet.  Es belegt einen quadratischen Bereich von 200x200 in der rechten oberen Ecke der Seite.  Das zweite ist ein <xref:System.Windows.Controls.StackPanel>\-Element mit einer Gruppe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelementen, die Informationen anzeigen und Ihnen Änderungen am ListBox\-Steuerelement ermöglichen, indem verfügbar gemachte Interoperationseigenschaften festgelegt werden.  Die einzelnen Elemente, die untergeordnete Elemente von <xref:System.Windows.Controls.StackPanel> darstellen, werden im Referenzmaterial für die verschiedenen Elemente näher erläutert. Dort wird erklärt, worum es sich bei den Elementen handelt und was sie bewirken. Sie sind im Beispielcode unten aufgelistet, werden aber an dieser Stelle nicht erklärt \(sie sind nicht für das grundlegende Interoperationsmodell erforderlich, sondern werden bereitgestellt, um Interaktivität im Beispiel zu ermöglichen\).  
  
 [!code-xml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## Implementieren einer Klasse zum Hosten des Microsoft Win32\-Steuerelements  
 Der Kern dieses Beispiels ist die Klasse, die das Steuerelement ControlHost.cs tatsächlich hostet.  Sie erbt von <xref:System.Windows.Interop.HwndHost>.  Der Konstruktor verwendet zwei Parameter, Höhe und Breite, die der Höhe und Breite des <xref:System.Windows.Controls.Border>\-Elements entsprechen, das das ListBox\-Steuerelement hostet.  Diese Werte werden später verwendet, um sicherzustellen, dass die Größe des Steuerelements dem <xref:System.Windows.Controls.Border>\-Element entspricht.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Außerdem ist ein Satz von Konstanten verfügbar.  Die Konstanten stammen zum großen Teil aus Winuser.h und ermöglichen die Verwendung konventioneller Namen beim Aufrufen von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Funktionen.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### Überschreiben von BuildWindowCore zum Erstellen des Microsoft Win32\-Fensters  
 Sie überschreiben diese Methode zum Erstellen des von der Seite gehosteten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fensters und stellen die Verbindung zwischen dem Fenster und der Seite her.  Da in diesem Beispiel auch ein ListBox\-Steuerelement gehostet wird, werden zwei Fenster erstellt.  Das erste ist das tatsächlich von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite gehostete Fenster.  Das ListBox\-Steuerelement wird als untergeordnetes Element dieses Fensters erstellt.  
  
 Mit diesem Ansatz soll der Prozess des Empfangens von Benachrichtigungen vom Steuerelement vereinfacht werden.  Mit der <xref:System.Windows.Interop.HwndHost>\-Klasse können Sie Meldungen verarbeiten, die an das Fenster gesendet wurden, in dem sie gehostet wird.  Wenn Sie ein [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Steuerelement direkt hosten, empfangen Sie die Meldungen, die an die interne Nachrichtenschleife des Steuerelements gesendet wurden.  Sie können das Steuerelement anzeigen und Meldungen daran senden, aber Sie empfangen nicht die Benachrichtigungen, die vom Steuerelement an das übergeordnete Fenster gesendet werden.  Das bedeutet u. a., dass Sie nicht erkennen können, wann der Benutzer mit dem Steuerelement interagiert.  Erstellen Sie stattdessen ein Hostfenster, und machen Sie das Steuerelement zu einem untergeordneten Element dieses Fensters.  Dadurch können Sie die Meldungen für das Hostfenster verarbeiten, darunter die Benachrichtigungen, die vom Steuerelement dorthin gesendet wurden.  Der Einfachheit halber wird das Paket als ListBox\-Steuerelement bezeichnet, da das Hostfenster im Grunde nur einen einfachen Wrapper für das Steuerelement darstellt.  
  
<a name="create_the_window_and_listbox"></a>   
#### Erstellen des Hostfensters und des ListBox\-Steuerelements  
 Sie können mit [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)] ein Hostfenster für das Steuerelement erstellen, indem Sie eine Fensterklasse erstellen und registrieren usw.  Einfacher ist es jedoch, ein Fenster mit der vordefinierten "statischen" Fensterklasse zu erstellen.  Dadurch verfügen Sie über die Fensterprozedur, die Sie zum Empfangen von Benachrichtigungen vom Steuerelement benötigen, und der Codierungsaufwand ist minimal.  
  
 Das HWND des Steuerelements wird durch eine schreibgeschützte Eigenschaft verfügbar gemacht, sodass die Hostseite Meldungen an das Steuerelement senden kann.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Das ListBox\-Steuerelement wird als untergeordnetes Element des Hostfensters erstellt.  Die Höhe und die Breite beider Fenster werden auf die Werte festgelegt, die an den Konstruktor übergeben werden, wie oben beschrieben.  Damit ist sichergestellt, dass die Größe von Hostfenster und Steuerelement mit dem reservierten Bereich auf der Seite übereinstimmen.  Nachdem die Fenster erstellt wurden, gibt das Beispiel ein <xref:System.Runtime.InteropServices.HandleRef>\-Objekt zurück, dass das HWND des Hostfensters enthält.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### Implementieren von DestroyWindow und WndProc  
 Zusätzlich zu <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> müssen Sie auch die <xref:System.Windows.Interop.HwndHost.WndProc%2A>\-Methode und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>\-Methode von <xref:System.Windows.Interop.HwndHost> überschreiben.  In diesem Beispiel werden die Meldungen für das Steuerelement vom <xref:System.Windows.Interop.HwndHost.MessageHook>\-Handler verarbeitet, daher ist die Implementierung von <xref:System.Windows.Interop.HwndHost.WndProc%2A> und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> minimal.  Im Fall von <xref:System.Windows.Interop.HwndHost.WndProc%2A> legen Sie `handled` auf `false` fest, um anzugeben, dass die Meldung nicht verarbeitet wurde und geben 0 \(null\) zurück.  Für <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> löschen Sie einfach das Fenster.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## Hosten des Steuerelements auf der Seite  
 Um das Steuerelement auf der Seite zu hosten, erstellen Sie zuerst eine neue Instanz der `ControlHost`\-Klasse.  Übergeben Sie die Höhe und die Breite des Rahmenelements, das das Steuerelement \(`ControlHostElement`\) enthält, an den `ControlHost`\-Konstruktor.  Dadurch ist sichergestellt, dass das Listenfeld die richtige Größe hat.  Anschließend hosten Sie das Steuerelement auf der Seite, indem Sie das `ControlHost`\-Objekt der <xref:System.Windows.Controls.Decorator.Child%2A>\-Eigenschaft von <xref:System.Windows.Controls.Border> des Hosts zuweisen.  
  
 Im Beispiel wird ein Handler an das <xref:System.Windows.Interop.HwndHost.MessageHook>\-Ereignis von `ControlHost` angefügt, um Meldungen vom Steuerelement zu empfangen.  Dieses Ereignis wird für jede Meldung ausgelöst, die an das gehostete Fenster gesendet wird.  In diesem Fall handelt es sich dabei um die Meldungen, die an das Fenster gesendet wurden, das das tatsächliche ListBox\-Steuerelement umschließt, darunter Benachrichtigungen des Steuerelements.  Im Beispiel wird SendMessage aufgerufen, um Informationen aus dem Steuerelement abzurufen und dessen Inhalt zu ändern.  Im nächsten Abschnitt wird die Kommunikation zwischen Seite und Steuerelement ausführlicher erläutert.  
  
> [!NOTE]
>  Beachten Sie, dass es zwei [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)]\-Deklarationen für SendMessage gibt.  Das ist erforderlich, weil der `wParam`\-Parameter von einer Deklaration zum Übergeben einer Zeichenfolge und von der anderen zum Übergeben einer ganzen Zahl verwendet wird.  Sie benötigen für jede Signatur eine separate Deklaration, um sicherzustellen, dass die Daten ordnungsgemäß gemarshallt werden.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## Implementieren der Kommunikation zwischen dem Steuerelement und der Seite  
 Sie bearbeiten das Steuerelement, indem Sie [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)]\-Meldungen an das Steuerelement senden.  Sie werden vom Steuerelement benachrichtigt, wenn der Benutzer damit interagiert, indem es Benachrichtigungen an dessen Hostfenster sendet.  Das [Beispiel für das Hosten eines Win32\-Listenfeld\-Steuerelements in Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkID=159998) umfasst eine Benutzeroberfläche, mit der folgende Funktionen veranschaulicht werden:  
  
-   Anfügen eines Elements an die Liste  
  
-   Löschen des ausgewählten Elements aus der Liste  
  
-   Anzeigen des Texts des zurzeit ausgewählten Elements  
  
-   Anzeigen der Anzahl der Elemente in der Liste  
  
 Der Benutzer kann auch ein Element im Listenfeld auswählen, indem er wie bei einer normalen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung darauf klickt.  Die angezeigten Daten werden jedes Mal aktualisiert, wenn der Benutzer den Status des Listenfelds durch Auswählen, Hinzufügen oder Anfügen eines Elements ändert.  
  
 Um Elemente anzufügen, senden Sie eine LB\_ADDSTRING\-Meldung an das Listenfeld.  Wenn Sie Elemente löschen möchten, senden Sie LB\_GETCURSEL, um den Index der aktuellen Auswahl abzurufen, und dann LB\_DELETESTRING, um das Element zu löschen.  In dem Beispiel wird außerdem LB\_GETCOUNT gesendet und der zurückgegebene Wert verwendet, um die Anzeige mit der Anzahl der Elemente zu aktualisieren.  Diese beiden Instanzen von SendMessage verwenden eine der [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)]\-Deklarationen, die im vorherigen Abschnitt erläutert wurden.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Wenn der Benutzer ein Element auswählt oder die Auswahl ändert, benachrichtigt das Steuerelement das Hostfenster durch Senden einer WM\_COMMAND\-Meldung, die das <xref:System.Windows.Interop.HwndHost.MessageHook>\-Ereignis für die Seite auslöst.  Der Handler empfängt dieselben Informationen wie die Hauptfensterprozedur des Hostfensters.  Außerdem wird ein Verweis an einen booleschen Wert übergeben: `handled`.  Sie legen `handled` auf `true` fest, um anzugeben, dass die Meldung verarbeitet wurde und keine weitere Verarbeitung erforderlich ist.  
  
 Da WM\_COMMAND aus den unterschiedlichsten Gründen gesendet wird, müssen Sie die Benachrichtigungs\-ID daraufhin überprüfen, ob ein Ereignis behandelt werden soll.  Die ID ist im hohen WORD des `wParam`\-Parameters enthalten.  Da [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] kein HIWORD\-Makro aufweist, werden im Beispiel zum Extrahieren der ID bitweise Operatoren verwendet.  Wenn der Benutzer die Auswahl vorgenommen oder geändert hat, lautet die ID LBN\_SELCHANGE.  
  
 Wird LBN\_SELCHANGE empfangen, wird im Beispiel der Index des ausgewählten Elements abgerufen. Dies geschieht durch Senden einer LB\_GETCURSEL\-Meldung an das Steuerelement.  Zum Abrufen des Texts erstellen Sie zuerst <xref:System.Text.StringBuilder>.  Anschließend senden Sie eine LB\_GETTEXT\-Meldung an das Steuerelement.  Übergeben Sie das leere <xref:System.Text.StringBuilder>\-Objekt als `wParam`\-Parameter.  Wenn SendMessage zurückgegeben wird, enthält <xref:System.Text.StringBuilder> den Text des ausgewählten Elements.  Diese Verwendung von SendMessage erfordert eine weitere [!INCLUDE[TLA2#tla_pinvoke](../../../../includes/tla2sharptla-pinvoke-md.md)]\-Deklaration.  
  
 Legen Sie abschließend `handled` auf `true` fest, um anzugeben, dass die Meldung verarbeitet wurde.  
  
## Siehe auch  
 <xref:System.Windows.Interop.HwndHost>   
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)