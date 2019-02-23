---
title: 'Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 047ccd4ea4ba83c8d7427559f3ee76cc3547a430
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747530"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF
Windows Presentation Foundation (WPF) bietet eine umfangreiche Umgebung zum Erstellen von Anwendungen. Jedoch wenn Sie eine erhebliche Investition in Win32-Code verfügen, es möglicherweise effektiver sein, mindestens einige wiederzuverwenden, Programmieren Sie in der WPF-Anwendung anstatt ihn vollständig neu zu schreiben. WPF bietet ein einfaches Verfahren zum Hosten eines Win32-Fensters, in einer WPF-Seite.  
  
 Dieses Thema führt Sie durch eine Anwendung, [Hosten eines Win32-ListBox-Steuerelements in WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), ein Listenfeld, das Win32-Hosts zu steuern. Dieses allgemeine Verfahren kann erweitert werden, für das Hosten von jeder Win32-Fensters.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Thema wird davon ausgegangen, sowohl WPF und Win32-Programmierung vertraut sind. Eine grundlegende Einführung in WPF-Programmierung, finden Sie unter [Einstieg](../../../../docs/framework/wpf/getting-started/index.md). Eine Einführung in Win32-Programmierung, Sie sollten verweisen auf eine der zahlreichen Büchern zu diesem Thema, insbesondere *Programming Windows* von Charles Petzold.  
  
 Da das Beispiel, das in diesem Thema begleitet in implementiert ist C#, Platform Invocation Services (PInvoke) nutzen, um Zugriff auf die Win32-API vereinfacht. Eine gewisse Vertrautheit mit PInvoke ist hilfreich, aber keine Voraussetzung.  
  
