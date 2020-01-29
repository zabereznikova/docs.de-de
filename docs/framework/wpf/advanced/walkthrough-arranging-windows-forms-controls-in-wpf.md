---
title: Anordnen von Windows Forms Steuerelementen in WPF
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 5e7544dfdbee234bb968c9a7f39814e8749ece15
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735289"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF

In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfeatures [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer Hybrid Anwendung anordnen.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts
- Verwenden der Standardlayouteinstellungen.
- Anpassen der Größe an Inhalt.
- Verwenden der absoluten Positionierung.
- Explizites Angeben der Größe.
- Festlegen der Layouteigenschaften.
- Grundlegendes zu Einschränkungen der Z-Reihenfolge.
- Andocken.
- Einstellen der Sichtbarkeit.
- Hosten eines Steuerelements, das nicht gestreckt wird.
- Scaling.
- Drehen.
- Einstellen von Abständen und Rändern.
- Verwenden von dynamischen Layoutcontainern.

Eine umfassende Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971).

Wenn Sie fertig sind, verfügen Sie über die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layoutfeatures in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendungen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="creating-the-project"></a>Erstellen des Projekts

Führen Sie die folgenden Schritte aus, um das Projekt zu erstellen und einzurichten:

1. Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.

2. Fügen Sie in Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu:

    - WindowsFormsIntegration
    - System.Windows.Forms
    - System.Drawing

3. Doppelklicken Sie auf " *MainWindow. XAML* ", um Sie in der XAML-Ansicht zu öffnen.

