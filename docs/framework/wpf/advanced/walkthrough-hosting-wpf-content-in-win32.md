---
title: "Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32 | Microsoft Docs"
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
  - "Hosten von WPF-Inhalt in einem Win32-Fenster"
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit.  Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]\-Code betrieben haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung wieder zu verwenden, anstatt ihn vollständig neu zu schreiben.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet ein einfaches Verfahren zum Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalten in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster.  
  
 Dieses Lernprogramm führt Sie durch die Anwendung [Beispiel für das Hosten von WPF\-Inhalt in einem Win32\-Fenster](http://go.microsoft.com/fwlink/?LinkID=160004), in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster gehostet wird.  Dieses Beispiel kann auf das Hosten beliebiger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster erweitert werden.   Da verwalteter und nicht verwalteter Code kombiniert werden muss, wird die Anwendung in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] geschrieben.  
  
   
  
<a name="requirements"></a>   
## Anforderungen  
 In diesem Lernprogramm wird vorausgesetzt, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung und der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programmierung vertraut sind.  Eine Einführung in die Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung finden Sie unter [Erste Schritte](../../../../docs/framework/wpf/getting-started/index.md).  Eine Einführung in die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Programmierung finden Sie in zahlreichen Büchern zu diesem Thema, insbesondere in *Windows\-Programmierung* von Charles Petzold.  
  
 Da das Beispiel für dieses Lernprogramm in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] implementiert wurde, werden Kenntnisse im Umgang mit [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] für die Programmierung von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] vorausgesetzt. Außerdem sollten Sie mit der Programmierung verwalteten Codes vertraut sein.  Grundkenntnisse in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] sind hilfreich, aber keine Voraussetzung.  
  
> [!NOTE]
>  Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel.  Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt.  Den vollständigen Code können Sie im [Beispiel für das Hosten von WPF\-Inhalt in einem Win32\-Fenster](http://go.microsoft.com/fwlink/?LinkID=160004) abrufen oder dort einsehen.  
  
<a name="basic_procedure"></a>   
## Das grundlegende Verfahren  
 Dieser Abschnitt enthält das grundlegende Verfahren zum Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster.  In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Entscheidend für das Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster ist die <xref:System.Windows.Interop.HwndSource>\-Klasse.  Diese Klasse umschließt den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt mit einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fenster, sodass er als untergeordnetes Fenster in Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] eingebunden werden kann.  Bei folgender Vorgehensweise werden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer einzigen Anwendung zusammengefasst.  
  
1.  Implementieren Sie Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt als verwaltete Klasse.  
  
2.  Implementieren Sie eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung mit [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)].  Wenn Sie mit einer vorhandenen Anwendung und nicht verwaltetem [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]\-Code beginnen, können Sie diese in der Regel verwalteten Code aufrufen lassen, indem Sie das `/clr`\-Compilerflag in die Projekteinstellungen aufnehmen.  
  
3.  Legen Sie das Threadingmodell auf Singlethread\-Apartment \(STA\) fest.  
  
