---
title: Hosten eines Win32-Steuerelements in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 5185e60640c652b79bd105db54830ac3acc57129
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186743"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF
Windows Presentation Foundation (WPF) bietet eine umfassende Umgebung zum Erstellen von Anwendungen. Wenn Sie jedoch über eine erhebliche Investition in Win32-Code verfügen, ist es möglicherweise effektiver, zumindest einen Teil dieses Codes in Ihrer WPF-Anwendung wiederzuverwenden, anstatt ihn vollständig neu zu schreiben. WPF bietet einen einfachen Mechanismus zum Hosten eines Win32-Fensters auf einer WPF-Seite.  
  
 In diesem Thema werden Sie durch eine Anwendung mit dem [Hosten eines Win32 ListBox-Steuerelements in WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)geleitet, in dem ein Win32-Listenfeldsteuerelement gehostet wird. Dieses allgemeine Verfahren kann auf das Hosten eines beliebigen Win32-Fensters erweitert werden.  

<a name="requirements"></a>
## <a name="requirements"></a>Requirements (Anforderungen)  
 In diesem Thema wird eine grundlegende Vertrautheit mit der WPF- und der Windows-API-Programmierung vorausgesetzt. Eine grundlegende Einführung in die WPF-Programmierung finden Sie unter [Erste Schritte](../getting-started/index.md). Eine Einführung in die Windows-API-Programmierung finden Sie in einem der zahlreichen Bücher zu diesem Thema, insbesondere *Programming Windows* von Charles Petzold.  
  
 Da das Beispiel, das diesem Thema beiliegt, in C- implementiert ist, werden Platform Invocation Services (PInvoke) für den Zugriff auf die Windows-API verwendet. Eine gewisse Vertrautheit mit PInvoke ist hilfreich, aber nicht wesentlich.  
  
> [!NOTE]
> Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Sie können vollständigen Code über [das Hosten eines Win32 ListBox-Steuerelements in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)abrufen oder anzeigen.  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 In diesem Abschnitt wird das grundlegende Verfahren zum Hosten eines Win32-Fensters auf einer WPF-Seite beschrieben. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Die grundlegende Vorgehensweise beim Hosten ist:  
  
1. Implementieren Sie eine WPF-Seite, um das Fenster zu hosten. Eine Technik besteht <xref:System.Windows.Controls.Border> darin, ein Element zu erstellen, um einen Abschnitt der Seite für das gehostete Fenster zu reservieren.  
  
2. Implementieren Sie eine Klasse, um das <xref:System.Windows.Interop.HwndHost>Steuerelement zu hosten, das von erbt.  
  
3. Überschreiben Sie in <xref:System.Windows.Interop.HwndHost> dieser <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>Klasse den Klassenmember .  
  
4. Erstellen Sie das gehostete Fenster als untergeordnetes Element des Fensters, das die WPF-Seite enthält. Obwohl herkömmliche WPF-Programmierung nicht explizit genutzt werden muss, ist die Hostingseite ein Fenster mit einem Handle (HWND). Sie erhalten die Seite `hwndParent` HWND <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> über den Parameter der Methode. Das gehostete Fenster sollte als untergeordnetes Element dieses HWND erstellt werden.  
  
5. Sobald Sie das Hostfenster erstellt haben, geben Sie das HWND des gehosteten Fensters zurück. Wenn Sie ein oder mehrere Win32-Steuerelemente hosten möchten, erstellen Sie in der Regel ein Hostfenster als untergeordnetes Element der HWND und machen die Steuerelemente zu untergeordneten Elementen dieses Hostfensters. Das Umschließen der Steuerelemente in einem Hostfenster bietet eine einfache Möglichkeit für Ihre WPF-Seite, Benachrichtigungen von den Steuerelementen zu erhalten, die bestimmte Win32-Probleme mit Benachrichtigungen über die HWND-Grenze hinweg behandeln.  
  
6. Behandeln Sie spezifische an das Hostfenster gesendete Nachrichten, z.B. Benachrichtigungen von untergeordneten Steuerelementen. Es gibt hierbei zwei Möglichkeiten.  
  
    - Wenn Sie Nachrichten in Ihrer Hostingklasse behandeln <xref:System.Windows.Interop.HwndHost.WndProc%2A> möchten, <xref:System.Windows.Interop.HwndHost> überschreiben Sie die Methode der Klasse.  
  
    - Wenn Sie möchten, dass der WPF <xref:System.Windows.Interop.HwndHost> die <xref:System.Windows.Interop.HwndHost.MessageHook> Nachrichten verarbeitet, behandeln Sie das Klassenereignis in Ihrem CodeBehind. Dieses Ereignis tritt für jede Nachricht auf, die vom gehosteten Fenster empfangen wird. Wenn Sie diese Option auswählen, <xref:System.Windows.Interop.HwndHost.WndProc%2A>müssen Sie immer noch überschreiben, aber Sie benötigen nur eine minimale Implementierung.  
  
