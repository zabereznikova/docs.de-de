---
title: "Übersicht über WPF-Fenster"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "65"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3323efa3306fd55d7c1d43cbc6eeaaf846e373ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-windows-overview"></a>Übersicht über WPF-Fenster
Benutzer interagieren über Fenster mit eigenständigen [!INCLUDE[TLA#tla_wpf](./../../../includes/tlasharptla-wpf-md.md)]-Anwendungen. Die Hauptaufgabe eines Fensters besteht darin, Inhalt zu hosten, der Daten visuell darstellen kann und Benutzern die Interaktion mit Daten ermöglicht. Eigenständige [!INCLUDE[TLA2#tla_wpf](./../../../includes/tla2sharptla-wpf-md.md)] Anwendungen ihre eigenen Windows bereitstellen, indem Sie mit der <xref:System.Windows.Window> Klasse. Dieses Thema enthält <xref:System.Windows.Window> vor die Grundlagen zum Erstellen und Verwalten von Windows in eigenständigen Anwendungen abdecken.  
  
> [!NOTE]
>  Im Browser gehostete [!INCLUDE[TLA2#tla_wpf](./../../../includes/tla2sharptla-wpf-md.md)] Anwendungen, einschließlich [!INCLUDE[TLA#tla_xbap#plural](./../../../includes/tlasharptla-xbapsharpplural-md.md)] und Netzkabel ordnungsgemäß angeschlossen sind [!INCLUDE[TLA#tla_xaml](./../../../includes/tlasharptla-xaml-md.md)] Seiten, nicht ihre eigenen Windows bereitgestellt. Stattdessen werden sie in Windows gebotenen gehostet [!INCLUDE[TLA#tla_iegeneric](./../../../includes/tlasharptla-iegeneric-md.md)]. Finden Sie unter [Übersicht über WPF-XAML-Browseranwendungen](./../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
  
<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Die Fensterklasse  
 In der folgenden Abbildung werden die Bestandteile eines Fensters dargestellt.  
  
 ![Fensterelemente](./../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Ein Fenster wird in zwei Bereiche geteilt: der Nicht-Clientbereich und der Clientbereich.  
  
 Die *nicht-Clientbereichs* eines Fensters wird dadurch implementiert, [!INCLUDE[TLA2#tla_wpf](./../../../includes/tla2sharptla-wpf-md.md)] und enthält die Teile eines Fensters, die für die meisten Fenster, einschließlich der folgenden gelten:  
  
-   Rahmen  
  
-   Titelleiste  
  
-   Symbol  
  
-   Schaltflächen zum Minimieren, Maximieren und Wiederherstellen  
  
-   Schaltfläche Schließen  
  
-   Ein Systemmenü mit Menüelementen, mit denen Benutzer ein Fenster minimieren, maximieren, wiederherstellen, verschieben, schließen und dessen Größe ändern können.  
  
 Die *Clientbereich* eines Fensters wird der nicht-Clientbereich eines Fensters und wird von Entwicklern verwendet, um anwendungsspezifische Inhalte wie Menüs, Symbolleisten und Steuerelemente hinzufügen.  
  
 In [!INCLUDE[TLA2#tla_wpf](./../../../includes/tla2sharptla-wpf-md.md)], ein Fenster gekapselt, durch die <xref:System.Windows.Window> -Klasse, die Sie verwenden, um die folgenden Aktionen ausführen:  
  
-   Anzeigen eines Fensters  
  
-   Konfigurieren der Größe, Position und Darstellung eines Fensters  
  
-   Hosten von anwendungsspezifischem Inhalt  
  
-   Verwalten der Lebensdauer eines Fensters  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Implementieren eines Fensters  
 Die Implementierung eines typischen Fensters umfasst, Darstellung und Verhalten, in denen *Darstellung* definiert, wie ein Fenster Benutzern aussieht und *Verhalten* bestimmt, wie ein Fenster zu Funktionen, wie Benutzer interagieren mit ihm. In [!INCLUDE[TLA2#tla_wpf](./../../../includes/tla2sharptla-wpf-md.md)], können Sie implementieren, die Darstellung und Verhalten eines Fensters entweder mit code oder [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 Im Allgemeinen jedoch die Darstellung eines Fensters wird mithilfe von implementiert [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup und sein Verhalten ist implementiert mit Code-Behind, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 So aktivieren Sie eine [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup und CodeBehind-Datei zusammenarbeiten sind Folgendes erforderlich:  
  
-   Im Markup der `Window` -Element muss enthalten die `x:Class` Attribut. Als die Anwendung erstellt wird, wird das Vorhandensein des `x:Class` im Markup Datei bewirkt, dass [!INCLUDE[TLA#tla_msbuild](./../../../includes/tlasharptla-msbuild-md.md)] zum Erstellen einer `partial` von abgeleitete Klasse <xref:System.Windows.Window> und hat den Namen, die von angegeben wird die `x:Class` Attribut. Dies erfordert das Hinzufügen einer [!INCLUDE[TLA2#tla_xml](./../../../includes/tla2sharptla-xml-md.md)] Namespacedeklaration für das [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Die generierte `partial` -Klasse implementiert die `InitializeComponent` -Methode, die aufgerufen wird, um die Ereignisse zu registrieren, und legen Sie die Eigenschaften, die im Markup implementiert werden.  
  
-   In der CodeBehind-Klasse muss eine `partial` Klasse mit dem gleichen Namen, die von angegeben wird die `x:Class` Attribut in Markup aus, und leiten sich aus <xref:System.Windows.Window>. Dadurch wird der Code-Behind-Datei zugeordnet werden die `partial` -Klasse, die für die Markupdatei generiert wird, wenn die Anwendung erstellt wurde (finden Sie unter [Erstellen einer WPF-Anwendung](./../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   Im Code-Behind die <xref:System.Windows.Window> Klasse muss einen Konstruktor, der Aufrufe implementieren die `InitializeComponent` Methode. `InitializeComponent`wird implementiert von Markup generierte `partial` Klasse, um Ereignisse zu registrieren, und legen Sie Eigenschaften, die im Markup definiert sind.  
  
> [!NOTE]
>  Beim Hinzufügen einer neuen <xref:System.Windows.Window> zu Ihrem Projekt mithilfe von [!INCLUDE[TLA#tla_visualstu](./../../../includes/tlasharptla-visualstu-md.md)], die <xref:System.Windows.Window> wird mithilfe von Markup und CodeBehind implementiert sind, sowie die erforderliche Konfiguration zum Erstellen der Zuordnung zwischen dem Markup und Code-Behind-Dateien als Die hier beschriebenen.  
  
 Mit dieser Konfiguration vorhanden, Sie können den Fokus auf definieren die Darstellung des Fensters in [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup und dessen Verhalten zu implementieren, im Code-Behind. Das folgende Beispiel zeigt ein Fenster mit einer Schaltfläche, implementiert [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup und einen Ereignishandler für der Schaltfläche <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis im Code-Behind implementiert.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Konfigurieren einer Fensterdefinition für MSBuild  
 Bestimmt, wie Sie das Fenster implementieren Konfiguration für [!INCLUDE[TLA2#tla_msbuild](./../../../includes/tla2sharptla-msbuild-md.md)]. Für ein Fenster, das definiert ist, verwenden beide [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup und CodeBehind:  
  
-   [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)]Markupdateien werden als konfiguriert [!INCLUDE[TLA2#tla_msbuild](./../../../includes/tla2sharptla-msbuild-md.md)] `Page` Elemente.  
  
-   Code-Behind-Dateien werden als konfiguriert [!INCLUDE[TLA2#tla_msbuild](./../../../includes/tla2sharptla-msbuild-md.md)] `Compile` Elemente.  
  
 Dies wird im folgenden gezeigt [!INCLUDE[TLA2#tla_msbuild](./../../../includes/tla2sharptla-msbuild-md.md)] Projektdatei.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Informationen zum Erstellen von [!INCLUDE[TLA2#tla_wpf](./../../../includes/tla2sharptla-wpf-md.md)] -Anwendungen finden Sie unter [Erstellen einer WPF-Anwendung](./../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Fensterlebensdauer  
 Wie alle Klassen hat auch ein Fenster eine Lebensdauer, die mit dem erstmaligen Instanziieren beginnt. Anschließend wird es geöffnet, aktiviert, deaktiviert und schließlich geschlossen.  
  
  
<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Öffnen eines Fensters  
 Wenn Sie ein Fenster öffnen möchten, müssen Sie zuerst eine Instanz davon erstellen. Dies wird im folgenden Beispiel veranschaulicht.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 In diesem Beispiel wird die `MarkupAndCodeBehindWindow` wird instanziiert, wenn die Anwendung gestartet wird, Dies tritt ein, wenn die <xref:System.Windows.Application.Startup> Ereignis wird ausgelöst.  
  
 Bei der Instanziierung ein Fensters verwendet wird, wird ein Verweis darauf automatisch eine Liste von Fenstern, die von verwalteten hinzugefügt der <xref:System.Windows.Application> Objekt (siehe <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Darüber hinaus wird das erste Fenster instanziiert werden standardmäßig durch festgelegt <xref:System.Windows.Application> als das Hauptanwendungsfenster (siehe <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 Öffnen des Fensters schließlich durch Aufrufen der <xref:System.Windows.Window.Show%2A> Methode wird das Ergebnis in der folgenden Abbildung dargestellt.  
  
 ![Ein durch Aufrufen von Show geöffnetes Fenster](./../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Ein Fenster, das durch Aufrufen von <xref:System.Windows.Window.Show%2A> ist ein nicht modales Fenster, was bedeutet, dass die Anwendung in einem Modus ausgeführt, die Benutzern ermöglicht wird, die andere Fenster in derselben Anwendung zu aktivieren.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A>wird aufgerufen, um Windows, z. B. Dialogfelder modal zu öffnen. Finden Sie unter [Dialog Boxes Overview](./../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) für Weitere Informationen.  
  
 Wenn <xref:System.Windows.Window.Show%2A> ist führt Initialisierungsarbeit aufgerufen wird, ein Fenster werden, bevor es angezeigt wird, um die Infrastruktur festzulegen, die eine Benutzereingabe empfangen kann. Wenn das Fenster initialisiert wird, die <xref:System.Windows.Window.SourceInitialized> Ereignis wird ausgelöst, und das Fenster wird angezeigt.  
  
 Als Tastenkombination können <xref:System.Windows.Application.StartupUri%2A> kann festgelegt werden, an das erste Fenster, die automatisch geöffnet wird, wenn eine Anwendung gestartet wird.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Beim Starten der Anwendung, durch den Wert des angegebenen Fensters <xref:System.Windows.Application.StartupUri%2A> geöffnet wird nicht modalen Modus; intern Öffnen des Fensters durch Aufrufen seiner <xref:System.Windows.Window.Show%2A> Methode.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Besitz von Fenstern  
 Ein Fenster, das geöffnet wurde die <xref:System.Windows.Window.Show%2A> Methode verfügt nicht über eine implizite Beziehung zu dem Fenster, das sie erstellt; Benutzerinteraktion mit den beiden Fenstern unabhängig voneinander, d. h. entweder Fenster die folgenden Aktionen ausführen kann:  
  
-   Abdecken, die andere (es sei denn, eines der Fenster seine <xref:System.Windows.Window.Topmost%2A> -Eigenschaftensatz auf `true`).  
  
-   Es wird minimiert, maximiert und wiederhergestellt, ohne das andere zu beeinflussen.  
  
 Bei einigen Fenstern ist eine Beziehung zu dem Fenster erforderlich, durch das es geöffnet wird. Angenommen, ein [!INCLUDE[TLA#tla_ide](./../../../includes/tlasharptla-ide-md.md)] Anwendung möglicherweise öffnen, Eigenschaft und Toolfenster, deren typische Verhalten besteht darin, das Fenster zu behandeln, die sie erstellt. Darüber hinaus sollten solche Fenster stets mit den Fenstern geschlossen, minimiert, maximiert und wiederhergestellt werden, durch die sie erstellt wurden. Eine solche Beziehung hergestellt werden kann, indem Sie die Verfügbarkeit von einem Fenster *eigenen* einer anderen, und erreicht, indem die <xref:System.Windows.Window.Owner%2A> Eigenschaft von der *Fenster gehören* mit einem Verweis auf die *Besitzer Fenster*. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 Nach Einrichten des Besitzes:  
  
-   Das zugehörige Fenster kann Besitzerfensters durch überprüfen den Wert der verweisen die <xref:System.Windows.Window.Owner%2A> Eigenschaft.  
  
-   Das besitzende Fenster erkennen alle Fenster, die er besitzt, durch den Wert der Überprüfen seiner <xref:System.Windows.Window.OwnedWindows%2A> Eigenschaft.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Verhindern der Fensteraktivierung  
 Es gibt Szenarien, in denen angezeigte Fenster nicht aktiviert werden sollten, z. B. Unterhaltungsfenster einer Internet-Messenger-Anwendung oder Benachrichtigungsfenster einer E-Mail-Anwendung.  
  
 Wenn die Anwendung ein Fenster verfügt, die nicht aktiviert werden sollte, wenn Sie angezeigt wird, legen Sie seine <xref:System.Windows.Window.ShowActivated%2A> Eigenschaft, um `false` vor dem Aufruf der <xref:System.Windows.Window.Show%2A> Methode zum ersten Mal. Daraus folgt:  
  
-   Das Fenster wird nicht aktiviert.  
  
-   Des Fensters <xref:System.Windows.Window.Activated> Ereignis wird nicht ausgelöst.  
  
-   Das momentan aktivierte Fenster bleibt aktiviert.  
  
 Das Fenster wird jedoch aktiviert, sobald der Benutzer es durch Klicken auf den Client- oder Nicht-Clientbereich aktiviert. In diesem Fall gilt Folgendes:  
  
-   Das Fenster wird aktiviert.  
  
-   Des Fensters <xref:System.Windows.Window.Activated> Ereignis wird ausgelöst.  
  
-   Das zuvor aktivierte Fenster wird deaktiviert.  
  
-   Des Fensters <xref:System.Windows.Window.Deactivated> und <xref:System.Windows.Window.Activated> Ereignisse werden anschließend als Reaktion auf Benutzeraktionen wie erwartet ausgelöst.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Aktivieren von Fenstern  
 Wenn ein Fenster erstmalig geöffnet wird, wird das aktive Fenster (es sei denn, dies mit dargestellt ist <xref:System.Windows.Window.ShowActivated%2A> festgelegt `false`). Die *aktive Fenster* ist das Fenster, das derzeit von Benutzereingaben, z. B. Tastenanschläge und Mausklicks erfasst. Wenn ein Fenster aktiv wird, löst die <xref:System.Windows.Window.Activated> Ereignis.  
  
> [!NOTE]
>  Wenn ein Fenster erstmalig geöffnet wird, die <xref:System.Windows.FrameworkElement.Loaded> und <xref:System.Windows.Window.ContentRendered> Ereignisse werden erst ausgelöst, nachdem die <xref:System.Windows.Window.Activated> Ereignis wird ausgelöst. In diesem Sinn, ein Fenster als tatsächlich geöffnet, wenn <xref:System.Windows.Window.ContentRendered> ausgelöst wird.  
  
 Nachdem ein Fenster aktiv geworden ist, kann ein Benutzer ein weiteres Fenster in derselben Anwendung oder eine andere Anwendung aktivieren. In diesem Fall wird das derzeit aktive Fenster deaktiviert und löst die <xref:System.Windows.Window.Deactivated> Ereignis. Ebenso, wenn der Benutzer ein derzeit deaktiviertes Fenster auswählt, das Fenster wird wieder aktiv und <xref:System.Windows.Window.Activated> ausgelöst wird.  
  
 Ein häufiger Grund zum Behandeln <xref:System.Windows.Window.Activated> und <xref:System.Windows.Window.Deactivated> ist das Aktivieren und Deaktivieren von Funktionen, die nur ausgeführt werden kann, wenn ein Fenster aktiv ist. In einigen Fenstern wird beispielsweise interaktiver Inhalt angezeigt, der andauernde Benutzereingaben oder Aufmerksamkeit erfordert, wie beispielsweise Spiele und Videoplayer. Das folgende Beispiel ist eine vereinfachte Videoplayer, die zeigt, wie behandelt <xref:System.Windows.Window.Activated> und <xref:System.Windows.Window.Deactivated> dieses Verhalten zu implementieren.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Andere Anwendungstypen führen im Hintergrund möglicherweise weiterhin Code aus, nachdem ein Fenster deaktiviert wurde. Ein E-Mail-Client kann z. B. weiterhin den E-Mail-Server abrufen, während der Benutzer andere Anwendungen verwendet. Während das Hauptfenster deaktiviert ist, stellen derartige Anwendungen häufig zusätzliches oder anderes Verhalten zur Verfügung. Im Hinblick auf das E-Mail-Programm kann das sowohl das Hinzufügen des neuen E-Mail-Elements zum Posteingang als auch eines Benachrichtigungssymbol in die Taskleiste bedeuten. Ein Benachrichtigungssymbol muss nur angezeigt, wenn das e-Mail-Fenster nicht aktiv ist, der durch Überprüfung bestimmt werden kann die <xref:System.Windows.Window.IsActive%2A> Eigenschaft.  
  
 Wenn eine Hintergrundtask abgeschlossen ist, ein Fenster sollten mehr dringend Benachrichtigung des Benutzers durch Aufrufen <xref:System.Windows.Window.Activate%2A> Methode. Wenn es sich bei der Interaktion des Benutzers mit einer anderen Anwendung aktiviert, wenn <xref:System.Windows.Window.Activate%2A> aufgerufen wird, wird die Schaltfläche auf der Taskleiste das Fenster blinkt. Wenn ein Benutzer mit der aktuellen Anwendung interagiert, Aufrufen von <xref:System.Windows.Window.Activate%2A> wird das Fenster in den Vordergrund bringen.  
  
> [!NOTE]
>  Können Sie behandeln, Anwendungsbereich Aktivierung mit der <xref:System.Windows.Application.Activated?displayProperty=nameWithType> und <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> Ereignisse.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Schließen eines Fensters  
 Die Lebensdauer eines Fensters endet, wenn der Benutzer das Fenster schließt. Ein Fenster kann mithilfe der Elemente im Nicht-Clientbereich geschlossen werden, z. B. mit den folgenden:  
  
-   Die **schließen** Elements von der **System** Menü.  
  
-   Drücken von ALT+F4.  
  
-   Drücken Sie die **schließen** Schaltfläche.  
  
 Zum Schließen eines Fensters können Sie dem Clientbereich weitere Mechanismen hinzufügen. Zu den gebräuchlichsten zählen:  
  
-   Ein **beenden** Element in der **Datei** Menü, in der Regel für die Hauptassembly der Anwendung Windows.  
  
-   Ein **schließen** Element in der **Datei** im Menü in der Regel auf einem sekundären Anwendungsfenster.  
  
-   Ein **"Abbrechen"** Schaltfläche in der Regel auf ein modales Dialogfeld.  
  
-   Ein **schließen** Schaltfläche in der Regel auf ein nicht modales Dialogfeld.  
  
 Um ein Fenster als Antwort auf eine der benutzerdefinierten Mechanismen zu schließen, müssen Sie zum Aufrufen der <xref:System.Windows.Window.Close%2A> Methode. Das folgende Beispiel implementiert die Möglichkeit, ein Fenster zu schließen, indem Sie auswählen der **beenden** auf die **Datei** Menü.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Wenn ein Fenster wird, und geschlossen es werden zwei Ereignisse ausgelöst: <xref:System.Windows.Window.Closing> und <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing>wird ausgelöst, bevor das Fenster wird geschlossen, und bietet einen Mechanismus, durch welches, den Fenster Closure verhindert werden kann. Der häufigste Grund, um das Schließen eines Fensters zu verhindern, liegt darin, dass Fensterinhalt geänderte Daten enthält. In diesem Fall die <xref:System.Windows.Window.Closing> -Ereignis behandelt werden, um zu bestimmen, ob Daten geändert wurden, und wenn Ja, auf der Benutzer gefragt, ob Sie entweder weiterhin das Fenster schließen, ohne die Daten zu speichern oder Schließen des Fensters "Abbrechen". Das folgende Beispiel zeigt die wichtigsten Aspekte bei der Behandlung <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  
 
  
 Die <xref:System.Windows.Window.Closing> übergebene Ereignishandler eine <xref:System.ComponentModel.CancelEventArgs>, implementiert die `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> -Eigenschaft, die Sie, um festlegen `true` zum Schließen ein Fensters zu verhindern.  
  
 Wenn <xref:System.Windows.Window.Closing> nicht behandelt wird, oder behandelt, aber nicht abgebrochen wird, wird das Fenster zu schließen. Kurz bevor tatsächlich ein Fenster wird, und geschlossen <xref:System.Windows.Window.Closed> ausgelöst wird. An dieser Stelle kann das Schließen des Fensters nicht verhindert werden.  
  
> [!NOTE]
>  Eine Anwendung kann so konfiguriert werden, dass heruntergefahren, wenn entweder das Hauptanwendungsfenster automatisch schließt (finden Sie unter <xref:System.Windows.Application.MainWindow%2A>) oder den letzten Fenster geschlossen wird. Ausführliche Informationen finden Sie unter <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Während ein Fensters über Mechanismen, die in den Bereichen clientfremden und Client explizit geschlossen werden kann, ein Fenster kann implizit geschlossen werden als Ergebnis Verhalten in anderen Teilen der Anwendung oder [!INCLUDE[TLA#tla_mswin](./../../../includes/tlasharptla-mswin-md.md)], u. a. folgende:  
  
-   Ein Benutzer abmeldet oder heruntergefahren [!INCLUDE[TLA2#tla_mswin](./../../../includes/tla2sharptla-mswin-md.md)].  
  
-   Der Besitzer eines Fensters geschlossen wird (siehe <xref:System.Windows.Window.Owner%2A>).  
  
-   Das Hauptanwendungsfenster wird geschlossen und <xref:System.Windows.Application.ShutdownMode%2A> ist <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
-   <xref:System.Windows.Application.Shutdown%2A> wird aufgerufen.  
  
> [!NOTE]
>  Ein Fenster kann nicht erneut geöffnet werden, nachdem es geschlossen wurde.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>Ereignisse in der Lebensdauer eines Fensters  
 In der folgenden Darstellung wird die Abfolge der wichtigsten Ereignisse in der Lebensdauer eines Fensters gezeigt.  
  
 ![Fensterlebensdauer](./../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 Die folgende Abbildung veranschaulicht die Abfolge der wichtigsten Ereignisse in der Lebensdauer eines Fensters, das ohne Aktivierung angezeigt wird (<xref:System.Windows.Window.ShowActivated%2A> festgelegt ist, um `false` , bevor das Fenster angezeigt wird).  
  
 ![Fensterlebensdauer &#40;Window.ShowActivated &#61; False&#41;](./../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Fensterposition  
 Solange ein Fenster geöffnet ist, befindet sich dessen Position in der x- und y-Dimension relativ zum Desktop. Dieser Speicherort kann bestimmt werden, durch Überprüfen der <xref:System.Windows.Window.Left%2A> und <xref:System.Windows.Window.Top%2A> Eigenschaften bzw. Sie können diese Eigenschaften festlegen, um die Position des Fensters zu ändern.  
  
 Sie können auch angeben, die ursprüngliche Position des eine <xref:System.Windows.Window> bei seinem ersten Auftreten durch Festlegen der <xref:System.Windows.Window.WindowStartupLocation%2A> Eigenschaft mit einem der folgenden <xref:System.Windows.WindowStartupLocation> Enumerationswerte:  
  
-   <xref:System.Windows.WindowStartupLocation.CenterOwner> (Standardwert)  
  
-   <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
-   <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Wenn die Startposition, als angegeben wird <xref:System.Windows.WindowStartupLocation.Manual>, und die <xref:System.Windows.Window.Left%2A> und <xref:System.Windows.Window.Top%2A> Eigenschaften wurden nicht festgelegt wurde, <xref:System.Windows.Window> fragt [!INCLUDE[TLA2#tla_mswin](./../../../includes/tla2sharptla-mswin-md.md)] für einen Standort in angezeigt werden.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Oberstes Fenster und Z-Reihenfolge  
 Neben der X- und Y-Position verfügt das Fenster auch über eine Position in der Z-Dimension, die dessen vertikale Position im Verhältnis zu anderen Fenstern bestimmt. Dies wird als Z-Reihenfolge des Fensters bezeichnet. Davon gibt es zwei Typen: die normale Z-Reihenfolge und die oberste Z-Reihenfolge. Die Position eines Fensters in den *normalen Z-Reihenfolge* richtet sich nach, ob es derzeit aktiv ist. Standardmäßig befindet sich ein Fenster in der normalen Z-Reihenfolge. Die Position eines Fensters in den *oberste Z-Reihenfolge* richtet sich zudem nach, ob es derzeit aktiv ist. Darüber hinaus befinden sich Fenster in der obersten Z-Reihenfolge stets über den Fenstern in der normalen Z-Reihenfolge. Ein Fenster befindet sich im obersten Z-Reihenfolge durch Festlegen seiner <xref:System.Windows.Window.Topmost%2A> Eigenschaft `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup2)]  
  
 Innerhalb jeder Z-Reihenfolge wird das aktuell aktive Fenster über allen anderen Fenstern derselben Z-Reihenfolge angezeigt.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Fenstergröße  
 Abgesehen von einer Position auf dem desktop ein Fenster hat eine Größe, die durch mehrere Eigenschaften, einschließlich der verschiedenen Eigenschaften der Breite und Höhe bestimmt ist und <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, und <xref:System.Windows.FrameworkElement.MaxWidth%2A> dienen zum Verwalten des Bereichs von Breiten verwendet, ein Fensters während seiner Lebensdauer haben kann konfiguriert werden, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup2)]  
  
 Fensterhöhe erfolgt durch <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, und <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und konfiguriert sind, wie im folgenden Beispiel gezeigt.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup2)]  
  
 Da die verschiedenen Werte für die Breite und für die Höhe jeweils einen Bereich angeben, kann die Breite und Höhe eines in der Größe veränderbaren Fensters irgendwo innerhalb des angegebenen Bereichs für die entsprechende Dimension liegen. Um die aktuelle Breite und Höhe zu ermitteln, untersuchen Sie <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A>zugeordnet.  
  
 Wenn Sie die Breite und Höhe des Fensters möchten den Inhalt eine Größe aufweisen, die auf die Größe des Fensters entspricht, können Sie mithilfe der <xref:System.Windows.Window.SizeToContent%2A> -Eigenschaft, die den folgenden Werten:  
  
-   <xref:System.Windows.SizeToContent.Manual>. Keine Auswirkung (Standard).  
  
-   <xref:System.Windows.SizeToContent.Width>. An Inhalt Breite dieselbe Wirkung hat wie das Festlegen von sowohl anpassen <xref:System.Windows.FrameworkElement.MinWidth%2A> und <xref:System.Windows.FrameworkElement.MaxWidth%2A> auf die Breite des Inhalts.  
  
-   <xref:System.Windows.SizeToContent.Height>. An Inhalt Höhe dieselbe Wirkung hat wie das Festlegen von sowohl anpassen <xref:System.Windows.FrameworkElement.MinHeight%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> an die Höhe des Inhalts.  
  
-   <xref:System.Windows.SizeToContent.WidthAndHeight>. An Inhalt Breite und Höhe dieselbe Wirkung hat wie das Festlegen von sowohl anpassen <xref:System.Windows.FrameworkElement.MinHeight%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> die Höhe der Inhalte und Einstellung beide <xref:System.Windows.FrameworkElement.MinWidth%2A> und <xref:System.Windows.FrameworkElement.MaxWidth%2A> auf die Breite des Inhalts.  
  
 Im folgenden Beispiel wird ein Fenster dass die Größe automatisch an seinen Inhalt vertikal und horizontal an, wenn es zuerst angezeigt wird.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup2)]  
  
 Im folgende Beispiel wird gezeigt, wie zum Festlegen der <xref:System.Windows.Window.SizeToContent%2A> -Eigenschaft im Code angeben, wie die Fenstergröße an ihren Inhalt.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Rangfolge der Größeneigenschaften  
 Im Wesentlichen werden die verschiedenen Größeneigenschaften eines Fensters kombiniert, um den Bereich der Breite und der Höhe für ein in der Größe veränderbares Fenster zu definieren. Um sicherzustellen, dass ein gültiger Bereich beibehalten wird, <xref:System.Windows.Window> die Werte der Größeneigenschaften anhand der folgenden Rangfolge ausgewertet.  
  
 **Für Höheneigenschaften:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Für Breiteneigenschaften:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 Rangfolge kann bestimmen die Größe eines Fensters auch zu, wenn dieses die maximiert mit verwaltet wird, die <xref:System.Windows.Window.WindowState%2A> Eigenschaft.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Fensterzustand  
 Während der Lebensdauer eines in der Größe veränderbaren Fenster kann dieses über drei Zustände verfügen: normal, minimiert und maximiert. Ein Fenster mit einem *normalen* Zustand ist der Standardzustand eines Fensters. Ein Benutzer kann ein Fenster mit diesem Zustand verschieben und dessen Größe ändern, indem er den Ziehpunkt zur Größenänderung oder den Rahmen verwendet, sofern er in der Größe veränderbar ist.  
  
 Ein Fenster mit einem *minimiert* Status wird auf seine Taskleistenschaltfläche reduziert, wenn <xref:System.Windows.Window.ShowInTaskbar%2A> festgelegt ist, um `true`ist, andernfalls wird reduziert, um die kleinstmögliche Größe es kann sein, und verschiebt selbst in der unteren linken Ecke des Desktops. Keiner der minimierten Fenstertypen kann mithilfe des Ziehpunkts zur Größenreduzierung oder mit dem Rahmen in der Größe verändert werden. Allerdings kann ein minimiertes Fenster, das nicht in der Taskleiste angezeigt wird, auf dem Desktop hin und her verschoben werden.  
  
 Ein Fenster mit einem *maximiert* Zustand wird erweitert, um die maximale Größe möglich, die nur so groß wie dessen <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, und <xref:System.Windows.Window.SizeToContent%2A> Eigenschaften vorgeben. Wie ein minimiertes Fenster kann auch ein maximiertes Fenster nicht mithilfe des Ziehpunkts zur Größenänderung oder durch Ziehen des Rahmens in seiner Größe verändert werden.  
  
> [!NOTE]
>  Die Werte der <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften eines Fensters stellen immer die Werte für den Zustand "normal", selbst wenn das Fenster derzeit maximiert oder minimiert wird.  
  
 Der Status eines Fensters kann konfiguriert werden, durch Festlegen seiner <xref:System.Windows.Window.WindowState%2A> -Eigenschaft, die einen der folgenden verfügen, können <xref:System.Windows.WindowState> Enumerationswerte:  
  
-   <xref:System.Windows.WindowState.Normal> (Standardwert)  
  
-   <xref:System.Windows.WindowState.Maximized>  
  
-   <xref:System.Windows.WindowState.Minimized>  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie ein Fenster erstellen, das beim Öffnen als maximiert angezeigt wird.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup2)]  
  
 Sie sollten im Allgemeinen festlegen <xref:System.Windows.Window.WindowState%2A> an den Ausgangszustand eines Fensters zu konfigurieren. Wenn ein in der Größe veränderbares Fenster angezeigt wird, können die Benutzer die Schaltflächen zum Minimieren, Maximieren oder Wiederherstellen auf der Titelleiste des Fensters aktivieren, um den Fensterzustand zu ändern.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Fensterdarstellung  
 Sie ändern die Darstellung des Clientbereichs eines Fensters, indem Sie fensterspezifischen Inhalt hinzufügen, z. B. Schaltflächen, Bezeichnungen und Textfelder. So konfigurieren Sie den nicht-Clientbereich <xref:System.Windows.Window> enthält verschiedene Eigenschaften, darunter <xref:System.Windows.Window.Icon%2A> Symbol für ein Fenster festlegen und <xref:System.Windows.Window.Title%2A> seinen Titel festlegen.  
  
 Außerdem können Sie die Darstellung und das Verhalten des Rahmens im Nicht-Clientbereich ändern, indem Sie den Größenänderungsmodus, den Fensterstil und die Tatsache konfigurieren, ob es als Schaltfläche in der Desktoptaskleiste angezeigt wird.  
  
  
<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Größenänderungsmodus  
 Je nach den <xref:System.Windows.Window.WindowStyle%2A> -Eigenschaft, können Sie steuern, wie (und ob) Benutzer können die Größe des Fensters. Die Auswahl des Fensterstil auswirkt, ob ein Benutzer die Größe des Editorfensters kann durch Ziehen eine Rahmenlinie mit der Maus, ob die **Minimieren**, **Maximieren**, und **Größe** Schaltflächen auf den nicht-Clientbereich angezeigt werden und, falls sie angezeigt, ob sie aktiviert sind.  
  
 Sie können konfigurieren, wie eine Fenstergröße durch Festlegen seiner <xref:System.Windows.Window.ResizeMode%2A> -Eigenschaft, die in der folgenden Werte sind möglich <xref:System.Windows.ResizeMode> Enumerationswerte:  
  
-   <xref:System.Windows.ResizeMode.NoResize>  
  
-   <xref:System.Windows.ResizeMode.CanMinimize>  
  
-   <xref:System.Windows.ResizeMode.CanResize> (Standardwert)  
  
-   <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Wie bei <xref:System.Windows.Window.WindowStyle%2A>, der Größenänderungsmodus eines Fensters ist es unwahrscheinlich, dass während seiner Lebensdauer zu ändern, was bedeutet, dass sie über sehr wahrscheinlich festgelegt werden [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup2)]  
  
 Beachten Sie, die Sie erkennen, ob ein Fenster maximiert ist, minimiert oder wiederhergestellt, indem Sie überprüfen die <xref:System.Windows.Window.WindowState%2A> Eigenschaft.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Fensterstil  
 Der Rahmen, der vom Nicht-Clientbereich eines Fensters verfügbar gemacht wird, eignet sich für die meisten Anwendungen. Unter bestimmten Umständen werden je nach Fenstertyp dennoch andere Rahmentypen oder überhaupt keine Rahmen benötigt.  
  
 Steuern, welche Art des Rahmens ein Fensters, legen Sie seine <xref:System.Windows.Window.WindowStyle%2A> Eigenschaft mit einem der folgenden Werte für die <xref:System.Windows.WindowStyle> Enumeration:  
  
-   <xref:System.Windows.WindowStyle.None>  
  
-   <xref:System.Windows.WindowStyle.SingleBorderWindow> (Standardwert)  
  
-   <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
-   <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Die Auswirkung dieser Fensterstile wird in der folgenden Abbildung veranschaulicht.  
  
 ![Fensterstile](./../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.PNG "WindowOverviewFigure6")  
  
 Sie können festlegen, <xref:System.Windows.Window.WindowStyle%2A> entweder [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup oder-Code; da es unwahrscheinlich ist, während der Lebensdauer eines Fensters zu ändern, wahrscheinlich konfigurieren Sie ihn mit [!INCLUDE[TLA2#tla_xaml](./../../../includes/tla2sharptla-xaml-md.md)] Markup.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup2)]  
  
#### <a name="non-rectangular-window-style"></a>Nicht rechteckiger Fensterstil  
 Es gibt auch Situationen, in dem der Rahmen Formatvorlagen, <xref:System.Windows.Window.WindowStyle%2A> ermöglicht es Ihnen, sind nicht ausreichend. Sie möchten beispielsweise erstellen Sie eine Anwendung mit einem viereckig Rahmen wie [!INCLUDE[TLA#tla_wmp](./../../../includes/tlasharptla-wmp-md.md)] verwendet.  
  
 Betrachten Sie beispielsweise das Sprechblasenfenster in der folgenden Abbildung.  
  
 ![Nicht rechteckiges Fenster](./../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Diese Art von Fenster erstellt werden, indem Sie die Einstellung der <xref:System.Windows.Window.WindowStyle%2A> Eigenschaft <xref:System.Windows.WindowStyle.None>, und mit besonderen unterstützen, die <xref:System.Windows.Window> wurde für die Transparenz.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup2)]  
  
 Durch diese Kombination von Werten wird das Fenster angewiesen, ein vollkommen transparentes Rendering zu übernehmen. In diesem Zustand können die Zusatzelemente des Nicht-Clientbereichs des Fensters (das Menü „Schließen“, die Schaltflächen „Minimieren“, „Maximieren“ und „Wiederherstellen“ usw.) nicht verwendet werden. Folglich müssen Sie Ihre eigenen bereitstellen.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Vorhandensein der Taskleiste  
 Die Standarddarstellung eines Fensters umfasst eine Taskleistenschaltfläche wie in der folgenden Abbildung.  
  
 ![Fenster mit einer Taskleistenschaltfläche](./../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.PNG "WindowOverviewFigure7")  
  
 Bei einigen Typen von Windows keine Taskleistenschaltfläche wie Meldungsfelder und Dialogfelder sind (finden Sie unter [Dialog Boxes Overview](./../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)). Sie können steuern, ob die Taskleistenschaltfläche für ein Fenster, durch Festlegen angezeigt wird der <xref:System.Windows.Window.ShowInTaskbar%2A> Eigenschaft (`true` standardmäßig).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
[!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup2)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Sicherheitsüberlegungen  
 <xref:System.Windows.Window>erfordert `UnmanagedCode` Sicherheitsberechtigung instanziiert werden. Bei Anwendungen, die auf dem lokalen Computer installiert und gestartet werden, wird dies durch die Berechtigungen abgedeckt, die der Anwendung gewährt werden.  
  
 Allerdings Dies liegt außerhalb des Satzes von Berechtigungen für Anwendungen, die aus dem Internet oder lokales Intranet-Zone mit gestartet werden [!INCLUDE[TLA#tla_clickonce](./../../../includes/tlasharptla-clickonce-md.md)]. Folglich erhalten Benutzer eine [!INCLUDE[TLA2#tla_clickonce](./../../../includes/tla2sharptla-clickonce-md.md)] sicherheitswarnung, und müssen den Berechtigungssatz für die Anwendung auf volle Vertrauenswürdigkeit zu erhöhen.  
  
 Darüber hinaus [!INCLUDE[TLA2#tla_xbap#plural](./../../../includes/tla2sharptla-xbapsharpplural-md.md)] kann nicht in der Standardeinstellung Windows- oder Dialogfeldern angezeigt. Ausführliche Informationen zu sicherheitsüberlegungen für eigenständige Anwendung, finden Sie unter [WPF-Sicherheitsstrategie – Plattformsicherheit](./../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Andere Fenstertypen  
 <xref:System.Windows.Navigation.NavigationWindow>ist ein Fenster, die zum Hosten von navigierbaren Inhalt vorgesehen ist. Weitere Informationen finden Sie unter [Navigation Overview](./../../../docs/framework/wpf/app-development/navigation-overview.md)).  
  
 Dialogfelder sind Fenster, die häufig zum Erfassen von Benutzerinformationen verwendet werden, um eine Funktion ausführen. Z. B. wenn ein Benutzer möchte zum Öffnen einer Datei, die **Datei öffnen** Dialogfeld wird in der Regel von einer Anwendung zum Abrufen des Dateinamens aus dem Benutzer angezeigt. Weitere Informationen finden Sie unter [Übersicht über Dialogfelder](./../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Window>  
 <xref:System.Windows.MessageBox>  
 <xref:System.Windows.Navigation.NavigationWindow>  
 <xref:System.Windows.Application>  
 [Übersicht über Dialogfelder](./../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)  
 [Erstellen einer WPF-Anwendung](./../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
