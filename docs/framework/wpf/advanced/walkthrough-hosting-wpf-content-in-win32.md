---
title: 'Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 9ab046c6f7c070ade9d3e474309b33afbf78370e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629639"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Code betrieben haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung wieder zu verwenden, anstatt ihn vollständig neu zu schreiben. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet einen einfachen Mechanismus zum Hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von Inhalten in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] einem-Fenster.  
  
 In diesem Tutorial wird beschrieben, wie Sie eine Beispielanwendung, die [WPF-Inhalte hostet, in einem Win32-Fenster Beispiel](https://go.microsoft.com/fwlink/?LinkID=160004)schreiben, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster hostet. Dieses Beispiel kann auf das Hosten beliebiger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fenster erweitert werden. Da verwalteter und nicht verwalteter Code gemischt werden muss, wird die Anwendung C++in/CLI. geschrieben.  

<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Lernprogramm wird vorausgesetzt, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung und der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Programmierung vertraut sind. Eine grundlegende Einführung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Programmierung finden Sie unter [Getting Started](../getting-started/index.md). Eine Einführung in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] die Programmierung finden Sie in den zahlreichen Büchern zu diesem Thema, insbesondere in den *Programmier Fenstern* von Charles Petzold.  
  
 Da das Beispiel für dieses Lernprogramm in/CLI implementiert C++ist, wird in diesem Tutorial die Verwendung von C++ zum Programmieren der Windows-API und ein Verständnis der Programmierung mit verwaltetem Code vorausgesetzt. Vertrautheit mit C++/CLI ist hilfreich, aber nicht unbedingt erforderlich.  
  
