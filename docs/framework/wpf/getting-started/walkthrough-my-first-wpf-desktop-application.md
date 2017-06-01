---
title: "Exemplarische Vorgehensweise: Erste Schritte mit WPF | Microsoft Docs"
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
  - "Erste Schritte, WPF"
  - "WPF, Erste Schritte"
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 68
---
# Exemplarische Vorgehensweise: Erste Schritte mit WPF
<a name="introduction"></a> Diese exemplarische Vorgehensweise bietet eine Einführung in die Entwicklung einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Anwendung, in der die Elemente enthalten sind, die von den meisten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen verwendet werden: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Markup, Code\-Behind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile.  
  
 Diese exemplarische Vorgehensweise führt Sie mithilfe der folgenden Schritte durch die Entwicklung einer einfachen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung.  
  
-   Definieren Sie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], um die Darstellung der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] der Anwendung zu entwerfen.  
  
-   Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.  
  
-   Erstellen Sie eine Anwendungsdefinition, um die Anwendung zu verwalten.  
  
-   Fügen Sie Steuerelemente hinzu und erstellen Sie das Layout, aus dem die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung zusammengesetzt werden soll.  
  
-   Erstellen Sie Stile, um eine konsistente Darstellung in der gesamten Anwendungs\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zu erstellen.  
  
