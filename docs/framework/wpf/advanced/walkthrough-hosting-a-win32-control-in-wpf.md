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
ms.openlocfilehash: af8491a2887f4a35e2cd9926304948c12a67623a
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314977"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF
Windows Presentation Foundation (WPF) bietet eine funktionsreiche Umgebung zum Erstellen von Anwendungen. Jedoch, wenn Sie eine erhebliche Investition in Win32-Code verfügen, es möglicherweise effektiver mindestens einige wiederverwenden, code in der WPF-Anwendung statt es vollständig neu zu schreiben. WPF bietet ein einfaches Verfahren zum Hosten von Win32-Fenster auf einer WPF-Seite.  
  
 Dieses Thema führt Sie durch eine Anwendung [hosten ein Win32-ListBox-Steuerelement in WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), Hosts über ein Win32-Listenfeld steuern. Diese allgemeine Prozedur kann erweitert werden, zum Hosten der Win32-Fenster.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 Dieses Thema setzt voraus, grundlegende Kenntnisse von WPF und Win32-Programmierung. Eine grundlegende Einführung in WPF-Programmierung finden Sie unter [Einstieg](../../../../docs/framework/wpf/getting-started/index.md). Eine Einführung in Win32-Programmierung noch, Sie sollten verweisen zahlreiche Büchern zu diesem Thema, insbesondere *Windows-Programmierung* von Charles Petzold.  
  
 Da das Beispiel, das in diesem Thema begleitet in c# implementiert wird, macht es Platform Invocation Services (PInvoke) verwenden, um die Win32-API zugreifen. Einige Kenntnisse in der mit PInvoke ist hilfreich, aber nicht unbedingt.  
  
