---
title: Windows-Übersicht
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
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145539"
---
# <a name="wpf-windows-overview"></a>Übersicht über WPF-Fenster
Benutzer interagieren über Fenster mit eigenständigen Windows Presentation Foundation (WPF)-Anwendungen. Die Hauptaufgabe eines Fensters besteht darin, Inhalt zu hosten, der Daten visuell darstellen kann und Benutzern die Interaktion mit Daten ermöglicht. Eigenständige WPF-Anwendungen stellen ihre eigenen <xref:System.Windows.Window> Fenster mithilfe der Klasse bereit. In diesem <xref:System.Windows.Window> Thema werden die Grundlagen zum Erstellen und Verwalten von Fenstern in eigenständigen Anwendungen behandelt.  
  
> [!NOTE]
> Browser-gehostete WPF-Anwendungen, einschließlich XAML-Browseranwendungen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] (XBAPs) und lose Seiten, stellen keine eigenen Fenster bereit. Stattdessen werden sie in Fenstern gehostet, die von Windows Internet Explorer bereitgestellt werden. Siehe [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a>Die Fensterklasse  
 Die folgende Abbildung veranschaulicht die Bestandteile eines Fensters:  
  
 ![Screenshot, der Fensterelemente anzeigt.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Ein Fenster wird in zwei Bereiche geteilt: der Nicht-Clientbereich und der Clientbereich.  
  
 Der *Nicht-Client-Bereich* eines Fensters wird von WPF implementiert und umfasst die Teile eines Fensters, die den meisten Fenstern gemeinsam sind, einschließlich der folgenden:  
  
- Rahmen  
  
- Titelleiste  
  
- Symbol  
  
- Schaltflächen zum Minimieren, Maximieren und Wiederherstellen  
  
- Schaltfläche Schließen  
  
- Ein Systemmenü mit Menüelementen, mit denen Benutzer ein Fenster minimieren, maximieren, wiederherstellen, verschieben, schließen und dessen Größe ändern können.  
  
 Der *Clientbereich* eines Fensters ist der Bereich innerhalb des Nicht-Clientbereichs eines Fensters und wird von Entwicklern zum Hinzufügen anwendungsspezifischer Inhalte wie Menüleisten, Symbolleisten und Steuerelemente verwendet.  
  
 In WPF wird ein Fenster von <xref:System.Windows.Window> der Klasse gekapselt, die Sie für Folgendes verwenden:  
  
- Anzeigen eines Fensters  
  
- Konfigurieren der Größe, Position und Darstellung eines Fensters  
  
- Hosten von anwendungsspezifischem Inhalt  
  
- Verwalten der Lebensdauer eines Fensters  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a>Implementieren eines Fensters  
 Die Implementierung eines typischen Fensters umfasst sowohl das Erscheinungsbild als auch das Verhalten, wobei das *Erscheinungsbild* definiert, wie ein Fenster für Benutzer aussieht, und *das Verhalten* definiert, wie ein Fenster funktioniert, wenn Benutzer mit ihm interagieren. In WPF können Sie die Darstellung und das Verhalten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] eines Fensters mithilfe von Code oder Markup implementieren.  
  
 Im Allgemeinen wird jedoch die Darstellung eines [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Fensters mithilfe von Markup implementiert, und sein Verhalten wird mithilfe von CodeBehind implementiert, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Damit eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markupdatei und eine CodeBehind-Datei zusammenarbeiten können, sind Folgendes erforderlich:  
  
- In Markup `Window` muss das `x:Class` Element das Attribut enthalten. Wenn die Anwendung erstellt wird, bewirkt das Vorhandensein in `x:Class` der Markupdatei, dass Microsoft Build engine (MSBuild) eine `partial` Klasse erstellt, die von <xref:System.Windows.Window> dem Attribut ableitet und den Namen hat, der durch das `x:Class` Attribut angegeben wird. Dies erfordert das Hinzufügen einer XML-Namespacedeklaration für das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Die `partial` generierte Klasse `InitializeComponent` implementiert die Methode, die aufgerufen wird, um die Ereignisse zu registrieren und die Eigenschaften festzulegen, die in Markup implementiert werden.  
  
- Im CodeBehind muss die Klasse `partial` eine Klasse mit demselben Namen `x:Class` sein, der durch das Attribut <xref:System.Windows.Window>in Markup angegeben wird, und sie muss von ableiten. Dadurch kann die CodeBehind-Datei der `partial` Klasse zugeordnet werden, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wird (siehe [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)).  
  
- In CodeBehind muss <xref:System.Windows.Window> die Klasse einen Konstruktor `InitializeComponent` implementieren, der die Methode aufruft. `InitializeComponent`wird von der generierten `partial` Klasse der Markupdatei implementiert, um Ereignisse zu registrieren und Eigenschaften festzulegen, die in Markup definiert sind.  
  
> [!NOTE]
> Wenn Sie ihrem <xref:System.Windows.Window> Projekt mithilfe von Visual <xref:System.Windows.Window> Studio ein neues Hinzufügen, wird der sowohl mit Markup als auch mit CodeBehind implementiert und enthält die erforderliche Konfiguration, um die Zuordnung zwischen Markup- und CodeBehind-Dateien zu erstellen, wie hier beschrieben.  
  
 Mit dieser Konfiguration können Sie sich darauf konzentrieren, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] das Erscheinungsbild des Fensters in Markup zu definieren und sein Verhalten im CodeBehind zu implementieren. Das folgende Beispiel zeigt ein Fenster [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mit einer Schaltfläche, die in Markup implementiert ist, und einem Ereignishandler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis der Schaltfläche, das in CodeBehind implementiert ist.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a>Konfigurieren einer Fensterdefinition für MSBuild  
 Wie Sie das Fenster implementieren, bestimmt, wie es für MSBuild konfiguriert ist. Für ein Fenster, das [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sowohl mit Markup als auch codebehind definiert wird:  
  
- XAML-Markupdateien werden als `Page` MSBuild-Elemente konfiguriert.  
  
- CodeBehind-Dateien werden als MSBuild-Elemente `Compile` konfiguriert.  
  
 Dies wird in der folgenden MSBuild-Projektdatei angezeigt.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Informationen zum Erstellen von WPF-Anwendungen finden Sie unter [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a>Fensterlebensdauer  
 Wie alle Klassen hat auch ein Fenster eine Lebensdauer, die mit dem erstmaligen Instanziieren beginnt. Anschließend wird es geöffnet, aktiviert, deaktiviert und schließlich geschlossen.  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a>Öffnen eines Fensters  
 Wenn Sie ein Fenster öffnen möchten, müssen Sie zuerst eine Instanz davon erstellen. Dies wird im folgenden Beispiel veranschaulicht.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In diesem Beispiel `MarkupAndCodeBehindWindow` wird der instanziiert, wenn die <xref:System.Windows.Application.Startup> Anwendung gestartet wird, was auftritt, wenn das Ereignis ausgelöst wird.  
  
 Wenn ein Fenster instanziiert wird, wird automatisch ein Verweis darauf zu einer <xref:System.Windows.Application> Liste <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>von Fenstern hinzugefügt, die vom Objekt verwaltet werden (siehe ). Darüber hinaus wird das erste zu instanziierte Fenster <xref:System.Windows.Application> standardmäßig als Hauptanwendungsfenster <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>festgelegt (siehe ).  
  
 Das Fenster wird schließlich <xref:System.Windows.Window.Show%2A> durch Aufrufen der Methode geöffnet. das Ergebnis wird in der folgenden Abbildung dargestellt.  
  
 ![Ein Fenster, das durch Aufrufen von Window.Show geöffnet wurde](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Ein Fenster, das <xref:System.Windows.Window.Show%2A> durch Aufrufen geöffnet wird, ist ein modusloses Fenster, was bedeutet, dass die Anwendung in einem Modus arbeitet, der es Benutzern ermöglicht, andere Fenster in derselben Anwendung zu aktivieren.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>wird aufgerufen, um Fenster wie Dialogfelder modal zu öffnen. Weitere Informationen finden Sie unter [Dialogfelder Übersicht.](dialog-boxes-overview.md)  
  
 Wenn <xref:System.Windows.Window.Show%2A> aufgerufen wird, führt ein Fenster Initialisierungsarbeiten durch, bevor es gezeigt wird, um eine Infrastruktur einzurichten, die es ihm ermöglicht, Benutzereingaben zu empfangen. Wenn das Fenster initialisiert <xref:System.Windows.Window.SourceInitialized> wird, wird das Ereignis ausgelöst und das Fenster angezeigt.  
  
 Als Verknüpfung <xref:System.Windows.Application.StartupUri%2A> kann so eingestellt werden, dass das erste Fenster angegeben wird, das beim Starten einer Anwendung automatisch geöffnet wird.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Wenn die Anwendung gestartet wird, wird <xref:System.Windows.Application.StartupUri%2A> das durch den Wert von angegebene Fenster moduslos geöffnet. intern wird das Fenster durch <xref:System.Windows.Window.Show%2A> Aufrufen seiner Methode geöffnet.  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a>Besitz von Fenstern  
 Ein Fenster, das mithilfe <xref:System.Windows.Window.Show%2A> der Methode geöffnet wird, hat keine implizite Beziehung zu dem Fenster, das es erstellt hat. Benutzer können unabhängig vom anderen Fenster mit beiden Fenstern interagieren, was bedeutet, dass beide Fenster Folgendes tun können:  
  
- Bedecken Sie das andere Fenster <xref:System.Windows.Window.Topmost%2A> (es `true`sei denn, eines der Fenster hat seine Eigenschaft auf ).  
  
- Es wird minimiert, maximiert und wiederhergestellt, ohne das andere zu beeinflussen.  
  
 Bei einigen Fenstern ist eine Beziehung zu dem Fenster erforderlich, durch das es geöffnet wird. Beispielsweise kann eine IDE-Anwendung (Integrated Development Environment) Eigenschaftenfenster und Toolfenster öffnen, deren typisches Verhalten darin besteht, das Fenster zu bedecken, das sie erstellt. Darüber hinaus sollten solche Fenster stets mit den Fenstern geschlossen, minimiert, maximiert und wiederhergestellt werden, durch die sie erstellt wurden. Eine solche Beziehung kann hergestellt werden, indem ein Fenster <xref:System.Windows.Window.Owner%2A> ein anderes zu *besitzen,* und wird durch Festlegen der Eigenschaft des eigenen *Fensters* mit einem Verweis auf das *Besitzerfenster*erreicht. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Nach Einrichten des Besitzes:  
  
- Das eigene Fenster kann auf sein Besitzerfenster <xref:System.Windows.Window.Owner%2A> verweisen, indem es den Wert seiner Eigenschaft überprüft.  
  
- Das Besitzerfenster kann alle Fenster entdecken, die es <xref:System.Windows.Window.OwnedWindows%2A> besitzt, indem es den Wert seiner Eigenschaft überprüft.  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a>Verhindern der Fensteraktivierung  
 Es gibt Szenarien, in denen Fenster nicht aktiviert werden sollten, wenn sie angezeigt werden, z. B. Unterhaltungsfenster einer Anwendung im Internet-Messenger-Stil oder Benachrichtigungsfenster einer E-Mail-Anwendung.  
  
 Wenn Ihre Anwendung über ein Fenster verfügt, das nicht <xref:System.Windows.Window.ShowActivated%2A> aktiviert `false` werden sollte, wenn es angezeigt wird, können Sie die Eigenschaft auf festlegen, bevor Sie die <xref:System.Windows.Window.Show%2A> Methode zum ersten Mal aufrufen. Daraus folgt:  
  
- Das Fenster wird nicht aktiviert.  
  
- Das Ereignis <xref:System.Windows.Window.Activated> des Fensters wird nicht ausgelöst.  
  
- Das momentan aktivierte Fenster bleibt aktiviert.  
  
 Das Fenster wird jedoch aktiviert, sobald der Benutzer es durch Klicken auf den Client- oder Nicht-Clientbereich aktiviert. In diesem Fall:  
  
- Das Fenster wird aktiviert.  
  
- Das Ereignis <xref:System.Windows.Window.Activated> des Fensters wird ausgelöst.  
  
- Das zuvor aktivierte Fenster wird deaktiviert.  
  
- Die Fenster <xref:System.Windows.Window.Deactivated> und <xref:System.Windows.Window.Activated> Ereignisse werden anschließend wie erwartet als Reaktion auf Benutzeraktionen ausgelöst.  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a>Aktivieren von Fenstern  
 Wenn ein Fenster zum ersten Mal geöffnet wird, wird <xref:System.Windows.Window.ShowActivated%2A> es `false`zum aktiven Fenster (es sei denn, es wird mit gesetzt auf angezeigt). Das *aktive Fenster* ist das Fenster, das derzeit Benutzereingaben erfasst, z. B. Tastenanschläge und Mausklicks. Wenn ein Fenster aktiv wird, löst es das <xref:System.Windows.Window.Activated> Ereignis aus.  
  
> [!NOTE]
> Wenn ein Fenster zum <xref:System.Windows.FrameworkElement.Loaded> ersten <xref:System.Windows.Window.ContentRendered> Mal geöffnet wird, werden die und-Ereignisse erst ausgelöst, nachdem das <xref:System.Windows.Window.Activated> Ereignis ausgelöst wurde. Vor diesem Hintergrund kann ein Fenster effektiv <xref:System.Windows.Window.ContentRendered> als geöffnet betrachtet werden, wenn es angehoben wird.  
  
 Nachdem ein Fenster aktiv geworden ist, kann ein Benutzer ein weiteres Fenster in derselben Anwendung oder eine andere Anwendung aktivieren. In diesem Fall wird das aktuell aktive <xref:System.Windows.Window.Deactivated> Fenster deaktiviert und löst das Ereignis aus. Wenn der Benutzer ein derzeit deaktiviertes Fenster auswählt, <xref:System.Windows.Window.Activated> wird das Fenster ebenfalls wieder aktiv und ausgelöst.  
  
 Ein häufiger Grund <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> für die Handhabung und Funktion zum Aktivieren und Deaktivieren von Funktionen, die nur ausgeführt werden können, wenn ein Fenster aktiv ist. In einigen Fenstern wird beispielsweise interaktiver Inhalt angezeigt, der andauernde Benutzereingaben oder Aufmerksamkeit erfordert, wie beispielsweise Spiele und Videoplayer. Das folgende Beispiel ist ein vereinfachter <xref:System.Windows.Window.Activated> Videoplayer, der veranschaulicht, wie dieses Verhalten behandelt und <xref:System.Windows.Window.Deactivated> implementiert wird.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Andere Anwendungstypen führen im Hintergrund möglicherweise weiterhin Code aus, nachdem ein Fenster deaktiviert wurde. Ein E-Mail-Client kann z. B. weiterhin den E-Mail-Server abrufen, während der Benutzer andere Anwendungen verwendet. Während das Hauptfenster deaktiviert ist, stellen derartige Anwendungen häufig zusätzliches oder anderes Verhalten zur Verfügung. Im Hinblick auf das E-Mail-Programm kann das sowohl das Hinzufügen des neuen E-Mail-Elements zum Posteingang als auch eines Benachrichtigungssymbol in die Taskleiste bedeuten. Ein Benachrichtigungssymbol muss nur angezeigt werden, wenn das E-Mail-Fenster <xref:System.Windows.Window.IsActive%2A> nicht aktiv ist, was durch Überprüfen der Eigenschaft ermittelt werden kann.  
  
 Wenn eine Hintergrundaufgabe abgeschlossen ist, kann ein Fenster den <xref:System.Windows.Window.Activate%2A> Benutzer durch Aufrufen der Methode dringender benachrichtigen. Wenn der Benutzer mit einer anderen <xref:System.Windows.Window.Activate%2A> Anwendung interagiert, die beim Aufruf aktiviert wird, blinkt die Taskleistenschaltfläche des Fensters. Wenn ein Benutzer mit der aktuellen <xref:System.Windows.Window.Activate%2A> Anwendung interagiert, wird das Fenster durch den Aufruf in den Vordergrund gerückt.  
  
> [!NOTE]
> Sie können die Aktivierung des <xref:System.Windows.Application.Activated?displayProperty=nameWithType> <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> Anwendungsbereichs mithilfe der und-Ereignisse verarbeiten.  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a>Schließen eines Fensters  
 Die Lebensdauer eines Fensters endet, wenn der Benutzer das Fenster schließt. Ein Fenster kann mithilfe der Elemente im Nicht-Clientbereich geschlossen werden, z. B. mit den folgenden:  
  
- Das **Element Schließen** des **Menüs System.**  
  
- Drücken von ALT+F4.  
  
- Drücken Sie die **Schaltfläche Schließen.**  
  
 Zum Schließen eines Fensters können Sie dem Clientbereich weitere Mechanismen hinzufügen. Zu den gebräuchlichsten zählen:  
  
- Ein **Exit-Element** im **Menü Datei,** in der Regel für Hauptanwendungsfenster.  
  
- Ein **Schließenelement** im Menü **Datei,** in der Regel in einem sekundären Anwendungsfenster.  
  
- Eine **Schaltfläche Abbrechen,** in der Regel in einem modalen Dialogfeld.  
  
- Eine **Schaltfläche Schließen,** in der Regel in einem moduslosen Dialogfeld.  
  
 Um ein Fenster als Reaktion auf einen dieser benutzerdefinierten <xref:System.Windows.Window.Close%2A> Mechanismen zu schließen, müssen Sie die Methode aufrufen. Im folgenden Beispiel wird die Möglichkeit implementiert, ein Fenster zu schließen, indem Sie im Menü **Datei** das Menü **Beenden** auswählen.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Wenn ein Fenster geschlossen wird, <xref:System.Windows.Window.Closing> werden <xref:System.Windows.Window.Closed>zwei Ereignisse angezeigt: und .  
  
 <xref:System.Windows.Window.Closing>wird angehoben, bevor das Fenster geschlossen wird, und bietet einen Mechanismus, durch den fensterschließen verhindert werden kann. Der häufigste Grund, um das Schließen eines Fensters zu verhindern, liegt darin, dass Fensterinhalt geänderte Daten enthält. In diesem Fall <xref:System.Windows.Window.Closing> kann das Ereignis behandelt werden, um zu bestimmen, ob Daten verschmutzt sind, und wenn ja, den Benutzer zu fragen, ob er das Fenster entweder weiterhin schließen soll, ohne die Daten zu speichern, oder ob er den Fensterabschluss abgebrochen hat. Das folgende Beispiel zeigt die <xref:System.Windows.Window.Closing>wichtigsten Aspekte der Handhabung .  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Dem <xref:System.Windows.Window.Closing> Ereignishandler wird <xref:System.ComponentModel.CancelEventArgs>eine übergeben, `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> die die `true` Eigenschaft implementiert, auf die Sie festgelegt haben, um zu verhindern, dass ein Fenster geschlossen wird.  
  
 Wenn <xref:System.Windows.Window.Closing> das Fenster nicht behandelt oder behandelt, aber nicht abgebrochen wird, wird das Fenster geschlossen. Kurz bevor sich ein <xref:System.Windows.Window.Closed> Fenster tatsächlich schließt, wird erhöht. An dieser Stelle kann das Schließen des Fensters nicht verhindert werden.  
  
> [!NOTE]
> Eine Anwendung kann so konfiguriert werden, dass sie automatisch heruntergefahren wird, wenn entweder das Hauptanwendungsfenster geschlossen wird (siehe <xref:System.Windows.Application.MainWindow%2A>) oder das letzte Fenster geschlossen wird. Einzelheiten dazu finden Sie unter <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Während ein Fenster durch Mechanismen, die im Nicht-Client- und Clientbereich bereitgestellt werden, explizit geschlossen werden kann, kann ein Fenster auch implizit aufgrund von Verhalten in anderen Teilen der Anwendung oder von Windows geschlossen werden, einschließlich der folgenden:  
  
- Ein Benutzer meldet sich ab oder fährt Windows herunter.  
  
- Der Besitzer eines Fensters <xref:System.Windows.Window.Owner%2A>wird geschlossen (siehe ).  
  
- Das Hauptanwendungsfenster ist <xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnMainWindowClose>geschlossen und ist .  
  
- <xref:System.Windows.Application.Shutdown%2A> wird aufgerufen.  
  
> [!NOTE]
> Ein Fenster kann nicht erneut geöffnet werden, nachdem es geschlossen wurde.  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a>Ereignisse in der Lebensdauer eines Fensters  
 Die folgende Abbildung zeigt die Reihenfolge der Hauptereignisse während der Lebensdauer eines Fensters:  
  
 ![Diagramm, das Ereignisse in der Lebensdauer eines Fensters anzeigt.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 Die folgende Abbildung zeigt die Reihenfolge der Hauptereignisse während der Lebensdauer<xref:System.Windows.Window.ShowActivated%2A> eines `false` Fensters, das ohne Aktivierung angezeigt wird (wird vor dem Angezeigt des Fensters festgelegt):  
  
 ![Diagramm, das Ereignisse in der Lebensdauer eines Fensters ohne Aktivierung anzeigt.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a>Fensterposition  
 Solange ein Fenster geöffnet ist, befindet sich dessen Position in der x- und y-Dimension relativ zum Desktop. Diese Position kann durch Überprüfung <xref:System.Windows.Window.Left%2A> <xref:System.Windows.Window.Top%2A> der bzw. Eigenschaften bestimmt werden. Sie können diese Eigenschaften festlegen, um die Position des Fensters zu ändern.  
  
 Sie können auch die Anfangsposition eines <xref:System.Windows.Window> angeben, <xref:System.Windows.Window.WindowStartupLocation%2A> wenn sie zum <xref:System.Windows.WindowStartupLocation> ersten Mal angezeigt wird, indem Sie die Eigenschaft mit einem der folgenden Enumerationswerte festlegen:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (Standard)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Wenn der Startspeicherort <xref:System.Windows.WindowStartupLocation.Manual>als angegeben <xref:System.Windows.Window.Left%2A> <xref:System.Windows.Window.Top%2A> ist und die <xref:System.Windows.Window> und die Eigenschaften nicht festgelegt wurden, wird Windows aufgefordert, einen Speicherort anzuzeigen.  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a>Oberstes Fenster und Z-Reihenfolge  
 Neben der X- und Y-Position verfügt das Fenster auch über eine Position in der Z-Dimension, die dessen vertikale Position im Verhältnis zu anderen Fenstern bestimmt. Dies wird als Z-Reihenfolge des Fensters bezeichnet. Davon gibt es zwei Typen: die normale Z-Reihenfolge und die oberste Z-Reihenfolge. Die Position eines Fensters in der *normalen Z-Reihenfolge* wird davon bestimmt, ob es aktuell aktiv ist oder nicht. Standardmäßig befindet sich ein Fenster in der normalen Z-Reihenfolge. Die Position eines Fensters in der *obersten Z-Reihenfolge* wird auch davon bestimmt, ob es derzeit aktiv ist oder nicht. Darüber hinaus befinden sich Fenster in der obersten Z-Reihenfolge stets über den Fenstern in der normalen Z-Reihenfolge. Ein Fenster befindet sich in der obersten <xref:System.Windows.Window.Topmost%2A> Z-Reihenfolge, indem es seine Eigenschaft auf `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 Innerhalb jeder Z-Reihenfolge wird das aktuell aktive Fenster über allen anderen Fenstern derselben Z-Reihenfolge angezeigt.  
  
<a name="WindowSize"></a>
## <a name="window-size"></a>Fenstergröße  
 Neben einer Desktop-Position hat ein Fenster eine Größe, die durch mehrere Eigenschaften <xref:System.Windows.Window.SizeToContent%2A>bestimmt wird, einschließlich der verschiedenen Breiten- und Höheneigenschaften und .  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>und <xref:System.Windows.FrameworkElement.MaxWidth%2A> werden verwendet, um den Breitenbereich zu verwalten, den ein Fenster während seiner Lebensdauer haben kann, und werden wie im folgenden Beispiel gezeigt konfiguriert.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Die Fensterhöhe <xref:System.Windows.FrameworkElement.MinHeight%2A>wird <xref:System.Windows.FrameworkElement.Height%2A>von <xref:System.Windows.FrameworkElement.MaxHeight%2A>verwaltet , und , und sie werden wie im folgenden Beispiel gezeigt konfiguriert.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Da die verschiedenen Werte für die Breite und für die Höhe jeweils einen Bereich angeben, kann die Breite und Höhe eines in der Größe veränderbaren Fensters irgendwo innerhalb des angegebenen Bereichs für die entsprechende Dimension liegen. Um die aktuelle Breite und <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A>Höhe zu erkennen, überprüfen bzw. .  
  
 Wenn die Breite und Höhe des Fensters eine Größe aufweisen soll, die an die Größe <xref:System.Windows.Window.SizeToContent%2A> des Fensterinhalts anpasst, können Sie die Eigenschaft verwenden, die die folgenden Werte aufweist:  
  
- <xref:System.Windows.SizeToContent.Manual>. Keine Auswirkung (Standard).  
  
- <xref:System.Windows.SizeToContent.Width>. Passen Sie an die Inhaltsbreite an, <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> die den gleichen Effekt hat wie das Festlegen sowohl als auch auf die Breite des Inhalts.  
  
- <xref:System.Windows.SizeToContent.Height>. Passen Sie an die Inhaltshöhe an, <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> die den gleichen Effekt hat wie das Festlegen sowohl als auch auf die Höhe des Inhalts.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Passen Sie an die Inhaltsbreite und -höhe <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> an, die den gleichen Effekt <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> wie das Festlegen sowohl als auch auf die Höhe des Inhalts und das Festlegen sowohl und auf die Breite des Inhalts hat.  
  
 Im folgenden Beispiel wird ein Fenster dass die Größe automatisch an seinen Inhalt vertikal und horizontal an, wenn es zuerst angezeigt wird.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Window.SizeToContent%2A> wie die Eigenschaft im Code festgelegt wird, um anzugeben, wie die Größe eines Fensters an den Inhalt angepasst wird.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a>Rangfolge der Größeneigenschaften  
 Im Wesentlichen werden die verschiedenen Größeneigenschaften eines Fensters kombiniert, um den Bereich der Breite und der Höhe für ein in der Größe veränderbares Fenster zu definieren. Um sicherzustellen, dass ein <xref:System.Windows.Window> gültiger Bereich beibehalten wird, werden die Werte der Größeneigenschaften anhand der folgenden Rangfolge ausgewertet.  
  
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
  
 Die Rangfolge kann auch die Größe eines Fensters bestimmen, wenn <xref:System.Windows.Window.WindowState%2A> es maximiert wird, das mit der Eigenschaft verwaltet wird.  
  
<a name="WindowState"></a>
## <a name="window-state"></a>Fensterzustand  
 Während der Lebensdauer eines in der Größe veränderbaren Fenster kann dieses über drei Zustände verfügen: normal, minimiert und maximiert. Ein Fenster mit einem *normalen* Zustand ist der Standardstatus eines Fensters. Ein Benutzer kann ein Fenster mit diesem Zustand verschieben und dessen Größe ändern, indem er den Ziehpunkt zur Größenänderung oder den Rahmen verwendet, sofern er in der Größe veränderbar ist.  
  
 Ein Fenster mit einem *minimierten* Zustand reduziert <xref:System.Windows.Window.ShowInTaskbar%2A> sich auf `true`seine Taskleistenschaltfläche, wenn auf festgelegt ist. Andernfalls bricht es auf die kleinstmögliche Größe zurück, die es sein kann, und verschiebt sich selbst in die untere linke Ecke des Desktops. Keiner der minimierten Fenstertypen kann mithilfe des Ziehpunkts zur Größenreduzierung oder mit dem Rahmen in der Größe verändert werden. Allerdings kann ein minimiertes Fenster, das nicht in der Taskleiste angezeigt wird, auf dem Desktop hin und her verschoben werden.  
  
 Ein Fenster mit einem *maximierten* Zustand wird auf die maximale Größe erweitert, <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>die <xref:System.Windows.Window.SizeToContent%2A> es sein kann, die nur so groß ist, wie es , und Eigenschaften diktieren. Wie ein minimiertes Fenster kann auch ein maximiertes Fenster nicht mithilfe des Ziehpunkts zur Größenänderung oder durch Ziehen des Rahmens in seiner Größe verändert werden.  
  
> [!NOTE]
> Die Werte <xref:System.Windows.Window.Top%2A>von <xref:System.Windows.Window.Left%2A> <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> , und die Eigenschaften eines Fensters stellen immer die Werte für den Normalzustand dar, auch wenn das Fenster derzeit maximiert oder minimiert ist.  
  
 Der Status eines Fensters kann durch <xref:System.Windows.Window.WindowState%2A> Festlegen seiner Eigenschaft konfiguriert <xref:System.Windows.WindowState> werden, die einen der folgenden Enumerationswerte aufweisen kann:  
  
- <xref:System.Windows.WindowState.Normal> (Standard)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie ein Fenster erstellen, das beim Öffnen als maximiert angezeigt wird.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 Im Allgemeinen sollten <xref:System.Windows.Window.WindowState%2A> Sie festlegen, dass der Anfangszustand eines Fensters konfiguriert wird. Wenn ein in der Größe veränderbares Fenster angezeigt wird, können die Benutzer die Schaltflächen zum Minimieren, Maximieren oder Wiederherstellen auf der Titelleiste des Fensters aktivieren, um den Fensterzustand zu ändern.  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a>Fensterdarstellung  
 Sie ändern die Darstellung des Clientbereichs eines Fensters, indem Sie fensterspezifischen Inhalt hinzufügen, z. B. Schaltflächen, Bezeichnungen und Textfelder. Zum Konfigurieren des Nicht-Client-Bereichs <xref:System.Windows.Window> werden <xref:System.Windows.Window.Icon%2A> mehrere Eigenschaften angezeigt, die <xref:System.Windows.Window.Title%2A> zum Festlegen des Fenstersymbols und zum Festlegen des Titels gehören.  
  
 Außerdem können Sie die Darstellung und das Verhalten des Rahmens im Nicht-Clientbereich ändern, indem Sie den Größenänderungsmodus, den Fensterstil und die Tatsache konfigurieren, ob es als Schaltfläche in der Desktoptaskleiste angezeigt wird.  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a>Größenänderungsmodus  
 Abhängig von <xref:System.Windows.Window.WindowStyle%2A> der Eigenschaft können Sie steuern, wie (und wenn) Benutzer die Größe des Fensters ändern können. Die Auswahl des Fensterstils wirkt sich darauf aus, ob ein Benutzer die Größe des Fensters ändern kann, indem er den Rahmen mit der Maus zieht, ob die **Schaltflächen Minimieren**, **Maximieren**und **Größe** im Nicht-Clientbereich angezeigt werden und, falls er angezeigt wird, ob sie aktiviert sind.  
  
 Sie können konfigurieren, wie die <xref:System.Windows.Window.ResizeMode%2A> Größe eines Fensters geändert <xref:System.Windows.ResizeMode> wird, indem Sie seine Eigenschaft festlegen, die einer der folgenden Enumerationswerte sein kann:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (Standard)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Wie <xref:System.Windows.Window.WindowStyle%2A>bei wird sich der Größenänderungsmodus eines Fensters während seiner Lebensdauer wahrscheinlich nicht [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ändern, was bedeutet, dass Sie es höchstwahrscheinlich aus Markup festlegen.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Beachten Sie, dass Sie erkennen können, ob ein Fenster maximiert, minimiert oder wiederhergestellt wird, indem Sie die <xref:System.Windows.Window.WindowState%2A> Eigenschaft überprüfen.  
  
<a name="Window_Style"></a>
### <a name="window-style"></a>Fensterstil  
 Der Rahmen, der vom Nicht-Clientbereich eines Fensters verfügbar gemacht wird, eignet sich für die meisten Anwendungen. Unter bestimmten Umständen werden je nach Fenstertyp dennoch andere Rahmentypen oder überhaupt keine Rahmen benötigt.  
  
 Um zu steuern, welchen Rahmentyp ein <xref:System.Windows.Window.WindowStyle%2A> Fenster erhält, legen Sie <xref:System.Windows.WindowStyle> seine Eigenschaft mit einem der folgenden Werte der Enumeration fest:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (Standard)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Die Auswirkungen dieser Fensterstile werden in der folgenden Abbildung dargestellt:  
  
 ![Abbildung von Fensterrahmenstilen.](./media/wpf-windows-overview/window-border-styles.png)  
  
 Sie können <xref:System.Windows.Window.WindowStyle%2A> entweder [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup oder Code festlegen. Da sich während der Lebensdauer eines Fensters wahrscheinlich nicht geändert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird, konfigurieren Sie es höchstwahrscheinlich mithilfe von Markup.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Nicht rechteckiger Fensterstil  
 Es gibt auch Situationen, <xref:System.Windows.Window.WindowStyle%2A> in denen die Rahmenstile, die Sie haben können, nicht ausreichen. Sie können z. B. eine Anwendung mit einem nicht rechteckigen Rahmen erstellen, wie microsoft Windows Media Player verwendet.  
  
 Betrachten Sie beispielsweise das in der folgenden Abbildung gezeigte Sprechblasenfenster:  
  
 ![Ein Sprechblasenfenster, das Drag Me sagt.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Dieser Fenstertyp kann erstellt werden, indem die <xref:System.Windows.Window.WindowStyle%2A> Eigenschaft auf <xref:System.Windows.WindowStyle.None>, und durch spezielle Unterstützung <xref:System.Windows.Window> für Transparenz erstellt werden.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Durch diese Kombination von Werten wird das Fenster angewiesen, ein vollkommen transparentes Rendering zu übernehmen. In diesem Zustand können die Zusatzelemente des Nicht-Clientbereichs des Fensters (das Menü „Schließen“, die Schaltflächen „Minimieren“, „Maximieren“ und „Wiederherstellen“ usw.) nicht verwendet werden. Folglich müssen Sie Ihre eigenen bereitstellen.  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a>Vorhandensein der Taskleiste  

Die Standarddarstellung eines Fensters enthält eine Taskleistenschaltfläche, wie in der folgenden Abbildung dargestellt:

 ![Screenshot, der ein Fenster mit einer Taskleistenschaltfläche anzeigt.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Einige Fenstertypen verfügen nicht über eine Taskleistenschaltfläche, z. B. Meldungsfelder und Dialogfelder (siehe [Dialogfelder Übersicht](dialog-boxes-overview.md)). Sie können steuern, ob die Taskleistenschaltfläche für <xref:System.Windows.Window.ShowInTaskbar%2A> ein`true` Fenster angezeigt wird, indem Sie die Eigenschaft festlegen (standardmäßig).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a>Überlegungen zur Sicherheit  
 <xref:System.Windows.Window>erfordert, `UnmanagedCode` dass die Sicherheitsberechtigung instanziiert wird. Bei Anwendungen, die auf dem lokalen Computer installiert und gestartet werden, wird dies durch die Berechtigungen abgedeckt, die der Anwendung gewährt werden.  
  
 Dies liegt jedoch außerhalb des Satzes von Berechtigungen, die Anwendungen gewährt werden, die aus der Internet- oder lokalen Intranetzone mit ClickOnce gestartet werden. Daher erhalten Benutzer eine ClickOnce-Sicherheitswarnung und müssen den Berechtigungssatz für die Anwendung auf volle Vertrauenswürdigkeit erhöhen.  
  
 Darüber hinaus können XBAPs standardmäßig keine Fenster oder Dialogfelder anzeigen. Eine Diskussion zu Überlegungen zur Sicherheit von eigenständigen Anwendungen finden Sie unter [WPF-Sicherheitsstrategie - Plattformsicherheit](../wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a>Andere Fenstertypen  
 <xref:System.Windows.Navigation.NavigationWindow>ist ein Fenster, das zum Hosten navigierbarer Inhalte entwickelt wurde. Weitere Informationen finden Sie unter [Navigationsübersicht](navigation-overview.md)).  
  
 Dialogfelder sind Fenster, die häufig zum Erfassen von Benutzerinformationen verwendet werden, um eine Funktion ausführen. Wenn ein Benutzer beispielsweise eine Datei öffnen möchte, wird das Dialogfeld **Datei** öffnen normalerweise von einer Anwendung angezeigt, um den Dateinamen vom Benutzer abzurufen. Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Übersicht über Dialogfelder](dialog-boxes-overview.md)
- [Erstellen einer WPF-Anwendung](building-a-wpf-application-wpf.md)
