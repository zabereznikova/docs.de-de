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
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794224"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen

Das Binden einer Datenquelle an ein Steuerelement ist entscheidend, um Benutzern den Zugriff auf die zugrunde liegenden Daten zu gewähren, unabhängig davon, ob Sie Windows Forms oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwenden. In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die Datenbindung in Hybrid Anwendungen verwenden können, die sowohl Windows Forms als auch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente enthalten

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts

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

- Visual Studio erstellen.

- Zugriff auf die Beispieldatenbank Northwind, die auf Microsoft SQL Server ausgeführt wird.

## <a name="creating-the-project"></a>Erstellen des Projekts

### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein

1. Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WPFWithWFAndDatabinding`.

2. Fügen Sie im Projektmappen-Explorer die Verweise auf die folgenden Assemblys hinzu.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.

4. Fügen Sie im <xref:System.Windows.Window>-Element die folgenden Windows Forms Namespace Zuordnung hinzu.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Benennen Sie die Standard <xref:System.Windows.Controls.Grid> Element `mainGrid`, indem Sie die <xref:System.Windows.FrameworkElement.Name%2A>-Eigenschaft zuweisen.

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>Definieren der Datenvorlage

Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox>-Steuerelement angezeigt. Im folgenden Codebeispiel wird ein <xref:System.Windows.DataTemplate> Objekt mit dem Namen `ListItemsTemplate` definiert, das die visuelle Struktur des <xref:System.Windows.Controls.ListBox>-Steuer Elements steuert. Diese <xref:System.Windows.DataTemplate> wird der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> Steuer Elements zugewiesen.

### <a name="to-define-the-data-template"></a>Definieren der Datenvorlage

- Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>Angeben des Formularlayouts

Das Layout des Formulars wird durch ein Raster mit drei Zeilen und drei Spalten definiert. <xref:System.Windows.Controls.Label>-Steuerelemente werden bereitgestellt, um jede Spalte in der Customers-Tabelle zu identifizieren.

### <a name="to-set-up-the-grid-layout"></a>Einrichten des Rasterlayouts

- Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>Label-Steuerelemente einrichten

- Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>Angeben von Datenbindungen

Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox>-Steuerelement angezeigt. Der angefügte `ListItemsTemplate` bindet ein <xref:System.Windows.Controls.TextBlock> Steuerelement an das `ContactName` Feld aus der Datenbank.

Die Details der einzelnen Kundendaten Sätze werden in mehreren <xref:System.Windows.Controls.TextBox>-Steuerelementen angezeigt.

### <a name="to-specify-data-bindings"></a>Datenbindungen angeben

- Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.

     Die <xref:System.Windows.Data.Binding>-Klasse bindet die <xref:System.Windows.Controls.TextBox>-Steuerelemente an die entsprechenden Felder in der Datenbank.

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>Anzeigen von Daten mithilfe von Interoperation

Die Aufträge, die dem ausgewählten Kunden entsprechen, werden in einem <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType>-Steuerelement mit dem Namen `dataGridView1`angezeigt. Das `dataGridView1`-Steuerelement ist an die Datenquelle in der Code-Behind-Datei gebunden. Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement ist das übergeordnete Element dieses Windows Forms Steuer Elements.

### <a name="to-display-data-in-the-datagridview-control"></a>Anzeigen von Daten im DataGridView-Steuerelement

- Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>Hinzufügen der Datenquelle zum Projekt

Mit Visual Studio können Sie Ihrem Projekt problemlos eine Datenquelle hinzufügen. Bei diesem Vorgang wird dem Projekt ein stark typisiertes Dataset hinzugefügt. Mehrere andere Unterstützungsklassen, wie z.B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.

### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu

1. Wählen Sie im Menü **Daten** die Option **neue Datenquelle hinzufügen**aus.

2. Erstellen Sie im **Assistenten zum Konfigurieren von Datenquellen**eine Verbindung mit der Northwind-Datenbank, indem Sie ein DataSet verwenden. Weitere Informationen finden Sie unter [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).

3. Wenn Sie vom **Assistenten zum Konfigurieren von Datenquellen**dazu aufgefordert werden, speichern Sie die Verbindungs Zeichenfolge als `NorthwindConnectionString`.

4. Wenn Sie zur Auswahl der Datenbankobjekte aufgefordert werden, wählen Sie die `Customers`-und `Orders` Tabellen aus, und benennen Sie das generierte Dataset `NorthwindDataSet`.

## <a name="binding-to-the-data-source"></a>Bindung an die Datenquelle

Die <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Komponente stellt eine einheitliche Schnittstelle für die Datenquelle der Anwendung bereit. Die Bindung an die Datenquelle wird in der CodeBehind-Datei implementiert.

### <a name="to-bind-to-the-data-source"></a>Bindung an die Datenquelle

1. Öffnen Sie die CodeBehind-Datei mit die Namen „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.

2. Kopieren Sie den folgenden Code in die Definition der `MainWindow`-Klasse.

     Dieser Code deklariert die <xref:System.Windows.Forms.BindingSource> Komponente und zugeordnete Hilfsklassen, die eine Verbindung mit der Datenbank herstellen.

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Kopieren Sie den folgenden Code in den Konstruktor.

     Dieser Code erstellt und initialisiert die <xref:System.Windows.Forms.BindingSource> Komponente.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Öffnen Sie „MainWindow.xaml“.

5. Wählen Sie in Designansicht-oder XAML-Ansicht das <xref:System.Windows.Window> Element aus.

6. Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .

7. Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.

8. Kopieren Sie den folgenden Code in den <xref:System.Windows.FrameworkElement.Loaded>-Ereignishandler.

     Dieser Code weist die <xref:System.Windows.Forms.BindingSource> Komponente als Datenkontext zu und füllt die `Customers` und `Orders` Adapter Objekte auf.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Kopieren Sie den folgenden Code in die Definition der `MainWindow`-Klasse.

     Diese Methode behandelt das <xref:System.Windows.Data.CollectionView.CurrentChanged>-Ereignis und aktualisiert das aktuelle Element der Datenbindung.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Beispiel für Datenbindung in Hybrid Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