4. Fügen Sie im <xref:System.Windows.Window>-Element die folgende [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespace Zuordnung hinzu.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Legen Sie im <xref:System.Windows.Controls.Grid>-Element die <xref:System.Windows.Controls.Grid.ShowGridLines%2A>-Eigenschaft auf `true` fest, und definieren Sie fünf Zeilen und drei Spalten.

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen

Standardmäßig behandelt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement.

Gehen Sie folgendermaßen vor, um Standardlayouteinstellungen zu verwenden:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType>-Steuerelement wird im <xref:System.Windows.Controls.Canvas>angezeigt. Das gehostete Steuerelement wird basierend auf seinem Inhalt angepasst, und das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element ist für das gehostete Steuerelement angepasst.

## <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt

Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element stellt sicher, dass das gehostete Steuerelement seine Inhalte ordnungsgemäß anzeigt.

Führen Sie die folgenden Schritte aus, um die Größe für den Inhalt zu

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Die zwei neuen Schaltflächen-Steuerelemente werden angepasst, um die längere Text Zeichenfolge und eine größere Schriftgröße korrekt anzuzeigen, und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden angepasst, um die gehosteten Steuerelemente anzupassen.

## <a name="using-absolute-positioning"></a>Verwenden der absoluten Positionierung

Sie können die absolute Positionierung verwenden, um das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element an einer beliebigen Stelle in der Benutzeroberfläche (UI) zu platzieren.

Führen Sie die folgenden Schritte aus, um die absolute Positionierung zu verwenden:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird 20 Pixel von der oberen Seite der Raster Zelle und 20 Pixel von Links platziert.

## <a name="specifying-size-explicitly"></a>Explizites Angeben der Größe

Mithilfe der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> können Sie die Größe des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements angeben.

Um die Größe explizit anzugeben, führen Sie die folgenden Schritte aus:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird auf eine Größe von 50 Pixel Breite um 70 Pixel hoch festgelegt, die kleiner ist als die Standardlayouteinstellungen. Der Inhalt des [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuer Elements wird entsprechend neu angeordnet.

## <a name="setting-layout-properties"></a>Festlegen der Layouteigenschaften

Legen Sie Layout-bezogene Eigenschaften für das gehostete Steuerelement immer fest, indem Sie die Eigenschaften des <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Elements verwenden. Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.

 Das Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.

Führen Sie die folgenden Schritte aus, um die Auswirkungen der Einstellungs Eigenschaften für das gehostete Steuerelement anzuzeigen:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei *MainWindow. XAML. vb* oder *MainWindow.XAML.cs* , um Sie im Code-Editor zu öffnen.

3. Kopieren Sie den folgenden Code in die `MainWindow`-Klassendefinition:

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.

5. Klicken Sie auf die Schaltfläche **Klicken Sie** . Der `button1_Click`-Ereignishandler legt die Eigenschaften <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> für das gehostete Steuerelement fest. Dies bewirkt, dass das gehostete Steuerelement im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element neu positioniert wird. Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten. Stattdessen sollte das gehostete Steuerelement immer das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element ausfüllen.

## <a name="understanding-z-order-limitations"></a>Grundlegendes zu Einschränkungen der Z-Reihenfolge

Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer auf anderen WPF-Elementen gezeichnet, und Sie sind nicht von der z-Reihenfolge betroffen. Gehen Sie folgendermaßen vor, um dieses z-Reihen folgen Verhalten anzuzeigen:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird über das Label-Element gezeichnet.

## <a name="docking"></a>Docking

<xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken. Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte-Eigenschaft fest, um das gehostete-Steuerelement in einem <xref:System.Windows.Controls.DockPanel>-Element

Führen Sie die folgenden Schritte aus, um ein gehostetes Steuerelement zu

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird an der rechten Seite des <xref:System.Windows.Controls.DockPanel> Elements angedockt.

## <a name="setting-visibility"></a>Einstellen der Sichtbarkeit

Sie können das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement unsichtbar machen oder reduzieren, indem Sie die <xref:System.Windows.UIElement.Visibility%2A>-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element festlegen. Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich. Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.

Führen Sie die folgenden Schritte aus, um die Sichtbarkeit eines gehosteten Steuer Elements festzulegen:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. Kopieren Sie in *MainWindow. XAML. vb* oder *MainWindow.XAML.cs*den folgenden Code in die Klassendefinition:

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen.

4. Klicken Sie auf die Schaltfläche **zum sichtbar machen** , um das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element unsichtbar zu machen.

5. Klicken Sie auf die Schaltfläche **zum reduzieren klicken** , um das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig auszublenden. Wenn das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um ihren Platz zu belegen.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird

Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente haben eine Festgröße und werden nicht gestreckt, um den verfügbaren Platz im Layout auszufüllen. Das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement zeigt z. b. einen Monat in einem fester Bereich an.

Zum Hosten eines Steuer Elements, das nicht gestreckt wird, führen Sie die folgenden Schritte aus:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Raster Zeile zentriert, aber nicht gestreckt, um den verfügbaren Platz auszufüllen. Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate vom gehosteten <xref:System.Windows.Forms.MonthCalendar> Steuerelement angezeigt, diese werden jedoch in der Zeile zentriert. Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, deren Größen nicht so groß sind, dass der verfügbare Platz ausgefüllt wird.

## <a name="scaling"></a>Skalieren

Anders als WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar. Zum Bereitstellen einer benutzerdefinierten Skalierung überschreiben Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>-Methode.

Führen Sie die folgenden Schritte aus, um ein gehostetes Steuerelement mithilfe des Standard Verhaltens zu skalieren:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert. Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Drehen

Anders als WPF-Elemente unterstützen Windows Forms Steuerelemente keine Rotation. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird nicht mit anderen WPF-Elementen gedreht, wenn eine Rotations Transformation angewendet wird. Bei einem anderen Rotations Wert als 180 Grad wird das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>-Ereignis ausgelöst.

Führen Sie die folgenden Schritte aus, um die Auswirkung der Drehung in einer Hybrid Anwendung anzuzeigen:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht. Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.

## <a name="setting-padding-and-margins"></a>Einstellen von Abständen und Rändern

Abstand und Ränder in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout ähneln der Auffüll-und Seitenränder in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Legen Sie einfach die Eigenschaften <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> für das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element fest.

Gehen Sie folgendermaßen vor, um Auffüll-und Seitenränder für ein gehosteter Steuerelement festzulegen:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Die Auffüll-und Rand Einstellungen werden auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise wie auf [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]angewendet.

## <a name="using-dynamic-layout-containers"></a>Verwenden von dynamischen Layoutcontainern

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] stellt zwei dynamische Layoutcontainer bereit, <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>. Diese Container können auch in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts verwendet werden.

Führen Sie die folgenden Schritte aus, um einen dynamischen Layoutcontainer zu verwenden:

1. Kopieren Sie den folgenden XAML-Code in das <xref:System.Windows.Controls.Grid>-Element:

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. Kopieren Sie in *MainWindow. XAML. vb* oder *MainWindow.XAML.cs*den folgenden Code in die Klassendefinition:

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Fügen Sie im Konstruktor einen aufzurufenden `InitializeFlowLayoutPanel`-Methode hinzu:

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Drücken Sie <kbd>F5</kbd>, um die Anwendung zu erstellen und auszuführen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet die untergeordneten Steuerelemente im Standard <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>an.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md)
- [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
