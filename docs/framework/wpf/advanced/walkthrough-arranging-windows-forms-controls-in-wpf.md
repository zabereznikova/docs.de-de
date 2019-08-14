---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972312"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF

In dieser exemplarischen Vorgehensweise erfahren Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , wie Sie mithilfe [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] von Layoutfunktionen Steuerelemente in einer Hybrid Anwendung anordnen.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts.

- Verwenden der Standardlayouteinstellungen.

- Anpassen der Größe an Inhalt.

- Verwenden der absoluten Positionierung.

- Explizites Angeben der Größe.

- Festlegen der Layouteigenschaften.

- Grundlegendes zu Einschränkungen der Z-Reihenfolge.

- Andocken.

- Einstellen der Sichtbarkeit.

- Hosten eines Steuerelements, das nicht gestreckt wird.

- Skalieren.

- Drehen.

- Einstellen von Abständen und Rändern.

- Verwenden von dynamischen Layoutcontainern.

Eine umfassende Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971).

Wenn Sie fertig sind, verfügen Sie über ein Verständnis der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layoutfeatures [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]in-basierten Anwendungen.

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="creating-the-project"></a>Erstellen des Projekts

### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein

1. Erstellen Sie ein WPF-Anwendungs `WpfLayoutHostingWf`Projekt mit dem Namen.

2. Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.

    - WindowsFormsIntegration

    - System.Windows.Forms

    - System.Drawing

3. Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.

4. Fügen Sie im- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ElementdiefolgendeNamespaceZuordnunghinzu.<xref:System.Windows.Window>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Legen Sie im- <xref:System.Windows.Controls.Grid.ShowGridLines%2A> `true` Element die-Eigenschaft auf fest, und definieren Sie fünf Zeilen und drei Spalten. <xref:System.Windows.Controls.Grid>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen

Standardmäßig behandelt das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement.

### <a name="to-use-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. <xref:System.Windows.Controls.Canvas>Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuer<xref:System.Windows.Forms.Button?displayProperty=nameWithType> Element wird in der angezeigt. Das gehostete Steuerelement wird basierend auf seinem Inhalt angepasst, <xref:System.Windows.Forms.Integration.WindowsFormsHost> und das Element wird für das gehostete Steuerelement angepasst.

## <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt

Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt sicher, dass das gehostete Steuerelement seine Inhalte ordnungsgemäß anzeigt.

### <a name="to-size-to-content"></a>Anpassen der Größe an Inhalt

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die zwei neuen Schaltflächen-Steuerelemente werden angepasst, um die längere Text Zeichenfolge und eine größere <xref:System.Windows.Forms.Integration.WindowsFormsHost> Schriftgröße korrekt anzuzeigen, und die Elemente werden angepasst, um die gehosteten Steuerelemente anzupassen.

## <a name="using-absolute-positioning"></a>Verwenden der absoluten Positionierung

Sie können die absolute Positionierung verwenden, um <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Element an einer beliebigen Stelle in der Benutzeroberfläche (UI) zu platzieren.

### <a name="to-use-absolute-positioning"></a>Verwenden der absoluten Positionierung

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird 20 Pixel von der oberen Seite der Raster Zelle und 20 Pixel von Links platziert.

## <a name="specifying-size-explicitly"></a>Explizites Angeben der Größe

Sie können die Größe des <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Elements mithilfe der <xref:System.Windows.FrameworkElement.Width%2A> -Eigenschaft <xref:System.Windows.FrameworkElement.Height%2A> und der-Eigenschaft angeben.