7. Überschreiben <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> Sie <xref:System.Windows.Interop.HwndHost.WndProc%2A> die <xref:System.Windows.Interop.HwndHost>und-Methoden von . Sie müssen diese Methoden überschreiben, um den <xref:System.Windows.Interop.HwndHost> Vertrag zu erfüllen, aber Sie müssen möglicherweise nur eine minimale Implementierung bereitstellen.  
  
8. Erstellen Sie in der CodeBehind-Datei eine Instanz der Steuerelementhostingklasse, und machen Sie sie zu einem untergeordneten Element des <xref:System.Windows.Controls.Border> Elements, das das Fenster hosten soll.  
  
9. Kommunizieren Sie mit dem gehosteten Fenster, indem Sie ihm Microsoft Windows-Nachrichten senden und Nachrichten von seinen untergeordneten Fenstern verarbeiten, z. B. Benachrichtigungen, die von Steuerelementen gesendet werden.  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>Implementieren des Seitenlayouts  
 Das Layout für die WPF-Seite, auf der das ListBox-Steuerelement gehostet wird, besteht aus zwei Regionen. Auf der linken Seite der Seite werden [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mehrere WPF-Steuerelemente gehostet, mit denen Sie das Win32-Steuerelement bearbeiten können. In der oberen rechten Ecke der Seite befindet sich ein quadratischer Bereich für das gehostete ListBox-Steuerelement.  
  
 Der Code zum Implementieren dieses Layouts ist ganz einfach. Das Stammelement <xref:System.Windows.Controls.DockPanel> ist ein Element mit zwei untergeordneten Elementen. Das erste <xref:System.Windows.Controls.Border> ist ein Element, das das ListBox-Steuerelement hostet. Es belegt einen 200x200 großen quadratischen Bereich in der oberen rechten Ecke der Seite. Das zweite <xref:System.Windows.Controls.StackPanel> Element enthält einen Satz von WPF-Steuerelementen, mit denen Informationen angezeigt werden und mit denen Sie das ListBox-Steuerelement bearbeiten können, indem Sie verfügbar gemachte Interoperationseigenschaften festlegen. Für jedes elementare Elemente der <xref:System.Windows.Controls.StackPanel>siehe das Referenzmaterial für die verschiedenen Elemente, die für Details darüber verwendet werden, was diese Elemente sind oder was sie tun, werden diese im Beispielcode unten aufgeführt, werden aber hier nicht erläutert (das grundlegende Interoperationsmodell erfordert keines davon, sie werden bereitgestellt, um der Stichprobe eine gewisse Interaktivität hinzuzufügen).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementieren einer Klasse zum Hosten des Microsoft Win32-Steuerelements  
 Der Kern dieses Beispiels ist die Klasse ControlHost.cs, die das Steuerelement tatsächlich hostet. Er erbt von <xref:System.Windows.Interop.HwndHost>. Der Konstruktor verwendet zwei Parameter, Höhe und Breite, die <xref:System.Windows.Controls.Border> der Höhe und Breite des Elements entsprechen, das das ListBox-Steuerelement hostet. Diese Werte werden später verwendet, um sicherzustellen, <xref:System.Windows.Controls.Border> dass die Größe des Steuerelements mit dem Element übereinstimmt.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Des Weiteren gibt es auch einen Satz von Konstanten. Diese Konstanten stammen größtenteils von Winuser.h und ermöglichen es Ihnen, herkömmliche Namen beim Aufrufen von Win32-Funktionen zu verwenden.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Überschreiben von BuildWindowCore zum Erstellen des Microsoft Win32-Fensters  
 Sie überschreiben diese Methode, um das Win32-Fenster zu erstellen, das von der Seite gehostet wird, und stellen die Verbindung zwischen dem Fenster und der Seite her. Da dieses Beispiel das Hosten eines ListBox-Steuerelements umfasst, werden zwei Fenster erstellt. Das erste ist das Fenster, das tatsächlich von der WPF-Seite gehostet wird. Das ListBox-Steuerelement wird als untergeordnetes Element dieses Fensters erstellt.  
  
 Dieser Ansatz wurde bewusst gewählt, um den Empfang von Benachrichtigungen aus dem Steuerelement zu vereinfachen. Mit <xref:System.Windows.Interop.HwndHost> der Klasse können Sie Nachrichten verarbeiten, die an das Fenster gesendet werden, das sie hostet. Wenn Sie ein Win32-Steuerelement direkt hosten, erhalten Sie die Nachrichten, die an die interne Nachrichtenschleife des Steuerelements gesendet werden. Sie können das Steuerelement anzeigen und ihm Nachrichten senden, aber Sie erhalten keine der Benachrichtigungen, die das Steuerelement an das übergeordnete Fenster sendet. Dies bedeutet unter anderem, dass Sie keine Möglichkeit haben, zu erkennen, wann der Benutzer mit dem Steuerelement interagiert. Erstellen Sie stattdessen ein Hostfenster, und machen Sie das Steuerelement zu einem untergeordneten Element dieses Fensters. Dadurch können Sie sowohl Nachrichten für das Hostfenster als auch vom Steuerelement gesendete Benachrichtigungen verarbeiten. Da das Hostfenster kaum mehr als ein einfacher Wrapper für das Steuerelement ist, bezeichnen wir das Gesamtpaket der Einfachheit halber künftig als ListBox-Steuerelement.  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>Erstellen des Hostfensters und des ListBox-Steuerelements  
 Sie können PInvoke verwenden, um ein Hostfenster für das Steuerelement zu erstellen, indem Sie eine Fensterklasse erstellen und registrieren usw. Ein wesentlicher einfacherer Ansatz ist jedoch, ein Fenster mithilfe der vordefinierten „statischen“ Fensterklasse zu definieren. Dadurch erhalten Sie mit minimalem Codieraufwand die Fensterprozedur, die Sie benötigen, um Benachrichtigungen vom Steuerelement zu empfangen.  
  
 Das HWND des Steuerelements wird über eine schreibgeschützte Eigenschaft verfügbar gemacht, sodass es von der Hostseite zum Senden von Nachrichten an das Steuerelement verwendet werden kann.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Das ListBox-Steuerelement wird als untergeordnetes Element des Hostfensters erstellt. Die Höhe und Breite beider Fenster werden wie oben erläutert auf die an den Konstruktor übergebenen Werte festgelegt. Dadurch wird sichergestellt, dass die Größe von Hostfenster und Steuerelement exakt dem auf der Seite reservierten Bereich entspricht.  Nachdem die Fenster erstellt wurden, <xref:System.Runtime.InteropServices.HandleRef> gibt das Beispiel ein Objekt zurück, das die HWND des Hostfensters enthält.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>Implementieren von DestroyWindow und WndProc  
 Zusätzlich zu <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>müssen Sie auch <xref:System.Windows.Interop.HwndHost.WndProc%2A> die <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> und <xref:System.Windows.Interop.HwndHost>Methoden der überschreiben. In diesem Beispiel werden die Meldungen für <xref:System.Windows.Interop.HwndHost.MessageHook> das Steuerelement vom <xref:System.Windows.Interop.HwndHost.WndProc%2A> Handler <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> verarbeitet, daher ist die Implementierung von und minimal. Im Fall <xref:System.Windows.Interop.HwndHost.WndProc%2A>von `handled` wird `false` auf , angegeben, dass die Nachricht nicht verarbeitet wurde, und geben Sie 0 zurück. Für <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, zerstören Sie einfach das Fenster.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>Hosten des Steuerelements auf der Seite  
 Um das Steuerelement auf der Seite zu hosten, erstellen Sie zunächst eine neue Instanz der `ControlHost` Klasse. Übergeben Sie die Höhe und Breite des`ControlHostElement`Rahmenelements, `ControlHost` das das Steuerelement ( ) enthält, an den Konstruktor. Dadurch wird sichergestellt, dass das Listenfeld die richtige Größe hat. Anschließend hosten Sie das Steuerelement auf `ControlHost` der <xref:System.Windows.Controls.Decorator.Child%2A> Seite, indem <xref:System.Windows.Controls.Border>Sie das Objekt der Eigenschaft des Hosts zuweisen.  
  
 Das Beispiel fügt einen <xref:System.Windows.Interop.HwndHost.MessageHook> Handler an `ControlHost` das Ereignis des zum Empfangen von Nachrichten vom Steuerelement an. Dieses Ereignis wird für jede Nachricht ausgelöst, die an das gehostete Fenster gesendet wird. In diesem Fall sind dies die Nachrichten, die an das das eigentliche ListBox-Steuerelement umschließende Fenster gesendet werden, einschließlich der Benachrichtigungen aus dem Steuerelement. Das Beispiel ruft die SendMessage-Methode auf, um Informationen aus dem Steuerelement abzurufen und dessen Inhalt zu ändern. Wie die Seite im Detail mit dem Steuerelement kommuniziert, wird im nächsten Abschnitt erläutert.  
  
> [!NOTE]
> Beachten Sie, dass es zwei PInvoke-Deklarationen für SendMessage gibt. Dies ist notwendig, `wParam` da der eine den Parameter verwendet, um eine Zeichenfolge zu übergeben, und der andere ihn verwendet, um eine ganze Zahl zu übergeben. Um sicherzustellen, dass die Daten ordnungsgemäß gemarshallt werden, wird daher eine separate Deklaration für jede Signatur benötigt.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementieren der Kommunikation zwischen dem Steuerelement und der Seite  
 Sie bearbeiten das Steuerelement, indem Sie es Windows-Nachrichten senden. Das Steuerelement benachrichtigt Sie, wenn der Benutzer durch Senden von Benachrichtigungen an das Hostfenster mit ihm interagiert. Das [Hosten eines Win32 ListBox-Steuerelements im WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) enthält eine Benutzeroberfläche, die mehrere Beispiele dafür enthält:  
  
- Der Liste ein Element hinzufügen.  
  
- Das markierte Element aus der Liste löschen  
  
- Den Text des aktuell markierten Elements anzeigen.  
  
- Die Anzahl der Elemente in der Liste anzeigen.  
  
 Der Benutzer kann auch ein Element im Listenfeld auswählen, indem er darauf klickt, genau wie bei einer herkömmlichen Win32-Anwendung. Die angezeigten Daten werden bei jeder Zustandsänderung des Listenfelds durch den Benutzer aktualisiert, egal ob ein Element ausgewählt, hinzugefügt oder angefügt wurde.  
  
 Um Elemente anzuhängen, senden [ `LB_ADDSTRING` ](/windows/desktop/Controls/lb-addstring)Sie dem Listenfeld eine Nachricht . Um Elemente zu [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) löschen, senden Sie, um [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) den Index der aktuellen Auswahl abzubekommen, und löschen Sie dann das Element. Das Beispiel [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)sendet auch , und verwendet den zurückgegebenen Wert, um die Anzeige zu aktualisieren, die die Anzahl der Elemente anzeigt. Beide [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) Anwendungsinstanzen verwenden eine der im vorherigen Abschnitt beschriebenen PInvoke-Deklarationen.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Wenn der Benutzer ein Element auswählt oder seine Auswahl ändert, benachrichtigt das Steuerelement das <xref:System.Windows.Interop.HwndHost.MessageHook> Hostfenster, indem es eine [ `WM_COMMAND` Nachricht](/windows/desktop/menurc/wm-command)sendet, die das Ereignis für die Seite auslöst. Der Handler empfängt dieselben Informationen wie die Hauptfensterprozedur des Hostfensters. Es übergibt auch einen Verweis `handled`auf einen booleschen Wert, . Sie `handled` legen `true` fest, dass Sie angeben, dass Sie die Nachricht verarbeitet haben und keine weitere Verarbeitung erforderlich ist.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)wird aus einer Vielzahl von Gründen gesendet, daher müssen Sie die Benachrichtigungs-ID überprüfen, um festzustellen, ob es sich um ein Ereignis handelt, das Sie behandeln möchten. Die ID ist im hohen `wParam` Wort des Parameters enthalten. Das Beispiel verwendet bitweise Operatoren, um die ID zu extrahieren. Wenn der Benutzer seine Auswahl vorgenommen oder [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)geändert hat, wird die ID .  
  
 Wenn [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) das Beispiel empfangen wird, ruft es den Index [ `LB_GETCURSEL` ](/windows/desktop/Controls/lb-getcursel)des ausgewählten Elements ab, indem dem Steuerelement eine Nachricht gesendet wird. Um den Text zu erhalten, erstellen Sie zunächst eine <xref:System.Text.StringBuilder>. Anschließend senden Sie [ `LB_GETTEXT` ](/windows/desktop/Controls/lb-gettext)dem Steuerelement eine Nachricht . Übergeben Sie <xref:System.Text.StringBuilder> das `wParam` leere Objekt als Parameter. Wenn [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) zurückgegeben <xref:System.Text.StringBuilder> wird, enthält der den Text des ausgewählten Elements. Diese Verwendung [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) von erfordert eine weitere PInvoke-Deklaration.  
  
 Legen Sie `handled` `true` schließlich fest, dass die Nachricht verarbeitet wurde.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Interop.HwndHost>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