> [!NOTE]
>  Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Sie können auch abrufen oder Anzeigen der vollständigen Code unter [Hosten eines Win32-ListBox-Steuerelements in WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 In diesem Abschnitt wird beschrieben, das grundlegende Verfahren zum Hosten eines Win32-Fensters auf einer WPF-Seite. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Die grundlegende Vorgehensweise beim Hosten ist:  
  
1.  Implementieren Sie eine WPF-Seite, um das Fenster hostet. Eine Möglichkeit ist die Erstellung einer <xref:System.Windows.Controls.Border> Element um einen Abschnitt der Seite für das gehostete Fenster zu reservieren.  
  
2.  Implementieren Sie eine Klasse, um das Steuerelement zu hosten, die von erbt <xref:System.Windows.Interop.HwndHost>.  
  
3.  In dieser Klasse außer Kraft setzen der <xref:System.Windows.Interop.HwndHost> Klassenmember <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Erstellen Sie das gehostete Fenster als untergeordnetes Element des Fensters, das die WPF-Seite enthält. Obwohl der konventionellen WPF-Programmierung nicht explizit treffen muss es verwenden, die Hostseite ein Fenster mit einem Handle (HWND). Sie erhalten das HWND die Seite über die `hwndParent` Parameter, der die <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> Methode. Das gehostete Fenster sollte als untergeordnetes Element dieses HWND erstellt werden.  
  
5.  Sobald Sie das Hostfenster erstellt haben, geben Sie das HWND des gehosteten Fensters zurück. Wenn Sie ein oder mehrere Win32-Steuerelemente hosten möchten, erstellen ein Hostfenster als untergeordnetes Element des HWND Sie in der Regel an und stellen die Steuerelemente zu untergeordneten Elementen dieses Hostfensters. Umschließen der Steuerelemente mit einem Hostfenster bietet eine einfache Möglichkeit für Ihre WPF-Seite zum Empfangen von Benachrichtigungen von den Steuerelementen, die bestimmten Win32-Probleme mit Benachrichtigungen über HWND-Grenze hinweg behandelt.  
  
6.  Behandeln Sie spezifische an das Hostfenster gesendete Nachrichten, z.B. Benachrichtigungen von untergeordneten Steuerelementen. Hierfür gibt es zwei Möglichkeiten.  
  
    -   Falls gewünscht, um Nachrichten in Ihrer Hostklasse zu behandeln, überschreiben die <xref:System.Windows.Interop.HwndHost.WndProc%2A> Methode der <xref:System.Windows.Interop.HwndHost> Klasse.  
  
    -   Wenn Sie möchten, dass die Nachrichten behandelt, behandeln Sie WPF die <xref:System.Windows.Interop.HwndHost> Klasse <xref:System.Windows.Interop.HwndHost.MessageHook> Ereignis im Code-Behind. Dieses Ereignis tritt für jede Nachricht auf, die vom gehosteten Fenster empfangen wird. Wenn Sie diese Option auswählen, müssen Sie immer noch überschreiben <xref:System.Windows.Interop.HwndHost.WndProc%2A>, aber Sie benötigen nur eine minimale Implementierung.  
  
7.  Überschreiben der <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> und <xref:System.Windows.Interop.HwndHost.WndProc%2A> Methoden <xref:System.Windows.Interop.HwndHost>. Müssen Sie erfüllen diese Methoden überschreiben die <xref:System.Windows.Interop.HwndHost> Vertrag, aber Sie müssen möglicherweise nur eine minimale Implementierung.  
  
8.  Klicken Sie in der CodeBehind-Datei erstellen Sie eine Instanz der Hostingklasse des Steuerelements, und stellen Sie es ein untergeordnetes Element des der <xref:System.Windows.Controls.Border> -Element, das das Fenster hosten soll.  
  
9. Durch das senden es mit dem gehosteten Fenster kommunizieren [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] und Behandlung von Nachrichten aus dessen untergeordneten Fenstern, z. B. von Steuerelementen gesendete Benachrichtigungen.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementieren des Seitenlayouts  
 Das Layout für die WPF-Seite, die das ListBox-Steuerelement hostet besteht aus zwei Bereichen. Der linken Seite der Seite hostet mehrere WPF-Steuerelemente, die eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , mit der Sie die Win32-Steuerelement zu ändern. In der oberen rechten Ecke der Seite befindet sich ein quadratischer Bereich für das gehostete ListBox-Steuerelement.  
  
 Der Code zum Implementieren dieses Layouts ist recht einfach. Das Stammelement ist ein <xref:System.Windows.Controls.DockPanel> , das zwei untergeordnete Elemente besitzt. Die erste ist ein <xref:System.Windows.Controls.Border> -Element, das ListBox-Steuerelement hostet. Es belegt einen 200x200 großen quadratischen Bereich in der oberen rechten Ecke der Seite. Die zweite ist ein <xref:System.Windows.Controls.StackPanel> Element, das einen Satz von WPF-Steuerelemente, die Informationen angezeigt und ermöglichen es Ihnen enthält, die das ListBox-Steuerelement anpassen können, verfügbar gemacht werden interoperations-Eigenschaften. Für jedes der Elemente, die untergeordneten Elemente sind die <xref:System.Windows.Controls.StackPanel>, finden Sie unter das Referenzmaterial für die verschiedenen Elemente, die Einzelheiten dieser Elemente oder dazu verwendet, diese sind in den folgenden Beispielcode aufgeführt, aber nicht hier (die grundlegende erläutert interoperations-Modell nicht mit einer von ihnen erfordert, werden sie bereitgestellt, um dem Beispiel lediglich mehr Interaktivität hinzuzufügen).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementieren einer Klasse zum Hosten des Microsoft Win32-Steuerelements  
 Der Kern dieses Beispiels ist die Klasse ControlHost.cs, die das Steuerelement tatsächlich hostet. Sie erbt von <xref:System.Windows.Interop.HwndHost>. Der Konstruktor akzeptiert zwei Parameter, Höhe und Breite, die die Höhe und Breite des entsprechen den <xref:System.Windows.Controls.Border> -Element, das ListBox-Steuerelement hostet. Diese Werte werden später verwendet, um sicherzustellen, dass die Größe des Steuerelements Übereinstimmungen die <xref:System.Windows.Controls.Border> Element.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Des Weiteren gibt es auch einen Satz von Konstanten. Diese Konstanten sind zum größten Teil aus Winuser.h entlehnt, und ermöglichen es Ihnen, die Verwendung konventioneller Namen beim Aufrufen von Win32-Funktionen.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Überschreiben von BuildWindowCore zum Erstellen des Microsoft Win32-Fensters  
 Sie überschreiben diese Methode, um das Win32-Fenster zu erstellen, das von der Seite gehostet wird, und stellen die Verbindung zwischen dem Fenster und die Seite. Da dieses Beispiel das Hosten eines ListBox-Steuerelements umfasst, werden zwei Fenster erstellt. Die erste ist das Fenster, das tatsächlich von der WPF-Seite gehostet wird. Das ListBox-Steuerelement wird als untergeordnetes Element dieses Fensters erstellt.  
  
 Dieser Ansatz wurde bewusst gewählt, um den Empfang von Benachrichtigungen aus dem Steuerelement zu vereinfachen. Die <xref:System.Windows.Interop.HwndHost> -Klasse können Sie zum Verarbeiten von Nachrichten an das Fenster, das er gehostet wird. Wenn Sie eine Win32-Host direkt steuern zu können, erhalten Sie e-Mails von internen Nachrichtenschleife des Steuerelements. Sie können das Steuerelement anzeigen und ihm Nachrichten senden, aber Sie erhalten keine der Benachrichtigungen, die das Steuerelement an das übergeordnete Fenster sendet. Dies bedeutet unter anderem, dass Sie keine Möglichkeit haben, zu erkennen, wann der Benutzer mit dem Steuerelement interagiert. Erstellen Sie stattdessen ein Hostfenster, und machen Sie das Steuerelement zu einem untergeordneten Element dieses Fensters. Dadurch können Sie sowohl Nachrichten für das Hostfenster als auch vom Steuerelement gesendete Benachrichtigungen verarbeiten. Da das Hostfenster kaum mehr als ein einfacher Wrapper für das Steuerelement ist, bezeichnen wir das Gesamtpaket der Einfachheit halber künftig als ListBox-Steuerelement.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Erstellen des Hostfensters und des ListBox-Steuerelements  
 Sie können PInvoke verwenden, um ein Hostfenster für das Steuerelement zu erstellen, indem erstellen und eine Fensterklasse registrieren und so weiter. Ein wesentlicher einfacherer Ansatz ist jedoch, ein Fenster mithilfe der vordefinierten „statischen“ Fensterklasse zu definieren. Dadurch erhalten Sie mit minimalem Codieraufwand die Fensterprozedur, die Sie benötigen, um Benachrichtigungen vom Steuerelement zu empfangen.  
  
 Das HWND des Steuerelements wird über eine schreibgeschützte Eigenschaft verfügbar gemacht, sodass es von der Hostseite zum Senden von Nachrichten an das Steuerelement verwendet werden kann.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Das ListBox-Steuerelement wird als untergeordnetes Element des Hostfensters erstellt. Die Höhe und Breite beider Fenster werden wie oben erläutert auf die an den Konstruktor übergebenen Werte festgelegt. Dadurch wird sichergestellt, dass die Größe von Hostfenster und Steuerelement exakt dem auf der Seite reservierten Bereich entspricht.  Das Beispiel gibt zurück, nachdem die Windows erstellt wurden, ein <xref:System.Runtime.InteropServices.HandleRef> -Objekt, das HWND des Hostfensters enthält.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementieren von DestroyWindow und WndProc  
 Zusätzlich zu <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, müssen Sie auch überschreiben die <xref:System.Windows.Interop.HwndHost.WndProc%2A> und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> Methoden der <xref:System.Windows.Interop.HwndHost>. In diesem Beispiel werden die Nachrichten für das Steuerelement behandelt, durch die <xref:System.Windows.Interop.HwndHost.MessageHook> Handler auf, wodurch sich die Implementierung von <xref:System.Windows.Interop.HwndHost.WndProc%2A> und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> ist sehr einfach gehalten. Im Fall von <xref:System.Windows.Interop.HwndHost.WndProc%2A>legen `handled` zu `false` anzugeben, dass die Nachricht nicht verarbeitet wurde, und gibt 0 zurück. Für <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, löschen Sie das Fenster einfach.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Hosten des Steuerelements auf der Seite  
 Um das Steuerelement auf der Seite zu hosten, erstellen Sie zunächst eine neue Instanz der dem `ControlHost` Klasse. Die Höhe und Breite des Border-Elements mit dem Steuerelement zu übergeben (`ControlHostElement`) auf die `ControlHost` Konstruktor. Dadurch wird sichergestellt, dass das Listenfeld die richtige Größe hat. Anschließend hosten Sie das Steuerelement auf der Seite durch Zuweisen der `ControlHost` -Objekt an die <xref:System.Windows.Controls.Decorator.Child%2A> Eigenschaft des Hosts <xref:System.Windows.Controls.Border>.  
  
 Das Beispiel fügt einen Handler, der die <xref:System.Windows.Interop.HwndHost.MessageHook> Ereignis die `ControlHost` zum Empfangen von Nachrichten aus dem Steuerelement. Dieses Ereignis wird für jede Nachricht ausgelöst, die an das gehostete Fenster gesendet wird. In diesem Fall sind dies die Nachrichten, die an das das eigentliche ListBox-Steuerelement umschließende Fenster gesendet werden, einschließlich der Benachrichtigungen aus dem Steuerelement. Das Beispiel ruft die SendMessage-Methode auf, um Informationen aus dem Steuerelement abzurufen und dessen Inhalt zu ändern. Wie die Seite im Detail mit dem Steuerelement kommuniziert, wird im nächsten Abschnitt erläutert.  
  
> [!NOTE]
>  Beachten Sie, dass es zwei PInvoke-Deklarationen für SendMessage gibt. Dies ist erforderlich, da eine verwendet den `wParam` Parameter, der eine Zeichenfolge und der andere übergeben es verwendet, um eine ganze Zahl zu übergeben. Um sicherzustellen, dass die Daten ordnungsgemäß gemarshallt werden, wird daher eine separate Deklaration für jede Signatur benötigt.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementieren der Kommunikation zwischen dem Steuerelement und der Seite  
 Sie bearbeiten das Steuerelement von Windows-Nachrichten senden. Das Steuerelement benachrichtigt Sie, wenn der Benutzer durch Senden von Benachrichtigungen an das Hostfenster mit ihm interagiert. Die [Hosten eines Win32-ListBox-Steuerelements in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) umfasst eine Benutzeroberfläche, die enthält einige Beispiele, wie dies funktioniert:  
  
-   Der Liste ein Element hinzufügen.  
  
-   Das markierte Element aus der Liste löschen  
  
-   Den Text des aktuell markierten Elements anzeigen.  
  
-   Die Anzahl der Elemente in der Liste anzeigen.  
  
 Der Benutzer kann auch ein Element im Listenfeld auswählen, indem er darauf klickt, genauso wie für eine herkömmliche Win32-Anwendung. Die angezeigten Daten werden bei jeder Zustandsänderung des Listenfelds durch den Benutzer aktualisiert, egal ob ein Element ausgewählt, hinzugefügt oder angefügt wurde.  
  
 Um Elemente anzufügen, senden Sie im Listenfeld eine [ `LB_ADDSTRING` Nachricht](/windows/desktop/Controls/lb-addstring). Um Elemente zu löschen, senden [ `LB_GETCURSEL` ](/windows/desktop/Controls/lb-getcursel) um den Index der aktuellen Auswahl abzurufen und dann [ `LB_DELETESTRING` ](/windows/desktop/Controls/lb-deletestring) zum Löschen des Elements. Das Beispiel sendet auch [ `LB_GETCOUNT` ](/windows/desktop/Controls/lb-getcount), und der zurückgegebene Wert verwendet, um die Anzeige zu aktualisieren, die die Anzahl der Elemente anzeigt. Beide dieser Instanzen von [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) gehen die PInvoke-Deklarationen, die im vorherigen Abschnitt erläutert.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Wenn der Benutzer ein Element wählt oder die Auswahl ändert, benachrichtigt das Steuerelement das Hostfenster durch Senden einer [ `WM_COMMAND` Nachricht](/windows/desktop/menurc/wm-command), löst dadurch die <xref:System.Windows.Interop.HwndHost.MessageHook> -Ereignis für die Seite. Der Handler empfängt dieselben Informationen wie die Hauptfensterprozedur des Hostfensters. Sie übergibt außerdem einen Verweis auf ein boolescher Wert, `handled`. Sie legen `handled` zu `true` , um anzugeben, dass Sie die Meldung verarbeitet wurde und keine weitere Verarbeitung erforderlich ist.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) wird für eine Vielzahl von Gründen gesendet, damit Sie, dass die benachrichtigungs-ID überprüfen müssen, um festzustellen, ob es sich um ein Ereignis handelt, die Sie behandeln möchten. Die ID ist das hohe Word der Bestandteil der `wParam` Parameter. Das Beispiel verwendet bitweise Operatoren, um die ID zu extrahieren Wenn der Benutzer vorgenommen oder deren Auswahl geändert hat, werden die ID [ `LBN_SELCHANGE` ](/windows/desktop/Controls/lbn-selchange).  
  
 Wenn [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx) wird empfangen, das Beispiel ruft den Index des ausgewählten Elements von an das Steuerelements sendet eine [ `LB_GETCURSEL` Nachricht](/windows/desktop/Controls/lb-getcursel). Um den Text zu erhalten, erstellen Sie zunächst eine <xref:System.Text.StringBuilder>. Sie senden, klicken Sie dann das Steuerelement eine [ `LB_GETTEXT` Nachricht](/windows/desktop/Controls/lb-gettext). Übergeben Sie die leere <xref:System.Text.StringBuilder> -Objekts entsprechend der `wParam` Parameter. Wenn [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) zurückgegeben wird, die <xref:System.Text.StringBuilder> enthält den Text des ausgewählten Elements. Diese Verwendung von [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) erfordert noch eine andere PInvoke-Deklaration.  
  
 Legen Sie schließlich `handled` zu `true` , um anzugeben, dass die Nachricht verarbeitet wurde.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Interop.HwndHost>
- [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
- [Exemplarische Vorgehensweise: Walkthrough: My first WPF desktop application (Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung)](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
