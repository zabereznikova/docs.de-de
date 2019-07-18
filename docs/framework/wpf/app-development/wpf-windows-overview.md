---
title: Übersicht über WPF-Fenster
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: 60ed101df691db9f1afa8e47702f131bee384495
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625316"
---
# <a name="wpf-windows-overview"></a>Übersicht über WPF-Fenster
Benutzer interagieren mit Windows Presentation Foundation (WPF), eigenständige Anwendungen über Windows. Die Hauptaufgabe eines Fensters besteht darin, Inhalt zu hosten, der Daten visuell darstellen kann und Benutzern die Interaktion mit Daten ermöglicht. Eigenständige [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen stellen ihre eigenen Windows über das <xref:System.Windows.Window> Klasse. In diesem Thema werden <xref:System.Windows.Window> , bevor Sie die Grundlagen der Erstellung und Verwaltung von Fenstern in eigenständigen Anwendungen behandelt.  
  
> [!NOTE]
>  Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen, einschließlich [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seiten, stellen keine eigenen Fenster. Stattdessen werden sie in von bereitgestellten Windows gehostet [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]. Finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Die Fensterklasse  
 Die folgende Abbildung zeigt die Bestandteile eines Fensters an:  
  
 ![Screenshot mit Windows-Elementen.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Ein Fenster wird in zwei Bereiche geteilt: der Nicht-Clientbereich und der Clientbereich.  
  
 Die *nicht-Clientbereich* eines Fensters wird implementiert, indem [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und enthält die Teile eines Fensters, das für die meisten Fenster, einschließlich der folgenden gelten:  
  
- Rahmen  
  
- Titelleiste  
  
- Symbol  
  
- Schaltflächen zum Minimieren, Maximieren und Wiederherstellen  
  
- Schaltfläche Schließen  
  
- Ein Systemmenü mit Menüelementen, mit denen Benutzer ein Fenster minimieren, maximieren, wiederherstellen, verschieben, schließen und dessen Größe ändern können.  
  
 Die *Clientbereich* ist ein Bereich innerhalb eines Fensters nicht-Clientbereich eines Fensters und wird von Entwicklern verwendet, anwendungsspezifischen Inhalt, z. B. Menüleisten, Symbolleisten und Steuerelemente hinzufügen.  
  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], ein Fenster wird gekapselt, durch die <xref:System.Windows.Window> -Klasse, die Sie verwenden, um die folgenden Aktionen ausführen:  
  
- Anzeigen eines Fensters  
  
- Konfigurieren der Größe, Position und Darstellung eines Fensters  
  
- Hosten von anwendungsspezifischem Inhalt  
  
- Verwalten der Lebensdauer eines Fensters  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Implementieren eines Fensters  
 Die Implementierung eines typischen Fensters umfasst sowohl Darstellung und Verhalten, in denen *Darstellung* definiert, wie ein Fenster angezeigt und *Verhalten* definiert die Funktionsweise ein Fensters während Benutzer interagieren mit ihm. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], können Sie implementieren, die Darstellung und Verhalten eines Fensters mithilfe entweder mit code oder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 Im Allgemeinen jedoch die Darstellung eines Fensters wird mithilfe von implementiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup und dessen Verhalten implementiert mit Code-Behind, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 So aktivieren Sie eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup-Datei und Code-Behind-Datei zusammenarbeiten können, gelten die folgenden Voraussetzungen:  
  
- Im Markup der `Window` -Element muss enthalten der `x:Class` Attribut. Wenn die Anwendung erstellt wird, wird das Vorhandensein des `x:Class` im Markup führt [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] zum Erstellen einer `partial` abgeleitete Klasse <xref:System.Windows.Window> und hat den Namen, die angegeben wird die `x:Class` Attribut. Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Namespace-Deklaration für die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Die generierte `partial` -Klasse implementiert die `InitializeComponent` -Methode, die aufgerufen wird, um die Ereignisse zu registrieren, und legen die Eigenschaften, die im Markup implementiert werden.  
  
- Im Code-Behind muss die Klasse muss eine `partial` Klasse mit dem gleichen Namen, die angegeben wird die `x:Class` Attribut im Markup, und es muss abgeleitet <xref:System.Windows.Window>. Dadurch wird der Code-Behind-Datei zugeordnet werden die `partial` -Klasse, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wird (finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).  
  
- Im Code-Behind muss die <xref:System.Windows.Window> Klasse implementieren muss einen Konstruktor, der Aufrufe der `InitializeComponent` Methode. `InitializeComponent` wird implementiert, indem Sie das Markup generierte `partial` Klasse zum Registrieren von Ereignissen und Festlegen von Eigenschaften, die im Markup definierte.  
  
> [!NOTE]
>  Beim Hinzufügen einer neuen <xref:System.Windows.Window> zu Ihrem Projekt mithilfe von [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Window> wird mithilfe von Markup und CodeBehind implementiert und enthält die erforderlichen Konfigurationsschritte zum Erstellen der Verknüpfung zwischen Markup- und Code-Behind-Dateien als hier beschrieben.  
  
 Mit dieser Konfiguration können Sie sich auf definieren die Darstellung des Fensters in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup und dessen Verhalten im Code-Behind implementiert. Das folgende Beispiel zeigt ein Fenster mit einer Schaltfläche in implementiert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup und einen Ereignishandler für der Schaltfläche " <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis im Code-Behind implementiert.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Konfigurieren einer Fensterdefinition für MSBuild  
 Wie der Implementierung des Fensters bestimmt dessen Konfiguration für [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]. Für ein Fenster, das definiert ist, mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup und CodeBehind:  
  
- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup-Dateien werden als konfiguriert [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` Elemente.  
  
- Code-Behind-Dateien werden als konfiguriert [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` Elemente.  
  
 Dies wird im folgenden gezeigt [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] Projektdatei.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Informationen zum Erstellen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -Anwendungen finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Fensterlebensdauer  
 Wie alle Klassen hat auch ein Fenster eine Lebensdauer, die mit dem erstmaligen Instanziieren beginnt. Anschließend wird es geöffnet, aktiviert, deaktiviert und schließlich geschlossen.  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Öffnen eines Fensters  
 Wenn Sie ein Fenster öffnen möchten, müssen Sie zuerst eine Instanz davon erstellen. Dies wird im folgenden Beispiel veranschaulicht.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In diesem Beispiel die `MarkupAndCodeBehindWindow` wird instanziiert, wenn die Anwendung gestartet wird, dies geschieht, wenn die <xref:System.Windows.Application.Startup> Ereignis wird ausgelöst.  
  
 Wenn ein Fenster instanziiert wird, wird ein Verweis darauf automatisch zu einer Liste von Windows, die von verwaltet wird hinzugefügt der <xref:System.Windows.Application> Objekt (finden Sie unter <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Darüber hinaus wird das erste zu instanziierende Fenster standardmäßig von festgelegt <xref:System.Windows.Application> als das Hauptanwendungsfenster (siehe <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 Schließlich Öffnen des Fensters durch den Aufruf der <xref:System.Windows.Window.Show%2A> Methode das Ergebnis wird in der folgenden Abbildung dargestellt.  
  
 ![Ein Fenster, das durch den Aufruf von Window.Show geöffnet](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Ein Fenster, das durch Aufrufen von <xref:System.Windows.Window.Show%2A> wird ein nicht modales Fenster, das bedeutet, dass die Anwendung in einem Modus ausgeführt, die Benutzern ermöglicht wird, andere Fenster in derselben Anwendung zu aktivieren.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> wird aufgerufen, um Windows, z. B. Dialogfelder, modal aufzurufen. Finden Sie unter [Übersicht über Dialogfelder](dialog-boxes-overview.md) für Weitere Informationen.  
  
 Wenn <xref:System.Windows.Window.Show%2A> ist führt Initialisierung aufgerufen wird, ein Fenster aus, bevor es angezeigt wird, zum Festlegen der Infrastruktur, die es Benutzereingaben empfangen kann. Wenn das Fenster initialisiert wird, die <xref:System.Windows.Window.SourceInitialized> Ereignis wird ausgelöst, und das Fenster wird angezeigt.  
  
 Als abgekürztes <xref:System.Windows.Application.StartupUri%2A> kann festgelegt werden, um das erste Fenster anzugeben, die automatisch geöffnet wird, wenn eine Anwendung startet.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Beim Starten der Anwendung, die durch den Wert des angegebenen Fensters <xref:System.Windows.Application.StartupUri%2A> geöffnet wird im nicht modalen Modus; intern Öffnen des Fensters durch den Aufruf der <xref:System.Windows.Window.Show%2A> Methode.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Besitz von Fenstern  
 Ein Fenster, das mit geöffnet wird die <xref:System.Windows.Window.Show%2A> Methode verfügt nicht über eine implizite Beziehung mit dem Fenster, das sie erstellt haben, kann der Benutzerinteraktion mit beiden Fenster unabhängig, was bedeutet, dass die beiden Fenster die folgenden Aktionen ausführen kann:  
  
- Das andere Fenster überdecken (es sei denn, eines der Fenster die <xref:System.Windows.Window.Topmost%2A> -Eigenschaftensatz auf `true`).  
  
- Es wird minimiert, maximiert und wiederhergestellt, ohne das andere zu beeinflussen.  
  
 Bei einigen Fenstern ist eine Beziehung zu dem Fenster erforderlich, durch das es geöffnet wird. Z. B. eine [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] Anwendung öffnen kann, Eigenschaftenfenster und Toolfenster, deren typisches Verhalten besteht darin, das Fenster zu überdecken, der sie erstellt. Darüber hinaus sollten solche Fenster stets mit den Fenstern geschlossen, minimiert, maximiert und wiederhergestellt werden, durch die sie erstellt wurden. Eine solche Beziehung hergestellt werden kann, durch dass ein Fenster *eigenen* eine andere, und wird erreicht, indem die <xref:System.Windows.Window.Owner%2A> Eigenschaft der *Besitzer gehöriges Fenster* mit einem Verweis auf die *Besitzer Fenster*. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Nach Einrichten des Besitzes:  
  
- Besitzer gehörige Fenster kann auf sein Besitzerfenster verweisen, indem der Wert von dessen <xref:System.Windows.Window.Owner%2A> Eigenschaft.  
  
- Das Besitzerfenster kann alle Fenster durch Überprüfen des Werts des ermitteln die <xref:System.Windows.Window.OwnedWindows%2A> Eigenschaft.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Verhindern der Fensteraktivierung  
 Es gibt Szenarien, in denen Windows nicht aktiviert werden soll, wenn, wie z. B. Unterhaltungsfenster einer Internet-Messenger-Anwendung oder Benachrichtigungsfenster einer e-Mail-Anwendung angezeigt.  
  
 Wenn Ihre Anwendung ein Fenster verfügt, die nicht aktiviert werden sollte, wenn Sie angezeigt wird, legen Sie seine <xref:System.Windows.Window.ShowActivated%2A> Eigenschaft `false` vor dem Aufruf der <xref:System.Windows.Window.Show%2A> Methode zum ersten Mal. Daraus folgt:  
  
- Das Fenster wird nicht aktiviert.  
  
- Des Fensters des <xref:System.Windows.Window.Activated> Ereignis wird nicht ausgelöst.  
  
- Das momentan aktivierte Fenster bleibt aktiviert.  
  
 Das Fenster wird jedoch aktiviert, sobald der Benutzer es durch Klicken auf den Client- oder Nicht-Clientbereich aktiviert. In diesem Fall gilt Folgendes:  
  
- Das Fenster wird aktiviert.  
  
- Des Fensters des <xref:System.Windows.Window.Activated> Ereignis wird ausgelöst.  
  
- Das zuvor aktivierte Fenster wird deaktiviert.  
  
- Des Fensters des <xref:System.Windows.Window.Deactivated> und <xref:System.Windows.Window.Activated> Ereignisse werden anschließend als Reaktion auf Benutzeraktionen wie erwartet ausgelöst.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Aktivieren von Fenstern  
 Wenn ein Fenster zum ersten Mal geöffnet wird, wird es zum aktiven Fenster (es sei denn, es mit angezeigt wird <xref:System.Windows.Window.ShowActivated%2A> festgelegt `false`). Die *des aktiven Fensters* ist das Fenster, das gegenwärtig Benutzereingaben, z. B. Tastenanschläge und Mausklicks. Wenn ein Fenster aktiv ist, löst die <xref:System.Windows.Window.Activated> Ereignis.  
  
> [!NOTE]
>  Beim ersten ein Fensters öffnen, das <xref:System.Windows.FrameworkElement.Loaded> und <xref:System.Windows.Window.ContentRendered> Ereignisse werden erst ausgelöst, nachdem die <xref:System.Windows.Window.Activated> Ereignis wird ausgelöst. In diesem Sinn, ein Fenster als tatsächlich geöffnet, wenn <xref:System.Windows.Window.ContentRendered> ausgelöst wird.  
  
 Nachdem ein Fenster aktiv geworden ist, kann ein Benutzer ein weiteres Fenster in derselben Anwendung oder eine andere Anwendung aktivieren. In diesem Fall das momentan aktive Fenster deaktiviert wird, und löst die <xref:System.Windows.Window.Deactivated> Ereignis. Ebenso, wenn der Benutzer ein derzeit deaktiviertes Fenster auswählt, das Fenster wird wieder aktiv und <xref:System.Windows.Window.Activated> ausgelöst wird.  
  
 Ein häufiger Grund für die Behandlung <xref:System.Windows.Window.Activated> und <xref:System.Windows.Window.Deactivated> ist das Aktivieren und Deaktivieren von Funktionen, die nur ausgeführt werden kann, wenn ein Fenster aktiv ist. In einigen Fenstern wird beispielsweise interaktiver Inhalt angezeigt, der andauernde Benutzereingaben oder Aufmerksamkeit erfordert, wie beispielsweise Spiele und Videoplayer. Das folgende Beispiel enthält einen vereinfachten Videoplayer, der zeigt, wie behandelt <xref:System.Windows.Window.Activated> und <xref:System.Windows.Window.Deactivated> auf dieses Verhalten zu implementieren.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Andere Anwendungstypen führen im Hintergrund möglicherweise weiterhin Code aus, nachdem ein Fenster deaktiviert wurde. Ein E-Mail-Client kann z. B. weiterhin den E-Mail-Server abrufen, während der Benutzer andere Anwendungen verwendet. Während das Hauptfenster deaktiviert ist, stellen derartige Anwendungen häufig zusätzliches oder anderes Verhalten zur Verfügung. Im Hinblick auf das E-Mail-Programm kann das sowohl das Hinzufügen des neuen E-Mail-Elements zum Posteingang als auch eines Benachrichtigungssymbol in die Taskleiste bedeuten. Ein Benachrichtigungssymbol muss nur angezeigt werden, wenn das e-Mail-Fenster nicht aktiv ist dies kann durch Überprüfen ermittelt werden die <xref:System.Windows.Window.IsActive%2A> Eigenschaft.  
  
 Wenn eine Hintergrundaufgabe ausgeführt wird, ein Fenster kann den Benutzer etwas dringlicher durch Aufrufen benachrichtigen möchten <xref:System.Windows.Window.Activate%2A> Methode. Wenn der Benutzer interagiert mit einer anderen Anwendung aktiviert, wenn <xref:System.Windows.Window.Activate%2A> aufgerufen wird, blinkt die Taskleistenschaltfläche des Fensters. Wenn ein Benutzer mit der aktuellen Anwendung interagiert, wird beim Aufrufen <xref:System.Windows.Window.Activate%2A> bringt das Fenster in den Vordergrund gestellt.  
  
> [!NOTE]
>  Sie können die Verwendung der Aktivierung der Anwendungsbereich behandeln die <xref:System.Windows.Application.Activated?displayProperty=nameWithType> und <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> Ereignisse.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Schließen eines Fensters  
 Die Lebensdauer eines Fensters endet, wenn der Benutzer das Fenster schließt. Ein Fenster kann mithilfe der Elemente im Nicht-Clientbereich geschlossen werden, z. B. mit den folgenden:  
  
- Die **schließen** Element der **System** Menü.  
  
- Drücken von ALT+F4.  
  
- Drücken Sie die **schließen** Schaltfläche.  
  
 Zum Schließen eines Fensters können Sie dem Clientbereich weitere Mechanismen hinzufügen. Zu den gebräuchlichsten zählen:  
  
- Ein **beenden** Element in der **Datei** Menü i. d. r. für Hauptanwendungsfenster.  
  
- Ein **schließen** Element in der **Datei** Menü in der Regel auf einem sekundären Anwendungsfenster.  
  
- Ein **Abbrechen** Schaltfläche in der Regel auf ein modales Dialogfeld.  
  
- Ein **schließen** Schaltfläche in der Regel auf ein nicht modales Dialogfeld.  
  
 Um ein Fenster mit einem der benutzerdefinierten Mechanismen zu schließen, müssen Sie zum Aufrufen der <xref:System.Windows.Window.Close%2A> Methode. Das folgende Beispiel implementiert die Möglichkeit, ein Fenster zu schließen, durch Auswählen der **beenden** auf die **Datei** Menü.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Wenn ein Fenster geschlossen wird, löst es zwei Ereignisse: <xref:System.Windows.Window.Closing> und <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> wird ausgelöst, bevor das Fenster wird geschlossen, und bietet einen Mechanismus, durch welches, den Fenster verhindert werden kann. Der häufigste Grund, um das Schließen eines Fensters zu verhindern, liegt darin, dass Fensterinhalt geänderte Daten enthält. In diesem Fall die <xref:System.Windows.Window.Closing> -Ereignis behandelt werden, um zu bestimmen, ob Daten geändert wurden, und wenn Ja, auf der Benutzer gefragt werden, ob das Fenster schließen, ohne die Daten speichern fortfahren oder Schließen des Fensters abzubrechen. Das folgende Beispiel zeigt die wichtigsten Aspekte bei der Behandlung <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Die <xref:System.Windows.Window.Closing> -Ereignishandler übergeben wird eine <xref:System.ComponentModel.CancelEventArgs>, implementiert die `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> -Eigenschaft, die Sie, um festlegen `true` zum Schließen ein Fensters zu verhindern.  
  
 Wenn <xref:System.Windows.Window.Closing> nicht behandelt, oder behandelt, aber nicht abgebrochen, wird das Fenster zu schließen. Unmittelbar vor der eigentlichen Schließen des Fensters <xref:System.Windows.Window.Closed> ausgelöst wird. An dieser Stelle kann das Schließen des Fensters nicht verhindert werden.  
  
> [!NOTE]
>  Eine Anwendung kann zum Herunterfahren, wenn entweder das Hauptanwendungsfenster automatisch schließt konfiguriert werden (siehe <xref:System.Windows.Application.MainWindow%2A>) oder das letzte Fenster geschlossen. Ausführliche Informationen finden Sie unter <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Während ein Fenster über in den Bereichen nicht-Client und Client bereitgestellten Mechanismen explizit geschlossen werden kann, ein Fenster kann implizit geschlossen werden infolge des Verhaltens in anderen Teilen der Anwendung oder [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], einschließlich der folgenden:  
  
- Ein Benutzer abmeldet oder Windows heruntergefahren.  
  
- Der Besitzer eines Fensters schließt (siehe <xref:System.Windows.Window.Owner%2A>).  
  
- Das Hauptanwendungsfenster wird geschlossen und <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
- <xref:System.Windows.Application.Shutdown%2A> wird aufgerufen.  
  
> [!NOTE]
>  Ein Fenster kann nicht erneut geöffnet werden, nachdem es geschlossen wurde.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Ereignisse in der Lebensdauer eines Fensters  
 Die folgende Abbildung zeigt die Abfolge der wichtigsten Ereignisse in der Lebensdauer eines Fensters an:  
  
 ![Diagramm, das Ereignisse in ein Fenster Lebensdauer angezeigt.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 Die folgende Abbildung zeigt die Abfolge der wichtigsten Ereignisse in der Lebensdauer eines Fensters, das ohne Aktivierung angezeigt wird (<xref:System.Windows.Window.ShowActivated%2A> nastaven NA hodnotu `false` , bevor das Fenster angezeigt wird):  
  
 ![Diagramm, das Ereignisse in der Lebensdauer eines Fensters, ohne Aktivierung angezeigt.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Fensterposition  
 Solange ein Fenster geöffnet ist, befindet sich dessen Position in der x- und y-Dimension relativ zum Desktop. Dieser Speicherort kann bestimmt werden, durch Überprüfen der <xref:System.Windows.Window.Left%2A> und <xref:System.Windows.Window.Top%2A> Eigenschaften, bzw. Sie können diese Eigenschaften festlegen, um die Position des Fensters zu ändern.  
  
 Sie können auch angeben, die ursprüngliche Position des ein <xref:System.Windows.Window> bei seinem ersten Auftreten durch Festlegen der <xref:System.Windows.Window.WindowStartupLocation%2A> Eigenschaft mit einer der folgenden <xref:System.Windows.WindowStartupLocation> -Enumerationswerte fest:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (Standard)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Wenn die Startposition, als angegeben wird <xref:System.Windows.WindowStartupLocation.Manual>, und die <xref:System.Windows.Window.Left%2A> und <xref:System.Windows.Window.Top%2A> nicht festgelegt wurde, <xref:System.Windows.Window> fragt Windows für einen Standort in angezeigt werden.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Oberstes Fenster und Z-Reihenfolge  
 Neben der X- und Y-Position verfügt das Fenster auch über eine Position in der Z-Dimension, die dessen vertikale Position im Verhältnis zu anderen Fenstern bestimmt. Dies wird als Z-Reihenfolge des Fensters bezeichnet. Davon gibt es zwei Typen: die normale Z-Reihenfolge und die oberste Z-Reihenfolge. Die Position eines Fensters in der *normalen Z-Reihenfolge* richtet sich nach, ob er derzeit aktiv ist. Standardmäßig befindet sich ein Fenster in der normalen Z-Reihenfolge. Die Position eines Fensters in der *oberste Z-Reihenfolge* hängt ebenfalls davon, ob er derzeit aktiv ist. Darüber hinaus befinden sich Fenster in der obersten Z-Reihenfolge stets über den Fenstern in der normalen Z-Reihenfolge. Ein Fenster befindet sich in der obersten Z-Reihenfolge durch Festlegen seiner <xref:System.Windows.Window.Topmost%2A> Eigenschaft `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 Innerhalb jeder Z-Reihenfolge wird das aktuell aktive Fenster über allen anderen Fenstern derselben Z-Reihenfolge angezeigt.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Fenstergröße  
 Neben der Position auf dem desktop, ein Fenster hat eine Größe, die durch mehrere Eigenschaften, einschließlich der verschiedenen Eigenschaften für Breite und Höhe bestimmt wird und <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, und <xref:System.Windows.FrameworkElement.MaxWidth%2A> dienen zum Verwalten des Bereichs von Breiten verwendet, die ein Fenster während seiner Lebensdauer haben kann, und konfiguriert sind, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Die Fensterhöhe wird von verwaltet <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, und <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und konfiguriert sind, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Da die verschiedenen Werte für die Breite und für die Höhe jeweils einen Bereich angeben, kann die Breite und Höhe eines in der Größe veränderbaren Fensters irgendwo innerhalb des angegebenen Bereichs für die entsprechende Dimension liegen. Wenn um die aktuelle Breite und Höhe zu ermitteln, überprüfen Sie <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A>bzw.  
  
 Wenn Sie möchten die Breite und Höhe des Fensters, um eine Größe aufweisen, die auf die Größe des Fensters entspricht den Inhalt, können Sie verwenden die <xref:System.Windows.Window.SizeToContent%2A> -Eigenschaft, die in den folgenden Werten:  
  
- <xref:System.Windows.SizeToContent.Manual>. Keine Auswirkung (Standard).  
  
- <xref:System.Windows.SizeToContent.Width>. Anpassen an die Breite Inhalts dieselbe Wirkung hat wie das Festlegen sowohl <xref:System.Windows.FrameworkElement.MinWidth%2A> und <xref:System.Windows.FrameworkElement.MaxWidth%2A> auf die Breite des Inhalts.  
  
- <xref:System.Windows.SizeToContent.Height>. Anpassen an die Höhe Inhalts dieselbe Wirkung hat wie das Festlegen sowohl <xref:System.Windows.FrameworkElement.MinHeight%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> auf die Höhe des Inhalts.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Anpassen an die Breite des Inhalts und die Höhe dieselbe Wirkung hat wie das Festlegen sowohl <xref:System.Windows.FrameworkElement.MinHeight%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> auf die Höhe des Inhalts sowie das Festlegen sowohl <xref:System.Windows.FrameworkElement.MinWidth%2A> und <xref:System.Windows.FrameworkElement.MaxWidth%2A> auf die Breite des Inhalts.  
  
 Im folgenden Beispiel wird ein Fenster dass die Größe automatisch an seinen Inhalt vertikal und horizontal an, wenn es zuerst angezeigt wird.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Im folgende Beispiel veranschaulicht die legen Sie die <xref:System.Windows.Window.SizeToContent%2A> Eigenschaft im Code, um anzugeben, wie die Fenstergröße um seinen Inhalt anzupassen.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Rangfolge der Größeneigenschaften  
 Im Wesentlichen werden die verschiedenen Größeneigenschaften eines Fensters kombiniert, um den Bereich der Breite und der Höhe für ein in der Größe veränderbares Fenster zu definieren. Um sicherzustellen, dass ein gültiger Bereich beibehalten wird, <xref:System.Windows.Window> wertet die Werte der Größeneigenschaften anhand der folgenden Rangfolgen aus.  
  
 **Für Höheneigenschaften:**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Für Breiteneigenschaften:**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 Rangfolge kann bestimmen die Größe eines Fensters auch zu, wenn dieses, die maximiert ist mit verwaltet wird, die <xref:System.Windows.Window.WindowState%2A> Eigenschaft.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Fensterzustand  
 Während der Lebensdauer eines in der Größe veränderbaren Fenster kann dieses über drei Zustände verfügen: normal, minimiert und maximiert. Ein Fenster mit einem *normalen* Zustand ist der Standardzustand eines Fensters. Ein Benutzer kann ein Fenster mit diesem Zustand verschieben und dessen Größe ändern, indem er den Ziehpunkt zur Größenänderung oder den Rahmen verwendet, sofern er in der Größe veränderbar ist.  
  
 Ein Fenster mit einem *minimiert* Status wird auf seine Taskleistenschaltfläche reduziert, wenn <xref:System.Windows.Window.ShowInTaskbar%2A> nastaven NA hodnotu `true`ist, andernfalls wird reduziert, um die kleinstmögliche Größe es kann sein und in der unteren linken Ecke des Desktops. Keiner der minimierten Fenstertypen kann mithilfe des Ziehpunkts zur Größenreduzierung oder mit dem Rahmen in der Größe verändert werden. Allerdings kann ein minimiertes Fenster, das nicht in der Taskleiste angezeigt wird, auf dem Desktop hin und her verschoben werden.  
  
 Ein Fenster mit einem *maximiert* Zustand wird erweitert, um die maximale Größe es sein kann, die nur so groß wie die <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und <xref:System.Windows.Window.SizeToContent%2A> Eigenschaften. Wie ein minimiertes Fenster kann auch ein maximiertes Fenster nicht mithilfe des Ziehpunkts zur Größenänderung oder durch Ziehen des Rahmens in seiner Größe verändert werden.  
  
> [!NOTE]
>  Die Werte der <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften eines Fensters stellen immer die Werte für den normalen Zustand dar, selbst wenn das Fenster gerade maximiert oder minimiert wird.  
  
 Der Zustand eines Fensters kann konfiguriert werden, durch Festlegen der <xref:System.Windows.Window.WindowState%2A> -Eigenschaft, die einen der folgenden enthalten kann <xref:System.Windows.WindowState> Enumerationswerte:  
  
- <xref:System.Windows.WindowState.Normal> (Standard)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie ein Fenster erstellen, das beim Öffnen als maximiert angezeigt wird.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 Im Allgemeinen sollten Sie festlegen <xref:System.Windows.Window.WindowState%2A> so konfigurieren Sie den Ausgangszustand eines Fensters. Wenn ein in der Größe veränderbares Fenster angezeigt wird, können die Benutzer die Schaltflächen zum Minimieren, Maximieren oder Wiederherstellen auf der Titelleiste des Fensters aktivieren, um den Fensterzustand zu ändern.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Fensterdarstellung  
 Sie ändern die Darstellung des Clientbereichs eines Fensters, indem Sie fensterspezifischen Inhalt hinzufügen, z. B. Schaltflächen, Bezeichnungen und Textfelder. So konfigurieren Sie den nicht-Clientbereich, <xref:System.Windows.Window> stellt mehrere Eigenschaften, darunter <xref:System.Windows.Window.Icon%2A> auf das Symbol eines Fensters festzulegen und <xref:System.Windows.Window.Title%2A> um den Fenstertitel festzulegen.  
  
 Außerdem können Sie die Darstellung und das Verhalten des Rahmens im Nicht-Clientbereich ändern, indem Sie den Größenänderungsmodus, den Fensterstil und die Tatsache konfigurieren, ob es als Schaltfläche in der Desktoptaskleiste angezeigt wird.  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Größenänderungsmodus  
 Je die <xref:System.Windows.Window.WindowStyle%2A> -Eigenschaft, können Sie steuern, wie (und ob) Benutzer die Größe des Fensters ändern können. Die Auswahl des Fensterstils bestimmt, ob es sich bei ein Benutzer die Fenstergröße durch Ziehen von, ob der Rahmen mit der Maus ändern kann die **Minimieren**, **Maximieren**, und **Größe** Schaltflächen auf den nicht-Clientbereich angezeigt werden und, falls sie angezeigt, ob diese aktiviert sind.  
  
 Sie können konfigurieren, wie durch Festlegen von die Fenstergröße der <xref:System.Windows.Window.ResizeMode%2A> -Eigenschaft, die in der folgenden Werte sind möglich <xref:System.Windows.ResizeMode> -Enumerationswerte fest:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (Standard)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Wie bei <xref:System.Windows.Window.WindowStyle%2A>, der Größenänderungsmodus eines Fensters ist es unwahrscheinlich, dass während seiner Lebensdauer ändern, was bedeutet, dass Sie es vom wahrscheinlich festlegen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Beachten Sie, die Sie können erkennen, ob ein Fenster maximiert, minimiert oder wiederhergestellt, indem Sie überprüfen die <xref:System.Windows.Window.WindowState%2A> Eigenschaft.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Fensterstil  
 Der Rahmen, der vom Nicht-Clientbereich eines Fensters verfügbar gemacht wird, eignet sich für die meisten Anwendungen. Unter bestimmten Umständen werden je nach Fenstertyp dennoch andere Rahmentypen oder überhaupt keine Rahmen benötigt.  
  
 Um welche Art des Rahmens ein Fensters zu steuern, legen Sie dessen <xref:System.Windows.Window.WindowStyle%2A> Eigenschaft mit einem der folgenden Werte von der <xref:System.Windows.WindowStyle> Enumeration:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (Standard)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Die Auswirkung dieser Fensterstile sind in der folgenden Abbildung dargestellt:  
  
 ![Abbildung der Rahmenarten des Fensters.](./media/wpf-windows-overview/window-border-styles.png)  
  
 Sie können festlegen, <xref:System.Windows.Window.WindowStyle%2A> entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup oder Code, da es unwahrscheinlich ist, um während der Lebensdauer eines Fensters zu ändern ist, in den meisten Fällen konfigurieren sie mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Nicht rechteckiger Fensterstil  
 Es gibt auch Situationen, in dem der Rahmen, die formatiert <xref:System.Windows.Window.WindowStyle%2A> ermöglicht Ihnen, sind nicht ausreichend. Sie möchten z. B. eine Anwendung mit einem nicht rechteckigen Rahmen erstellen, wie [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] verwendet.  
  
 Betrachten Sie beispielsweise das Sprechblasenfenster in der folgenden Abbildung aus:  
  
 ![Ein Spracherkennung Blase-Fenster, das besagt der Drag & Me.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Diese Art von Fenster erstellt werden kann, indem die <xref:System.Windows.Window.WindowStyle%2A> Eigenschaft <xref:System.Windows.WindowStyle.None>, und mithilfe von speziellen zu unterstützen, die <xref:System.Windows.Window> zur Transparenz bietet.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Durch diese Kombination von Werten wird das Fenster angewiesen, ein vollkommen transparentes Rendering zu übernehmen. In diesem Zustand können die Zusatzelemente des Nicht-Clientbereichs des Fensters (das Menü „Schließen“, die Schaltflächen „Minimieren“, „Maximieren“ und „Wiederherstellen“ usw.) nicht verwendet werden. Folglich müssen Sie Ihre eigenen bereitstellen.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Vorhandensein der Taskleiste  

Die standarddarstellung eines Fensters umfasst eine Taskleistenschaltfläche wie in der folgenden Abbildung dargestellt:

 ![Screenshot, der ein Fenster mit einer Taskleistenschaltfläche anzeigt.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Einige Arten von Windows keine Taskleistenschaltfläche, z. B. Meldungsfelder und Dialogfelder (siehe [Übersicht über Dialogfelder](dialog-boxes-overview.md)). Sie können steuern, ob die Taskleistenschaltfläche für ein Fenster, durch Festlegen angezeigt wird der <xref:System.Windows.Window.ShowInTaskbar%2A> Eigenschaft (`true` standardmäßig).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Sicherheitsüberlegungen  
 <xref:System.Windows.Window> erfordert `UnmanagedCode` Sicherheitsberechtigung instanziiert werden. Bei Anwendungen, die auf dem lokalen Computer installiert und gestartet werden, wird dies durch die Berechtigungen abgedeckt, die der Anwendung gewährt werden.  
  
 Allerdings gilt dies nicht außerhalb des Satzes von Berechtigungen für Anwendungen, die aus dem Internet oder lokalen Intranet-Zone mit gestartet werden [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]. Infolgedessen erhalten Benutzer eine [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] sicherheitswarnung, und den Berechtigungssatz für die Anwendung auf volle Vertrauenswürdigkeit erhöhen müssen.  
  
 Darüber hinaus [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] kann nicht in der Standardeinstellung Fenster oder Dialogfelder angezeigt. Ausführliche Informationen zu sicherheitsüberlegungen für eigenständige Anwendung, finden Sie unter [WPF-Sicherheitsstrategie – Plattformsicherheit](../wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Andere Fenstertypen  
 <xref:System.Windows.Navigation.NavigationWindow> ist ein Fenster, das zum Hosten von navigierbarem Inhalt konzipiert ist. Weitere Informationen finden Sie unter [Übersicht über die Navigation](navigation-overview.md)).  
  
 Dialogfelder sind Fenster, die häufig zum Erfassen von Benutzerinformationen verwendet werden, um eine Funktion ausführen. Z. B. wenn ein Benutzer möchte eine Datei öffnen die **Datei öffnen** Dialogfeld wird in der Regel von einer Anwendung zum Abrufen des Dateinamens des Benutzers angezeigt. Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Übersicht über Dialogfelder](dialog-boxes-overview.md)
- [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)
