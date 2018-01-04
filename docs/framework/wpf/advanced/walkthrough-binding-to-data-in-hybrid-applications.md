---
title: 'Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen'
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
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3afc0d2eabb7554d64a40863b182a6edefe169f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen
Binden einer Datenquelle an ein Steuerelement ist wichtig für das Bereitstellen von Benutzern mit Zugriff auf die zugrunde liegenden Daten, unabhängig davon, ob Sie sind [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die Datenbindung in hybridanwendungen verwenden können, die beide enthalten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Definieren der Datenvorlage.  
  
-   Angeben des Formularlayouts.  
  
-   Angeben von Datenbindungen.  
  
-   Anzeigen von Daten mithilfe von Interoperation.  
  
-   Hinzufügen der Datenquelle zum Projekt.  
  
-   Bindung an die Datenquelle.  
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Binden von Daten in Anwendungen Hybridbeispiel](http://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Anschließend werden Sie verstehen, welche Rolle Datenbindungsfunktionen bei Hybridanwendungen spielen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
-   Zugriff auf die Beispieldatenbank Northwind für Microsoft SQL Server ausgeführt wird.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein  
  
1.  Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WPFWithWFAndDatabinding`.  
  
2.  Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Öffnen Sie "MainWindow.xaml" in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  In der <xref:System.Windows.Window> Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespacezuordnung.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Benennen Sie die Standardeinstellung <xref:System.Windows.Controls.Grid> Element `mainGrid` durch Zuweisen der <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft.  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>Definieren der Datenvorlage  
 Die Masterliste der Kunden wird angezeigt, einem <xref:System.Windows.Controls.ListBox> Steuerelement. Das folgende Codebeispiel definiert eine <xref:System.Windows.DataTemplate> Objekt mit dem Namen `ListItemsTemplate` , steuert die visuelle Struktur der <xref:System.Windows.Controls.ListBox> Steuerelement. Dies <xref:System.Windows.DataTemplate> zugewiesen ist die <xref:System.Windows.Controls.ListBox> des Steuerelements <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft.  
  
#### <a name="to-define-the-data-template"></a>Definieren der Datenvorlage  
  
-   Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>Angeben des Formularlayouts  
 Das Layout des Formulars wird durch ein Raster mit drei Zeilen und drei Spalten definiert. <xref:System.Windows.Controls.Label>Steuerelemente werden bereitgestellt, um jede Spalte in der Customers-Tabelle zu identifizieren.  
  
#### <a name="to-set-up-the-grid-layout"></a>Einrichten des Rasterlayouts  
  
-   Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>Label-Steuerelemente einrichten  
  
-   Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>Angeben von Datenbindungen  
 Die Masterliste der Kunden wird angezeigt, einem <xref:System.Windows.Controls.ListBox> Steuerelement. Der angefügte `ListItemsTemplate` bindet ein <xref:System.Windows.Controls.TextBlock> die Steuerung an die `ContactName` Feld aus der Datenbank.  
  
 Die Details für jeden Kundendatensatz werden angezeigt, in mehreren <xref:System.Windows.Controls.TextBox> Steuerelemente.  
  
#### <a name="to-specify-data-bindings"></a>Datenbindungen angeben  
  
-   Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     Die <xref:System.Windows.Data.Binding> -Klasse bindet die <xref:System.Windows.Controls.TextBox> Steuerelemente mit den entsprechenden Feldern in der Datenbank.  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>Anzeigen von Daten mithilfe von Interoperation  
 Werden die Aufträge entsprechen, die dem ausgewählten Kunden angezeigt, einem <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> Steuerelement namens `dataGridView1`. Die `dataGridView1` Steuerelement an die Datenquelle in der Code-Behind-Datei gebunden ist. Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement ist das übergeordnete Element dieses [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>Anzeigen von Daten im DataGridView-Steuerelement  
  
-   Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>Hinzufügen der Datenquelle zum Projekt  
 Mit [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], Sie können problemlos eine Datenquelle zu Ihrem Projekt hinzufügen. Bei diesem Vorgang wird dem Projekt ein stark typisiertes Dataset hinzugefügt. Mehrere andere Unterstützungsklassen, wie z.B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.  
  
#### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu  
  
1.  Aus der **Daten** klicken Sie im Menü **neue Datenquelle hinzufügen**.  
  
2.  In der **Data Source Configuration Wizard**, erstellen Sie eine Verbindung zur Northwind-Datenbank unter Verwendung eines Datasets. Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Verbindung mit Daten in einer Datenbank](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).  
  
3.  Wenn Sie aufgefordert werden durch die **Datenquellen Konfigurations-Assistenten**, Speichern der Verbindungszeichenfolge als `NorthwindConnectionString`.  
  
4.  Wenn Sie aufgefordert werden, um Datenbankobjekte auszuwählen, wählen Sie die `Customers` und `Orders` Tabellen und der Name der generierten DataSet `NorthwindDataSet`.  
  
## <a name="binding-to-the-data-source"></a>Bindung an die Datenquelle  
 Die <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Komponente bietet eine einheitliche Schnittstelle für die Anwendung die Datenquelle. Die Bindung an die Datenquelle wird in der CodeBehind-Datei implementiert.  
  
#### <a name="to-bind-to-the-data-source"></a>Bindung an die Datenquelle  
  
1.  Öffnen Sie die CodeBehind-Datei mit die Namen „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.  
  
2.  Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.  
  
     Dieser Code deklariert die <xref:System.Windows.Forms.BindingSource> Komponente und zugeordnete Hilfsklassen, die mit der Datenbank herstellen.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  Kopieren Sie den folgenden Code in den Konstruktor.  
  
     Dieser Code erstellt und initialisiert die <xref:System.Windows.Forms.BindingSource> Komponente.  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  Öffnen Sie „MainWindow.xaml“.  
  
5.  Wählen Sie in der Entwurfsansicht oder der XAML-Ansicht, die <xref:System.Windows.Window> Element.  
  
6.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.  
  
7.  Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.  
  
8.  Kopieren Sie den folgenden Code in der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.  
  
     Dieser Code weist die <xref:System.Windows.Forms.BindingSource> -Komponente als Datenkontext und füllt die `Customers` und `Orders` adapterobjekten.  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.  
  
     Diese Methode behandelt das <xref:System.Windows.Data.CollectionView.CurrentChanged> Ereignis und aktualisiert das aktuelle Element der Datenbindung.  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF-Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Im Beispiel für Hybrid-Anwendungen Binden von Daten](http://go.microsoft.com/fwlink/?LinkID=159983)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
