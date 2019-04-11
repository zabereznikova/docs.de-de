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
ms.openlocfilehash: 5b759baebb7192c1ee94b4aa925198864ba7a31a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338773"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF
In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfunktionen anordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer hybridanwendung.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Verwenden der Standardlayouteinstellungen.  
  
-   Anpassen der Größe an Inhalt.  
  
-   Verwenden der absoluten Positionierung.  
  
-   Explizites Angeben der Größe.  
  
-   Festlegen der Layouteigenschaften.  
  
-   Grundlegendes zu Einschränkungen der Z-Reihenfolge.  
  
-   Andocken.  
  
-   Einstellen der Sichtbarkeit.  
  
-   Hosten eines Steuerelements, das nicht gestreckt wird.  
  
-   Skalieren.  
  
-   Drehen.  
  
-   Einstellen von Abständen und Rändern.  
  
-   Verwenden von dynamischen Layoutcontainern.  
  
 Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Wenn Sie fertig sind, haben Sie einen Überblick über [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Layoutfunktionen bei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierte Anwendungen.  
  
## <a name="prerequisites"></a>Vorraussetzungen  

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein  
  
1. Erstellen einer WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.  
  
2. Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3. Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.  
  
4. In der <xref:System.Windows.Window> -Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespace-Zuordnung.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. In der <xref:System.Windows.Controls.Grid> Elementsatz der <xref:System.Windows.Controls.Grid.ShowGridLines%2A> Eigenschaft `true` und fünf Zeilen und drei Spalten definieren.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen  
 In der Standardeinstellung die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element behandelt das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
#### <a name="to-use-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen  
  
1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> Steuerelement angezeigt wird, der <xref:System.Windows.Controls.Canvas>. Das gehostete Steuerelement wird basierend auf den Inhalt, Größe und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird angepasst, sodass das gehostete Steuerelement angepasst.  
  
## <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element stellt sicher, dass das gehostete Steuerelement angepasst wird, dass der Inhalt ordnungsgemäß angezeigt.  
  
#### <a name="to-size-to-content"></a>Anpassen der Größe an Inhalt  
  
1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die zwei neuen Schaltflächen-Steuerelemente sind die Größe der längeren Textzeichenfolge und einer größeren Schriftgrad ordnungsgemäß angezeigt werden und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden geändert, um die gehosteten Steuerelemente angepasst.  
  
## <a name="using-absolute-positioning"></a>Verwenden der absoluten Positionierung  
 Sie können die absolute Positionierung verwenden, platzieren die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element an einer beliebigen Stelle in der Benutzeroberfläche (UI).  
  
#### <a name="to-use-absolute-positioning"></a>Verwenden der absoluten Positionierung  
  
1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element wird 20 Pixel vom oberen Rand der Rasterzelle und 20 Pixel vom linken Rand platziert.  
  
## <a name="specifying-size-explicitly"></a>Explizites Angeben der Größe  
 Sie können angeben, die Größe des der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element mit dem <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften.  
  
#### <a name="to-specify-size-explicitly"></a>Explizites Angeben der Größe  
  
1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf eine Größe von 50 Pixel breit und 70 Pixel hoch, Element festgelegt ist, ist damit kleiner als die standardlayouteinstellungen. Den Inhalt der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird entsprechend neu angeordnet.  
  
## <a name="setting-layout-properties"></a>Festlegen der Layouteigenschaften  
 Layoutbezogene Eigenschaften immer für das gehostete Steuerelement legen Sie mithilfe der Eigenschaften von den <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.  
  
 Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement  
  
1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2. Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml. vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.  
  
3. Kopieren Sie den folgenden Code der `MainWindow` Definition der Klasse.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

5. Klicken Sie auf die **hier klicken** Schaltfläche. Die `button1_Click` Ereignishandler legt die <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften des gehosteten Steuerelements. Dies bewirkt, dass das gehostete Steuerelement in neu positioniert werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten. Stattdessen sollte das gehostete Steuerelement immer ausfüllen der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.

## <a name="understanding-z-order-limitations"></a>Grundlegendes zu Einschränkungen der Z-Reihenfolge
 Sichtbare <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer über anderen WPF-Elemente gezeichnet werden soll, und sie die Z-Reihenfolge betroffen sind. Um dieses Verhalten für die Z-Reihenfolge anzuzeigen, führen Sie folgende Schritte aus:

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element über das Label-Element gezeichnet wird.

## <a name="docking"></a>Andocken
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken. Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte Eigenschaft, um das gehostete Steuerelement in Andocken eine <xref:System.Windows.Controls.DockPanel> Element.

#### <a name="to-dock-a-hosted-control"></a>Andocke eines gehosteten Steuerelements

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element rechts angedockt ist die <xref:System.Windows.Controls.DockPanel> Element.

## <a name="setting-visibility"></a>Einstellen der Sichtbarkeit
 Möglich Ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement ausblenden oder reduzieren, indem Sie die Einstellung der <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich. Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.

#### <a name="to-set-the-visibility-of-a-hosted-control"></a>Festlegen der Sichtbarkeit eines gehosteten Steuerelements

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

4. Klicken Sie auf die **zum Ausblenden klicken** Schaltfläche, um die stellen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element nicht sichtbar.

5. Klicken Sie auf die **zum Reduzieren klicken** Schaltfläche zum Ausblenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig. Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um dessen Bereich einzunehmen.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird
 Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente haben eine feste Größe und können nicht gestreckt werden, um den verfügbaren Platz im Layout auszufüllen. Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement zeigt einen Monat in einem festen Bereich.

#### <a name="to-host-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Rasterzeile zentriert, aber es ist nicht gestreckt, um den verfügbaren Platz auszufüllen. Wenn das Fenster groß genug ist, wird möglicherweise angezeigt mindestens zwei Monate angezeigt, indem das gehostete <xref:System.Windows.Forms.MonthCalendar> -Steuerelement, aber diese sind in der Zeile zentriert. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout-Engine zentriert Elemente, deren Größe geändert werden können nicht um den verfügbaren Platz auszufüllen.

## <a name="scaling"></a>Skalieren
 Im Gegensatz zu WPF-Elemente sind die meisten Windows Forms-Steuerelemente nicht kontinuierlich skalierbar. Um benutzerdefinierte Skalierung zu ermöglichen, Sie überschreiben die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> Methode.

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert. Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Drehen
 Im Gegensatz zu WPF-Elemente unterstützen Windows Forms-Steuerelemente keine Drehung. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird nicht mit anderen WPF-Elementen gedreht, wenn eine Drehtransformation angewendet wird. Jeder andere Drehungswert als 180 Grad löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis.

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Anzeigen der Auswirkung der Drehung in einer Hybridanwendung

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht. Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.

## <a name="setting-padding-and-margins"></a>Einstellen von Abständen und Rändern
 Abstand und Ränder im [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Layout ähneln den Abständen und Rändern in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Legen Sie einfach die <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Festlegen von Abstand und Rändern für ein gehostetes Steuerelement

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die Einstellungen für Ränder und Abstände werden angewendet, an das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise, die sie in angewendet werden sollen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

## <a name="using-dynamic-layout-containers"></a>Verwenden von dynamischen Layoutcontainern
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] stellt zwei dynamische Layoutcontainer, <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>. Sie können auch dieser Container in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts.

#### <a name="to-use-a-dynamic-layout-container"></a>Verwenden von dynamischen Layoutcontainern

1. Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Element.

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Fügen Sie einen Aufruf der `InitializeFlowLayoutPanel` -Methode im Konstruktor hinzu.

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seine untergeordneten Steuerelemente in der standardmäßigen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md)
- [Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
