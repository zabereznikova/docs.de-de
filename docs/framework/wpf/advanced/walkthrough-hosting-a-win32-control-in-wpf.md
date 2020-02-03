---
title: Hosten eines Win32-Steuer Elements in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: eb497a88c119dece85d61d6a32e7b86fb03b44b5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744931"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines Win32-Steuer Elements in WPF
Windows Presentation Foundation (WPF) bietet eine umfangreiche Umgebung zum Erstellen von Anwendungen. Wenn Sie jedoch eine beträchtliche Investition in Win32-Code haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer WPF-Anwendung wiederzuverwenden, anstatt ihn vollständig neu zu schreiben. WPF bietet einen einfachen Mechanismus zum Hosting eines Win32-Fensters auf einer WPF-Seite.  
  
 Dieses Thema führt Sie durch eine Anwendung, die [ein Win32-ListBox-Steuerelement in WPF hostet](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), das ein Win32-Listenfeld-Steuerelement hostet. Dieses allgemeine Verfahren kann so erweitert werden, dass ein beliebiges Win32-Fenster gehostet wird.  

<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Thema wird eine grundlegende Vertrautheit mit der WPF-und Windows-API-Programmierung vorausgesetzt. Eine grundlegende Einführung in die WPF-Programmierung finden Sie unter [Getting Started](../getting-started/index.md). Eine Einführung in die Windows-API-Programmierung finden Sie in den zahlreichen Büchern zu diesem Thema, insbesondere in den *Programmier Fenstern* von Charles Petzold.  
  
 Da das Beispiel für dieses Thema in C#implementiert ist, nutzt es Platform invoations Services (PInvoke) für den Zugriff auf die Windows-API. Eine Vertrautheit mit PInvoke ist hilfreich, aber nicht unbedingt erforderlich.  
  
> [!NOTE]
> Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Sie können den gesamten Code über das [Hosting eines Win32-ListBox-Steuer Elements im WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)abrufen oder anzeigen.  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 In diesem Abschnitt wird das grundlegende Verfahren zum Hosting eines Win32-Fensters auf einer WPF-Seite beschrieben. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Die grundlegende Vorgehensweise beim Hosten ist:  
  
1. Implementieren Sie eine WPF-Seite, um das Fenster zu hosten. Eine Methode besteht darin, ein <xref:System.Windows.Controls.Border> Element zu erstellen, um einen Abschnitt der Seite für das gehostete Fenster zu reservieren.  
  
2. Implementieren Sie eine Klasse, um das Steuerelement zu hosten, das von <xref:System.Windows.Interop.HwndHost>erbt.  
  
3. Überschreiben Sie in dieser Klasse den <xref:System.Windows.Interop.HwndHost> Klassenmember <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4. Erstellen Sie das gehostete Fenster als untergeordnetes Element des Fensters, das die WPF-Seite enthält. Obwohl bei der herkömmlichen WPF-Programmierung diese nicht explizit verwendet werden muss, ist die Hostseite ein Fenster mit einem Handle (HWND). Sie erhalten das HWND der Seite über den `hwndParent`-Parameter der <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>-Methode. Das gehostete Fenster sollte als untergeordnetes Element dieses HWND erstellt werden.  
  
5. Sobald Sie das Hostfenster erstellt haben, geben Sie das HWND des gehosteten Fensters zurück. Wenn Sie ein oder mehrere Win32-Steuerelemente hosten möchten, erstellen Sie in der Regel ein Host Fenster als untergeordnetes Element des HWND, und legen Sie die Steuerelemente in diesem Host Fenster als untergeordnete Elemente fest. Das umwickeln der Steuerelemente in einem Host Fenster bietet eine einfache Möglichkeit für Ihre WPF-Seite, Benachrichtigungen von den Steuerelementen zu empfangen, die bestimmte Win32-Probleme mit Benachrichtigungen über die HWND-Grenze behandeln.  
  
6. Behandeln Sie spezifische an das Hostfenster gesendete Nachrichten, z.B. Benachrichtigungen von untergeordneten Steuerelementen. Es gibt hierbei zwei Möglichkeiten.  
  
    - Wenn Sie die Verarbeitung von Nachrichten in ihrer Hostingklasse bevorzugen, überschreiben Sie die <xref:System.Windows.Interop.HwndHost.WndProc%2A>-Methode der <xref:System.Windows.Interop.HwndHost>-Klasse.  
  
    - Wenn Sie möchten, dass die Nachrichten von WPF verarbeitet werden, behandeln Sie die <xref:System.Windows.Interop.HwndHost>-Klasse <xref:System.Windows.Interop.HwndHost.MessageHook>-Ereignis im Code Behind. Dieses Ereignis tritt für jede Nachricht auf, die vom gehosteten Fenster empfangen wird. Wenn Sie diese Option auswählen, müssen Sie <xref:System.Windows.Interop.HwndHost.WndProc%2A>weiterhin überschreiben, aber Sie benötigen nur eine minimale Implementierung.  
  
