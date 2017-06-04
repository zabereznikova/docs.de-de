---
title: "Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen | Microsoft Docs"
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
  - "Datenbindung [WPF-Interoperabilität]"
  - "Hybridanwendungen [WPF-Interoperabilität]"
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen
Die Bindung einer Datenquelle an ein Steuerelement ist äußerst wichtig, um Benutzern den Zugriff auf zugrunde liegende Daten zu ermöglichen, unabhängig davon, ob Sie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwenden.  In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie Datenbindung in Hybridanwendungen verwenden können, die sowohl [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente als auch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelemente enthalten.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Definieren der Datenvorlage.  
  
-   Angeben des Formularlayouts.  
  
-   Angeben von Datenbindungen.  
  
-   Anzeigen von Daten durch Verwenden von Interoperation.  
  
-   Hinzufügen der Datenquelle zum Projekt.  
  
-   Binden an die Datenquelle.  
  
 Eine vollständige Codeauflistung der in dieser exemplarischen Vorgehensweise veranschaulichten Aufgaben finden Sie unter [Beispiel zur Datenbindung in Hybridanwendungen](http://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Anschließend werden Sie verstehen, welche Rolle Datenbindungsfeatures in Hybridanwendungen spielen.  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Zugriff auf die Beispieldatenbank Northwind, die unter Microsoft SQL Server ausgeführt wird.  
  
## Erstellen des Projekts  
  
#### So erstellen Sie das Projekt und richten es ein  
  
1.  Erstellen Sie ein WPF\-Anwendungsprojekt mit dem Namen `WPFWithWFAndDatabinding`.  
  
2.  Fügen Sie im Projektmappen\-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Öffnen Sie im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] die Datei MainWindow.xaml.  
  
4.  Fügen Sie im <xref:System.Windows.Window>\-Element die folgende [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Namespacezuordnung hinzu.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Nennen Sie das <xref:System.Windows.Controls.Grid>\-Standardelement `mainGrid`, indem Sie die <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft zuweisen.  
  
     [!code-xml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## Definieren der Datenvorlage  
 Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox>\-Steuerelement angezeigt.  Im folgenden Codebeispiel wird ein <xref:System.Windows.DataTemplate>\-Objekt mit dem Namen `ListItemsTemplate` definiert, das die visuelle Struktur des <xref:System.Windows.Controls.ListBox>\-Steuerelements steuert.  Diese <xref:System.Windows.DataTemplate> wird der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>\-Eigenschaft des <xref:System.Windows.Controls.ListBox>\-Steuerelements zugewiesen.  
  
#### So definieren Sie die Datenvorlage  
  
-   Kopieren Sie den folgenden XAML\-Code in die Deklaration des <xref:System.Windows.Controls.Grid>\-Elements.  
  
     [!code-xml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## Angeben des Formularlayouts  
 Das Layout des Formulars wird von einem Raster mit drei Zeilen und drei Spalten definiert.  Es werden <xref:System.Windows.Controls.Label>\-Steuerelemente bereitgestellt, um jede Spalte in der Kundentabelle zu identifizieren.  
  
#### So richten Sie das Rasterlayout ein  
  
-   Kopieren Sie den folgenden XAML\-Code in die Deklaration des <xref:System.Windows.Controls.Grid>\-Elements.  
  
     [!code-xml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### So richten Sie die Label\-Steuerelemente ein  
  
-   Kopieren Sie den folgenden XAML\-Code in die Deklaration des <xref:System.Windows.Controls.Grid>\-Elements.  
  
     [!code-xml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## Angeben von Datenbindungen  
 Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox>\-Steuerelement angezeigt.  Die angefügte `ListItemsTemplate` bindet ein <xref:System.Windows.Controls.TextBlock>\-Steuerelement an das `ContactName`\-Feld der Datenbank.  
  
 Die Details für jeden Kundendatensatz werden in mehreren <xref:System.Windows.Controls.TextBox>\-Steuerelementen angezeigt.  
  
#### So geben Sie Datenbindungen an  
  
-   Kopieren Sie den folgenden XAML\-Code in die Deklaration des <xref:System.Windows.Controls.Grid>\-Elements.  
  
     Die <xref:System.Windows.Data.Binding>\-Klasse bindet die <xref:System.Windows.Controls.TextBox>\-Steuerelemente an die entsprechenden Felder in der Datenbank.  
  
     [!code-xml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## Anzeigen von Daten mithilfe von Interoperation  
 Die Aufträge, die dem ausgewählten Kunden entsprechen, werden in einem <xref:System.Windows.Forms.DataGridView?displayProperty=fullName>\-Steuerelement mit dem Namen `dataGridView1` angezeigt.  Das `dataGridView1`\-Steuerelement wird an die Datenquelle in der Code\-Behind\-Datei gebunden.  Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement ist das übergeordnete Element dieses [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelements.  
  
#### So zeigen Sie Daten im DataGridView\-Steuerelement an  
  
-   Kopieren Sie den folgenden XAML\-Code in die Deklaration des <xref:System.Windows.Controls.Grid>\-Elements.  
  
     [!code-xml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## Hinzufügen der Datenquelle zum Projekt  
 Mit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] können Sie dem Projekt einfach eine Datenquelle hinzufügen.  Durch diesen Vorgang wird dem Projekt ein Dataset mit strikter Typbindung hinzugefügt.  Mehrere andere Unterstützungsklassen, z. B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.  
  
#### So fügen Sie die Datenquelle hinzu  
  
1.  Wählen Sie im Menü **Daten** die Option **Neue Datenquelle hinzufügen** aus.  
  
2.  Erstellen Sie im **Assistenten zum Konfigurieren von Datenquellen** mithilfe eines Dataset eine Verbindung mit der Northwind\-Datenbank.  Weitere Informationen finden Sie unter [Gewusst wie: Herstellen einer Verbindung zu Daten in einer Datenbank](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md).  
  
3.  Wenn Sie vom **Assistenten zum Konfigurieren von Datenquellen** dazu aufgefordert werden, speichern Sie die Verbindungszeichenfolge als `NorthwindConnectionString`.  
  
4.  Wenn Sie zur Auswahl der Datenbankobjekte aufgefordert werden, wählen Sie die Tabellen `Orders` und `Customers` aus, und geben Sie für das generierte Dataset den Namen `NorthwindDataSet` ein.  
  
## Binden an die Datenquelle  
 Die <xref:System.Windows.Forms.BindingSource?displayProperty=fullName>\-Komponente stellt eine einheitliche Schnittstelle für die Datenquelle der Anwendung bereit.  Das Binden an die Datenquelle wird in der Code\-Behind\-Datei implementiert.  
  
#### So binden Sie an die Datenquelle  
  
1.  Öffnen Sie die CodeBehind\-Datei mit dem Namen "MainWindow.xaml.vb" oder "MainWindow.xaml.cs".  
  
2.  Kopieren Sie den folgenden Code in die `MainWindow`\-Klassendefinition.  
  
     In diesem Code werden die <xref:System.Windows.Forms.BindingSource>\-Komponente und zugeordnete Hilfsklassen, die eine Verbindung mit der Datenbank herstellen, deklariert.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  Kopieren Sie den folgenden Code in den Konstruktor.  
  
     Durch diesen Code wird die <xref:System.Windows.Forms.BindingSource>\-Komponente erstellt und initialisiert.  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  Öffnen Sie MainWindow.xaml.  
  
5.  Wählen Sie in der Designansicht oder XAML\-Ansicht das <xref:System.Windows.Window>\-Element aus.  
  
6.  Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse**.  
  
7.  Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis.  
  
8.  Kopieren Sie den folgenden Code in den <xref:System.Windows.FrameworkElement.Loaded>\-Ereignishandler.  
  
     Durch diesen Code wird die <xref:System.Windows.Forms.BindingSource>\-Komponente als Datenkontext zugewiesen, und die `Customers`\- und `Orders`\-Adapterobjekte werden aufgefüllt.  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. Kopieren Sie den folgenden Code in die `MainWindow`\-Klassendefinition.  
  
     Diese Methode behandelt das <xref:System.Windows.Data.CollectionView.CurrentChanged>\-Ereignis und aktualisiert das aktuelle Element der Datenbindung.  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Beispiel zur Datenbindung in Hybridanwendungen](http://go.microsoft.com/fwlink/?LinkID=159983)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)