---
title: 'Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: ef5f14cdbecab8bc780cb7b2a642429970a25316
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972274"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen

Das Binden einer Datenquelle an ein Steuerelement ist entscheidend, um Benutzern den Zugriff auf die zugrunde liegenden Daten zu [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gewähren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], egal ob Sie oder verwenden. Diese exemplarische Vorgehensweise zeigt, wie Sie die Datenbindung in Hybrid Anwendungen verwenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] können [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , die sowohl-als auch-Steuerelemente enthalten

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts.

- Definieren der Datenvorlage.

- Angeben des Formularlayouts.

- Angeben von Datenbindungen.

- Anzeigen von Daten mithilfe von Interoperation.

- Hinzufügen der Datenquelle zum Projekt.

- Bindung an die Datenquelle.

Eine komplette Code Auflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden Sie unter Beispiel für die [Datenbindung in Hybrid Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159983).

Anschließend werden Sie verstehen, welche Rolle Datenbindungsfunktionen bei Hybridanwendungen spielen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio.

- Zugriff auf die Beispieldatenbank Northwind, die auf Microsoft SQL Server ausgeführt wird.

## <a name="creating-the-project"></a>Erstellen des Projekts

### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein

1. Erstellen Sie ein WPF-Anwendungs `WPFWithWFAndDatabinding`Projekt mit dem Namen.

2. Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Öffnen Sie die [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]Datei "MainWindow. XAML" im.

4. Fügen Sie im- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ElementdiefolgendeNamespaceZuordnunghinzu.<xref:System.Windows.Window>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Benennen Sie das <xref:System.Windows.Controls.Grid> Standard `mainGrid` Element, indem <xref:System.Windows.FrameworkElement.Name%2A> Sie die-Eigenschaft zuweisen.

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>Definieren der Datenvorlage

Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox> -Steuerelement angezeigt. Im folgenden Codebeispiel wird ein <xref:System.Windows.DataTemplate> -Objekt `ListItemsTemplate` mit dem Namen definiert, das <xref:System.Windows.Controls.ListBox> die visuelle Struktur des Steuer Elements steuert. Diese <xref:System.Windows.DataTemplate> wird der <xref:System.Windows.Controls.ListBox> -<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft des-Steuer Elements zugewiesen.

### <a name="to-define-the-data-template"></a>Definieren der Datenvorlage

- Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in die Deklaration des Elements.

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>Angeben des Formularlayouts

Das Layout des Formulars wird durch ein Raster mit drei Zeilen und drei Spalten definiert. <xref:System.Windows.Controls.Label>Steuerelemente werden bereitgestellt, um jede Spalte in der Customers-Tabelle zu identifizieren.

### <a name="to-set-up-the-grid-layout"></a>Einrichten des Rasterlayouts

- Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in die Deklaration des Elements.

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>Label-Steuerelemente einrichten

- Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in die Deklaration des Elements.

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>Angeben von Datenbindungen

Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox> -Steuerelement angezeigt. Der angefügte `ListItemsTemplate` bindet <xref:System.Windows.Controls.TextBlock> ein-Steuer `ContactName` Element an das Feld aus der Datenbank.

Die Details der einzelnen Kundendaten Sätze werden in mehreren <xref:System.Windows.Controls.TextBox> Steuerelementen angezeigt.

### <a name="to-specify-data-bindings"></a>Datenbindungen angeben

- Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in die Deklaration des Elements.

     Die <xref:System.Windows.Data.Binding> -Klasse bindet <xref:System.Windows.Controls.TextBox> die Steuerelemente an die entsprechenden Felder in der Datenbank.

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>Anzeigen von Daten mithilfe von Interoperation

Die Aufträge, die dem ausgewählten Kunden entsprechen, werden in <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> einem- `dataGridView1`Steuerelement mit dem Namen angezeigt. Das `dataGridView1` -Steuerelement wird an die Datenquelle in der Code-Behind-Datei gebunden. Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Steuerelement ist das über [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] geordnete Element dieses Steuer Elements.

### <a name="to-display-data-in-the-datagridview-control"></a>Anzeigen von Daten im DataGridView-Steuerelement

- Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in die Deklaration des Elements.

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>Hinzufügen der Datenquelle zum Projekt

Mit Visual Studio können Sie Ihrem Projekt problemlos eine Datenquelle hinzufügen. Bei diesem Vorgang wird dem Projekt ein stark typisiertes Dataset hinzugefügt. Mehrere andere Unterstützungsklassen, wie z.B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.

### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu

1. Wählen Sie im Menü **Daten** die Option **neue Datenquelle hinzufügen**aus.

2. Erstellen Sie im **Assistenten zum Konfigurieren von Datenquellen**eine Verbindung mit der Northwind-Datenbank, indem Sie ein DataSet verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Stellen Sie eine Verbindung mit Daten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))in einer Datenbank her.

3. Wenn Sie vom **Assistenten zum Konfigurieren von Datenquellen**dazu aufgefordert werden, speichern Sie die `NorthwindConnectionString`Verbindungs Zeichenfolge als.

4. Wenn Sie zur Auswahl der Datenbankobjekte aufgefordert werden, wählen `Customers` Sie `Orders` die Tabellen und aus, und `NorthwindDataSet`benennen Sie das generierte Dataset.

## <a name="binding-to-the-data-source"></a>Bindung an die Datenquelle

Die <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Komponente stellt eine einheitliche Schnittstelle für die Datenquelle der Anwendung bereit. Die Bindung an die Datenquelle wird in der CodeBehind-Datei implementiert.

### <a name="to-bind-to-the-data-source"></a>Bindung an die Datenquelle

1. Öffnen Sie die CodeBehind-Datei mit die Namen „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.

2. Kopieren Sie den folgenden Code in `MainWindow` die Klassendefinition.

     Dieser Code deklariert die <xref:System.Windows.Forms.BindingSource> -Komponente und zugehörige Hilfsklassen, die eine Verbindung mit der-Datenbank herstellen.

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Kopieren Sie den folgenden Code in den Konstruktor.

     Dieser Code erstellt und initialisiert die <xref:System.Windows.Forms.BindingSource> Komponente.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Öffnen Sie „MainWindow.xaml“.

5. Wählen Sie in Designansicht-oder XAML- <xref:System.Windows.Window> Ansicht das-Element aus.

6. Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .

7. Doppelklicken Sie auf <xref:System.Windows.FrameworkElement.Loaded> das Ereignis.

8. Kopieren Sie den folgenden Code in <xref:System.Windows.FrameworkElement.Loaded> den-Ereignishandler.

     Dieser Code weist die <xref:System.Windows.Forms.BindingSource> Komponente als Datenkontext zu und füllt die `Customers` Adapter Objekte `Orders` und auf.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Kopieren Sie den folgenden Code in `MainWindow` die Klassendefinition.

     Diese Methode behandelt das <xref:System.Windows.Data.CollectionView.CurrentChanged> -Ereignis und aktualisiert das aktuelle Element der Datenbindung.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Beispiel für Datenbindung in Hybrid Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Exemplarische Vorgehensweise: Hosting eines Windows Forms zusammengesetzten Steuer Elements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
