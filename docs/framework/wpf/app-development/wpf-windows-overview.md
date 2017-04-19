---
title: "&#220;bersicht &#252;ber WPF-Fenster | Microsoft Docs"
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
  - "Anwendungen, Hosting"
  - "Inhalt, Anzeigen"
  - "Inhalt, Anzeigen über prozeduralen Code"
  - "Inhalt, Anzeigen über XAML"
  - "Erstellen, Fenster"
  - "Dialogfelder"
  - "Anzeigen von Inhalt"
  - "Anzeigen von Inhalt über prozeduralen Code"
  - "Anzeigen von XAML-Seiten"
  - "Ereignisse"
  - "Hosting, Anwendungen"
  - "Verwalten von Fenstern"
  - "Modale Dialogfelder"
  - "Modale Fenster"
  - "NavigationWindow-Objekte"
  - "Page-Objekt"
  - "Prozeduraler Code, Anzeigen von Inhalt über"
  - "Fensterereignisse"
  - "Fensterverwaltung"
  - "Fensterobjekte"
  - "Fenster"
  - "XAML-Seiten, Anzeigen"
  - "XAML, Anzeigen von Inhalt über"
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
caps.latest.revision: 65
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 60
---
# &#220;bersicht &#252;ber WPF-Fenster
Benutzer interagieren über Fenster mit eigenständigen [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendungen.  Die Hauptaufgabe eines Fensters besteht darin, Inhalt zu hosten, der Daten visuell darstellen kann und Benutzern die Interaktion mit Daten ermöglicht. Eigenständige [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen stellen mithilfe der <xref:System.Windows.Window>\-Klasse eigene Fenster bereit.  In diesem Thema wird <xref:System.Windows.Window> vorgestellt, bevor die Grundlagen der Erstellung und Verwaltung von Fenstern in eigenständigen Anwendungen behandelt werden.  
  
> [!NOTE]
>  Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen, einschließlich [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und Loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Seiten, stellen keine eigenen Fenster zur Verfügung.  Stattdessen werden sie in von [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] bereitgestellten Fenstern gehostet.  Weitere Informationen finden Sie unter [Übersicht über WPF\-XAML\-Browseranwendungen](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
   
  
<a name="TheWindowClass"></a>   
## Die Fensterklasse  
 In der folgenden Abbildung werden die Bestandteile eines Fensters dargestellt.  
  
 ![Fensterelemente](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Ein Fenster wird in zwei Bereiche geteilt: der Nicht\-Clientbereich und der Clientbereich.  
  
 Der *Nicht\-Clientbereich* eines Fensters wird mit [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] implementiert und enthält die Teile eines Fenster, die den meisten Fenstern gemeinsam sind, einschließlich:  
  
-   Rahmen  
  
-   Titelleiste  
  
-   Symbol  
  
-   Schaltflächen zum Minimieren, Maximieren und Wiederherstellen  
  
-   Schaltfläche Schließen  
  
-   Ein Systemmenü mit Menüelementen, mit denen Benutzer ein Fenster minimieren, maximieren, wiederherstellen, verschieben, schließen und dessen Größe ändern können.  
  
 Der *Clientbereich* eines Fensters befindet sich im Nicht\-Clientbereich eines Fensters und wird von Entwicklern dazu verwendet, anwendungsspezifischen Inhalt hinzuzufügen, z. B. Menüleisten, Symbolleisten und Steuerelemente.  
  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wird ein Fenster von der <xref:System.Windows.Window>\-Klasse gekapselt, die Sie für folgende Aufgaben verwenden:  
  
-   Anzeigen eines Fensters  
  
-   Konfigurieren der Größe, Position und Darstellung eines Fensters  
  
-   Hosten von anwendungsspezifischem Inhalt  
  
-   Verwalten der Lebensdauer eines Fensters  
  
<a name="DefiningAWindow"></a>   
## Implementieren eines Fensters  
 Die Implementierung eines typischen Fensters umfasst die Darstellung und das Verhalten. Dabei definiert die *Darstellung*, wie ein Fenster einem Benutzer angezeigt wird und das *Verhalten* die Funktionsweise eines Fensters bei der Interaktion mit Benutzern.  In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] können Sie die Darstellung und das Verhalten eines Fensters entweder mit Code oder mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup implementieren.  
  
 Im Allgemeinen wird die Darstellung eines Fenster jedoch mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup und dessen Verhalten mit Code\-Behind implementiert, wie im folgenden Beispiel gezeigt.  
  
 [!code-xml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Folgende Voraussetzungen müssen erfüllt sein, damit die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markupdatei und die Code\-Behind\-Datei zusammenarbeiten:  
  
-   Im Markup muss das `Window`\-Element das `x:Class`\-Attribut enthalten.  Beim Erstellen der Anwendung führt das Vorhandensein von `x:Class` in der Markupdatei dazu, dass [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] eine `partial`\-Klasse erstellt, die von <xref:System.Windows.Window> abgeleitet wird und den durch das `x:Class`\-Attribut festgelegten Namen erhält.  Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Namespacedeklaration für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Schema \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  Die generierte `partial`\-Klasse implementiert die `InitializeComponent`\-Methode, die zum Registrieren der Ereignisse und Festlegen der Eigenschaften aufgerufen wird, die im Markup implementiert werden.  
  
-   Bei Code\-Behind muss die Klasse eine `partial`\-Klasse mit demselben Namen sein, der im Markup durch das `x:Class`\-Attribut angegeben ist, und sie muss von <xref:System.Windows.Window> abgeleitet werden.  Auf diese Weise kann die Code\-Behind\-Datei mit der `partial`\-Klasse verknüpft werden, die beim Erstellen der Anwendung \(siehe [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\) für die Markupdatei generiert wird.  
  
-   Bei Code\-Behind muss die <xref:System.Windows.Window>\-Klasse einen Konstruktor implementieren, der die `InitializeComponent`\-Methode aufruft.  `InitializeComponent` wird durch die generierte `partial`\-Klasse der Markupdatei implementiert, um Ereignisse zu registrieren und im Markup definierte Eigenschaften festzulegen.  
  
> [!NOTE]
>  Wenn Sie Ihrem Projekt ein neues <xref:System.Windows.Window> mithilfe von [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] hinzufügen, wird <xref:System.Windows.Window> unter Verwendung von Markup und Code\-Behind implementiert. Außerdem wird eine Konfiguration eingefügt, die zum Erstellen der Verknüpfung zwischen Markup\- und Code\-Behind\-Dateien, wie hier beschrieben, benötigt wird.  
  
 Mit dieser Konfiguration können Sie den Fokus auf das Definieren der Fensterdarstellung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup richten und das Fensterverhalten in Code\-Behind implementieren.  Im folgenden Beispiel wird ein Fenster mit einer Schaltfläche gezeigt, das in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup implementiert wurde, sowie ein Ereignishandler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis der Schaltfläche, der in Code\-Behind implementiert wurde.  
  
 [!code-xml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## Konfigurieren einer Fensterdefinition für MSBuild  
 Die Implementierung des Fensters bestimmt dessen Konfiguration für [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].  Für ein Fenster, das sowohl mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup als auch mit Code\-Behind definiert ist:  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup\-Dateien werden als [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page`\-Elemente konfiguriert.  
  
-   Code\-Behind\-Dateien werden als [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile`\-Elemente konfiguriert.  
  
 Dies wird in der folgenden [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]\-Projektdatei veranschaulicht.  
  
```  
<Project ... xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Weitere Informationen zum Erstellen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen finden Sie unter [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## Fensterlebensdauer  
 Wie alle Klassen hat auch ein Fenster eine Lebensdauer, die mit dem erstmaligen Instanziieren beginnt. Anschließend wird es geöffnet, aktiviert, deaktiviert und schließlich geschlossen.  
  
   
  
<a name="Opening_a_Window"></a>   
### Öffnen eines Fensters  
 Wenn Sie ein Fenster öffnen möchten, müssen Sie zuerst eine Instanz davon erstellen. Dies wird im folgenden Beispiel veranschaulicht.  
  
 [!code-xml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In diesem Beispiel wird `MarkupAndCodeBehindWindow` beim Starten der Anwendung instanziiert, was beim Auslösen des <xref:System.Windows.Application.Startup>\-Ereignisses erfolgt.  
  
 Wird ein Fenster instanziiert, wird einer Liste der vom <xref:System.Windows.Application>\-Objekt verwalteten Fenster automatisch ein Verweis darauf hinzugefügt \(siehe <xref:System.Windows.Application.Windows%2A?displayProperty=fullName>\).  Zusätzlich wird das erste zu instanziierende Fenster standardmäßig von <xref:System.Windows.Application> als Hauptanwendungsfenster festgelegt \(siehe <xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName>\).  
  
 Schließlich wird das Fenster durch Aufrufen der <xref:System.Windows.Window.Show%2A>\-Methode geöffnet. Das Ergebnis wird in der folgenden Abbildung dargestellt.  
  
 ![Ein durch den Aufruf von Window.Show geöffnetes Fenster](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Ein durch Aufrufen von <xref:System.Windows.Window.Show%2A> geöffnetes Fenster wird als nicht modales Fenster bezeichnet. Das bedeutet, dass die Anwendung in einem Modus ausgeführt wird, in dem Benutzer weitere Fenster in derselben Anwendung öffnen können.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> wird aufgerufen, um Fenster, z. B. Dialogfelder, modal aufzurufen.  Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
 Wenn <xref:System.Windows.Window.Show%2A> aufgerufen wird, führt ein Fenster die Initialisierung aus, bevor es zum Festlegen der Infrastruktur angezeigt wird, durch die es Benutzereingaben empfangen kann.  Wenn das Fenster initialisiert wird, wird das <xref:System.Windows.Window.SourceInitialized>\-Ereignis ausgelöst, und das Fenster wird angezeigt.  
  
 Als Arbeitserleichterung kann <xref:System.Windows.Application.StartupUri%2A> so festgelegt werden, dass er das Fenster angibt, das beim Starten der Anwendung automatisch geöffnet wird.  
  
 [!code-xml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Wenn die Anwendung gestartet wird, wird das durch den Wert von <xref:System.Windows.Application.StartupUri%2A> angegebene Fenster im nicht modalen Modus geöffnet. Intern wird das Fenster durch Aufrufen der <xref:System.Windows.Window.Show%2A>\-Methode geöffnet.  
  
<a name="Ownership"></a>   
#### Besitz von Fenstern  
 Zwischen dem mit der <xref:System.Windows.Window.Show%2A>\-Methode geöffneten Fenster und dem Fenster, von dem es erstellt wurde, besteht keine implizite Beziehung. Benutzer können mit dem jeweiligen Fenster unabhängig interagieren. Infolgedessen kann jedes Fenster folgende Aufgaben ausführen:  
  
-   Das andere Fenster überdecken \(es sei denn, die <xref:System.Windows.Window.Topmost%2A>\-Eigenschaft eines der Fenster ist auf `true` festgelegt\).  
  
-   Es wird minimiert, maximiert und wiederhergestellt, ohne das andere zu beeinflussen.  
  
 Bei einigen Fenstern ist eine Beziehung zu dem Fenster erforderlich, durch das es geöffnet wird.  Eine [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)]\-Anwendung kann beispielsweise Eigenschaftenfenster und Toolfenster öffnen, deren typisches Verhalten es ist, das Fenster zu überdecken, von dem es erstellt wurde.  Darüber hinaus sollten solche Fenster stets mit den Fenstern geschlossen, minimiert, maximiert und wiederhergestellt werden, durch die sie erstellt wurden.  Eine solche Beziehung lässt sich herstellen, indem festgelegt wird, dass ein Fenster das andere *besitzt*. Dazu legen Sie die <xref:System.Windows.Window.Owner%2A>\-Eigenschaft von *zum Besitzer gehöriges Fenster* mit einem Verweis auf *Besitzerfenster* fest.  Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Nach Einrichten des Besitzes:  
  
-   Das zum Besitzer gehörige Fenster kann auf sein Besitzerfenster verweisen, indem der Wert der <xref:System.Windows.Window.Owner%2A>\-Eigenschaft überprüft wird.  
  
-   Das Besitzerfenster kann alle ihm gehörenden Fenster durch Überprüfen des Wertes der <xref:System.Windows.Window.OwnedWindows%2A>\-Eigenschaft ermitteln.  
  
<a name="Preventing"></a>   
#### Verhindern der Fensteraktivierung  
 Es gibt Szenarien, in denen angezeigte Fenster nicht aktiviert werden sollten, z. B. Unterhaltungsfenster einer Internet\-Messenger\-Anwendung oder Benachrichtigungsfenster einer E\-Mail\-Anwendung.  
  
 Falls Ihre Anwendung ein Fenster bereitstellt, das nicht aktiviert werden sollte, wenn Sie es anzeigen, können Sie die <xref:System.Windows.Window.ShowActivated%2A>\-Eigenschaft auf `false` festlegen, bevor Sie die <xref:System.Windows.Window.Show%2A>\-Methode zum ersten Mal ausführen.  Daraus folgt:  
  
-   Das Fenster wird nicht aktiviert.  
  
-   Das <xref:System.Windows.Window.Activated>\-Ereignis des Fensters wird nicht ausgelöst.  
  
-   Das momentan aktivierte Fenster bleibt aktiviert.  
  
 Das Fenster wird jedoch aktiviert, sobald der Benutzer es durch Klicken auf den Client\- oder Nicht\-Clientbereich aktiviert.  In diesem Fall gilt Folgendes:  
  
-   Das Fenster wird aktiviert.  
  
-   Das <xref:System.Windows.Window.Activated>\-Ereignis des Fensters wird ausgelöst.  
  
-   Das zuvor aktivierte Fenster wird deaktiviert.  
  
-   Die Ereignisse <xref:System.Windows.Window.Deactivated> und <xref:System.Windows.Window.Activated> des Fensters werden anschließend als Reaktion auf Benutzeraktionen wie erwartet ausgelöst.  
  
<a name="Window_Activation"></a>   
### Aktivieren von Fenstern  
 Wenn ein Fenster zum ersten Mal geöffnet wird, wird es zum aktiven Fenster \(es sei denn, <xref:System.Windows.Window.ShowActivated%2A> ist auf `false` festgelegt\).  Das *aktive Fenster* ist das Fenster, das gegenwärtig Benutzereingaben annimmt, z. B. Tastenanschläge und Mausklicks.  Wird ein Fenster aktiv, löst es das <xref:System.Windows.Window.Activated>\-Ereignis aus.  
  
> [!NOTE]
>  Beim ersten Öffnen eines Fensters, werden das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis und das <xref:System.Windows.Window.ContentRendered>\-Ereignis erst ausgelöst, nachdem das <xref:System.Windows.Window.Activated>\-Ereignis ausgelöst wurde.  Vor diesem Hintergrund gilt ein Fenster als tatsächlich geöffnet, nachdem <xref:System.Windows.Window.ContentRendered> ausgelöst wurde.  
  
 Nachdem ein Fenster aktiv geworden ist, kann ein Benutzer ein weiteres Fenster in derselben Anwendung oder eine andere Anwendung aktivieren.  In diesem Fall wird das derzeit aktive Fenster deaktiviert, und es löst das <xref:System.Windows.Window.Deactivated>\-Ereignis aus.  Wenn der Benutzer ein derzeit deaktiviertes Fenster auswählt, wird das Fenster entsprechend neu aktiviert, und <xref:System.Windows.Window.Activated> wird ausgelöst.  
  
 Ein häufiger Grund für das Behandeln von <xref:System.Windows.Window.Activated> und <xref:System.Windows.Window.Deactivated> ist das Aktivieren und Deaktivieren der Funktionalität, die nur bei einem aktiven Fenster ausgeführt werden kann.  In einigen Fenstern wird beispielsweise interaktiver Inhalt angezeigt, der andauernde Benutzereingaben oder Aufmerksamkeit erfordert, wie beispielsweise Spiele und Videoplayer.  Im folgenden Beispiel wird durch einen vereinfachten Videoplayer veranschaulicht, wie <xref:System.Windows.Window.Activated> und <xref:System.Windows.Window.Deactivated> behandelt wird, um dieses Verhalten zu implementieren.  
  
 [!code-xml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Andere Anwendungstypen führen im Hintergrund möglicherweise weiterhin Code aus, nachdem ein Fenster deaktiviert wurde.  Ein E\-Mail\-Client kann z. B. weiterhin den E\-Mail\-Server abrufen, während der Benutzer andere Anwendungen verwendet.  Während das Hauptfenster deaktiviert ist, stellen derartige Anwendungen häufig zusätzliches oder anderes Verhalten zur Verfügung.  Im Hinblick auf das E\-Mail\-Programm kann das sowohl das Hinzufügen des neuen E\-Mail\-Elements zum Posteingang als auch eines Benachrichtigungssymbol in die Taskleiste bedeuten.  Ein Benachrichtigungssymbol muss nur angezeigt werden, wenn das E\-Mail\-Fenster nicht aktiv ist. Dies lässt sich durch Überprüfen der <xref:System.Windows.Window.IsActive%2A>\-Eigenschaft feststellen.  
  
 Nach Ausführen einer Hintergrundtask benachrichtigt ein Fenster den Benutzer etwas dringlicher, indem die <xref:System.Windows.Window.Activate%2A>\-Methode aufgerufen wird.  Wenn der Benutzer mit einer anderen Anwendung interagiert, die durch Aufrufen von <xref:System.Windows.Window.Activate%2A> gestartet wird, blinkt die Taskleistenschaltfläche des Fensters.  Interagiert der Benutzer mit der aktuellen Anwendung, wird das Fenster durch Aufrufen von <xref:System.Windows.Window.Activate%2A> in den Vordergrund gestellt.  
  
> [!NOTE]
>  Sie können die Aktivierung für den Anwendungsbereich durch Verwenden des <xref:System.Windows.Application.Activated?displayProperty=fullName>\-Ereignisses und des <xref:System.Windows.Application.Deactivated?displayProperty=fullName>\-Ereignisses behandeln.  
  
<a name="Closing_a_Window"></a>   
### Schließen eines Fensters  
 Die Lebensdauer eines Fensters endet, wenn der Benutzer das Fenster schließt.  Ein Fenster kann mithilfe der Elemente im Nicht\-Clientbereich geschlossen werden, z. B. mit den folgenden:  
  
-   Das Element **Schließen** im Menü **System**.  
  
-   Drücken von ALT\+F4.  
  
-   Klicken auf die Schaltfläche **Schließen**.  
  
 Zum Schließen eines Fensters können Sie dem Clientbereich weitere Mechanismen hinzufügen. Zu den gebräuchlichsten zählen:  
  
-   Das Element **Beenden** im Menü **Datei**, i. d. R. für Hauptanwendungsfenster.  
  
-   Das Element **Schließen** im Menü **Datei**, i. d. R. in einem sekundären Anwendungsfenster.  
  
-   Das Element **Abbrechen**, i. d. R. in einem modalen Dialogfeld.  
  
-   Das Element **Schließen**, i. d. R. in einem nicht modalen Dialogfeld.  
  
 Sie müssen die <xref:System.Windows.Window.Close%2A>\-Methode aufrufen, um ein Fenster mit einem der benutzerdefinierten Mechanismen zu schließen.  Im folgenden Beispiel wird die Fähigkeit implementiert, ein Fenster mithilfe von **Beenden** im Menü **Datei** zu schließen.  
  
 [!code-xml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Wenn ein Fenster geschlossen wird, löst es zwei Ereignisse aus: <xref:System.Windows.Window.Closing> und <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> wird ausgelöst, bevor das Fenster geschlossen wird. Zusätzlich werden Mechanismen bereitgestellt, mit deren Hilfe das Schließen des Fensters verhindert werden kann.  Der häufigste Grund, um das Schließen eines Fensters zu verhindern, liegt darin, dass Fensterinhalt geänderte Daten enthält.  In diesem Fall kann das <xref:System.Windows.Window.Closing>\-Ereignis behandelt werden, um festzustellen, ob Daten geändert wurden und um in diesem Fall den Benutzer zu fragen, ob er mit dem Schließen des Fensters fortfahren oder den Vorgang abbrechen möchte.  Im folgenden Beispiel werden die wichtigsten Aspekte bei der Behandlung von <xref:System.Windows.Window.Closing> verdeutlicht.  
  
 [!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind1)]
 [!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind1)]  
[!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind2)]
[!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind2)]  
  
 Der <xref:System.Windows.Window.Closing>\-Ereignishandler wird an <xref:System.ComponentModel.CancelEventArgs> übergeben, das die `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>\-Eigenschaft implementiert, die Sie auf `true` festlegen, um das Schließen eines Fensters zu verhindern.  
  
 Wenn <xref:System.Windows.Window.Closing> nicht behandelt bzw. behandelt, aber nicht abgebrochen wird, wird das Fenster geschlossen.  Unmittelbar vor dem eigentlichen Schließen des Fensters wird <xref:System.Windows.Window.Closed> ausgelöst.  An dieser Stelle kann das Schließen des Fensters nicht verhindert werden.  
  
> [!NOTE]
>  Eine Anwendung kann so konfiguriert werden, dass sie automatisch beendet wird, wenn entweder das Hauptanwendungsfenster \(siehe <xref:System.Windows.Application.MainWindow%2A>\) oder das letzte Fenster geschlossen wird.  Ausführliche Informationen finden Sie unter <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Während ein Fenster über die im Nicht\-Clientbereich und im Clientbereich bereitgestellten Mechanismen explizit geschlossen werden kann, ist es auch möglich, dass es infolge des Verhaltens in anderen Bereichen der Anwendung oder [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] implizit geschlossen wird, z. B.:  
  
-   Ein Benutzer meldet sich ab oder schließt [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
-   Der Besitzer eines Fensters schließt \(siehe <xref:System.Windows.Window.Owner%2A>\).  
  
-   Das Hauptanwendungsfenster wird geschlossen, und <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode>.  
  
-   <xref:System.Windows.Application.Shutdown%2A> wird aufgerufen.  
  
> [!NOTE]
>  Ein Fenster kann nicht erneut geöffnet werden, nachdem es geschlossen wurde.  
  
<a name="Window_Lifetime_Events"></a>   
### Ereignisse in der Lebensdauer eines Fensters  
 In der folgenden Darstellung wird die Abfolge der wichtigsten Ereignisse in der Lebensdauer eines Fensters gezeigt.  
  
 ![Fensterlebensdauer](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 In der folgenden Abbildung wird die Abfolge der wichtigsten Ereignisse in der Lebensdauer eines Fensters, das ohne Aktivierung angezeigt wird, dargestellt \(<xref:System.Windows.Window.ShowActivated%2A> ist auf `false` festgelegt, bevor das Fenster angezeigt wird\).  
  
 ![Fensterlebensdauer &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## Fensterposition  
 Solange ein Fenster geöffnet ist, befindet sich dessen Position in der x\- und y\-Dimension relativ zum Desktop.  Diese Position kann durch Überprüfen der <xref:System.Windows.Window.Left%2A>\-Eigenschaft und der <xref:System.Windows.Window.Top%2A>\-Eigenschaft festgestellt werden.  Sie können diese Eigenschaften festlegen, um die Position des Fensters zu ändern.  
  
 Sie können auch die ursprüngliche Position von <xref:System.Windows.Window> angeben, wenn es zum ersten Mal angezeigt wird. Dazu legen Sie die <xref:System.Windows.Window.WindowStartupLocation%2A>\-Eigenschaft auf einen der folgenden <xref:System.Windows.WindowStartupLocation>\-Enumerationswerte fest:  
  
-   <xref:System.Windows.WindowStartupLocation> \(Standardwert\)  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
 Wird die Startposition als <xref:System.Windows.WindowStartupLocation> angegeben und wurden die <xref:System.Windows.Window.Left%2A>\-Eigenschaft und die <xref:System.Windows.Window.Top%2A>\-Eigenschaft nicht festgelegt, fragt <xref:System.Windows.Window> [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] nach einer Position, an der es angezeigt werden soll.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### Oberstes Fenster und Z\-Reihenfolge  
 Neben der X\- und Y\-Position verfügt das Fenster auch über eine Position in der Z\-Dimension, die dessen vertikale Position im Verhältnis zu anderen Fenstern bestimmt.  Dies wird als Z\-Reihenfolge des Fensters bezeichnet. Davon gibt es zwei Typen: die normale Z\-Reihenfolge und die oberste Z\-Reihenfolge.  Die Position eines Fensters in der *normalen Z\-Reihenfolge* hängt davon ab, ob das Fenster derzeit aktiv ist.  Standardmäßig befindet sich ein Fenster in der normalen Z\-Reihenfolge.  Die Position eines Fensters in der *obersten Z\-Reihenfolge* hängt ebenfalls davon ab, ob das Fenster derzeit aktiv ist.  Darüber hinaus befinden sich Fenster in der obersten Z\-Reihenfolge stets über den Fenstern in der normalen Z\-Reihenfolge.  Ein Fenster wird in der oberste Z\-Reihenfolge platziert, indem dessen <xref:System.Windows.Window.Topmost%2A>\-Eigenschaft auf `true` festgelegt wird.  
  
 [!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup2)]  
  
 Innerhalb jeder Z\-Reihenfolge wird das aktuell aktive Fenster über allen anderen Fenstern derselben Z\-Reihenfolge angezeigt.  
  
<a name="WindowSize"></a>   
## Fenstergröße  
 Abgesehen von der Position auf dem Desktop verfügt ein Fenster über eine Größe, die durch mehrere Eigenschaften bestimmt wird, beispielsweise die Eigenschaften für Breite, Höhe und <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.MaxWidth%2A> werden zum Verwalten des Bereichs von Breiten verwendet, die ein Fenster während seiner Lebensdauer haben kann. Sie werden wie im folgenden Beispiel gezeigt konfiguriert.  
  
 [!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup2)]  
  
 Die Fensterhöhe wird von <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> verwaltet und wie im folgenden Beispiel konfiguriert.  
  
 [!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup2)]  
  
 Da die verschiedenen Werte für die Breite und für die Höhe jeweils einen Bereich angeben, kann die Breite und Höhe eines in der Größe veränderbaren Fensters irgendwo innerhalb des angegebenen Bereichs für die entsprechende Dimension liegen.  Wenn Sie die aktuelle Breite und Höhe des Fensters ermitteln möchten, überprüfen Sie <xref:System.Windows.FrameworkElement.ActualWidth%2A> bzw. <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 Wenn Sie möchten, dass die Breite und Höhe des Fensters der Größe des Fensterinhalts entspricht, können Sie die <xref:System.Windows.Window.SizeToContent%2A>\-Eigenschaft verwenden, die über folgende Werte verfügt:  
  
-   <xref:System.Windows.SizeToContent>.  Keine Auswirkung \(Standard\).  
  
-   <xref:System.Windows.SizeToContent>.  Das Anpassen an die Breite des Inhalts hat dieselbe Auswirkung wie das Festlegen sowohl von <xref:System.Windows.FrameworkElement.MinWidth%2A> als auch von <xref:System.Windows.FrameworkElement.MaxWidth%2A> auf die Breite des Inhalts.  
  
-   <xref:System.Windows.SizeToContent>.  Das Anpassen an die Höhe des Inhalts hat dieselbe Auswirkung wie das Festlegen sowohl von <xref:System.Windows.FrameworkElement.MinHeight%2A> als auch von <xref:System.Windows.FrameworkElement.MaxHeight%2A> auf die Höhe des Inhalts.  
  
-   <xref:System.Windows.SizeToContent>.  Das Anpassen an die Breite und Höhe des Inhalts hat dieselbe Auswirkung wie das Festlegen sowohl von <xref:System.Windows.FrameworkElement.MinHeight%2A> als auch von <xref:System.Windows.FrameworkElement.MaxHeight%2A> auf die Höhe des Inhalts sowie das Festlegen sowohl von <xref:System.Windows.FrameworkElement.MinWidth%2A> als auch von <xref:System.Windows.FrameworkElement.MaxWidth%2A> auf die Breite des Inhalts.  
  
 Im folgenden Beispiel wird ein Fenster dass die Größe automatisch an seinen Inhalt vertikal und horizontal an, wenn es zuerst angezeigt wird.  
  
 [!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup2)]  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.Window.SizeToContent%2A>\-Eigenschaft im Code festlegen, um anzugeben, wie ein Fenster angepasst wird, um seinen Inhalt anzupassen.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## Rangfolge der Größeneigenschaften  
 Im Wesentlichen werden die verschiedenen Größeneigenschaften eines Fensters kombiniert, um den Bereich der Breite und der Höhe für ein in der Größe veränderbares Fenster zu definieren.  Um sicherzustellen, dass ein gültiger Bereich beibehalten wird, wertet <xref:System.Windows.Window> die Werte der Größeneigenschaften anhand der folgenden Rangfolgen aus.  
  
 **Für Höheneigenschaften:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=fullName>  
  
 **Für Breiteneigenschaften:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=fullName>  
  
 Durch die Rangfolge kann beim Maximieren eines Fensters auch dessen Größe festgelegt werden. Dies wird von der <xref:System.Windows.Window.WindowState%2A>\-Eigenschaft verwaltet.  
  
<a name="WindowState"></a>   
## Fensterzustand  
 Während der Lebensdauer eines in der Größe veränderbaren Fenster kann dieses über drei Zustände verfügen: normal, minimiert und maximiert.  Ein Fenster mit einem *normalen* Zustand ist der Standardzustand eines Fensters.  Ein Benutzer kann ein Fenster mit diesem Zustand verschieben und dessen Größe ändern, indem er den Ziehpunkt zur Größenänderung oder den Rahmen verwendet, sofern er in der Größe veränderbar ist.  
  
 Ein Fenster mit einem *minimierten* Zustand wird auf seine Taskleistenschaltfläche reduziert, wenn <xref:System.Windows.Window.ShowInTaskbar%2A> auf `true` festgelegt ist. Andernfalls wird es auf die kleinste mögliche Größe reduziert und in der linken unteren Ecke des Desktops angezeigt.  Keiner der minimierten Fenstertypen kann mithilfe des Ziehpunkts zur Größenreduzierung oder mit dem Rahmen in der Größe verändert werden. Allerdings kann ein minimiertes Fenster, das nicht in der Taskleiste angezeigt wird, auf dem Desktop hin und her verschoben werden.  
  
 Ein Fenster mit einem *maximierten* Zustand wird auf die maximal mögliche Größe erweitert, die von den Eigenschaften <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> und <xref:System.Windows.Window.SizeToContent%2A> abhängen.  Wie ein minimiertes Fenster kann auch ein maximiertes Fenster nicht mithilfe des Ziehpunkts zur Größenänderung oder durch Ziehen des Rahmens in seiner Größe verändert werden.  
  
> [!NOTE]
>  Die Werte der Eigenschaften <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> eines Fensters stellen immer die Werte für den normalen Zustand dar, auch wenn das Fenster gerade maximiert oder minimiert wird.  
  
 Der Zustand eines Fensters kann durch Festlegen der <xref:System.Windows.Window.WindowState%2A>\-Eigenschaft konfiguriert werden, die einen der folgenden <xref:System.Windows.WindowState>\-Enumerationswerte aufweisen kann:  
  
-   <xref:System.Windows.WindowState> \(Standardwert\)  
  
-   <xref:System.Windows.WindowState>  
  
-   <xref:System.Windows.WindowState>  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie ein Fenster erstellen, das beim Öffnen als maximiert angezeigt wird.  
  
 [!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup2)]  
  
 Im Allgemeinen sollten Sie <xref:System.Windows.Window.WindowState%2A> so festlegen, dass der Ausgangszustand eines Fensters konfiguriert wird.  Wenn ein in der Größe veränderbares Fenster angezeigt wird, können die Benutzer die Schaltflächen zum Minimieren, Maximieren oder Wiederherstellen auf der Titelleiste des Fensters aktivieren, um den Fensterzustand zu ändern.  
  
<a name="WindowAppearance"></a>   
## Fensterdarstellung  
 Sie ändern die Darstellung des Clientbereichs eines Fensters, indem Sie fensterspezifischen Inhalt hinzufügen, z. B. Schaltflächen, Bezeichnungen und Textfelder.  Zum Konfigurieren des Nicht\-Clientbereichs stellt <xref:System.Windows.Window> mehrere Eigenschaften bereit, darunter <xref:System.Windows.Window.Icon%2A>, um das Symbol eines Fensters festzulegen und <xref:System.Windows.Window.Title%2A>, um den Fenstertitel festzulegen.  
  
 Außerdem können Sie die Darstellung und das Verhalten des Rahmens im Nicht\-Clientbereich ändern, indem Sie den Größenänderungsmodus, den Fensterstil und die Tatsache konfigurieren, ob es als Schaltfläche in der Desktoptaskleiste angezeigt wird.  
  
   
  
<a name="Resize_Mode"></a>   
### Größenänderungsmodus  
 Abhängig von der <xref:System.Windows.Window.WindowStyle%2A>\-Eigenschaft können Sie steuern, wie \(und ob\) Benutzer die Größe des Fensters ändern können.  Die Auswahl des Fensterstils bestimmt, ob ein Benutzer die Fenstergröße durch Ziehen des Rahmens mit der Maus ändern kann, ob die Schaltflächen **Minimieren**, **Maximieren** und **Größe ändern** im Nicht\-Clientbereich angezeigt werden und ob sie aktiviert sind, falls sie angezeigt werden.  
  
 Sie können die Größenänderung eines Fensters konfigurieren, indem Sie die <xref:System.Windows.Window.ResizeMode%2A>\-Eigenschaft festlegen, die einen der folgenden <xref:System.Windows.ResizeMode>\-Enumerationswerte aufweisen kann:  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode> \(Standardwert\)  
  
-   <xref:System.Windows.ResizeMode>  
  
 Wie bei <xref:System.Windows.Window.WindowStyle%2A> ändert sich der Größenänderungsmodus eines Fensters während der Lebensdauer kaum. Folglich werden Sie diesen wahrscheinlich über das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup festlegen.  
  
 [!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup2)]  
  
 Beachten Sie, dass Sie durch Überprüfen der <xref:System.Windows.Window.WindowState%2A>\-Eigenschaft ermitteln können, ob ein Fenster minimiert, maximiert oder wiederhergestellt ist.  
  
<a name="Window_Style"></a>   
### Fensterstil  
 Der Rahmen, der vom Nicht\-Clientbereich eines Fensters verfügbar gemacht wird, eignet sich für die meisten Anwendungen.  Unter bestimmten Umständen werden je nach Fenstertyp dennoch andere Rahmentypen oder überhaupt keine Rahmen benötigt.  
  
 Um den Rahmentyp eines Fensters zu steuern, legen Sie die <xref:System.Windows.Window.WindowStyle%2A>\-Eigenschaft mit einem der folgenden <xref:System.Windows.WindowStyle>\-Enumerationswerte fest:  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle> \(Standardwert\)  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle>  
  
 Die Auswirkung dieser Fensterstile wird in der folgenden Abbildung veranschaulicht.  
  
 ![Fensterstile](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.png "WindowOverviewFigure6")  
  
 Sie können <xref:System.Windows.Window.WindowStyle%2A> entweder mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup oder Code festlegen. Da es unwahrscheinlich ist, dass der Stil während der Lebensdauer eines Fensters geändert wird, werden Sie ihn wahrscheinlich mit dem [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup konfigurieren.  
  
 [!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup2)]  
  
#### Nicht rechteckiger Fensterstil  
 Es kann auch vorkommen, dass Ihnen die von <xref:System.Windows.Window.WindowStyle%2A> bereitgestellten Rahmenstile nicht ausreichen.  Sie möchten z. B. eine Anwendung mit einem nicht rechteckigen Rahmen erstellen, wie er von [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] verwendet wird.  
  
 Betrachten Sie beispielsweise das Sprechblasenfenster in der folgenden Abbildung.  
  
 ![Nicht rechteckiges Fenster](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Dieser Fenstertyp kann erstellt werden, indem die <xref:System.Windows.Window.WindowStyle%2A>\-Eigenschaft auf <xref:System.Windows.WindowStyle> festgelegt und die Unterstützung genutzt wird, die <xref:System.Windows.Window> zur Transparenz bietet.  
  
 [!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup2)]  
  
 Durch diese Kombination von Werten wird das Fenster angewiesen, ein vollkommen transparentes Rendering zu übernehmen.  In diesem Zustand können die Zusatzelemente des Nicht\-Clientbereichs des Fensters \(das Menü Schließen, die Schaltflächen Minimieren, Maximieren und Wiederherstellen usw.\) nicht verwendet werden.  Folglich müssen Sie Ihre eigenen bereitstellen.  
  
<a name="Task_Bar_Presence"></a>   
### Vorhandensein der Taskleiste  
 Die Standarddarstellung eines Fensters umfasst eine Taskleistenschaltfläche wie in der folgenden Abbildung.  
  
 ![Fenster mit einer Taskleistenschaltfläche](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.png "WindowOverviewFigure7")  
  
 Einige Fenstertypen verfügen über keine Taskleistenschaltfläche, z. B. Meldungsfelder und Dialogfelder \(siehe [Übersicht über Dialogfelder](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)\).  Sie können steuern, ob die Taskleistenschaltfläche für ein Fenster angezeigt wird, indem Sie die <xref:System.Windows.Window.ShowInTaskbar%2A>\-Eigenschaft festlegen \(standardmäßig `true`\).  
  
 [!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup2)]  
  
<a name="SecurityConsiderations"></a>   
## Sicherheitsüberlegungen  
 <xref:System.Windows.Window> benötigt die `UnmanagedCode`\-Sicherheitsberechtigung, um instanziiert zu werden.  Bei Anwendungen, die auf dem lokalen Computer installiert und gestartet werden, wird dies durch die Berechtigungen abgedeckt, die der Anwendung gewährt werden.  
  
 Allerdings gilt dies nicht für Berechtigungen, die Anwendungen gewährt wurden, die mit [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] über das Internet oder die lokale Intranetzone gestartet werden.  Infolgedessen erhalten Benutzer eine [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Sicherheitswarnung. Außerdem müssen sie den Berechtigungssatz für die Anwendung auf volle Vertrauenswürdigkeit erhöhen.  
  
 Darüber hinaus kann [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] standardmäßig keine Fenster oder Dialogfelder anzeigen.  Eine Erörterung von Sicherheitsüberlegungen für eigenständige Anwendungen finden Sie unter [WPF\-Sicherheitsstrategie – Plattformsicherheit](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## Andere Fenstertypen  
 <xref:System.Windows.Navigation.NavigationWindow> ist ein Fenster, das zum Hosten von navigierbarem Inhalt konzipiert ist.  Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Dialogfelder sind Fenster, die häufig zum Erfassen von Benutzerinformationen verwendet werden, um eine Funktion ausführen.  Wenn ein Benutzer beispielsweise eine Datei öffnen möchte, wird normalerweise das Dialogfeld **Datei öffnen** von einer Anwendung angezeigt, um den Dateinamen vom Benutzer zu erhalten.  Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Window>   
 <xref:System.Windows.MessageBox>   
 <xref:System.Windows.Navigation.NavigationWindow>   
 <xref:System.Windows.Application>   
 [Übersicht über Dialogfelder](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)   
 [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)