-   Binden Sie die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an Daten, um die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit Daten zu füllen und die Daten und die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchron zu halten.  
  
 Nach Abschluss der exemplarischen Vorgehensweise haben Sie eine eigenständige [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]\-Anwendung erstellt, mit der Benutzer Spesenabrechnungen für bestimmte Personen anzeigen können.  Die Anwendung besteht aus mehreren [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Seiten, die in einem Fenster im Browserstil gehostet werden.  
  
 Der Beispielcode, der in dieser exemplarischen Vorgehensweise verwendet wird, steht sowohl für [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] als auch für [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] unter [Einführung in das Erstellen von Windows Presentation Foundation\-Anwendungen](http://go.microsoft.com/fwlink/?LinkID=160008) zur Verfügung.  
  
<a name="Requirements"></a>   
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]  
  
 Weitere Informationen zum Installieren von [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] finden Sie unter [Installieren von Visual Studio](../Topic/Install%20Visual%20Studio%202015.md).  
  
<a name="Create_The_Application_Code_Files"></a>   
## Erstellen des Anwendungsprojekts  
 In diesem Abschnitt erstellen Sie die Anwendungsstruktur, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.  
  
1.  Erstellen Sie ein neues WPF\-Anwendungsprojekt in Visual Basic oder Visual C\# mit dem Namen `ExpenseIt`.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines neuen WPF\-Anwendungsprojekts](http://msdn.microsoft.com/de-de/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
    > [!NOTE]
    >  In dieser exemplarischen Vorgehensweise wird das in .NET Framework 4 verfügbare <xref:System.Windows.Controls.DataGrid>\-Steuerelement verwendet.  Stellen Sie sicher, dass .NET Framework 4 als Zielversion für das Projekt festgelegt ist.  Weitere Informationen finden Sie unter [Gewusst wie: .NET Framework\-Version als Ziel](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
2.  Öffnen Sie Application.xaml \(Visual Basic\) oder App.xaml \(C\#\).  
  
     Diese [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei definiert eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung sowie Anwendungsressourcen. Mithilfe dieser Datei geben Sie auch die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an, die beim Anwendungsstart automatisch angezeigt wird \(in diesem Fall "MainWindow.xaml"\).  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
     [!code-xml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     Oder wie folgt in C\#:  
  
     [!code-xml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3.  Öffnen Sie MainWindow.xaml.  
  
     Diese [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Datei ist das Hauptfenster der Anwendung und zeigt erstellten Inhalt in Seiten an.  Die <xref:System.Windows.Window>\-Klasse definiert die Eigenschaften eines Fensters wie Titel, Größe oder Symbol, und behandelt Ereignisse wie Schließen oder Ausblenden.  
  
4.  Ändern Sie das <xref:System.Windows.Window>\-Element in ein <xref:System.Windows.Navigation.NavigationWindow>.  
  
     Diese Anwendung navigiert je nach Benutzerinteraktion zu anderem Inhalt.  Daher muss das Haupt\-<xref:System.Windows.Window> in ein <xref:System.Windows.Navigation.NavigationWindow> geändert werden.  <xref:System.Windows.Navigation.NavigationWindow> erbt alle Eigenschaften von <xref:System.Windows.Window>.  Das <xref:System.Windows.Navigation.NavigationWindow>\-Element in der XAML\-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow>\-Klasse.  Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
5.  Ändern Sie die folgenden Eigenschaften im <xref:System.Windows.Navigation.NavigationWindow>\-Element:  
  
    -   Legen Sie die <xref:System.Windows.Window.Title%2A>\-Eigenschaft auf "ExpenseIt" fest.  
  
    -   Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft auf 500 Pixel fest.  
  
    -   Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft auf 350 Pixel fest.  
  
    -   Entfernen Sie die <xref:System.Windows.Controls.Grid>\-Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow>\-Tags.  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
     [!code-xml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     Oder wie folgt in C\#:  
  
     [!code-xml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6.  Öffnen Sie MainWindow.xaml.vb oder MainWindow.xaml.cs.  
  
     Bei dieser Datei handelt es sich um eine CodeBehind\-Datei, die Code enthält, um die in MainWindow.xaml deklarierten Ereignisse zu behandeln.  Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.  
  
7.  Wenn Sie C\# verwenden, ändern Sie die `MainWindow`\-Klasse so, dass sie von <xref:System.Windows.Navigation.NavigationWindow> abgeleitet wird.  
  
     In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.  
  
     Der Code muss wie folgt aussehen.  
  
     [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
     [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
<a name="add_files_to_the_application"></a>   
## Hinzufügen von Dateien zur Anwendung  
 In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.  
  
1.  Fügen Sie dem Projekt eine neue Seite \(WPF\) mit dem Namen `ExpenseItHome.xaml` hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von neuen Elementen zu einem WPF\-Projekt](http://msdn.microsoft.com/de-de/17e6b238-fc32-4385-98ef-2f66ca09d9ad).  
  
     Diese Seite ist die erste Seite, die beim Anwendungsstart angezeigt wird.  Sie zeigt eine Liste von Personen, aus denen ein Benutzer eine Person auswählen kann, um die zugehörige Spesenabrechnung anzuzeigen.  
  
2.  Öffnen Sie ExpenseItHome.xaml.  
  
3.  Legen Sie den <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt \- Home" fest.  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
     [!code-xml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     Oder wie folgt in C\#:  
  
     [!code-xml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4.  Öffnen Sie MainWindow.xaml.  
  
5.  Legen Sie die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>\-Eigenschaft im <xref:System.Windows.Navigation.NavigationWindow> auf "ExpenseItHome.xaml" fest.  
  
     Damit wird ExpenseItHome.xaml als die erste Seite festgelegt, die beim Anwendungsstart geöffnet wird.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
     [!code-xml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     Oder wie folgt in C\#:  
  
     [!code-xml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6.  Fügen Sie dem Projekt eine neue Seite \(WPF\) mit dem Namen `ExpenseReportPage.xaml` hinzu.  
  
     Diese Seite zeigt die Spesenabrechnung für die Person an, die auf ExpenseItHome.xaml ausgewählt wird.  
  
7.  Öffnen Sie ExpenseReportPage.xaml.  
  
8.  Legen Sie den <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt \- View Expense" fest.  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:  
  
     [!code-xml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     Oder wie folgt in C\#:  
  
     [!code-xml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Öffnen Sie ExpenseItHome.xaml.vb und ExpenseReportPage.xaml.vb oder ExpenseItHome.xaml.cs und ExpenseReportPage.xaml.cs.  
  
     Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch eine CodeBehind\-Datei.  Diese CodeBehind\-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.  
  
     Der Code muss wie folgt aussehen.  
  
     [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
     [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
     [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
     [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Fügen Sie dem Projekt ein Bild mit dem Namen watermark.png hinzu.  Entweder erstellen Sie ein eigenes Bild, oder Sie kopieren die Datei aus dem Beispielcode.  Weitere Informationen hierzu finden Sie unter [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/de-de/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
<a name="Build_The_Application"></a>   
## Erstellen und Ausführen der Anwendung  
 In diesem Abschnitt erstellen Sie die Anwendung und führen sie aus.  
  
1.  Erstellen Sie die Anwendung, und führen Sie sie aus, indem Sie F5 drücken, oder wählen Sie **Debugging starten** im Menü **Debuggen** aus.  
  
     Die folgende Abbildung zeigt die Anwendung mit den <xref:System.Windows.Navigation.NavigationWindow>\-Schaltflächen.  
  
     ![Bildschirmabbildung für ExpenseIt&#45;Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2.  Schließen Sie die Anwendung, um zu [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] zurückzukehren.  
  
<a name="Add_Layout"></a>   
## Erstellen des Layouts  
 Das Layout bietet die Möglichkeit, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente auf geordnete Weise zu platzieren. Außerdem verwaltet es Größe und Position dieser Elemente, wenn die Größe einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] geändert wird.  In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 Jedes dieser Layoutsteuerelemente unterstützt einen speziellen Layouttyp für seine untergeordneten Elemente.  Die Größe von ExpenseIt\-Seiten kann geändert werden. Jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind.  Daher stellt <xref:System.Windows.Controls.Grid> das ideale Layoutelement für die Anwendung dar.  
  
> [!NOTE]
>  Weitere Informationen zu <xref:System.Windows.Controls.Panel>\-Elementen finden Sie unter [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md).  Weitere Informationen zu Layout finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Im Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10\-Pixel\-Rand durch Hinzufügen von Spalten\- und Zeilendefinitionen zu <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.  
  
1.  Öffnen Sie ExpenseItHome.xaml.  
  
2.  Legen Sie die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft im <xref:System.Windows.Controls.Grid>\-Element auf "10,0,10,10" für den linken, oberen, rechten und unteren Rand fest.  
  
3.  Fügen Sie folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zwischen den <xref:System.Windows.Controls.Grid>\-Tags hinzu, um die Zeilen\- und Spaltendefinitionen zu erstellen.  
  
     [!code-xml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     Die <xref:System.Windows.Controls.RowDefinition.Height%2A> von zwei Zeilen wird auf <xref:System.Windows.GridLength.Auto%2A> festgelegt, was bedeutet, dass die Größe der Zeilen auf dem Inhalt in den Zeilen basiert.  Die Standard\-<xref:System.Windows.Controls.RowDefinition.Height%2A> ist die <xref:System.Windows.GridUnitType>\-Größenanpassung, was bedeutet, dass die Zeile eine gewichtete Proportion des verfügbaren Platzes ist.  Wenn z. B. zwei Zeilen jeweils eine Höhe von "\*" haben, hat jede eine Höhe von der Hälfte des verfügbaren Platzes.  
  
     Das <xref:System.Windows.Controls.Grid> sollte jetzt wie der folgende XAML\-Code aussehen:  
  
     [!code-xml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
<a name="Add_Controls"></a>   
## Hinzufügen von Steuerelementen  
 In diesem Abschnitt wird die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Homepage aktualisiert, um eine Liste der Personen anzuzeigen, aus denen Benutzer eine Person auswählen können, um die zugehörige Spesenabrechnung anzuzeigen.  Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen.  Weitere Informationen finden Sie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md).  
  
 Um diese [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zu erstellen, werden ExpenseItHome.xaml die folgenden Elemente hinzugefügt:  
  
-   <xref:System.Windows.Controls.ListBox> \(für die Liste von Personen\)  
  
-   <xref:System.Windows.Controls.Label> \(für den Listenheader\)  
  
-   <xref:System.Windows.Controls.Button> \(zum Klicken, um die Spesenabrechnung für die Person anzuzeigen, die in der Liste ausgewählt ist\)  
  
 Jedes Steuerelement wird in einer Zeile von <xref:System.Windows.Controls.Grid> platziert, indem die angefügte <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=fullName>\-Eigenschaft festgelegt wird.  Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
1.  Öffnen Sie ExpenseItHome.xaml.  
  
2.  Fügen Sie folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zwischen den <xref:System.Windows.Controls.Grid>\-Tags hinzu.  
  
     [!code-xml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3.  Erstellen Sie die Anwendung, und führen Sie sie aus.  
  
 Die folgende Abbildung zeigt die Steuerelemente, die von XAML in diesem Abschnitt erstellt werden.  
  
 ![Bildschirmabbildung für ExpenseIt&#45;Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
<a name="Add_an_Image"></a>   
## Hinzufügen eines Bilds und eines Titels  
 In diesem Abschnitt wird die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Homepage mit einem Bild und einem Seitentitel aktualisiert.  
  
1.  Öffnen Sie ExpenseItHome.xaml.  
  
2.  Fügen Sie <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> eine weitere Spalte mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixel hinzu.  
  
     [!code-xml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3.  Fügen Sie <xref:System.Windows.Controls.Grid.RowDefinitions%2A> eine weitere Zeile hinzu.  
  
     [!code-xml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4.  Verschieben Sie die Steuerelemente in die zweite Spalte, indem Sie <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=fullName> auf 1 festlegen.  Verschieben Sie jedes Steuerelement eine Zeile nach unten, indem Sie <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=fullName> um 1 erhöhen.  
  
     [!code-xml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5.  Legen Sie den <xref:System.Windows.Controls.Panel.Background%2A> von <xref:System.Windows.Controls.Grid> auf die Bilddatei watermark.png fest.  
  
     [!code-xml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6.  Fügen Sie vor <xref:System.Windows.Controls.Border> eine <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report" als Titel der Seite hinzu.  
  
     [!code-xml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7.  Erstellen Sie die Anwendung, und führen Sie sie aus.  
  
 In der folgenden Abbildung sind die Ergebnisse dieses Abschnitts dargestellt.  
  
 ![Bildschirmabbildung für ExpenseIt&#45;Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
<a name="Add_Code_to_Process_Events"></a>   
## Schreiben von Code zum Behandeln von Ereignissen  
  
1.  Öffnen Sie ExpenseItHome.xaml.  
  
2.  Fügen Sie einen <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler zum <xref:System.Windows.Controls.Button>\-Element hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines einfachen Ereignishandlers](http://msdn.microsoft.com/de-de/b1456e07-9dec-4354-99cf-18666b64f480).  
  
     [!code-xml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3.  Öffnen Sie ExpenseItHome.xaml.vb oder ExpenseItHome.xaml.cs.  
  
4.  Fügen Sie folgenden Code zum <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler hinzu, der bewirkt, dass im Fenster zur Datei ExpenseReportPage.xaml navigiert wird.  
  
     [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
     [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
<a name="Create_the_UI_for_Pane2"></a>   
## Erstellen der Benutzeroberfläche für ExpenseReportPage  
 ExpenseReportPage.xaml zeigt die Spesenabrechnung für die Person an, die auf ExpenseItHome.xaml ausgewählt wurde.  In diesem Abschnitt werden Steuerelemente hinzugefügt und die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für ExpenseReportPage.xaml erstellt.  Außerdem werden den verschiedenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elementen Hintergrund und Füllfarben hinzugefügt.  
  
1.  Öffnen Sie ExpenseReportPage.xaml.  
  
2.  Fügen Sie folgenden XAML\-Code zwischen den <xref:System.Windows.Controls.Grid>\-Tags hinzu.  
  
     Dieses Benutzeroberfläche ähnelt der für "ExpenseItHome.xaml" erstellten Benutzeroberfläche, die Berichtsdaten werden hier jedoch in einem <xref:System.Windows.Controls.DataGrid> angezeigt.  
  
     [!code-xml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3.  Erstellen Sie die Anwendung, und führen Sie sie aus.  
  
    > [!NOTE]
    >  Falls ein Fehler angezeigt wird, dass das <xref:System.Windows.Controls.DataGrid> nicht gefunden wurde oder nicht vorhanden ist, überprüfen Sie, ob .NET Framework 4 als Zielversion für das Projekt festgelegt ist.  Weitere Informationen finden Sie unter [Gewusst wie: .NET Framework\-Version als Ziel](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
4.  Klicken Sie auf die Schaltfläche **Ansicht**.  
  
     Die Seite mit der Spesenabrechnung wird angezeigt.  
  
 Die folgende Abbildung zeigt die zu ExpenseReportPage.xaml hinzugefügten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente.  Beachten Sie, dass die Schaltflächen für die Navigation zurück aktiviert wird.  
  
 ![Bildschirmabbildung für ExpenseIt&#45;Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
<a name="Add_Code_to_Style_a_Control"></a>   
## Formatieren von Steuerelementen  
 Die Darstellung verschiedener Elemente ist häufig für alle Elemente desselben Typs in einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] identisch.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] verwendet Stile, damit Darstellungen in mehreren Elementen wieder verwendet werden können.  Die Wiederverwendbarkeit von Stilen vereinfacht die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Erstellung und \-Verwaltung.  Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.  
  
1.  Öffnen Sie Application.xaml oder App.xaml.  
  
2.  Fügen Sie folgenden XAML\-Code zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>\-Tags hinzu:  
  
     [!code-xml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fügt die folgenden Stile hinzu:  
  
    -   `headerTextStyle`: Zum Formatieren des Seitentitels <xref:System.Windows.Controls.Label>  
  
    -   `labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label>\-Steuerelemente.  
  
    -   `columnHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>  
  
    -   `listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border>\-Steuerelemente für Listenheader  
  
    -   `listHeaderTextStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label>\-Steuerelemente für Listenheader  
  
    -   `buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf ExpenseItHome.xaml.  
  
     Beachten Sie, dass es sich bei den Stilen um Ressourcen und untergeordnete Elemente des <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>\-Eigenschaftenelements handelt.  An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet.  Ein Beispiel zum Verwenden von Ressourcen in einer [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Anwendung finden Sie unter [Verwenden von Anwendungsressourcen](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).  
  
3.  Öffnen Sie ExpenseItHome.xaml.  
  
4.  Ersetzen Sie alles zwischen den <xref:System.Windows.Controls.Grid>\-Elementen durch den folgenden XAML\-Code.  
  
     [!code-xml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Die Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily>, die die Darstellung jedes Steuerelements definieren, werden entfernt und durch Anwenden der Stile ersetzt.  Der `headerTextStyle` wird z. B. auf die <xref:System.Windows.Controls.Label> "View Expense Report" angewendet.  
  
5.  Öffnen Sie ExpenseReportPage.xaml.  
  
6.  Ersetzen Sie alles zwischen den <xref:System.Windows.Controls.Grid>\-Elementen durch den folgenden XAML\-Code.  
  
     [!code-xml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     Damit werden den Elementen <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Border> Stile hinzugefügt.  
  
7.  Erstellen Sie die Anwendung, und führen Sie sie aus.  
  
     Nachdem Sie in diesem Abschnitt [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hinzugefügt haben, sieht die Anwendung genauso aus wie vor der Aktualisierung mit Stilen.  
  
<a name="Bind_Data_to_a_Control"></a>   
## Binden von Daten an ein Steuerelement  
 In diesem Abschnitt erstellen Sie die [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Daten, die an verschiedene Steuerelemente gebunden werden.  
  
1.  Öffnen Sie ExpenseItHome.xaml.  
  
2.  Fügen Sie nach dem öffnenden <xref:System.Windows.Controls.Grid>\-Element den folgenden XAML\-Code hinzu, um einen <xref:System.Windows.Data.XmlDataProvider> zu erstellen, der die Daten für jede Person enthält.  
  
     Die Daten werden als <xref:System.Windows.Controls.Grid>\-Ressource erstellt.  Normalerweise würde diese als Datei geladen, der Einfachheit halber werden die Daten jedoch inline hinzugefügt.  
  
     [!code-xml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3.  Fügen Sie in der <xref:System.Windows.Controls.Grid>\-Ressource die folgende <xref:System.Windows.DataTemplate> hinzu, die definiert, wie die Daten im <xref:System.Windows.Controls.ListBox> angezeigt werden.  Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
     [!code-xml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4.  Ersetzen Sie das vorhandene <xref:System.Windows.Controls.ListBox> durch folgenden XAML\-Code.  
  
     [!code-xml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Dieser XAML\-Code bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>\-Eigenschaft von <xref:System.Windows.Controls.ListBox> an die Datenquelle und übernimmt die Datenvorlage als <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.  
  
<a name="Connect_Data_to_Controls"></a>   
## Verbinden von Daten mit Steuerelementen  
 In diesem Abschnitt schreiben Sie Code, der das aktuelle Element, das in der Liste der Personen auf der Seite ExpenseItHome.xaml ausgewählt wurde, abruft und den zugehörigen Verweis an den Konstruktor der `ExpenseReportPage` während der Instanziierung übergibt.  `ExpenseReportPage` legt den Datenkontext mithilfe des übergebenen Elements fest, und die in ExpenseReportPage.xaml definierten Steuerelemente werden daran gebunden.  
  
1.  Öffnen Sie ExpenseReportPage.xaml.vb oder ExpenseReportPage.xaml.cs.  
  
2.  Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.  
  
     [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
     [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3.  Öffnen Sie ExpenseItHome.xaml.vb oder ExpenseItHome.xaml.cs.  
  
4.  Ändern Sie den <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignishandler, um den neuen Konstruktor aufzurufen, der die Spesenabrechnungsdaten der ausgewählten Person übergibt.  
  
     [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
     [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
<a name="Add_Style_to_Data"></a>   
## Formatieren von Daten mit Datenvorlagen  
 In diesem Abschnitt aktualisieren Sie mithilfe von Datenvorlagen die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für jedes Element in den datengebundenen Listen.  
  
1.  Öffnen Sie ExpenseReportPage.xaml.  
  
2.  Binden Sie den Inhalt der <xref:System.Windows.Controls.Label>\-Elemente "Name" und "Department" an die entsprechende Datenquelleneigenschaft.  Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     [!code-xml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3.  Fügen Sie nach dem öffnenden <xref:System.Windows.Controls.Grid>\-Element die folgenden Datenvorlagen hinzu, die definieren, wie die Spesenabrechnungsdaten angezeigt werden.  
  
     [!code-xml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4.  Wenden Sie die Vorlagen auf die <xref:System.Windows.Controls.DataGrid>\-Spalten an, in denen die Spesenabrechnungsdaten angezeigt werden.  
  
     [!code-xml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5.  Erstellen Sie die Anwendung, und führen Sie sie aus.  
  
6.  Wählen Sie eine Person aus, und klicken Sie auf die Schaltfläche **Ansicht**.  
  
 Die folgende Abbildung zeigt die beiden Seiten der ExpenseIt\-Anwendung mit angewendeten Steuerelementen, Stilen, Datenbindungen, Datenvorlagen und Layout.  
  
 ![Bildschirmabbildungen für ExpenseIt&#45;Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
<a name="Best_Practices"></a>   
## Bewährte Methoden  
 In diesem Beispiel soll nur eine bestimmte Funktion von WPF veranschaulicht werden, daher werden die bewährten Methoden für die Anwendungsentwicklung nicht befolgt.  Ausführliche Informationen über bewährte Methoden bei der Anwendungsentwicklung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] finden Sie unter folgenden Themen:  
  
-   Barrierefreiheit – [Bewährte Methoden für Eingabehilfen](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Sicherheit – [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Lokalisierung – [Übersicht über WPF\-Globalisierung und \-Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Leistung – [Optimieren der WPF\-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
<a name="Whats_Next"></a>   
## Weitere Informationen  
 Ihnen stehen jetzt eine Reihe von Techniken zur Verfügung, die Sie beim Erstellen einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verwenden können.  Sie sollten jetzt fundierte Kenntnisse über die grundlegenden Bausteine einer datengebundenen [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Anwendung haben.  Dieses Thema kann natürlich keinen Anspruch auf Vollständigkeit erheben, aber sicherlich haben Sie jetzt ein Gespür für einige der Möglichkeiten, die Sie noch zusätzlich zu den in diesem Thema veranschaulichten Techniken entdecken können.  
  
 Weitere Informationen zur WPF\-Architektur und Programmiermodellen finden Sie unter den folgenden Themen:  
  
-   [WPF\-Architektur](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Weitere Informationen zum Erstellen von Anwendungen finden Sie unter den folgenden Themen:  
  
-   [Anwendungsentwicklung](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Steuerelemente](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Grafiken und Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## Siehe auch  
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Stile und Vorlagen](../../../../docs/framework/wpf/controls/styles-and-templates.md)