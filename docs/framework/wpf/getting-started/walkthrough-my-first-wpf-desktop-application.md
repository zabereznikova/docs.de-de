---
title: 'Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung
In dieser exemplarischen Vorgehensweise bietet eine Einführung in die Entwicklung einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Anwendung, die die Elemente enthält, die für die meisten gelten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup, CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, die Datenbindung und Stile. 
  
Diese exemplarische Vorgehensweise führt Sie durch die Entwicklung einer einfachen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung mithilfe der folgenden Schritte. 
  
-   Definieren von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zum Entwerfen der Darstellung der Anwendung [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. 
  
-   Schreiben von Code, um das Verhalten der Anwendung zu erstellen. 
  
-   Erstellen einer Anwendungsdefinition, um die Anwendung zu verwalten 
  
-   Hinzufügen von Steuerelementen und erstellen Sie das Layout die Anwendung zusammengesetzt [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Erstellen Formate, um eine konsistente Darstellung in einer Anwendungsverzeichnis erstellen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Binden der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Auffüllen mit Daten, sowohl die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Daten- und Beibehalten der Daten und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronisiert. 
  
Am Ende dieser exemplarischen Vorgehensweise, Sie werden erstellt haben, eine eigenständige [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Anwendung, die Benutzern ermöglicht, Ausgabenberichte für ausgewählte Benutzer anzeigen. Die Anwendung besteht aus mehreren [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Seiten, die in einem Fenster im Webbrowserstil gehostet werden. 
  
Der Beispielcode, der verwendet wird, erstellen Sie in dieser exemplarischen Vorgehensweise steht sowohl für [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] und [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] am [Einführung zum Erstellen von WPF-Anwendungen](http://go.microsoft.com/fwlink/?LinkID=160008). 

## <a name="prerequisites"></a>Erforderliche Komponenten  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)] oder höher

Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [installieren Sie Visual Studio](/visualstudio/install/install-visual-studio).
  
## <a name="creating-the-application-project"></a>Erstellen des Anwendungsprojekts  
n diesem Abschnitt erstellen Sie die Anwendungsstruktur, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält. 
  
1. Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `ExpenseIt`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82). 
  
    > [!NOTE]
    >  Diese exemplarische Vorgehensweise verwendet die <xref:System.Windows.Controls.DataGrid> Steuerelement, das in .NET Framework 4 verfügbar. Stellen Sie sicher, dass Ihr Projekt auf .NET Framework 4 abzielt oder höher. Weitere Informationen finden Sie unter [Vorgehensweise: .NET Framework-Version als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
2. Öffnen Sie „Application.xaml“ (Visual Basic) oder „App.xaml“ (C#). 
  
     Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei definiert eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung und alle Ressourcen der Anwendung. Sie verwenden diese Datei auch an die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automatisch das wird angezeigt, wenn die Anwendung gestartet wird; in diesem Fall "MainWindow.xaml". 
  
     Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     Oder in C# wie folgt:  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. Öffnen Sie „MainWindow.xaml“. 
  
     Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei wird im Hauptfenster der Anwendung und zeigt den Inhalt in Seiten erstellt. Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters, z. B. Titel, Größe oder Symbol, und behandelt Ereignisse, z. B. Schließen oder ausblenden. 
  
4. Ändern der <xref:System.Windows.Window> Element zu einem <xref:System.Windows.Navigation.NavigationWindow>. 
  
     Diese Anwendung navigiert je nach Benutzerinteraktion zu anderem Inhalt. Aus diesem Grund für den Hauptknoten <xref:System.Windows.Window> muss geändert werden, um eine <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> erbt alle Eigenschaften des <xref:System.Windows.Window>. Die <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow> Klasse. Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md). 
  
5. Ändern Sie die folgenden Eigenschaften auf der <xref:System.Windows.Navigation.NavigationWindow> Element:  
  
    -   Legen Sie die <xref:System.Windows.Window.Title%2A> -Eigenschaft auf "ExpenseIt". 
  
    -   Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel. 
  
    -   Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 350 Pixel. 
  
    -   Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags. 
  
     Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     Oder in C# wie folgt:  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. Öffnen Sie „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“. 
  
     Bei dieser Datei handelt es sich um eine CodeBehind-Datei, die Code enthält, um die in „MainWindow.xaml“ deklarierten Ereignisse zu behandeln. Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster. 
  
7. Wenn Sie c# verwenden, ändern Sie die `MainWindow` Klasse abgeleitet <xref:System.Windows.Navigation.NavigationWindow>. 
  
     In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern. 
  
     Ihr Code sollte wie folgt aussehen. 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a>Hinzufügen von Dateien zur Anwendung  
In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu. 
  
1. Fügen Sie eine neue Seite (WPF) auf das Projekt mit dem Namen `ExpenseItHome.xaml`. Weitere Informationen finden Sie unter [wie: Hinzufügen neuer Elemente zu einem WPF-Projekt](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad). 
  
     Diese Seite ist die erste Seite, das beim Anwendungsstart angezeigt wird. Sie zeigt eine Liste von Personen, aus denen ein Benutzer eine Person auswählen kann, um die zugehörige Spesenabrechnung anzuzeigen. 
  
2. Öffnen Sie „ExpenseItHome.xaml“. 
  
3. Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt – Home". 
  
     Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     Oder in C# wie folgt:  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. Öffnen Sie „MainWindow.xaml“. 
  
5. Legen Sie die <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Eigenschaft auf die <xref:System.Windows.Navigation.NavigationWindow> auf "ExpenseItHome.xaml". 
  
     Dadurch wird „ExpenseItHome.xaml“ als erste Seite festgelegt, die beim Start der Anwendung geöffnet wird. Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     Oder in C# wie folgt:  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. Fügen Sie eine neue Seite (WPF) auf das Projekt mit dem Namen `ExpenseReportPage.xaml`. 
  
     Diese Seite zeigt die Spesenabrechnung für die Person an, die für „ExpenseItHome.xaml“ ausgewählt wird. 
  
7. Öffnen Sie „ExpenseReportPage.xaml“. 
  
8. Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt – View Expense". 
  
     Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     Oder in C# wie folgt:  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Öffnen Sie „ExpenseItHome.xaml.vb“ und „ExpenseReportPage.xaml.vb“ bzw. „ExpenseItHome.xaml.cs“ und „ExpenseReportPage.xaml.cs“. 
  
     Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch eine CodeBehind-Datei. Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe. 
  
     Ihr Code sollte wie folgt aussehen. 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Hinzufügen eines Bilds mit dem Namen *watermark.png* zum Projekt. Sie können ein eigenes Bild erstellen oder die Datei aus dem Beispielcode kopieren. Weitere Informationen finden Sie unter [wie: Hinzufügen von vorhandenen Elementen zu einem Projekt](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)). 

## <a name="building-and-running-the-application"></a>Erstellen und Ausführen der Anwendung  
In diesem Abschnitt wird die Anwendung erstellt und dann ausgeführt. 
  
1. Erstellen und führen Sie die Anwendung, indem Sie durch Drücken von F5 oder auswählen **Debuggen** aus der **Debuggen** Menü. 
  
     Die folgende Abbildung zeigt die Anwendung mit der <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen. 
  
     ![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2. Schließen Sie die Anwendung wieder [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]. 
  
## <a name="creating-the-layout"></a>Erstellen des Layouts  
Layout bietet die Möglichkeit zum platzieren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente, und verwaltet auch die Größe und Position dieser Elemente bei einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] angepasst wird. In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
Jedes dieser Layoutsteuerelemente unterstützt einen speziellen Layouttyp für seine untergeordneten Elemente. Die Größe von „ExpenseIt“-Seiten kann geändert werden. Jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind. Folglich die <xref:System.Windows.Controls.Grid> ist die ideale Layoutelement für die Anwendung. 
  
> [!NOTE]
>  Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md). Weitere Informationen zum Layout finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md). 
  
Klicken Sie im Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10-Pixel-Rand durch Hinzufügen von Spalten- und Definitionen, um die <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml. 
  
1. Öffnen Sie „ExpenseItHome.xaml“. 
  
2. Legen Sie die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft auf die <xref:System.Windows.Controls.Grid> -Elements auf "10,0,10,10" den linken, oberen, rechten und unteren Ränder. 
  
3. Fügen Sie die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zwischen den <xref:System.Windows.Controls.Grid> Tags aus, um die Zeilen- und Spaltendefinitionen zu erstellen. 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     Die <xref:System.Windows.Controls.RowDefinition.Height%2A> von zwei Zeilen wird festgelegt <xref:System.Windows.GridLength.Auto%2A> was bedeutet, dass die Größe der Zeilen als Grundlage für den Inhalt in den Zeilen. Die Standardeinstellung <xref:System.Windows.Controls.RowDefinition.Height%2A> ist <xref:System.Windows.GridUnitType.Star> Sizing, was bedeutet, dass die Zeile eine gewichtete Proportion des verfügbaren Speicherplatzes. Wenn z. B. zwei Zeilen jeweils eine Höhe von „*“ haben, hat jede eine Höhe von der Hälfte des verfügbaren Platzes.  
  
     Ihre <xref:System.Windows.Controls.Grid> sollte jetzt wie der folgende XAML-Code aussehen:  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a>Hinzufügen von Steuerelementen  
In diesem Abschnitt der Startseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aktualisiert, um einer Liste der Personen anzuzeigen, dass Benutzer aus auswählen können, um die Ausgabenbericht für eine ausgewählte Person angezeigt. Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen. Weitere Informationen finden Sie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md). 
  
Zum Erstellen dieser [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgenden Elemente ExpenseItHome.xaml hinzugefügt werden:  
  
-   <xref:System.Windows.Controls.ListBox> (für die Liste der Personen). 
  
-   <xref:System.Windows.Controls.Label> (für den List-Header). 
  
-   <xref:System.Windows.Controls.Button> (um klicken, um die Ausgabenbericht für die Person anzuzeigen, die in der Liste ausgewählt ist). 
  
Jedes Steuerelement wird in einer Zeile platziert die <xref:System.Windows.Controls.Grid> durch Festlegen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> -Eigenschaft. Weitere Informationen über angefügte Eigenschaften finden Sie unter [Eigenschaftenübersicht angefügt](../../../../docs/framework/wpf/advanced/attached-properties-overview.md). 
  
1. Öffnen Sie „ExpenseItHome.xaml“. 
  
2. Fügen Sie die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zwischen den <xref:System.Windows.Controls.Grid> Tags. 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. Erstellen Sie die Anwendung, und führen Sie sie aus. 
  
Die folgende Abbildung zeigt die Steuerelemente, die von der XAML in diesem Abschnitt erstellt werden. 
  
![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
## <a name="adding-an-image-and-a-title"></a>Hinzufügen eines Bilds und einen Titel  
In diesem Abschnitt der Startseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit ein Abbild und einen Seitentitel aktualisiert wird. 
  
1. Öffnen Sie „ExpenseItHome.xaml“. 
  
2. Eine weitere Spalte zum Hinzufügen der <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixeln. 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. Hinzufügen zu einer anderen Zeile die <xref:System.Windows.Controls.Grid.RowDefinitions%2A>. 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. Verschieben Sie die Steuerelemente in die zweite Spalte durch Festlegen von <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> auf 1. Verschieben Sie jedes Steuerelement eine Zeile nach unten durch Erhöhen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> um 1. 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. Legen Sie die <xref:System.Windows.Controls.Panel.Background%2A> von der <xref:System.Windows.Controls.Grid> auf die Bilddatei watermark.png sein. 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. Bevor Sie die <xref:System.Windows.Controls.Border>, Hinzufügen einer <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report" als Titel der Seite. 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. Erstellen Sie die Anwendung, und führen Sie sie aus. 
  
In der folgenden Abbildung werden die Ergebnisse dieses Abschnitts dargestellt. 
  
![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
## <a name="adding-code-to-handle-events"></a>Hinzufügen von Code zum Behandeln von Ereignissen  
  
1. Öffnen Sie „ExpenseItHome.xaml“. 
  
2. Hinzufügen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler, um die <xref:System.Windows.Controls.Button> Element. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer einfachen Ereignishandler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480). 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. Öffnen Sie „ExpenseItHome.xaml.vb“ bzw. „ExpenseItHome.xaml.cs“. 
  
4. Fügen Sie folgenden Code, der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler bewirkt, das Fenster dass, navigieren Sie zu der Datei "ExpenseReportPage.xaml". 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a>Erstellen der Benutzeroberfläche für ExpenseReportPage  
„ExpenseReportPage.xaml“ zeigt die Spesenabrechnung für die Person an, die für „ExpenseItHome.xaml“ ausgewählt wurde. In diesem Abschnitt fügt Steuerelemente hinzu und erstellt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für ExpenseReportPage.xaml. In diesem Abschnitt sowie die Hintergrund-und ausfüllen zu den verschiedenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente. 
  
1. Öffnen Sie „ExpenseReportPage.xaml“. 
  
2. Fügen Sie folgenden XAML-Code zwischen den <xref:System.Windows.Controls.Grid>-Tags hinzu. 
  
     Diese Benutzeroberfläche ähnelt der Benutzeroberfläche auf ExpenseItHome.xaml erstellt werden, außer die Berichtsdaten, in angezeigt werden einem <xref:System.Windows.Controls.DataGrid>. 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. Erstellen Sie die Anwendung, und führen Sie sie aus. 
  
    > [!NOTE]
    >  Wenn Sie eine Fehlermeldung, die erhalten die <xref:System.Windows.Controls.DataGrid> wurde nicht gefunden oder nicht vorhanden ist, stellen Sie sicher, dass das Projekt .NET Framework 4 oder höher abzielt. Weitere Informationen finden Sie unter [Vorgehensweise: .NET Framework-Version als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
4. Klicken Sie auf die **Ansicht** Schaltfläche. 
  
     Die Spesenabrechnungsseite wird angezeigt. 
  
Die folgende Abbildung zeigt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ExpenseReportPage.xaml hinzugefügte Elemente. Beachten Sie, dass die Navigationsschaltfläche "Zurück" aktiviert ist. 
  
![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
## <a name="styling-controls"></a>Formatieren von Steuerelementen  
Die Darstellung der verschiedenen Elemente kann häufig derselbe Pfad werden für alle Elemente des gleichen Typs in eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] verwendet Stile, damit Darstellungen in mehreren Elementen wieder verwendet werden können. Die Wiederverwendung von Stilen kann zur Vereinfachung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen und verwalten. Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md). Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden. 
  
1. Öffnen Sie „Application.xaml“ oder „App.xaml“. 
  
2. Fügen Sie den folgenden XAML-Code zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags:  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fügt die folgenden Stile hinzu:  
  
    -  `headerTextStyle`: Zum Formatieren des Seitentitels für <xref:System.Windows.Controls.Label>. 
  
    -  `labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> -Steuerelemente. 
  
    -  `columnHeaderStyle`: Zum Formatieren von <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>. 
  
    -  `listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border> -Kopfzeilensteuerelemente. 
  
    -  `listHeaderTextStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Label>. 
  
    -  `buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf ExpenseItHome.xaml. 
  
     Beachten Sie, dass die Stile für Ressourcen und die untergeordneten Elemente sind die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Property-Element. An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet. Ein Beispiel der Verwendung von Ressourcen in einer [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] -Anwendung finden Sie unter [verwenden Anwendungsressourcen](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md). 
  
3. Öffnen Sie „ExpenseItHome.xaml“. 
  
4. Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente durch Folgendes XAML. 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden. Z. B. die `headerTextStyle` wird angewendet, um die "View Expense Report" <xref:System.Windows.Controls.Label>. 
  
5. Öffnen Sie „ExpenseReportPage.xaml“. 
  
6. Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente durch Folgendes XAML. 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     Dadurch werden dem <xref:System.Windows.Controls.Label> -Element und <xref:System.Windows.Controls.Border> -Element Stile hinzugefügt. 
  
7. Erstellen Sie die Anwendung, und führen Sie sie aus. 
  
     Nach dem Hinzufügen der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in diesem Abschnitt die Anwendung sieht genauso aus wie gewohnt mit Stilen aktualisiert wird. 
  
## <a name="binding-data-to-a-control"></a>Binden von Daten an ein Steuerelement  
In diesem Abschnitt erstellen Sie die [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Daten, die an verschiedene Steuerelemente gebunden ist. 
  
1. Öffnen Sie „ExpenseItHome.xaml“. 
  
2. Nach dem Öffnen <xref:System.Windows.Controls.Grid> Element, fügen Sie den folgenden XAML-Code zum Erstellen einer <xref:System.Windows.Data.XmlDataProvider> , die Daten für jede Person enthält. 
  
     Die Daten werden als erstellt eine <xref:System.Windows.Controls.Grid> Ressource. Normalerweise würde sie als Datei geladen, aus Gründen der Einfachheit werden die Daten aber inline hinzugefügt. 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. In der <xref:System.Windows.Controls.Grid> Ressource, fügen Sie die folgenden <xref:System.Windows.DataTemplate>, die definiert, wie zum Anzeigen der Daten in der <xref:System.Windows.Controls.ListBox>. Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md). 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> durch Folgendes XAML. 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Dieser XAML-Code bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft von der <xref:System.Windows.Controls.ListBox> mit der Datenquelle und wendet die Datenvorlage als die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>. 
  
## <a name="connecting-data-to-controls"></a>Verbinden von Daten an Steuerelemente  
In diesem Abschnitt schreiben Sie Code, der das aktuelle Element, die in der Liste der Personen auf der Seite "ExpenseItHome.xaml" ausgewählt ist abruft, und übergibt den Verweis auf den Konstruktor des `ExpenseReportPage` während der Instanziierung. `ExpenseReportPage` legt den Datenkontext mithilfe des übergebenen Elements fest, und die in „ExpenseReportPage.xaml“ definierten Steuerelemente werden daran gebunden. 
  
1. Öffnen Sie „ExpenseReportPage.xaml.vb“ oder „ExpenseReportPage.xaml.cs“. 
  
2. Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können. 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. Öffnen Sie „ExpenseItHome.xaml.vb“ bzw. „ExpenseItHome.xaml.cs“. 
  
4. Ändern der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler aufrufen, den neuen Konstruktor die Spesenabrechnungsdaten der ausgewählten Person übergeben. 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a>Formatieren von Daten mit Datenvorlagen  
In diesem Abschnitt wird die Aktualisierung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für jedes Element in den Daten Listen mit Datenvorlagen gebunden. 
  
1. Öffnen Sie „ExpenseReportPage.xaml“. 
  
2. Binden Sie den Inhalt des "Name" und "Department" <xref:System.Windows.Controls.Label> Elemente, die die entsprechenden Daten source-Eigenschaft. Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. Nach der öffnenden <xref:System.Windows.Controls.Grid> Element, fügen Sie die folgenden Datenvorlagen, die definieren, wie die Spesenabrechnungsdaten angezeigt.  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. Wenden Sie die Vorlagen, die <xref:System.Windows.Controls.DataGrid> Berichtsdaten für Spalten, in denen die Ausgaben angezeigt. 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. Erstellen Sie die Anwendung, und führen Sie sie aus. 
  
6. Wählen Sie eine Person ein, und klicken Sie auf die **Ansicht** Schaltfläche. 
  
 Die folgende Abbildung zeigt die beiden Seiten der ExpenseIt-Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen, die angewendet wurden. 
  
 ![Bildschirmabbildungen für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
## <a name="best-practices"></a>Bewährte Methoden  
In diesem Beispiel soll nur eine bestimmte Funktion von WPF veranschaulicht werden, daher werden die bewährten Methoden für die Anwendungsentwicklung nicht befolgt. Für eine umfassende Erläuterung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] bewährte Methoden für die Anwendungsentwicklung, finden Sie unter den folgenden Themen nach Bedarf:  
  
-   Barrierefreiheit – [Bewährte Methoden für Eingabehilfen](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Sicherheit – [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Lokalisierung – [Übersicht über WPF-Globalisierung und -Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Leistung – [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
## <a name="whats-next"></a>Ausblick  
Sie haben nun eine Reihe von Techniken zur Verfügung, die zum Erstellen einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Sie verfügen jetzt über fundierte Kenntnisse über die grundlegenden Bausteine von einem datengebundenen [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] Anwendung. Dieses Thema erhebt keinen Anspruch auf Vollständigkeit, soll aber eine Vorstellung einiger Möglichkeiten vermitteln, die Sie neben den in diesem Thema vorgestellten Techniken selbst entdecken können. 
  
 Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:  
  
-   [WPF-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:  
  
-   [Anwendungsentwicklung](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Erstellen einer WPF-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Stile und Vorlagen](../../../../docs/framework/wpf/controls/styles-and-templates.md)