> [!NOTE]
>  Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Sie erhalten oder vollständige Code einsehen können [hosten ein Win32-ListBox-Steuerelement in WPF-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 Dieser Abschnitt beschreibt, das grundlegende Verfahren zum Hosten eines Win32-Fensters auf einer WPF-Seite. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Die grundlegende Vorgehensweise beim Hosten ist:  
  
1.  Implementieren Sie eine WPF-Seite, um das Fenster zu hosten. Eine Möglichkeit besteht darin, erstellen Sie eine <xref:System.Windows.Controls.Border> Element um einen Abschnitt der Seite für das gehostete Fenster zu reservieren.  
  
2.  Implementieren Sie eine Klasse, um das Steuerelement zu hosten, die von erben <xref:System.Windows.Interop.HwndHost>.  
  
3.  In dieser Klasse überschreiben, die <xref:System.Windows.Interop.HwndHost> Klassenmember <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Erstellen Sie das gehostete Fenster als untergeordnetes Element des Fensters, das WPF-Seite enthält. Obwohl herkömmliche WPF-Programmierung nicht explizit müssen sie verwenden möchten, die Seite "hosting" ist ein Fenster mit einem Handle (HWND). Erhalten Sie auf die Seite HWND über die `hwndParent` Parameter von der <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> Methode. Das gehostete Fenster sollte als untergeordnetes Element dieses HWND erstellt werden.  
  
5.  Sobald Sie das Hostfenster erstellt haben, geben Sie das HWND des gehosteten Fensters zurück. Wenn Sie ein oder mehrere Win32-Steuerelemente hosten möchten, in der Regel müssen Sie erstellen ein Hostfenster als untergeordnetes Element des HWND und die untergeordneten Steuerelemente Elemente dieser Hostfenster. Umschließen die Steuerelemente in einem Hostfenster bietet eine einfache Möglichkeit für die WPF-Seite zum Empfangen von Benachrichtigungen von den Steuerelementen der einige bestimmte Win32-Probleme mit der Benachrichtigungen über die Grenze HWND behandelt.  
  
6.  Behandeln Sie spezifische an das Hostfenster gesendete Nachrichten, z.B. Benachrichtigungen von untergeordneten Steuerelementen. Hierfür gibt es zwei Möglichkeiten.  
  
    -   Überschreiben, falls gewünscht, um Meldungen in die Hostingklasse zu verarbeiten, die <xref:System.Windows.Interop.HwndHost.WndProc%2A> Methode der <xref:System.Windows.Interop.HwndHost> Klasse.  
  
    -   Wenn Sie es vorziehen, Sie haben das WPF die Nachrichten behandeln, behandeln die <xref:System.Windows.Interop.HwndHost> Klasse <xref:System.Windows.Interop.HwndHost.MessageHook> Ereignis im Code-Behind. Dieses Ereignis tritt für jede Nachricht auf, die vom gehosteten Fenster empfangen wird. Wenn Sie diese Option auswählen, müssen Sie dennoch überschreiben <xref:System.Windows.Interop.HwndHost.WndProc%2A>, aber Sie benötigen nur eine minimale Implementierung.  
  
7.  Überschreiben Sie die <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> und <xref:System.Windows.Interop.HwndHost.WndProc%2A> Methoden der <xref:System.Windows.Interop.HwndHost>. Müssen Sie diese Methoden nicht erfüllen, überschreiben die <xref:System.Windows.Interop.HwndHost> Vertrag, aber Sie können nur eine minimale Implementierung bereitstellen müssen.  
  
8.  In der Code-Behind-Datei, erstellen Sie eine Instanz des Steuerelements Hostingklasse, und stellen Sie es ein untergeordnetes Element eines der <xref:System.Windows.Controls.Border> Element, das zum Hosten des Fensters vorgesehen ist.  
  
9. Kommunikation mit dem gehosteten Fenster senden [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] Nachrichten und Behandeln von Nachrichten aus zugehöriges untergeordnetes Fenster, z. B. Benachrichtigungen von Steuerelementen.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementieren des Seitenlayouts  
 Das Layout der WPF-Seite, die das ListBox-Steuerelement hostet besteht aus zwei Bereichen. Der linken Seite der Seite hostet, verschiedene WPF-Steuerelemente, die eine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] , mit der Sie die Win32-Steuerelement zu ändern. In der oberen rechten Ecke der Seite befindet sich ein quadratischer Bereich für das gehostete ListBox-Steuerelement.  
  
 Der Code zum Implementieren dieses Layout ist ganz einfach. Das Stammelement ist eine <xref:System.Windows.Controls.DockPanel> , zwei untergeordnete Elemente besitzt. Der erste ist ein <xref:System.Windows.Controls.Border> -Element, das das ListBox-Steuerelement hostet. Es belegt einen 200x200 großen quadratischen Bereich in der oberen rechten Ecke der Seite. Das zweite ist ein <xref:System.Windows.Controls.StackPanel> Element, das einen Satz von WPF-Steuerelemente, die ermöglichen es Ihnen enthält, durch Festlegen der ListBox-Steuerelement zu bearbeiten und Anzeigen von Informationen verfügbar gemacht, interoperation Eigenschaften. Für die einzelnen Elemente, die untergeordneten Elemente sind die <xref:System.Windows.Controls.StackPanel>, finden Sie unter das Referenzmaterial für die verschiedenen Elemente Was ist, wird diese im Beispielcode unten aufgeführt sind, aber nicht hier erläuterten (die grundlegenden Interoperation Modell einer von ihnen nicht erforderlich ist, werden sie bereitgestellt, um das Beispiel einige Interaktivität hinzuzufügen).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementieren einer Klasse zum Hosten des Microsoft Win32-Steuerelements  
 Der Kern dieses Beispiels ist die Klasse ControlHost.cs, die das Steuerelement tatsächlich hostet. Es erbt von <xref:System.Windows.Interop.HwndHost>. Der Konstruktor akzeptiert zwei Parameter, Höhe und Breite, die die Höhe und Breite der entsprechen den <xref:System.Windows.Controls.Border> Element, das das ListBox-Steuerelement hostet. Diese Werte werden später verwendet, um sicherzustellen, dass die Größe des Steuerelements Übereinstimmungen die <xref:System.Windows.Controls.Border> Element.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 Des Weiteren gibt es auch einen Satz von Konstanten. Diese Konstanten sind größtenteils Winuser.h entnommen und ermöglichen es Ihnen, die herkömmliche Namen verwenden, beim Aufrufen von Win32-Funktionen.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Überschreiben von BuildWindowCore zum Erstellen des Microsoft Win32-Fensters  
 Sie überschreiben diese Methode, um das Win32-Fenster erstellen, das von der Seite gehostet wird, und stellen die Verbindung zwischen dem Fenster und der Seite. Da dieses Beispiel das Hosten eines ListBox-Steuerelements umfasst, werden zwei Fenster erstellt. Das erste ist das Fenster, das tatsächlich von der WPF-Seite gehostet wird. Das ListBox-Steuerelement wird als untergeordnetes Element dieses Fensters erstellt.  
  
 Dieser Ansatz wurde bewusst gewählt, um den Empfang von Benachrichtigungen aus dem Steuerelement zu vereinfachen. Die <xref:System.Windows.Interop.HwndHost> Klasse bietet die Möglichkeit zum Verarbeiten von Nachrichten an das Fenster, das sie hostet. Wenn Sie eine Win32-Host direkt steuern zu können, erhalten Sie die Nachrichten in der internen Nachrichtenschleife des Steuerelements. Sie können das Steuerelement anzeigen und ihm Nachrichten senden, aber Sie erhalten keine der Benachrichtigungen, die das Steuerelement an das übergeordnete Fenster sendet. Dies bedeutet unter anderem, dass Sie keine Möglichkeit haben, zu erkennen, wann der Benutzer mit dem Steuerelement interagiert. Erstellen Sie stattdessen ein Hostfenster, und machen Sie das Steuerelement zu einem untergeordneten Element dieses Fensters. Dadurch können Sie sowohl Nachrichten für das Hostfenster als auch vom Steuerelement gesendete Benachrichtigungen verarbeiten. Da das Hostfenster kaum mehr als ein einfacher Wrapper für das Steuerelement ist, bezeichnen wir das Gesamtpaket der Einfachheit halber künftig als ListBox-Steuerelement.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Erstellen des Hostfensters und des ListBox-Steuerelements  
 Sie können um ein Hostfenster für das Steuerelement zu erstellen, und erstellen und registrieren eine Fensterklasse verwenden PInvoke und so weiter. Ein wesentlicher einfacherer Ansatz ist jedoch, ein Fenster mithilfe der vordefinierten „statischen“ Fensterklasse zu definieren. Dadurch erhalten Sie mit minimalem Codieraufwand die Fensterprozedur, die Sie benötigen, um Benachrichtigungen vom Steuerelement zu empfangen.  
  
 Das HWND des Steuerelements wird über eine schreibgeschützte Eigenschaft verfügbar gemacht, sodass es von der Hostseite zum Senden von Nachrichten an das Steuerelement verwendet werden kann.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Das ListBox-Steuerelement wird als untergeordnetes Element des Hostfensters erstellt. Die Höhe und Breite beider Fenster werden wie oben erläutert auf die an den Konstruktor übergebenen Werte festgelegt. Dadurch wird sichergestellt, dass die Größe von Hostfenster und Steuerelement exakt dem auf der Seite reservierten Bereich entspricht.  Nachdem die Windows erstellt wurden, gibt das Beispiel ein <xref:System.Runtime.InteropServices.HandleRef> -Objekt, das HWND des Hostfensters enthält.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementieren von DestroyWindow und WndProc  
 Zusätzlich zu <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, müssen Sie auch überschreiben die <xref:System.Windows.Interop.HwndHost.WndProc%2A> und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> Methoden die <xref:System.Windows.Interop.HwndHost>. In diesem Beispiel werden die Nachrichten für das Steuerelement behandelt, durch die <xref:System.Windows.Interop.HwndHost.MessageHook> Handler auf, daher wird die Implementierung der <xref:System.Windows.Interop.HwndHost.WndProc%2A> und <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> ist minimal. Im Fall von <xref:System.Windows.Interop.HwndHost.WndProc%2A>legen `handled` auf `false` , um anzugeben, dass die Nachricht nicht verarbeitet wurde, und geben 0 zurück. Für <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, löschen Sie einfach das Fenster.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Hosten des Steuerelements auf der Seite  
 Um das Steuerelement auf der Seite zu hosten, erstellen Sie zunächst eine neue Instanz der dem `ControlHost` Klasse. Übergeben Sie die Höhe und Breite des Rahmenelements, das das Steuerelement enthält (`ControlHostElement`), die `ControlHost` Konstruktor. Dadurch wird sichergestellt, dass das Listenfeld die richtige Größe hat. Anschließend hosten Sie das Steuerelement auf der Seite durch Zuweisen der `ControlHost` -Objekt an die <xref:System.Windows.Controls.Decorator.Child%2A> Eigenschaft des Hosts <xref:System.Windows.Controls.Border>.  
  
 Im Beispiel fügt einen Handler, der die <xref:System.Windows.Interop.HwndHost.MessageHook> -Ereignis für die `ControlHost` zum Empfangen von Nachrichten aus dem Steuerelement. Dieses Ereignis wird für jede Nachricht ausgelöst, die an das gehostete Fenster gesendet wird. In diesem Fall sind dies die Nachrichten, die an das das eigentliche ListBox-Steuerelement umschließende Fenster gesendet werden, einschließlich der Benachrichtigungen aus dem Steuerelement. Das Beispiel ruft die SendMessage-Methode auf, um Informationen aus dem Steuerelement abzurufen und dessen Inhalt zu ändern. Wie die Seite im Detail mit dem Steuerelement kommuniziert, wird im nächsten Abschnitt erläutert.  
  