> [!NOTE]
>  Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den gesamten Beispielcode finden Sie unter [Hosting WPF Content in a Win32 Window Sample](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 In diesem Abschnitt wird das grundlegende Verfahren erläutert, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Sie zum [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Hosten von Inhalten in einem Fenster verwenden. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Der Schlüssel zum Hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von Inhalten in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] einem Fenster ist <xref:System.Windows.Interop.HwndSource> die-Klasse. Diese Klasse umschließt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den-Inhalt [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] in einem-Fenster, sodass er als unter [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] geordnetes Fenster in Ihre eingebunden werden kann. Bei folgender Vorgehensweise werden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer einzigen Anwendung zusammengefasst.  
  
1. Implementieren Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ihre Inhalte als verwaltete Klasse.  
  
2. Implementieren einer Windows-Anwendung C++mit/CLI. Wenn Sie mit einer vorhandenen Anwendung und nicht verwaltetem C++ Code beginnen, können Sie diese normalerweise aktivieren, um verwalteten Code aufzurufen, indem Sie die Projekt `/clr` Einstellungen so ändern, dass Sie das Compilerflag einschließen.  
  
3. Legen Sie das Threadingmodell auf Singlethread-Apartment (STA) fest.  
  
4. Behandeln Sie die [WM_CREATE](/windows/desktop/winmsg/wm-create)-Benachrichtigung in der Fenster Prozedur, und führen Sie die folgenden Schritte aus:  
  
    1. Erstellen Sie ein neues <xref:System.Windows.Interop.HwndSource>-Objekt, und verwenden Sie das übergeordnete Fenster als `parent`-Parameter.  
  
    2. Erstellen Sie eine Instanz der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse.  
  
    3. Weisen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Interop.HwndSource>Sie der- EigenschaftvoneinenVerweisaufdas-InhaltsObjektzu.<xref:System.Windows.Interop.HwndSource.RootVisual%2A>  
  
    4. Rufen Sie HWND für den Inhalt ab. Die <xref:System.Windows.Interop.HwndSource.Handle%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts enthält das Fensterhandle (HWND). Um ein HWND zu erhalten, das Sie im nicht verwalteten Teil der Anwendung verwenden können, wandeln Sie `Handle.ToPointer()` in ein HWND um.  
  
5. Implementieren Sie eine verwaltete Klasse, die ein statisches Feld mit einem Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt enthält. Diese Klasse ermöglicht Ihnen, einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Code abzurufen.  
  
6. Weisen Sie dem statischen Feld den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu.  
  
7. Empfangen von Benachrichtigungen vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt durch Anfügen eines Handlers an mindestens ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignis.  
  
8. Kommunizieren Sie mithilfe des im statischen Feld gespeicherten Verweises mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt, um Eigenschaften festzulegen usw.  
  
> [!NOTE]
>  Sie können auch verwenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , um Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt zu implementieren. Sie müssen Sie jedoch separat als Dynamic Link Library (dll) kompilieren und von Ihrer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendung aus auf diese DLL verweisen. Die übrigen Schritte ähneln dem oben beschriebenen Verfahren.

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung
 In diesem Abschnitt wird beschrieben, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie Sie Inhalte in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] einer Basisanwendung hosten. Der Inhalt selbst wird in C++/CLI als verwaltete Klasse implementiert. Größtenteils handelt es sich um eine einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung. Die wichtigsten Aspekte der Inhalts Implementierung werden unter [Implementieren des WPF-Inhalts](#implementing_the_wpf_page)erläutert.

<a name="autoNestedSectionsOUTLINE1"></a>
- [Die grundlegende Anwendung](#the_basic_application)

- [Hosten des WPF-Inhalts](#hosting_the_wpf_page)

- [Verweisen auf den WPF-Inhalt](#holding_a_reference)

- [Kommunizieren mit dem WPF-Inhalt](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Die grundlegende Anwendung
 Der Ausgangspunkt für die Host Anwendung bestand darin, eine Visual Studio 2005-Vorlage zu erstellen.

1. Öffnen Sie Visual Studio 2005, und wählen Sie im Menü **Datei** die Option **Neues Projekt** aus.

2. Wählen Sie **Win32** aus der Liste [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)] der Projekttypen aus. Wenn die Standardsprache nicht C++ist, finden Sie diese Projekttypen unter **andere Sprachen**.

3. Wählen Sie eine **Win32-Projekt** Vorlage aus, weisen Sie dem Projekt einen Namen zu, und klicken Sie auf **OK** , um den Win32- **Anwendungs-Assistenten**

4. Akzeptieren Sie die Standardeinstellungen des Assistenten, und klicken Sie zum Starten des Projekts auf **Fertig** stellen.

 Mit der Vorlage wird eine grundlegende [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendung erstellt, die Folgendes enthält:

- Einen Einstiegspunkt für die Anwendung.

- Ein Fenster mit einer zugeordneten Fensterprozedur (WndProc).

- Ein Menü mit **Datei** -und **Hilfe** Überschriften. Das Menü **Datei** enthält ein **Exit** -Element, mit dem die Anwendung geschlossen wird. Das Menü **Hilfe** enthält ein Element Info, **mit** dem ein einfaches Dialogfeld gestartet wird.

 Bevor Sie mit dem Schreiben von Code zum [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Hosten des Inhalts beginnen, müssen Sie zwei Änderungen an der grundlegenden Vorlage vornehmen.

 Die erste besteht darin, das Projekt als verwalteten Code zu kompilieren. Standardmäßig wird das Projekt als nicht verwalteter Code kompiliert. Da aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in verwaltetem Code implementiert wird, muss das Projekt entsprechend kompiliert werden.

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und wählen Sie Eigenschaften aus dem Kontextmenü aus, um das Dialogfeld **Eigenschaften** **Seiten** aufzurufen.

2. Wählen Sie in der Strukturansicht im linken Bereich **Konfigurations Eigenschaften** aus.

3. Wählen Sie in der Liste **Projekt** Standards im rechten Bereich die Option **Common Language Runtime** -Unterstützung aus.

4. Wählen Sie im Dropdown-Listenfeld die Option **Common Language Runtime-Unterstützung (/CLR)** aus.

> [!NOTE]
>  Das Compilerflag ermöglicht Ihnen, in der Anwendung verwalteten Code zu verwenden. Der nicht verwaltete Code wird jedoch wie zuvor kompiliert.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet das Threadingmodell Singlethread-Apartment (STA). Um ordnungsgemäß mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Code zu arbeiten, müssen Sie das Threading Modell der Anwendung auf STA festlegen, indem Sie ein Attribut auf den Einstiegspunkt anwenden.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hosten des WPF-Inhalts
 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ist eine einfache Anwendung für den Adresseintrag. Sie besteht aus mehreren <xref:System.Windows.Controls.TextBox>-Steuerelementen zum Erfassen von Benutzername, Adresse usw. Außerdem gibt es zwei <xref:System.Windows.Controls.Button> Steuerelemente: **OK** und **Abbrechen**. Wenn der Benutzer auf **OK**klickt, sammelt der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der Schaltfläche die <xref:System.Windows.Controls.TextBox> Daten aus den-Steuerelementen, weist diese den entsprechenden Eigenschaften zu und `OnButtonClicked`löst ein benutzerdefiniertes Ereignis aus. Wenn der Benutzer auf **Abbrechen**klickt, löst der Handler `OnButtonClicked`einfach aus. Das Ereignisargumentobjekt für `OnButtonClicked` enthält ein boolesches Feld, das angibt, auf welche Schaltfläche geklickt wurde.

 Der Code zum Hosten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] des Inhalts wird in einem Handler für die [WM_CREATE](/windows/desktop/winmsg/wm-create) -Benachrichtigung im Host Fenster implementiert.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 Die `GetHwnd` -Methode übernimmt Größen-und Positionsinformationen sowie das übergeordnete Fenster Handle und gibt das Fenster Handle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] des gehosteten-Inhalts zurück.

> [!NOTE]
>  Sie können keine `#using`-Direktive für den `System::Windows::Interop`-Namespace verwenden. Dies würde zu einem Namenskonflikt zwischen der <xref:System.Windows.Interop.MSG>-Struktur in diesem Namespace und der in winuser.h deklarierten MSG-Struktur führen. Verwenden Sie stattdessen vollqualifizierte Namen, um auf den Inhalt dieses Namespace zuzugreifen.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt nicht direkt im Anwendungsfenster hosten. Stattdessen müssen Sie zuerst ein <xref:System.Windows.Interop.HwndSource>-Objekt erstellen, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu umschließen. Dieses Objekt ist im Grunde ein Fenster, das zum Hosten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eines Inhalts entworfen wurde. Sie hosten <xref:System.Windows.Interop.HwndSource> das Objekt im übergeordneten Fenster, indem Sie es als untergeordnetes [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Element eines Fensters erstellen, das Teil Ihrer Anwendung ist. Die <xref:System.Windows.Interop.HwndSource>-Konstruktorparameter enthalten größtenteils dieselben Informationen, die Sie beim Erstellen eines untergeordneten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fensters an CreateWindow übergeben würden.

 Als Nächstes erstellen Sie eine Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Objekts. In diesem Fall wird der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt als separate `WPFPage`Klasse,, mithilfe C++von/CLI. implementiert. Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt auch mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementieren. Hierzu müssen Sie jedoch ein separates Projekt einrichten und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt als DLL-Datei erstellen. Sie können dem Projekt einen Verweis auf die dll hinzufügen und diesen Verweis zum Erstellen einer Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts verwenden.

 Sie zeigen den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt im untergeordneten Fenster an <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndSource.RootVisual%2A> indem Sie einen Verweis [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf den-Inhalt der-Eigenschaft der zuweisen.

 Durch die nächste Codezeile wird ein Ereignishandler (`WPFButtonClicked`) an das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignis des `OnButtonClicked`-Inhalts angefügt. Dieser Handler wird aufgerufen, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt. Weitere Informationen zu diesem Ereignishandler finden Sie unter [communicating_with_the_WPF-Inhalt](#communicating_with_the_page) .

 Durch die letzte angezeigte Codezeile wird das Fensterhandle (HWND) zurückgegeben, das dem <xref:System.Windows.Interop.HwndSource>-Objekt zugeordnet ist. Sie können dieses Handle vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Code zum Senden von Meldungen an das gehostete Fenster verwenden, auch wenn das in diesem Beispiel nicht gezeigt wird. Das <xref:System.Windows.Interop.HwndSource>-Objekt löst jedes Mal ein Ereignis aus, wenn es eine Meldung empfängt. Rufen Sie zum Verarbeiten der Meldungen die <xref:System.Windows.Interop.HwndSource.AddHook%2A>-Methode auf, um einen Meldungshandler anzufügen und anschließend die Meldungen in diesem Handler zu verarbeiten.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Verweisen auf den WPF-Inhalt
 Bei vielen Anwendungen möchten Sie zu einem späteren Zeitpunkt mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt kommunizieren. Angenommen, Sie möchten die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften ändern oder vom <xref:System.Windows.Interop.HwndSource>-Objekt andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalte hosten lassen. Dazu benötigen Sie einen Verweis auf das <xref:System.Windows.Interop.HwndSource>-Objekt oder den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Das <xref:System.Windows.Interop.HwndSource>-Objekt und der zugehörige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt bleiben im Arbeitsspeicher, bis Sie das Fensterhandle zerstören. Die Variable, die Sie dem <xref:System.Windows.Interop.HwndSource>-Objekt zuweisen, verlässt jedoch den Gültigkeitsbereich, sobald die Steuerung von der Fensterprozedur zurückgegeben wird. Eine übliche Methode, dieses Problem bei [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendungen zu umgehen, besteht in der Verwendung einer statischen oder globalen Variablen. Leider können Sie diesen Variablentypen kein verwaltetes Objekt zuweisen. Sie können das Fensterhandle, das dem <xref:System.Windows.Interop.HwndSource>-Objekt zugeordnet ist, einer globalen oder statischen Variablen zuweisen. Dadurch erhalten Sie aber noch keinen Zugriff auf das Objekt.

 Die einfachste Lösung für dieses Problem besteht darin, eine verwaltete Klasse zu implementieren, die eine Reihe von statischen Feldern mit Verweisen auf alle verwalteten Objekte enthält, auf die Sie zugreifen müssen. Im Beispiel wird die `WPFPageHost`-Klasse für einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt verwendet. Außerdem soll sie die Anfangswerte einiger Eigenschaften enthalten, die später vom Benutzer geändert werden können. Dies wird im Header definiert.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 Der letzte Teil der `GetHwnd`-Funktion weist diesen Feldern Werte zur späteren Verwendung zu, während `myPage` im Gültigkeitsbereich verbleibt.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Kommunizieren mit dem WPF-Inhalt
 Es gibt zwei Arten der Kommunikation mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Die Anwendung empfängt Informationen aus dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, wenn der Benutzer auf die Schaltflächen **OK** oder **Abbrechen** klickt. Die Anwendung verfügt auch über eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die es dem Benutzer ermöglicht, zahlreiche [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften zu ändern, z. B. Hintergrundfarbe oder Standardschriftgröße.

 Wie oben erwähnt, löst der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt ein `OnButtonClicked`-Ereignis aus, wenn der Benutzer auf eine der beiden Schaltflächen klickt. Die Anwendung fügt einen Handler an dieses Ereignis an, um die entsprechenden Benachrichtigungen zu empfangen. Wenn auf die Schaltfläche **OK** geklickt wurde, ruft der Handler die Benutzerinformationen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aus dem Inhalt ab und zeigt ihn in einem Satz statischer Steuerelemente an.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 Der Handler empfängt ein benutzerdefiniertes Ereignisargumentobjekt vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt: `MyPageEventArgs`. Die- `IsOK` Eigenschaft des Objekts wird auf `true` festgelegt, wenn auf die Schaltfläche `false` **OK** geklickt wurde, und, wenn auf die Schaltfläche **Abbrechen** geklickt wurde.

 Wenn auf die Schaltfläche **OK** geklickt wurde, ruft der Handler einen Verweis [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf den Inhalt aus der Container Klasse ab. Anschließend ruft er die Benutzerinformationen ab, die in den zugeordneten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften enthalten sind. Dabei werden die statischen Steuerelemente zum Anzeigen der Informationen im übergeordneten Fenster verwendet. Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsdaten in Form einer verwalteten Zeichenfolge vorliegen, müssen Sie gemarshallt werden, damit sie von einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Steuerelement verwendet werden können. Wenn auf die Schaltfläche **Abbrechen** geklickt wurde, löscht der Handler die Daten aus den statischen Steuerelementen.

 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung stellt eine Reihe von Optionsfeldern bereit, mit denen der Benutzer die Hintergrundfarbe des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts und verschiedene Schriftarteigenschaften ändern kann. Das folgende Beispiel ist ein Auszug aus der Fensterprozedur der Anwendung (WndProc) und deren Meldungsbehandlung, die zahlreiche Eigenschaften für verschiedene Meldungen festlegt, darunter die Hintergrundfarbe. Die anderen sind ähnlich und werden nicht angezeigt. Sehen Sie sich das vollständige Beispiel an, um ausführliche Informationen, auch zum Kontext, zu erhalten.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Wenn Sie die Hintergrundfarbe festlegen möchten, rufen Sie einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt (`hostedPage`) von `WPFPageHost` ab, und legen Sie die Eigenschaft für die Hintergrundfarbe auf die entsprechende Farbe fest. Im Beispiel werden drei Farboptionen verwendet: die ursprüngliche Farbe, hellgrün oder helle Lachsfarbe. Die ursprüngliche Hintergrundfarbe wird als statisches Feld in der `WPFPageHost`-Klasse gespeichert. Um die anderen beiden festzulegen, erstellen Sie ein neues <xref:System.Windows.Media.SolidColorBrush>-Objekt und übergeben dem Konstruktor einen statischen Farbwert aus dem <xref:System.Windows.Media.Colors>-Objekt.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementieren der WPF-Seite
 Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt hosten und verwenden, ohne die tatsächliche Implementierung zu kennen. Wenn der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einer separaten DLL gepackt wurde, wurde er möglicherweise in jeder beliebigen Common Language Runtime (CLR)-Sprache erstellt. Im folgenden finden Sie eine kurze exemplarische C++Vorgehensweise der/CLI-Implementierung, die im Beispiel verwendet wird. Dieser Abschnitt enthält folgende Unterabschnitte:

<a name="autoNestedSectionsOUTLINE2"></a>
- [Layout](#page_layout)

- [Zurückgeben der Daten an das Hostfenster](#returning_data_to_window)

- [Festlegen der WPF-Eigenschaften](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Layout
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Label> im Inhalt bestehen aus fünf Steuerelementen mit zugeordneten Steuerelementen: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Name, Adresse, Stadt, Bundesland und zip. Es gibt auch zwei <xref:System.Windows.Controls.Button> Steuerelemente: **OK** und **Abbrechen** .

 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt wird in der `WPFPage`-Klasse implementiert. Das Layout wird mit einem <xref:System.Windows.Controls.Grid>-Layoutelement behandelt. Die Klasse erbt von <xref:System.Windows.Controls.Grid>, wodurch sie zum Stammelement des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts wird.

 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inhaltkonstruktor übernimmt die erforderliche Breite und Höhe und passt die <xref:System.Windows.Controls.Grid> Größe der entsprechend an. Anschließend wird das grundlegende Layout definiert, indem ein Satz <xref:System.Windows.Controls.ColumnDefinition> von <xref:System.Windows.Controls.RowDefinition> -Objekten und-Objekten erstellt und der <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> Objekt <xref:System.Windows.Controls.Grid.RowDefinitions%2A> Basis bzw. den <xref:System.Windows.Controls.Grid> Auflistungen hinzugefügt wird. Dadurch wird ein Raster von fünf Zeilen und sieben Spalten definiert. Die Abmessungen werden durch den Inhalt der Zellen bestimmt.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 Anschließend fügt der Konstruktor die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zu <xref:System.Windows.Controls.Grid> hinzu. Das erste Element ist der Titeltext. Dabei handelt es sich um ein <xref:System.Windows.Controls.Label>-Steuerelement, das in der ersten Zeile des Rasters zentriert ist.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 Die nächste Zeile enthält das <xref:System.Windows.Controls.Label>-Steuerelement für den Namen und das zugehörige <xref:System.Windows.Controls.TextBox>-Steuerelement. Da für jedes aus Beschriftung und Textfeld bestehende Paar derselbe Code verwendet wird, wird er in einem Paar privater Methoden platziert und für alle fünf Paare aus Beschriftung/Textfeld verwendet. Durch die Methoden wird das entsprechende Steuerelement erstellt, und es werden die statischen Methoden <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Grid.SetColumn%2A> der <xref:System.Windows.Controls.Grid.SetRow%2A>-Klasse aufgerufen, um die Steuerelemente in der entsprechenden Zelle zu platzieren. Nachdem das Steuerelement erstellt wurde, wird im Beispiel die <xref:System.Windows.Controls.UIElementCollection.Add%2A>-Methode für die <xref:System.Windows.Controls.Panel.Children%2A>-Eigenschaft von <xref:System.Windows.Controls.Grid> aufgerufen, um das Steuerelement zum Raster hinzuzufügen. Der Code zum Hinzufügen der übrigen Beschriftung/Textfeld-Paare ist ähnlich. Sehen Sie sich den Beispielcode an, um ausführliche Informationen zu erhalten.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 Die Implementierung der beiden Methoden wird wie folgt durchgeführt:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Schließlich fügt das Beispiel die Schaltflächen **OK** und **Abbrechen** hinzu und fügt einen Ereignishandler an <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ihre Ereignisse an.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Zurückgeben der Daten an das Hostfenster
 Das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis wird durch Klicken auf eine der Schaltflächen ausgelöst. Das Hostfenster könnte einfach Handler an diese Ereignisse anfügen und die Daten direkt aus den <xref:System.Windows.Controls.TextBox>-Steuerelementen abrufen. In diesem Beispiel wird ein weniger direkter Ansatz verwendet. Er verarbeitet den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> innerhalb des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts und löst dann ein benutzerdefiniertes `OnButtonClicked`Ereignis aus, um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den Inhalt zu benachrichtigen. Dies ermöglicht es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dem Inhalt, eine Parameter Validierung durchzuführen, bevor der Host benachrichtigt wird. Der Handler fragt den Text aus den <xref:System.Windows.Controls.TextBox>-Steuerelementen ab und weist ihn öffentlichen Eigenschaften zu, aus denen der Host die Informationen abrufen kann.

 Die Ereignisdeklaration in WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignishandler in WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Festlegen der WPF-Eigenschaften
 Der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Host ermöglicht es dem Benutzer, mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Eigenschaften zu ändern. In [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] müssen lediglich Eigenschaften geändert werden. Die Implementierung in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse ist etwas komplizierter, da es keine einzelne globale Eigenschaft gibt, mit der die Schriftarten für alle Steuerelemente gesteuert werden. Stattdessen wird die entsprechende Eigenschaft für die einzelnen Steuerelemente in den set-Accessoren der Eigenschaften geändert. Das folgende Beispiel zeigt den Code für die `DefaultFontFamily` -Eigenschaft. Durch Festlegen der Eigenschaft wird eine private Methode aufgerufen, mit der die <xref:System.Windows.Controls.Control.FontFamily%2A>-Eigenschaften für die verschiedenen Steuerelemente festgelegt werden.

 Aus WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Aus WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