4.  Behandeln Sie die [WM\_CREATE](http://msdn.microsoft.com/library/ms632619.aspx)\-Benachrichtigung in Ihrer Fensterprozedur, und führen Sie folgende Schritte aus:  
  
    1.  Erstellen Sie ein neues <xref:System.Windows.Interop.HwndSource>\-Objekt, und verwenden Sie das übergeordnete Fenster als `parent`\-Parameter.  
  
    2.  Erstellen Sie eine Instanz der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltsklasse.  
  
    3.  Weisen Sie dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltsobjekt einen Verweis auf die <xref:System.Windows.Interop.HwndSource.RootVisual%2A>\-Eigenschaft von <xref:System.Windows.Interop.HwndSource> zu.  
  
    4.  Rufen Sie HWND für den Inhalt ab.  Die <xref:System.Windows.Interop.HwndSource.Handle%2A>\-Eigenschaft des <xref:System.Windows.Interop.HwndSource>\-Objekts enthält das Fensterhandle \(HWND\).  Um ein HWND zu erhalten, das Sie im nicht verwalteten Teil der Anwendung verwenden können, wandeln Sie `Handle.ToPointer()` in ein HWND um.  
  
5.  Implementieren Sie eine verwaltete Klasse, die ein statisches Feld mit einem Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt enthält.  Diese Klasse ermöglicht Ihnen, einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Code abzurufen.  
  
6.  Weisen Sie dem statischen Feld den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zu.  
  
7.  Um Benachrichtigungen vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zu empfangen, fügen Sie an eines oder mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Ereignisse einen Handler an.  
  
8.  Kommunizieren Sie mithilfe des im statischen Feld gespeicherten Verweises mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt, um Eigenschaften festzulegen usw.  
  
> [!NOTE]
>  Sie können auch [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] verwenden, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zu implementieren.  Sie müssen ihn allerdings separat als eine [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] kompilieren und auf diese [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] aus Ihrer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung heraus verweisen.  Die übrigen Schritte ähneln dem oben beschriebenen Verfahren.  
  
<a name="implementing_the_application"></a>   
## Implementieren der Hostanwendung  
 In diesem Abschnitt wird beschrieben, wie Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt in einer grundlegenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung hosten.  Der Inhalt selbst wird in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] als verwaltete Klasse implementiert.  Größtenteils handelt es sich um eine einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Programmierung.  Die wichtigsten Aspekte bei der Implementierung von Inhalt werden unter [Implementieren des WPF\-Inhalts](#implementing_the_wpf_page) erläutert.  
  
<a name="autoNestedSectionsOUTLINE1"></a>   
-   [Die grundlegende Anwendung](#the_basic_application)  
  
-   [Hosten des WPF\-Inhalts](#hosting_the_wpf_page)  
  
-   [Verweisen auf den WPF\-Inhalt](#holding_a_reference)  
  
-   [Kommunizieren mit dem WPF\-Inhalt](#communicating_with_the_page)  
  
<a name="the_basic_application"></a>   
### Die grundlegende Anwendung  
 Der Ausgangspunkt für die Hostanwendung bestand darin, eine [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]\-Vorlage zu erstellen.  
  
1.  Öffnen Sie [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)], und wählen Sie im Menü  **Datei** die Option **Neues Projekt** aus.  
  
2.  Wählen Sie **Win32** aus der Liste der [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)]\-Projekttypen aus.  Wenn die Standardsprache nicht [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] ist, finden Sie diese Projekttypen unter **Andere Sprachen**.  
  
3.  Wählen Sie eine **Win32\-Projekt**\-Vorlage aus, weisen Sie dem Projekt einen Namen zu, und klicken Sie auf **OK**, um den **Win32\-Anwendungs\-Assistenten** zu starten.  
  
4.  Übernehmen Sie die Standardeinstellungen des Assistenten, und klicken Sie auf **Fertigstellen**, um das Projekt zu starten.  
  
 Mit der Vorlage wird eine grundlegende [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendung erstellt, die Folgendes enthält:  
  
-   Einen Einstiegspunkt für die Anwendung.  
  
-   Ein Fenster mit einer zugeordneten Fensterprozedur \(WndProc\).  
  
-   Ein Menü mit den Überschriften **Datei** und **Hilfe**.  Das Menü **Datei** enthält das Element **Beenden**, mit dem die Anwendung geschlossen wird.  Das Menü **Hilfe** enthält das Element **Info**, mit dem ein einfaches Dialogfeld gestartet wird.  
  
 Bevor Sie mit dem Schreiben von Code zum Hosten des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts beginnen, müssen Sie zwei Änderungen an der grundlegenden Vorlage vornehmen.  
  
 Die erste besteht darin, das Projekt als verwalteten Code zu kompilieren.  Standardmäßig wird das Projekt als nicht verwalteter Code kompiliert.  Da aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in verwaltetem Code implementiert wird, muss das Projekt entsprechend kompiliert werden.  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektnamen, und wählen Sie im Kontextmenü **Eigenschaften** aus, um das Dialogfeld **Eigenschaftenseiten** aufzurufen.  
  
2.  Wählen Sie links im Strukturansichtsbereich **Konfigurationseigenschaften** aus.  
  
3.  Wählen Sie in der Liste **Projektstandards** im rechten Bereich die Unterstützung für **Common Language Runtime** aus.  
  
4.  Wählen Sie im Dropdown\-Listenfeld **Common Language Runtime\-Unterstützung \(\/clr\)** aus.  
  
> [!NOTE]
>  Das Compilerflag ermöglicht Ihnen, in der Anwendung verwalteten Code zu verwenden. Der nicht verwaltete Code wird jedoch wie zuvor kompiliert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet das Threadingmodell Singlethread\-Apartment \(STA\).  Damit es ordnungsgemäß mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltscode funktioniert, müssen Sie das Threadingmodell der Anwendung auf STA festlegen, indem Sie ein Attribut auf den Einstiegspunkt anwenden.  
  
 [!code-cpp[Win32HostingWPFPage#WinMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]  
  
<a name="hosting_the_wpf_page"></a>   
### Hosten des WPF\-Inhalts  
 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt ist eine einfache Anwendung für die Adresseingabe.  Sie besteht aus mehreren <xref:System.Windows.Controls.TextBox>\-Steuerelementen zum Erfassen von Benutzername, Adresse usw.  Darüber hinaus sind die beiden <xref:System.Windows.Controls.Button>\-Steuerelemente **OK** und **Abbrechen** enthalten.  Wenn der Benutzer auf **OK** klickt, ruft der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler der Schaltfläche Daten aus den <xref:System.Windows.Controls.TextBox>\-Steuerelementen ab, weist sie entsprechenden Eigenschaften zu und löst das benutzerdefinierte Ereignis `OnButtonClicked` aus.  Wenn der Benutzer auf **Abbrechen** klickt, löst der Handler einfach `OnButtonClicked` aus.  Das Ereignisargumentobjekt für `OnButtonClicked` enthält ein boolesches Feld, das angibt, auf welche Schaltfläche geklickt wurde.  
  
 Der Code zum Hosten des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts wird in einem Handler für die [WM\_CREATE](http://msdn.microsoft.com/library/ms632619.aspx)\-Benachrichtigung im Hostfenster implementiert.  
  
 [!code-cpp[Win32HostingWPFPage#WMCreate](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]  
  
 Die `GetHwnd`\-Methode übernimmt Größen\- und Positionsinformationen sowie das übergeordnete Fensterhandle und gibt das Fensterhandle des gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts zurück.  
  
> [!NOTE]
>  Sie können keine `#using`\-Direktive für den `System::Windows::Interop`\-Namespace verwenden.  Dies würde zu einem Namenskonflikt zwischen der <xref:System.Windows.Interop.MSG>\-Struktur in diesem Namespace und der in winuser.h deklarierten MSG\-Struktur führen.  Verwenden Sie stattdessen vollqualifizierte Namen, um auf den Inhalt dieses Namespace zuzugreifen.  
  
 [!code-cpp[Win32HostingWPFPage#GetHwnd](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]  
  
 Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt nicht direkt im Anwendungsfenster hosten.  Stattdessen müssen Sie zuerst ein <xref:System.Windows.Interop.HwndSource>\-Objekt erstellen, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zu umschließen.  Dieses Objekt stellt im Wesentlichen ein Fenster zum Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt dar.  Sie hosten das <xref:System.Windows.Interop.HwndSource>\-Objekt im übergeordneten Fenster, indem Sie es als untergeordnetes Element eines [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fensters erstellen, das Teil Ihrer Anwendung ist.  Die <xref:System.Windows.Interop.HwndSource>\-Konstruktorparameter enthalten größtenteils dieselben Informationen, die Sie beim Erstellen eines untergeordneten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Fensters an CreateWindow übergeben würden.  
  
 Als Nächstes erstellen Sie eine Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltsobjekts.  In diesem Fall wird der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt unter Verwendung von [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] als separate Klasse, nämlich `WPFPage`, implementiert.  Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt auch mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementieren.  Dazu müssen Sie allerdings ein separates Projekt einrichten und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt als [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] erstellen.  Sie können dem Projekt einen Verweis auf diese [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] hinzufügen und ihn zum Erstellen einer Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts verwenden.  
  
 Sie zeigen den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt im untergeordneten Fenster an, indem Sie der <xref:System.Windows.Interop.HwndSource.RootVisual%2A>\-Eigenschaft von <xref:System.Windows.Interop.HwndSource> einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zuweisen.  
  
 Durch die nächste Codezeile wird ein Ereignishandler \(`WPFButtonClicked`\) an das `OnButtonClicked`\-Ereignis des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts angefügt.  Dieser Handler wird aufgerufen, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt.  Weitere Informationen zu diesem Ereignishandler finden Sie unter [Kommunizieren mit dem WPF\-Inhalt](#communicating_with_the_page).  
  
 Durch die letzte angezeigte Codezeile wird das Fensterhandle \(HWND\) zurückgegeben, das dem <xref:System.Windows.Interop.HwndSource>\-Objekt zugeordnet ist.  Sie können dieses Handle vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Code zum Senden von Meldungen an das gehostete Fenster verwenden, auch wenn das in diesem Beispiel nicht gezeigt wird.  Das <xref:System.Windows.Interop.HwndSource>\-Objekt löst jedes Mal ein Ereignis aus, wenn es eine Meldung empfängt.  Rufen Sie zum Verarbeiten der Meldungen die <xref:System.Windows.Interop.HwndSource.AddHook%2A>\-Methode auf, um einen Meldungshandler anzufügen und anschließend die Meldungen in diesem Handler zu verarbeiten.  
  
<a name="holding_a_reference"></a>   
### Verweisen auf den WPF\-Inhalt  
 Bei vielen Anwendungen möchten Sie zu einem späteren Zeitpunkt mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt kommunizieren.  Angenommen, Sie möchten die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltseigenschaften ändern oder vom <xref:System.Windows.Interop.HwndSource>\-Objekt andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalte hosten lassen.  Dazu benötigen Sie einen Verweis auf das <xref:System.Windows.Interop.HwndSource>\-Objekt oder den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt.  Das <xref:System.Windows.Interop.HwndSource>\-Objekt und der zugehörige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt bleiben im Arbeitsspeicher, bis Sie das Fensterhandle zerstören.  Die Variable, die Sie dem <xref:System.Windows.Interop.HwndSource>\-Objekt zuweisen, verlässt jedoch den Gültigkeitsbereich, sobald die Steuerung von der Fensterprozedur zurückgegeben wird.  Eine übliche Methode, dieses Problem bei [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Anwendungen zu umgehen, besteht in der Verwendung einer statischen oder globalen Variablen.  Leider können Sie diesen Variablentypen kein verwaltetes Objekt zuweisen.  Sie können das Fensterhandle, das dem <xref:System.Windows.Interop.HwndSource>\-Objekt zugeordnet ist, einer globalen oder statischen Variablen zuweisen. Dadurch erhalten Sie aber noch keinen Zugriff auf das Objekt.  
  
 Die einfachste Lösung für dieses Problem besteht darin, eine verwaltete Klasse zu implementieren, die eine Reihe von statischen Feldern mit Verweisen auf alle verwalteten Objekte enthält, auf die Sie zugreifen müssen.  Im Beispiel wird die `WPFPageHost`\-Klasse für einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt verwendet. Außerdem soll sie die Anfangswerte einiger Eigenschaften enthalten, die später vom Benutzer geändert werden können.  Dies wird im Header definiert.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageHost](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]  
  
 Der letzte Teil der `GetHwnd`\-Funktion weist diesen Feldern Werte zur späteren Verwendung zu, während `myPage` im Gültigkeitsbereich verbleibt.  
  
<a name="communicating_with_the_page"></a>   
### Kommunizieren mit dem WPF\-Inhalt  
 Es gibt zwei Arten der Kommunikation mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt.  Die Anwendung empfängt Informationen vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt, wenn der Benutzer auf die Schaltfläche **OK** oder **Abbrechen** klickt.  Die Anwendung verfügt auch über eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die es dem Benutzer ermöglicht, zahlreiche [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltseigenschaften zu ändern, z. B. Hintergrundfarbe oder Standardschriftgröße.  
  
 Wie oben erwähnt, löst der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt ein `OnButtonClicked`\-Ereignis aus, wenn der Benutzer auf eine der beiden Schaltflächen klickt.  Die Anwendung fügt einen Handler an dieses Ereignis an, um die entsprechenden Benachrichtigungen zu empfangen.  Nach dem Klicken auf die Schaltfläche **OK** ruft der Handler die Benutzerinformationen aus dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt ab und zeigt sie in einer Reihe von statischen Steuerelementen an.  
  
 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]  
  
 Der Handler empfängt ein benutzerdefiniertes Ereignisargumentobjekt vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt: `MyPageEventArgs`.  Die `IsOK`\-Eigenschaft des Objekts wird auf `true` festgelegt, wenn auf die Schaltfläche **OK** geklickt wurde, und auf `false` wenn auf die Schaltfläche **Abbrechen** geklickt wurde.  
  
 Nach dem Klicken auf die Schaltfläche **OK** ruft der Handler einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt aus der Containerklasse ab.  Anschließend ruft er die Benutzerinformationen ab, die in den zugeordneten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltseigenschaften enthalten sind. Dabei werden die statischen Steuerelemente zum Anzeigen der Informationen im übergeordneten Fenster verwendet.  Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltsdaten in Form einer verwalteten Zeichenfolge vorliegen, müssen Sie gemarshallt werden, damit sie von einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Steuerelement verwendet werden können.  Wenn auf die Schaltfläche **Abbrechen** geklickt wurde, löscht der Handler die Daten aus den statischen Steuerelementen.  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung stellt eine Reihe von Optionsfeldern bereit, mit denen der Benutzer die Hintergrundfarbe des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts und verschiedene Schriftarteigenschaften ändern kann.  Das folgende Beispiel ist ein Auszug aus der Fensterprozedur der Anwendung \(WndProc\) und deren Meldungsbehandlung, die zahlreiche Eigenschaften für verschiedene Meldungen festlegt, darunter die Hintergrundfarbe.  Die anderen sind ähnlich und werden nicht angezeigt.  Sehen Sie sich das vollständige Beispiel an, um ausführliche Informationen, auch zum Kontext, zu erhalten.  
  
 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]  
  
 Wenn Sie die Hintergrundfarbe festlegen möchten, rufen Sie einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt \(`hostedPage`\) von `WPFPageHost` ab, und legen Sie die Eigenschaft für die Hintergrundfarbe auf die entsprechende Farbe fest.  Im Beispiel werden drei Farboptionen verwendet: die ursprüngliche Farbe, hellgrün oder helle Lachsfarbe.  Die ursprüngliche Hintergrundfarbe wird als statisches Feld in der `WPFPageHost`\-Klasse gespeichert.  Um die anderen beiden festzulegen, erstellen Sie ein neues <xref:System.Windows.Media.SolidColorBrush>\-Objekt und übergeben dem Konstruktor einen statischen Farbwert aus dem <xref:System.Windows.Media.Colors>\-Objekt.  
  
<a name="implementing_the_wpf_page"></a>   
## Implementieren der WPF\-Seite  
 Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt hosten und verwenden, ohne die tatsächliche Implementierung zu kennen.  Wurde der[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \-Inhalt in einer separaten [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] gepackt, kann er in einer beliebigen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Sprache erstellt worden sein.  Es folgt eine kurze exemplarische Vorgehensweise zur [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]\-Implementierung, die in diesem Beispiel verwendet wird.  Dieser Abschnitt enthält folgende Unterabschnitte:  
  
<a name="autoNestedSectionsOUTLINE2"></a>   
-   [Layout](#page_layout)  
  
-   [Zurückgeben der Daten an das Hostfenster](#returning_data_to_window)  
  
-   [Festlegen der WPF\-Eigenschaften](#set_page_properties)  
  
<a name="page_layout"></a>   
### Layout  
 Die Elemente der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt bestehen aus fünf <xref:System.Windows.Controls.TextBox>\-Steuerelementen mit zugehörigen <xref:System.Windows.Controls.Label>\-Steuerelementen: Name, Adresse, Stadt, Bundesland und Postleitzahl.  Darüber hinaus sind die beiden <xref:System.Windows.Controls.Button>\-Steuerelemente **OK** und **Abbrechen** enthalten.  
  
 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt wird in der `WPFPage`\-Klasse implementiert.  Das Layout wird mit einem <xref:System.Windows.Controls.Grid>\-Layoutelement behandelt.  Die Klasse erbt von <xref:System.Windows.Controls.Grid>, wodurch sie zum Stammelement des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts wird.  
  
 Der Konstruktor des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts übernimmt die erforderliche Breite und Höhe und passt die Größe von <xref:System.Windows.Controls.Grid> entsprechend an.  Anschließend wird das grundlegende Layout definiert. Dazu wird eine Gruppe von <xref:System.Windows.Controls.ColumnDefinition>\- und <xref:System.Windows.Controls.RowDefinition>\-Objekten erstellt, die jeweils der <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>\-Auflistung und der <xref:System.Windows.Controls.Grid.RowDefinitions%2A>\-Auflistung der <xref:System.Windows.Controls.Grid>\-Objektbasis hinzugefügt werden.  Dadurch wird ein Raster von fünf Zeilen und sieben Spalten definiert. Die Abmessungen werden durch den Inhalt der Zellen bestimmt.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]  
  
 Anschließend fügt der Konstruktor die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente zu <xref:System.Windows.Controls.Grid> hinzu.  Das erste Element ist der Titeltext. Dabei handelt es sich um ein <xref:System.Windows.Controls.Label>\-Steuerelement, das in der ersten Zeile des Rasters zentriert ist.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]  
  
 Die nächste Zeile enthält das <xref:System.Windows.Controls.Label>\-Steuerelement für den Namen und das zugehörige <xref:System.Windows.Controls.TextBox>\-Steuerelement.  Da für jedes aus Beschriftung und Textfeld bestehende Paar derselbe Code verwendet wird, wird er in einem Paar privater Methoden platziert und für alle fünf Paare aus Beschriftung\/Textfeld verwendet.  Durch die Methoden wird das entsprechende Steuerelement erstellt, und es werden die statischen Methoden <xref:System.Windows.Controls.Grid.SetColumn%2A> und <xref:System.Windows.Controls.Grid.SetRow%2A> der <xref:System.Windows.Controls.Grid>\-Klasse aufgerufen, um die Steuerelemente in der entsprechenden Zelle zu platzieren.  Nachdem das Steuerelement erstellt wurde, wird im Beispiel die <xref:System.Windows.Controls.UIElementCollection.Add%2A>\-Methode für die <xref:System.Windows.Controls.Panel.Children%2A>\-Eigenschaft von <xref:System.Windows.Controls.Grid> aufgerufen, um das Steuerelement zum Raster hinzuzufügen.  Der Code zum Hinzufügen der übrigen Beschriftung\/Textfeld\-Paare ist ähnlich.  Sehen Sie sich den Beispielcode an, um ausführliche Informationen zu erhalten.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]  
  
 Die Implementierung der beiden Methoden wird wie folgt durchgeführt:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]  
  
 Abschließend werden in dem Beispiel die Schaltflächen **OK** und **Abbrechen** hinzugefügt, und es wird ein Ereignishandler an ihre <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignisse angefügt.  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]  
  
<a name="returning_data_to_window"></a>   
### Zurückgeben der Daten an das Hostfenster  
 Das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis wird durch Klicken auf eine der Schaltflächen ausgelöst.  Das Hostfenster könnte einfach Handler an diese Ereignisse anfügen und die Daten direkt aus den <xref:System.Windows.Controls.TextBox>\-Steuerelementen abrufen.  In diesem Beispiel wird ein weniger direkter Ansatz verwendet.  <xref:System.Windows.Controls.Primitives.ButtonBase.Click> wird innerhalb des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalts behandelt, und anschließend wird ein benutzerdefiniertes `OnButtonClicked`\-Ereignis ausgelöst, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt zu benachrichtigen.  Dadurch kann der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt die Gültigkeit einiger Parameter überprüfen, bevor der Host benachrichtigt wird.  Der Handler fragt den Text aus den <xref:System.Windows.Controls.TextBox>\-Steuerelementen ab und weist ihn öffentlichen Eigenschaften zu, aus denen der Host die Informationen abrufen kann.  
  
 Die Ereignisdeklaration in WPFPage.h:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]  
  
 Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler in WPFPage.cpp:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]  
  
<a name="set_page_properties"></a>   
### Festlegen der WPF\-Eigenschaften  
 Der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Host ermöglicht es dem Benutzer, mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltseigenschaften zu ändern.  In [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] müssen lediglich Eigenschaften geändert werden.  Die Implementierung in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhaltsklasse ist etwas komplizierter, da es keine einzelne globale Eigenschaft gibt, mit der die Schriftarten für alle Steuerelemente gesteuert werden.  Stattdessen wird die entsprechende Eigenschaft für die einzelnen Steuerelemente in den set\-Accessoren der Eigenschaften geändert.  Im folgenden Beispiel wird der Code für die `DefaultFontFamily`\-Eigenschaft angezeigt.  Durch Festlegen der Eigenschaft wird eine private Methode aufgerufen, mit der die <xref:System.Windows.Controls.Control.FontFamily%2A>\-Eigenschaften für die verschiedenen Steuerelemente festgelegt werden.  
  
 Aus WPFPage.h:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]  
  
 Aus WPFPage.cpp:  
  
 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](../../../../samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]  
  
## Siehe auch  
 <xref:System.Windows.Interop.HwndSource>   
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)