### <a name="to-specify-size-explicitly"></a>Explizites Angeben der Größe

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird auf eine Größe von 50 Pixel Breite um 70 Pixel hoch festgelegt, die kleiner ist als die Standardlayouteinstellungen. Der Inhalt des [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements wird entsprechend neu angeordnet.

## <a name="setting-layout-properties"></a>Festlegen der Layouteigenschaften

Legen Sie Layout-bezogene Eigenschaften für das gehostete Steuer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element immer mithilfe der Eigenschaften des-Elements fest. Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.

 Das Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml. vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.

3. Kopieren Sie den folgenden Code in `MainWindow` die Klassendefinition.

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

5. Klicken Sie auf die Schaltfläche **Klicken Sie** . Der `button1_Click` -Ereignishandler legt <xref:System.Windows.Forms.Control.Top%2A> die <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften und für das gehostete Steuerelement fest. Dies bewirkt, dass das gehostete Steuer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element im-Element neu positioniert wird. Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten. Stattdessen sollte das gehostete Steuerelement immer das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element ausfüllen.

## <a name="understanding-z-order-limitations"></a>Grundlegendes zu Einschränkungen der Z-Reihenfolge

Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer auf anderen WPF-Elementen gezeichnet, und Sie sind nicht von der z-Reihenfolge betroffen. Gehen Sie folgendermaßen vor, um dieses z-Reihen folgen Verhalten anzuzeigen:

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird über das Label-Element gezeichnet.

## <a name="docking"></a>Andocken

<xref:System.Windows.Forms.Integration.WindowsFormsHost>Das- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element unterstützt Docking. Legen Sie <xref:System.Windows.Controls.DockPanel.Dock%2A> die angefügte-Eigenschaft fest, um das <xref:System.Windows.Controls.DockPanel> gehostete Steuerelement in einem-Element

### <a name="to-dock-a-hosted-control"></a>Andocke eines gehosteten Steuerelements

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird an der rechten Seite <xref:System.Windows.Controls.DockPanel> des Elements angedockt.

## <a name="setting-visibility"></a>Einstellen der Sichtbarkeit

Sie können das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement unsichtbar machen oder reduzieren, indem Sie <xref:System.Windows.UIElement.Visibility%2A> die-Eigenschaft <xref:System.Windows.Forms.Integration.WindowsFormsHost> für das-Element festlegen. Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich. Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.

### <a name="to-set-the-visibility-of-a-hosted-control"></a>Festlegen der Sichtbarkeit eines gehosteten Steuerelements

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

4. Klicken Sie auf die Schaltfläche **zum unsichtbar machen** , <xref:System.Windows.Forms.Integration.WindowsFormsHost> um das Element unsichtbar zu machen.

5. Klicken Sie auf die Schaltfläche **zum** reduzieren klicken <xref:System.Windows.Forms.Integration.WindowsFormsHost> , um das Element aus dem Layout vollständig auszublenden. Wenn das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um ihren Platz zu belegen.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird

Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente verfügen über eine Größe mit fester Größe und werden nicht gestreckt, um den verfügbaren Platz im Layout auszufüllen. Das <xref:System.Windows.Forms.MonthCalendar> -Steuerelement zeigt z. b. einen Monat in einem fester Bereich an.

### <a name="to-host-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Raster Zeile zentriert, aber nicht gestreckt, um den verfügbaren Platz auszufüllen. Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate vom gehosteten <xref:System.Windows.Forms.MonthCalendar> Steuerelement angezeigt, diese werden jedoch in der Zeile zentriert. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, für die keine Größenanpassung möglich ist, um den verfügbaren Platz auszufüllen.

## <a name="scaling"></a>Skalieren

Anders als WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar. Zum Bereitstellen einer benutzerdefinierten Skalierung <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> überschreiben Sie die-Methode.

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert. Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Drehen

Anders als WPF-Elemente unterstützen Windows Forms Steuerelemente keine Rotation. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird nicht mit anderen WPF-Elementen gedreht, wenn eine Rotations Transformation angewendet wird. Ein beliebiger Rotations Wert außer 180 Grad löst <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> das-Ereignis aus.

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Anzeigen der Auswirkung der Drehung in einer Hybridanwendung

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht. Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.

## <a name="setting-padding-and-margins"></a>Einstellen von Abständen und Rändern

Auffüll-und Rand [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ränder im Layout ähneln den Auffüll-und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]Seitenrändern in. Legen Sie einfach <xref:System.Windows.Controls.Control.Padding%2A> die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften und für <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Element fest.

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Festlegen von Abstand und Rändern für ein gehostetes Steuerelement

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die Auffüll-und Rand Einstellungen werden auf dieselbe Weise [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] auf die gehosteten Steuerelemente angewendet wie in. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]

## <a name="using-dynamic-layout-containers"></a>Verwenden von dynamischen Layoutcontainern

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]stellt zwei dynamische Layoutcontainer <xref:System.Windows.Forms.FlowLayoutPanel> ( <xref:System.Windows.Forms.TableLayoutPanel>und) bereit. Diese Container können auch in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts verwendet werden.

### <a name="to-use-a-dynamic-layout-container"></a>Verwenden von dynamischen Layoutcontainern

1. Kopieren Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code in das-Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Fügen Sie einen Aufruf der `InitializeFlowLayoutPanel` -Methode im Konstruktor hinzu.

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element füllt <xref:System.Windows.Controls.DockPanel>das- <xref:System.Windows.Forms.FlowLayoutPanel> Element und ordnet seine untergeordneten Steuer <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>Elemente in der Standardeinstellung an.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md)
- [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Exemplarische Vorgehensweise: Hosting eines Windows Forms zusammengesetzten Steuer Elements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