> [!NOTE]
>  Beachten Sie, dass zwei PInvoke-Deklarationen für SendMessage vorhanden sind. Dies ist notwendig, da eine verwendet den `wParam` Übergabe einer Zeichenfolge und der andere Parameter verwendet, um eine ganze Zahl übergeben. Um sicherzustellen, dass die Daten ordnungsgemäß gemarshallt werden, wird daher eine separate Deklaration für jede Signatur benötigt.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementieren der Kommunikation zwischen dem Steuerelement und der Seite  
 Bearbeiten Sie das Steuerelement durch Windows-Meldungen senden. Das Steuerelement benachrichtigt Sie, wenn der Benutzer durch Senden von Benachrichtigungen an das Hostfenster mit ihm interagiert. Die [hosten ein Win32-ListBox-Steuerelement in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) Beispiel enthält eine Benutzeroberfläche, mehrere Beispiele für die Funktionsweise bereitstellt:  
  
-   Der Liste ein Element hinzufügen.  
  
-   Das markierte Element aus der Liste löschen  
  
-   Den Text des aktuell markierten Elements anzeigen.  
  
-   Die Anzahl der Elemente in der Liste anzeigen.  
  
 Der Benutzer kann auch ein Element im Listenfeld auswählen, indem darauf klickt, genauso wie für einen konventionellen Win32-Anwendung. Die angezeigten Daten werden bei jeder Zustandsänderung des Listenfelds durch den Benutzer aktualisiert, egal ob ein Element ausgewählt, hinzugefügt oder angefügt wurde.  
  
 Um Elemente anzufügen, senden Sie im Listenfeld eine [ `LB_ADDSTRING` Nachricht](https://msdn.microsoft.com/library/windows/desktop/bb775181(v=vs.85).aspx). Um Elemente zu löschen, senden [ `LB_GETCURSEL` ](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx) den Index der aktuellen Auswahl abgerufen und dann [ `LB_DELETESTRING` ](https://msdn.microsoft.com/library/windows/desktop/bb775183(v=vs.85).aspx) beim Löschen des Elements. Das Beispiel auch sendet [ `LB_GETCOUNT` ](https://msdn.microsoft.com/library/windows/desktop/bb775195(v=vs.85).aspx), und der zurückgegebene Wert verwendet, um die Anzeige zu aktualisieren, die die Anzahl der Elemente anzeigt. Diese beiden Instanzen von [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) Verwenden eines PInvoke-Deklarationen, die im vorherigen Abschnitt erläutert.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Wenn der Benutzer ein Element wählt oder die Auswahl ändert, benachrichtigt das Steuerelement das Hostfenster durch Senden einer [ `WM_COMMAND` Nachricht](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx), löst die <xref:System.Windows.Interop.HwndHost.MessageHook> Ereignis für die Seite. Der Handler empfängt dieselben Informationen wie die Hauptfensterprozedur des Hostfensters. Sie übergibt außerdem einen Verweis auf einen booleschen Wert `handled`. Festlegen der `handled` auf `true` , um anzugeben, dass die Nachricht verarbeitet und keine weitere Verarbeitung erforderlich ist.  
  
 [`WM_COMMAND`](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx) wird für eine Vielzahl von Gründen, gesendet zu untersuchen müssen die benachrichtigungs-ID, um festzustellen, ob es sich um ein Ereignis handelt, die Sie behandeln möchten. Die ID ist im hohen Word des enthalten die `wParam` Parameter. Das Beispiel verwendet die bitweise Operatoren zum Extrahieren der ID. Wenn der Benutzer vorgenommen oder ihrer Auswahl geändert hat, werden die ID [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx).  
  
 Wenn [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx) wird empfangen, das Beispiel ruft den Index des ausgewählten Elements durch das Steuerelement senden eine [ `LB_GETCURSEL` Nachricht](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx). Um den Text zu erhalten, erstellen Sie zunächst eine <xref:System.Text.StringBuilder>. Sie senden das Steuerelement eine [ `LB_GETTEXT` Nachricht](https://msdn.microsoft.com/library/windows/desktop/bb761313(v=vs.85).aspx). Übergeben Sie die leere <xref:System.Text.StringBuilder> -Objekts entsprechend der `wParam` Parameter. Wenn [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) zurückgibt, die <xref:System.Text.StringBuilder> enthält den Text des ausgewählten Elements. Diese Verwendung von [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) noch eine andere Deklaration aus PInvoke erfordert.  
  
 Legen Sie schließlich `handled` zu `true` um anzugeben, dass die Meldung verarbeitet wurde.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Interop.HwndHost>  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