7. Überschreiben Sie die Methoden <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> und <xref:System.Windows.Interop.HwndHost.WndProc%2A> von <xref:System.Windows.Interop.HwndHost>. Sie müssen diese Methoden außer Kraft setzen, um den <xref:System.Windows.Interop.HwndHost> Vertrag zu erfüllen, aber Sie müssen möglicherweise nur eine minimale Implementierung bereitstellen.  
  
8. Erstellen Sie in der Code Behind-Datei eine Instanz der Steuerelement-Hostingklasse, und machen Sie Sie zu einem untergeordneten Element des <xref:System.Windows.Controls.Border> Elements, das das Fenster hosten soll.  
  
9. Kommunikation mit dem gehosteten Fenster durch Senden von Microsoft Windows-Nachrichten und Verarbeiten von Nachrichten von den untergeordneten Fenstern, z. b. von Steuerelementen gesendete Benachrichtigungen  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementieren des Seitenlayouts  
 Das Layout für die WPF-Seite, die das ListBox-Steuerelement hostet, besteht aus zwei Bereichen. Die linke Seite der Seite hostet mehrere WPF-Steuerelemente, die eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] bereitstellen, mit der Sie das Win32-Steuerelement bearbeiten können. In der oberen rechten Ecke der Seite befindet sich ein quadratischer Bereich für das gehostete ListBox-Steuerelement.  
  
 Der Code zum Implementieren dieses Layouts ist ziemlich einfach. Das Stamm Element ist eine <xref:System.Windows.Controls.DockPanel>, die über zwei untergeordnete Elemente verfügt. Der erste ist ein <xref:System.Windows.Controls.Border> Element, das das ListBox-Steuerelement hostet. Es belegt einen 200x200 großen quadratischen Bereich in der oberen rechten Ecke der Seite. Die zweite ist ein <xref:System.Windows.Controls.StackPanel> Element, das eine Reihe von WPF-Steuerelementen enthält, die Informationen anzeigen und Ihnen ermöglichen, das ListBox-Steuerelement zu bearbeiten, indem Sie die verfügbar gemachten Interoperation-Eigenschaften festlegen Informationen zu den Elementen, die untergeordnete Elemente des-<xref:System.Windows.Controls.StackPanel>sind, finden Sie im Referenzmaterial für die verschiedenen Elemente, die für ausführliche Informationen zu den Elementen verwendet werden, oder was Sie tun. Diese werden im folgenden Beispielcode aufgeführt, werden hier aber nicht erläutert (das grundlegende Interoperation-Modell erfordert keines dieser Elemente, Sie werden bereitgestellt, um dem Beispiel Interaktivität hinzuzufügen).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementieren einer Klasse zum Hosten des Microsoft Win32-Steuerelements  
 Der Kern dieses Beispiels ist die Klasse ControlHost.cs, die das Steuerelement tatsächlich hostet. Er erbt von <xref:System.Windows.Interop.HwndHost>. Der Konstruktor übernimmt zwei Parameter: Höhe und Breite, die der Höhe und Breite des <xref:System.Windows.Controls.Border> Elements entsprechen, das das ListBox-Steuerelement hostet. Diese Werte werden später verwendet, um sicherzustellen, dass die Größe des Steuer Elements mit dem <xref:System.Windows.Controls.Border>-Element übereinstimmt.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Des Weiteren gibt es auch einen Satz von Konstanten. Diese Konstanten werden größtenteils aus Winuser. h entnommen und ermöglichen es Ihnen, herkömmliche Namen beim Aufrufen von Win32-Funktionen zu verwenden.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Überschreiben von BuildWindowCore zum Erstellen des Microsoft Win32-Fensters  
 Sie überschreiben diese Methode, um das Win32-Fenster zu erstellen, das von der Seite gehostet wird, und stellen die Verbindung zwischen dem Fenster und der Seite her. Da dieses Beispiel das Hosten eines ListBox-Steuerelements umfasst, werden zwei Fenster erstellt. Das erste ist das Fenster, das tatsächlich von der WPF-Seite gehostet wird. Das ListBox-Steuerelement wird als untergeordnetes Element dieses Fensters erstellt.  
  
 Dieser Ansatz wurde bewusst gewählt, um den Empfang von Benachrichtigungen aus dem Steuerelement zu vereinfachen. Die <xref:System.Windows.Interop.HwndHost>-Klasse ermöglicht es Ihnen, Nachrichten zu verarbeiten, die an das Fenster gesendet werden, das gehostet wird. Wenn Sie ein Win32-Steuerelement direkt hosten, erhalten Sie die Nachrichten, die an die interne Nachrichten Schleife des Steuer Elements gesendet werden. Sie können das Steuerelement anzeigen und ihm Nachrichten senden, aber Sie erhalten keine der Benachrichtigungen, die das Steuerelement an das übergeordnete Fenster sendet. Dies bedeutet unter anderem, dass Sie keine Möglichkeit haben, zu erkennen, wann der Benutzer mit dem Steuerelement interagiert. Erstellen Sie stattdessen ein Hostfenster, und machen Sie das Steuerelement zu einem untergeordneten Element dieses Fensters. Dadurch können Sie sowohl Nachrichten für das Hostfenster als auch vom Steuerelement gesendete Benachrichtigungen verarbeiten. Da das Hostfenster kaum mehr als ein einfacher Wrapper für das Steuerelement ist, bezeichnen wir das Gesamtpaket der Einfachheit halber künftig als ListBox-Steuerelement.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Erstellen des Hostfensters und des ListBox-Steuerelements  
 Mit PInvoke können Sie ein Host Fenster für das-Steuerelement erstellen, indem Sie eine Fenster Klasse erstellen und registrieren usw. Ein wesentlicher einfacherer Ansatz ist jedoch, ein Fenster mithilfe der vordefinierten „statischen“ Fensterklasse zu definieren. Dadurch erhalten Sie mit minimalem Codieraufwand die Fensterprozedur, die Sie benötigen, um Benachrichtigungen vom Steuerelement zu empfangen.  
  
 Das HWND des Steuerelements wird über eine schreibgeschützte Eigenschaft verfügbar gemacht, sodass es von der Hostseite zum Senden von Nachrichten an das Steuerelement verwendet werden kann.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Das ListBox-Steuerelement wird als untergeordnetes Element des Hostfensters erstellt. Die Höhe und Breite beider Fenster werden wie oben erläutert auf die an den Konstruktor übergebenen Werte festgelegt. Dadurch wird sichergestellt, dass die Größe von Hostfenster und Steuerelement exakt dem auf der Seite reservierten Bereich entspricht.  Nachdem die Fenster erstellt wurden, gibt das Beispiel ein <xref:System.Runtime.InteropServices.HandleRef> Objekt zurück, das das HWND des Host Fensters enthält.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementieren von DestroyWindow und WndProc  
 Zusätzlich zu <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>müssen Sie auch die <xref:System.Windows.Interop.HwndHost.WndProc%2A>-und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> Methoden der <xref:System.Windows.Interop.HwndHost>überschreiben. In diesem Beispiel werden die Nachrichten für das-Steuerelement vom <xref:System.Windows.Interop.HwndHost.MessageHook>-Handler verarbeitet, sodass die Implementierung von <xref:System.Windows.Interop.HwndHost.WndProc%2A> und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> minimal ist. Legen Sie im Fall von <xref:System.Windows.Interop.HwndHost.WndProc%2A>`handled` auf `false` fest, um anzugeben, dass die Nachricht nicht verarbeitet wurde, und geben Sie 0 zurück. Wenn Sie <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, löschen Sie das Fenster einfach.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Hosten des Steuerelements auf der Seite  
 Um das-Steuerelement auf der Seite zu hosten, erstellen Sie zunächst eine neue Instanz der `ControlHost`-Klasse. Übergeben Sie die Höhe und Breite des Border-Elements, das das-Steuerelement (`ControlHostElement`) enthält, an den `ControlHost`-Konstruktor. Dadurch wird sichergestellt, dass das Listenfeld die richtige Größe hat. Anschließend hosten Sie das Steuerelement auf der Seite, indem Sie das `ControlHost`-Objekt der <xref:System.Windows.Controls.Decorator.Child%2A>-Eigenschaft des Host <xref:System.Windows.Controls.Border>zuweisen.  
  
 Im Beispiel wird ein Handler an das <xref:System.Windows.Interop.HwndHost.MessageHook>-Ereignis des `ControlHost` angefügt, um Nachrichten vom-Steuerelement zu empfangen. Dieses Ereignis wird für jede Nachricht ausgelöst, die an das gehostete Fenster gesendet wird. In diesem Fall sind dies die Nachrichten, die an das das eigentliche ListBox-Steuerelement umschließende Fenster gesendet werden, einschließlich der Benachrichtigungen aus dem Steuerelement. Das Beispiel ruft die SendMessage-Methode auf, um Informationen aus dem Steuerelement abzurufen und dessen Inhalt zu ändern. Wie die Seite im Detail mit dem Steuerelement kommuniziert, wird im nächsten Abschnitt erläutert.  
  
