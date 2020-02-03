---
title: Hosten von WPF-Inhalt in Win32
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: ff95b330ff67e916a4d27ef841e757998d847c8b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735318"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie jedoch eine beträchtliche Investition in Win32-Code haben, kann es effektiver sein, der Anwendung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Funktionalität hinzuzufügen, anstatt den ursprünglichen Code neu zu schreiben. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt einen einfachen Mechanismus zum Hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts in einem Win32-Fenster bereit.  
  
 In diesem Tutorial wird beschrieben, wie Sie eine Beispielanwendung, die [WPF-Inhalte hostet, in einem Win32-Fenster Beispiel](https://go.microsoft.com/fwlink/?LinkID=160004)schreiben, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einem Win32-Fenster hostet. Sie können dieses Beispiel erweitern, um beliebige Win32-Fenster zu hosten. Da verwalteter und nicht verwalteter Code gemischt werden muss, wird die Anwendung C++in/CLI. geschrieben.  

<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Tutorial wird davon ausgegangen, dass es sich um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-und Win32-Programmierung handelt. Eine grundlegende Einführung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung finden Sie unter [Getting Started](../getting-started/index.md). Eine Einführung in die Win32-Programmierung finden Sie in den zahlreichen Büchern zu diesem Thema, insbesondere in den *Programmier Fenstern* von Charles Petzold.  
  
 Da das Beispiel für dieses Lernprogramm in/CLI implementiert C++ist, wird in diesem Tutorial die Verwendung von C++ zum Programmieren der Windows-API und ein Verständnis der Programmierung mit verwaltetem Code vorausgesetzt. Vertrautheit mit C++/CLI ist hilfreich, aber nicht unbedingt erforderlich.  
  
> [!NOTE]
> Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den gesamten Beispielcode finden Sie unter [Hosting WPF Content in a Win32 Window Sample](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 In diesem Abschnitt wird das grundlegende Verfahren erläutert, das Sie zum Hosten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einem Win32-Fenster verwenden. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Der Schlüssel zum Hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts in einem Win32-Fenster ist die <xref:System.Windows.Interop.HwndSource>-Klasse. Diese Klasse umschließt den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einem Win32-Fenster, sodass er als untergeordnetes Fenster in Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] eingebunden werden kann. Der folgende Ansatz kombiniert Win32 und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer einzigen Anwendung.  
  
1. Implementieren Sie Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte als verwaltete Klasse.  
  
2. Implementieren einer Windows-Anwendung C++mit/CLI. Wenn Sie mit einer vorhandenen Anwendung und nicht verwaltetem C++ Code beginnen, können Sie diese normalerweise aktivieren, um verwalteten Code aufzurufen, indem Sie die Projekteinstellungen so ändern, dass Sie das `/clr`-Compilerflag enthalten.  
  
3. Legen Sie das Threadingmodell auf Singlethread-Apartment (STA) fest.  
  
4. Behandeln Sie die [WM_CREATE](/windows/desktop/winmsg/wm-create)Benachrichtigung in der Fenster Prozedur, und führen Sie die folgenden Schritte aus:  
  
    1. Erstellen Sie ein neues <xref:System.Windows.Interop.HwndSource>-Objekt, und verwenden Sie das übergeordnete Fenster als `parent`-Parameter.  
  
    2. Erstellen Sie eine Instanz der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse.  
  
    3. Weisen Sie der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>einen Verweis auf das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Objekt zu.  
  
    4. Rufen Sie HWND für den Inhalt ab. Die <xref:System.Windows.Interop.HwndSource.Handle%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts enthält das Fensterhandle (HWND). Um ein HWND zu erhalten, das Sie im nicht verwalteten Teil der Anwendung verwenden können, wandeln Sie `Handle.ToPointer()` in ein HWND um.  
  
5. Implementieren Sie eine verwaltete Klasse, die ein statisches Feld mit einem Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt enthält. Diese Klasse ermöglicht es Ihnen, einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt aus Ihrem Win32-Code zu erhalten.  
  
6. Weisen Sie dem statischen Feld den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu.  
  
7. Empfangen von Benachrichtigungen vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt durch Anhängen eines Handlers an ein oder mehrere der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignisse.  
  
8. Kommunizieren Sie mithilfe des im statischen Feld gespeicherten Verweises mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt, um Eigenschaften festzulegen usw.  
  
> [!NOTE]
> Sie können auch [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwenden, um Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu implementieren. Sie müssen Sie jedoch separat als Dynamic Link Library (dll) kompilieren und von ihrer Win32-Anwendung aus auf diese DLL verweisen. Die übrigen Schritte ähneln dem oben beschriebenen Verfahren.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung
 In diesem Abschnitt wird beschrieben, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einer einfachen Win32-Anwendung gehostet wird. Der Inhalt selbst wird in C++/CLI als verwaltete Klasse implementiert. Größtenteils handelt es sich um eine einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung. Die wichtigsten Aspekte der Inhalts Implementierung werden unter [Implementieren des WPF-Inhalts](#implementing_the_wpf_page)erläutert.

- [Die grundlegende Anwendung](#the_basic_application)

- [Hosten des WPF-Inhalts](#hosting_the_wpf_page)

- [Verweisen auf den WPF-Inhalt](#holding_a_reference)

- [Kommunizieren mit dem WPF-Inhalt](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Die grundlegende Anwendung
 Der Ausgangspunkt für die Host Anwendung bestand darin, eine Visual Studio 2005-Vorlage zu erstellen.

1. Öffnen Sie Visual Studio 2005, und wählen Sie im Menü **Datei** die Option **Neues Projekt** aus.

2. Wählen Sie **Win32** aus der Liste der C++ visuellen Projekttypen aus. Wenn die Standardsprache nicht C++ist, finden Sie diese Projekttypen unter **andere Sprachen**.

3. Wählen Sie eine **Win32-Projekt** Vorlage aus, weisen Sie dem Projekt einen Namen zu, und klicken Sie auf **OK** , um den Win32- **Anwendungs-Assistenten**

4. Akzeptieren Sie die Standardeinstellungen des Assistenten, und klicken Sie zum Starten des Projekts auf **Fertig** stellen.

 Die Vorlage erstellt eine einfache Win32-Anwendung, einschließlich:

- Einen Einstiegspunkt für die Anwendung.

- Ein Fenster mit einer zugeordneten Fensterprozedur (WndProc).

- Ein Menü mit **Datei** -und **Hilfe** Überschriften. Das Menü **Datei** enthält ein **Exit** -Element, mit dem die Anwendung geschlossen wird. Das Menü **Hilfe** enthält ein Element Info, **mit** dem ein einfaches Dialogfeld gestartet wird.

 Bevor Sie mit dem Schreiben von Code beginnen, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt zu hosten, müssen Sie zwei Änderungen an der grundlegenden Vorlage vornehmen.

 Die erste besteht darin, das Projekt als verwalteten Code zu kompilieren. Standardmäßig wird das Projekt als nicht verwalteter Code kompiliert. Da aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in verwaltetem Code implementiert wird, muss das Projekt entsprechend kompiliert werden.

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und wählen Sie Eigenschaften aus dem Kontextmenü aus, um das Dialogfeld **Eigenschaften** **Seiten** aufzurufen.

2. Wählen Sie in der Strukturansicht im linken Bereich **Konfigurations Eigenschaften** aus.

3. Wählen Sie in der Liste **Projekt** Standards im rechten Bereich die Option **Common Language Runtime** -Unterstützung aus.

4. Wählen Sie im Dropdown-Listenfeld die Option **Common Language Runtime-Unterstützung (/CLR)** aus.

> [!NOTE]
> Das Compilerflag ermöglicht Ihnen, in der Anwendung verwalteten Code zu verwenden. Der nicht verwaltete Code wird jedoch wie zuvor kompiliert.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet das Threadingmodell Singlethread-Apartment (STA). Um ordnungsgemäß mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Code zu arbeiten, müssen Sie das Threading Modell der Anwendung auf STA festlegen, indem Sie ein Attribut auf den Einstiegspunkt anwenden.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hosten des WPF-Inhalts
 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ist eine einfache Anwendung für den Adresseintrag. Sie besteht aus mehreren <xref:System.Windows.Controls.TextBox>-Steuerelementen zum Erfassen von Benutzername, Adresse usw. Es gibt auch zwei <xref:System.Windows.Controls.Button>-Steuerelemente: **OK** und **Abbrechen**. Wenn der Benutzer auf **OK**klickt, sammelt der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler der Schaltfläche die Daten aus den <xref:System.Windows.Controls.TextBox> Steuerelementen, weist Sie den entsprechenden Eigenschaften zu und löst ein benutzerdefiniertes Ereignis aus, `OnButtonClicked`. Wenn der Benutzer auf **Abbrechen**klickt, löst der Handler einfach `OnButtonClicked`aus. Das Ereignisargumentobjekt für `OnButtonClicked` enthält ein boolesches Feld, das angibt, auf welche Schaltfläche geklickt wurde.

 Der Code zum Hosten des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts wird in einem Handler für die [WM_CREATE](/windows/desktop/winmsg/wm-create) Benachrichtigung im Host Fenster implementiert.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 Die `GetHwnd`-Methode übernimmt Größen-und Positionsinformationen sowie das übergeordnete Fenster Handle und gibt das Fenster Handle des gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts zurück.

> [!NOTE]
> Sie können keine `#using`-Direktive für den `System::Windows::Interop`-Namespace verwenden. Dies würde zu einem Namenskonflikt zwischen der <xref:System.Windows.Interop.MSG>-Struktur in diesem Namespace und der in winuser.h deklarierten MSG-Struktur führen. Verwenden Sie stattdessen vollqualifizierte Namen, um auf den Inhalt dieses Namespace zuzugreifen.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt nicht direkt im Anwendungsfenster hosten. Stattdessen müssen Sie zuerst ein <xref:System.Windows.Interop.HwndSource>-Objekt erstellen, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu umschließen. Bei diesem Objekt handelt es sich im Grunde um ein Fenster, das zum Hosten eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts konzipiert ist. Sie hosten das <xref:System.Windows.Interop.HwndSource> Objekt im übergeordneten Fenster, indem Sie es als untergeordnetes Element eines Win32-Fensters erstellen, das Teil Ihrer Anwendung ist. Die <xref:System.Windows.Interop.HwndSource>-Konstruktorparameter enthalten die gleichen Informationen, die Sie an "kreatewindow" übergeben würden, wenn Sie ein untergeordnetes Win32-Fenster erstellen.

 Im nächsten Schritt erstellen Sie eine Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Objekts. In diesem Fall wird der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt als separate Klasse, `WPFPage`, mithilfe C++von/CLI. implementiert. Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt auch mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementieren. Hierzu müssen Sie jedoch ein separates Projekt einrichten und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt als DLL erstellen. Sie können dem Projekt einen Verweis auf die dll hinzufügen und mit diesem Verweis eine Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts erstellen.

 Sie zeigen den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in Ihrem untergeordneten Fenster an, indem Sie der Eigenschaft <xref:System.Windows.Interop.HwndSource.RootVisual%2A> der <xref:System.Windows.Interop.HwndSource>einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zuweisen.

 Durch die nächste Codezeile wird ein Ereignishandler (`WPFButtonClicked`) an das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignis des `OnButtonClicked`-Inhalts angefügt. Dieser Handler wird aufgerufen, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt. Weitere Informationen zu diesem Ereignishandler finden Sie unter [communicating_with_the_WPF Inhalt](#communicating_with_the_page) .

 Durch die letzte angezeigte Codezeile wird das Fensterhandle (HWND) zurückgegeben, das dem <xref:System.Windows.Interop.HwndSource>-Objekt zugeordnet ist. Sie können dieses Handle aus dem Win32-Code verwenden, um Nachrichten an das gehostete Fenster zu senden, obwohl das Beispiel dies nicht tut. Das <xref:System.Windows.Interop.HwndSource>-Objekt löst jedes Mal ein Ereignis aus, wenn es eine Meldung empfängt. Rufen Sie zum Verarbeiten der Meldungen die <xref:System.Windows.Interop.HwndSource.AddHook%2A>-Methode auf, um einen Meldungshandler anzufügen und anschließend die Meldungen in diesem Handler zu verarbeiten.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Verweisen auf den WPF-Inhalt
 Bei vielen Anwendungen möchten Sie zu einem späteren Zeitpunkt mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt kommunizieren. Angenommen, Sie möchten die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften ändern oder vom <xref:System.Windows.Interop.HwndSource>-Objekt andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalte hosten lassen. Dazu benötigen Sie einen Verweis auf das <xref:System.Windows.Interop.HwndSource>-Objekt oder den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Das <xref:System.Windows.Interop.HwndSource>-Objekt und der zugehörige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt bleiben im Arbeitsspeicher, bis Sie das Fensterhandle zerstören. Die Variable, die Sie dem <xref:System.Windows.Interop.HwndSource>-Objekt zuweisen, verlässt jedoch den Gültigkeitsbereich, sobald die Steuerung von der Fensterprozedur zurückgegeben wird. Die übliche Vorgehensweise zum Behandeln dieses Problems mit Win32-Anwendungen ist die Verwendung einer statischen oder globalen Variablen. Leider können Sie diesen Variablentypen kein verwaltetes Objekt zuweisen. Sie können das Fensterhandle, das dem <xref:System.Windows.Interop.HwndSource>-Objekt zugeordnet ist, einer globalen oder statischen Variablen zuweisen. Dadurch erhalten Sie aber noch keinen Zugriff auf das Objekt.

 Die einfachste Lösung für dieses Problem besteht darin, eine verwaltete Klasse zu implementieren, die eine Reihe von statischen Feldern mit Verweisen auf alle verwalteten Objekte enthält, auf die Sie zugreifen müssen. Im Beispiel wird die `WPFPageHost`-Klasse für einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt verwendet. Außerdem soll sie die Anfangswerte einiger Eigenschaften enthalten, die später vom Benutzer geändert werden können. Dies wird im Header definiert.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 Der letzte Teil der `GetHwnd`-Funktion weist diesen Feldern Werte zur späteren Verwendung zu, während `myPage` im Gültigkeitsbereich verbleibt.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Kommunizieren mit dem WPF-Inhalt
 Es gibt zwei Arten der Kommunikation mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Die Anwendung empfängt Informationen vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, wenn der Benutzer auf die Schaltflächen **OK** oder **Abbrechen** klickt. Die Anwendung verfügt auch über eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die es dem Benutzer ermöglicht, zahlreiche [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften zu ändern, z. B. Hintergrundfarbe oder Standardschriftgröße.

 Wie oben erwähnt, löst der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt ein `OnButtonClicked`-Ereignis aus, wenn der Benutzer auf eine der beiden Schaltflächen klickt. Die Anwendung fügt einen Handler an dieses Ereignis an, um die entsprechenden Benachrichtigungen zu empfangen. Wenn auf die Schaltfläche **OK** geklickt wurde, ruft der Handler die Benutzerinformationen aus dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ab und zeigt ihn in einem Satz statischer Steuerelemente an.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 Der Handler empfängt ein benutzerdefiniertes Ereignisargumentobjekt vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt: `MyPageEventArgs`. Die `IsOK`-Eigenschaft des Objekts wird auf `true` festgelegt, wenn auf die Schaltfläche **OK** geklickt wurde, und `false`, wenn auf die Schaltfläche **Abbrechen** geklickt wurde.

 Wenn auf die Schaltfläche **OK** geklickt wurde, ruft der Handler einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt aus der Container Klasse ab. Anschließend ruft er die Benutzerinformationen ab, die in den zugeordneten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften enthalten sind. Dabei werden die statischen Steuerelemente zum Anzeigen der Informationen im übergeordneten Fenster verwendet. Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhaltsdaten in Form einer verwalteten Zeichenfolge vorliegen, müssen Sie für die Verwendung durch ein Win32-Steuerelement gemarshallt werden. Wenn auf die Schaltfläche **Abbrechen** geklickt wurde, löscht der Handler die Daten aus den statischen Steuerelementen.

 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung stellt eine Reihe von Optionsfeldern bereit, mit denen der Benutzer die Hintergrundfarbe des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts und verschiedene Schriftarteigenschaften ändern kann. Das folgende Beispiel ist ein Auszug aus der Fensterprozedur der Anwendung (WndProc) und deren Meldungsbehandlung, die zahlreiche Eigenschaften für verschiedene Meldungen festlegt, darunter die Hintergrundfarbe. Die anderen sind ähnlich und werden nicht angezeigt. Sehen Sie sich das vollständige Beispiel an, um ausführliche Informationen, auch zum Kontext, zu erhalten.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Wenn Sie die Hintergrundfarbe festlegen möchten, rufen Sie einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt (`hostedPage`) von `WPFPageHost` ab, und legen Sie die Eigenschaft für die Hintergrundfarbe auf die entsprechende Farbe fest. Im Beispiel werden drei Farboptionen verwendet: die ursprüngliche Farbe, hellgrün oder helle Lachsfarbe. Die ursprüngliche Hintergrundfarbe wird als statisches Feld in der `WPFPageHost`-Klasse gespeichert. Um die anderen beiden festzulegen, erstellen Sie ein neues <xref:System.Windows.Media.SolidColorBrush>-Objekt und übergeben dem Konstruktor einen statischen Farbwert aus dem <xref:System.Windows.Media.Colors>-Objekt.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementieren der WPF-Seite
 Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt hosten und verwenden, ohne die tatsächliche Implementierung zu kennen. Wenn der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einer separaten DLL gepackt wurde, könnte er in jeder beliebigen Common Language Runtime (CLR)-Sprache erstellt worden sein. Im folgenden finden Sie eine kurze exemplarische C++Vorgehensweise der/CLI-Implementierung, die im Beispiel verwendet wird. Dieser Abschnitt enthält folgende Unterabschnitte:

- [Layout](#page_layout)

- [Zurückgeben der Daten an das Hostfenster](#returning_data_to_window)

- [Festlegen der WPF-Eigenschaften](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Layout
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt bestehen aus fünf <xref:System.Windows.Controls.TextBox>-Steuerelementen mit zugeordneten <xref:System.Windows.Controls.Label> Steuerelementen: Name, Adresse, Stadt, Bundesland und zip. Es gibt auch zwei <xref:System.Windows.Controls.Button>-Steuerelemente: **OK** und **Abbrechen** .

 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt wird in der `WPFPage`-Klasse implementiert. Das Layout wird mit einem <xref:System.Windows.Controls.Grid>-Layoutelement behandelt. Die Klasse erbt von <xref:System.Windows.Controls.Grid>, wodurch sie zum Stammelement des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts wird.

 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inhaltkonstruktor übernimmt die erforderliche Breite und Höhe und passt entsprechend die Größe der <xref:System.Windows.Controls.Grid> an. Anschließend wird das grundlegende Layout definiert, indem ein Satz von <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> Objekten erstellt und dem <xref:System.Windows.Controls.Grid> Objekt Basis <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> bzw. <xref:System.Windows.Controls.Grid.RowDefinitions%2A> Sammlungen hinzugefügt wird. Dadurch wird ein Raster von fünf Zeilen und sieben Spalten definiert. Die Abmessungen werden durch den Inhalt der Zellen bestimmt.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 Anschließend fügt der Konstruktor die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zu <xref:System.Windows.Controls.Grid> hinzu. Das erste Element ist der Titeltext. Dabei handelt es sich um ein <xref:System.Windows.Controls.Label>-Steuerelement, das in der ersten Zeile des Rasters zentriert ist.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 Die nächste Zeile enthält das <xref:System.Windows.Controls.Label>-Steuerelement für den Namen und das zugehörige <xref:System.Windows.Controls.TextBox>-Steuerelement. Da für jedes aus Beschriftung und Textfeld bestehende Paar derselbe Code verwendet wird, wird er in einem Paar privater Methoden platziert und für alle fünf Paare aus Beschriftung/Textfeld verwendet. Durch die Methoden wird das entsprechende Steuerelement erstellt, und es werden die statischen Methoden <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Grid.SetColumn%2A> der <xref:System.Windows.Controls.Grid.SetRow%2A>-Klasse aufgerufen, um die Steuerelemente in der entsprechenden Zelle zu platzieren. Nachdem das Steuerelement erstellt wurde, wird im Beispiel die <xref:System.Windows.Controls.UIElementCollection.Add%2A>-Methode für die <xref:System.Windows.Controls.Panel.Children%2A>-Eigenschaft von <xref:System.Windows.Controls.Grid> aufgerufen, um das Steuerelement zum Raster hinzuzufügen. Der Code zum Hinzufügen der übrigen Beschriftung/Textfeld-Paare ist ähnlich. Sehen Sie sich den Beispielcode an, um ausführliche Informationen zu erhalten.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 Die Implementierung der beiden Methoden wird wie folgt durchgeführt:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Schließlich fügt das Beispiel die Schaltflächen **OK** und **Abbrechen** hinzu und fügt einen Ereignishandler an Ihre <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse an.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Zurückgeben der Daten an das Hostfenster
 Das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis wird durch Klicken auf eine der Schaltflächen ausgelöst. Das Hostfenster könnte einfach Handler an diese Ereignisse anfügen und die Daten direkt aus den <xref:System.Windows.Controls.TextBox>-Steuerelementen abrufen. In diesem Beispiel wird ein weniger direkter Ansatz verwendet. Die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> wird in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalten behandelt. Anschließend wird ein benutzerdefiniertes Ereignis `OnButtonClicked`ausgelöst, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt zu benachrichtigen. Dadurch kann der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt einige Parameter Validierungen durchführen, bevor der Host benachrichtigt wird. Der Handler fragt den Text aus den <xref:System.Windows.Controls.TextBox>-Steuerelementen ab und weist ihn öffentlichen Eigenschaften zu, aus denen der Host die Informationen abrufen kann.

 Die Ereignisdeklaration in WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignishandler in WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Festlegen der WPF-Eigenschaften
 Der Win32-Host ermöglicht es dem Benutzer, mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Eigenschaften zu ändern. Von der Win32-Seite aus ist es einfach, die Eigenschaften zu ändern. Die Implementierung in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse ist etwas komplizierter, da es keine einzelne globale Eigenschaft gibt, mit der die Schriftarten für alle Steuerelemente gesteuert werden. Stattdessen wird die entsprechende Eigenschaft für die einzelnen Steuerelemente in den set-Accessoren der Eigenschaften geändert. Das folgende Beispiel zeigt den Code für die `DefaultFontFamily`-Eigenschaft. Durch Festlegen der Eigenschaft wird eine private Methode aufgerufen, mit der die <xref:System.Windows.Controls.Control.FontFamily%2A>-Eigenschaften für die verschiedenen Steuerelemente festgelegt werden.

 Aus WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Aus WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Interop.HwndSource>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