> [!NOTE]
> Beachten Sie, dass es zwei PInvoke-Deklarationen für SendMessage gibt. Dies ist erforderlich, da der `wParam`-Parameter verwendet wird, um eine Zeichenfolge zu übergeben, die andere diese verwendet, um eine ganze Zahl zu übergeben. Um sicherzustellen, dass die Daten ordnungsgemäß gemarshallt werden, wird daher eine separate Deklaration für jede Signatur benötigt.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementieren der Kommunikation zwischen dem Steuerelement und der Seite  
 Sie bearbeiten das Steuerelement, indem Sie ihm Windows-Meldungen senden. Das Steuerelement benachrichtigt Sie, wenn der Benutzer durch Senden von Benachrichtigungen an das Hostfenster mit ihm interagiert. Das Beispiel zum [Hosting eines Win32-ListBox-Steuer Elements in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) enthält eine Benutzeroberfläche, die mehrere Beispiele für die Funktionsweise bereitstellt:  
  
- Der Liste ein Element hinzufügen.  
  
- Das markierte Element aus der Liste löschen  
  
- Den Text des aktuell markierten Elements anzeigen.  
  
- Die Anzahl der Elemente in der Liste anzeigen.  
  
 Der Benutzer kann auch ein Element im Listenfeld auswählen, indem er darauf klickt, ebenso wie bei einer herkömmlichen Win32-Anwendung. Die angezeigten Daten werden bei jeder Zustandsänderung des Listenfelds durch den Benutzer aktualisiert, egal ob ein Element ausgewählt, hinzugefügt oder angefügt wurde.  
  
 Um Elemente anzufügen, senden Sie das Listenfeld an eine [`LB_ADDSTRING` Nachricht](/windows/desktop/Controls/lb-addstring). Um Elemente zu löschen, senden Sie [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) , um den Index der aktuellen Auswahl zu erhalten, und [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) dann das Element zu löschen. Das Beispiel sendet auch [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)und verwendet den zurückgegebenen Wert, um die Anzeige zu aktualisieren, die die Anzahl der Elemente anzeigt. Beide Instanzen von [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) eine der im vorherigen Abschnitt erläuterten PInvoke-Deklarationen verwenden.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Wenn der Benutzer ein Element auswählt oder seine Auswahl ändert, benachrichtigt das-Steuerelement das Host Fenster, indem es eine [`WM_COMMAND` Meldung](/windows/desktop/menurc/wm-command)sendet, die das <xref:System.Windows.Interop.HwndHost.MessageHook>-Ereignis für die Seite auslöst. Der Handler empfängt dieselben Informationen wie die Hauptfensterprozedur des Hostfensters. Außerdem übergibt Sie einen Verweis auf einen booleschen Wert `handled`. Sie legen `handled` auf `true` fest, um anzugeben, dass die Meldung verarbeitet wurde und keine weitere Verarbeitung erforderlich ist.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) aus verschiedenen Gründen gesendet werden, müssen Sie die Benachrichtigungs-ID überprüfen, um zu bestimmen, ob es sich um ein Ereignis handelt, das Sie behandeln möchten. Die ID ist im hohen Wort des `wParam`-Parameters enthalten. Das Beispiel verwendet bitweise Operatoren, um die ID zu extrahieren. Wenn der Benutzer die Auswahl vorgenommen oder geändert hat, wird die ID [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange).  
  
 Wenn [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) empfangen wird, ruft das Beispiel den Index des ausgewählten Elements ab, indem das Steuerelement eine [`LB_GETCURSEL` Meldung](/windows/desktop/Controls/lb-getcursel)sendet. Um den Text zu erhalten, erstellen Sie zunächst einen <xref:System.Text.StringBuilder>. Anschließend senden Sie das Steuerelement an eine [`LB_GETTEXT` Meldung](/windows/desktop/Controls/lb-gettext). Übergeben Sie das leere <xref:System.Text.StringBuilder>-Objekt als `wParam`-Parameter. Wenn [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) zurückgibt, enthält der <xref:System.Text.StringBuilder> den Text des ausgewählten Elements. Diese Verwendung von [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) erfordert noch eine weitere PInvoke-Deklaration.  
  
 Legen Sie abschließend `handled` auf `true` fest, um anzugeben, dass die Nachricht behandelt wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Interop.HwndHost>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
