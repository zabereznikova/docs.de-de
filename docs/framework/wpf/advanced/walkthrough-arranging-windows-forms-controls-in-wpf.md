---
title: 'Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF'
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
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67bfa913627d33238aea92acdd49b6d2ecfef2a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutfunktionen anordnen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente in einer hybridanwendung.  
  
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
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Anordnen von Windows Forms-Steuerelementen im WPF-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Wenn Sie fertig sind, müssen Sie einen Überblick über [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Layout-Funktionen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendungen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein  
  
1.  Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WpfLayoutHostingWf`.  
  
2.  Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  Doppelklicken Sie auf „MainWindow.xaml“, um die Datei in der XAML-Ansicht zu öffnen.  
  
4.  In der <xref:System.Windows.Window> Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespacezuordnung.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  In der <xref:System.Windows.Controls.Grid> Elementsatz die <xref:System.Windows.Controls.Grid.ShowGridLines%2A> Eigenschaft `true` fünf Zeilen und drei Spalten definieren.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen  
 Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element behandelt das Layout für das gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
#### <a name="to-use-default-layout-settings"></a>Verwenden der Standardlayouteinstellungen  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Steuerelement wird in der <xref:System.Windows.Controls.Canvas>. Das gehostete Steuerelement wird basierend auf seinen Inhalt angepasst und der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird angepasst, um das gehostete Steuerelement aufzunehmen.  
  
## <a name="sizing-to-content"></a>Anpassen der Größe an Inhalt  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Elements sicher, dass das gehostete Steuerelement festgelegt wird, um seinen Inhalt ordnungsgemäß angezeigt.  
  
#### <a name="to-size-to-content"></a>Anpassen der Größe an Inhalt  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die zwei neue Schaltflächen-Steuerelemente sind Größe angepasst, um die Textzeichenfolge länger und größere Schriftgröße ordnungsgemäß angezeigt werden und die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden geändert, um die gehosteten Steuerelemente angepasst.  
  
## <a name="using-absolute-positioning"></a>Verwenden der absoluten Positionierung  
 Sie können absolute Positionierung Platzieren der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element an einer beliebigen Stelle in der Benutzeroberfläche (UI).  
  
#### <a name="to-use-absolute-positioning"></a>Verwenden der absoluten Positionierung  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> 20 Pixel vom oberen Rand der Rasterzelle und 20 Pixel vom linken Element befindet.  
  
## <a name="specifying-size-explicitly"></a>Explizites Angeben der Größe  
 Sie können die Größe der angeben der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element mit der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften.  
  
#### <a name="to-specify-size-explicitly"></a>Explizites Angeben der Größe  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element festgelegt, wird er auf eine Größe von 50 Pixel breit und 70 Pixel hoch, die kleiner als die Standardeinstellungen für das Layout. Der Inhalt der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement wird entsprechend neu angeordnet.  
  
## <a name="setting-layout-properties"></a>Festlegen der Layouteigenschaften  
 Layout-bezogene Eigenschaften immer im gehosteten Steuerelement festgelegt, wird mit den Eigenschaften des der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Das Festlegen der Layouteigenschaften direkt für das gehostete Steuerelement führt zu unbeabsichtigten Ergebnissen.  
  
 Festlegen von layoutbezogenen Eigenschaften für das gehostete Steuerelement im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hat keine Auswirkungen.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Anzeigen der Auswirkungen des Festlegens der Eigenschaften für das gehostete Steuerelement  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  Doppelklicken Sie in Projektmappen-Explorer „MainWindow.xaml. vb“ oder „MainWindow.Xaml.cs“, um die Datei im Code-Editor zu öffnen.  
  
3.  Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
5.  Klicken Sie auf die **Click me** Schaltfläche. Die `button1_Click` Ereignishandler legt die <xref:System.Windows.Forms.Control.Top%2A> und <xref:System.Windows.Forms.Control.Left%2A> Eigenschaften im gehosteten Steuerelement. Dies bewirkt, dass das gehostete Steuerelement innerhalb neu angeordnet werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Der Host behält den gleichen Bildschirmbereich bei, jedoch wird das gehostete Steuerelement abgeschnitten. Das gehostete Steuerelement sollte jedoch immer ausfüllen der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.  
  
## <a name="understanding-z-order-limitations"></a>Grundlegendes zu Einschränkungen der Z-Reihenfolge  
 Standardmäßig sichtbar <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente werden immer gezeichnet, zusätzlich zu anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, und Z-Reihenfolge nicht betroffen sind. Legen Sie zum Aktivieren der Z-Reihenfolge der <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> Eigenschaft von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf "true" und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> Eigenschaft <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### <a name="to-see-the-default-z-order-behavior"></a>Anzeigen des Standardverhaltens für die Z-Reihenfolge  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element über das Label-Element gezeichnet wird.  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a>Anzeigen des Verhaltens der Z-Reihenfolge, wenn IsRedirected auf true festgelegt ist  
  
1.  Ersetzen Sie im vorherigen Beispiel der Z-Reihenfolge durch Folgendes XAML.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das Label-Element gezeichnet wird, über die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.  
  
## <a name="docking"></a>Andocken  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>Element unterstützt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andocken. Legen Sie die <xref:System.Windows.Controls.DockPanel.Dock%2A> angefügte Eigenschaft, um das gehostete Steuerelement im Andocken ein <xref:System.Windows.Controls.DockPanel> Element.  
  
#### <a name="to-dock-a-hosted-control"></a>Andocke eines gehosteten Steuerelements  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element auf der rechten Seite des angedockt ist die <xref:System.Windows.Controls.DockPanel> Element.  
  
## <a name="setting-visibility"></a>Einstellen der Sichtbarkeit  
 Sie vornehmen können Ihre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unsichtbar zu steuern oder zu reduzieren, indem Sie festlegen der <xref:System.Windows.UIElement.Visibility%2A> Eigenschaft auf die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Wenn ein Steuerelement unsichtbar ist, wird es nicht angezeigt, es belegt jedoch Platz im Layoutbereich. Wenn ein Steuerelement reduziert ist, wird es nicht angezeigt, und es belegt auch keinen Platz im Layoutbereich.  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>Festlegen der Sichtbarkeit eines gehosteten Steuerelements  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassendefinition.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Klicken Sie auf die **klicken Sie hier, um unsichtbar zu machen** Schaltfläche stellen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element nicht sichtbar.  
  
5.  Klicken Sie auf die **zum Reduzieren** Schaltfläche Ausblenden der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element aus dem Layout vollständig. Wenn die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement reduziert ist, werden die umgebenden Elemente neu angeordnet, um seine Platz einnehmen.  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird  
 Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente verfügen über eine feste Größe und können nicht gestreckt werden, um das Layout verfügbaren Platz auszufüllen. Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement ein Monats in einem festen Bereich angezeigt.  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>Hosten eines Steuerelements, das nicht gestreckt wird  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird in der Rasterzeile zentriert, aber es ist nicht gestreckt, um den verfügbaren Platz auszufüllen. Wenn das Fenster groß genug ist, werden möglicherweise zwei oder mehr Monate angezeigt, die von der gehosteten <xref:System.Windows.Forms.MonthCalendar> -Steuerelement, doch diese sind in der Zeile zentriert. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul zentriert Elemente, deren Größe geändert werden können nicht um den verfügbaren Platz auszufüllen.  
  
## <a name="scaling"></a>Skalieren  
 Im Gegensatz zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, die meisten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente können nicht fortlaufend. Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element skaliert sein gehostetes Steuerelement, wenn möglich.  Um vollwertige Skalierung zu aktivieren, legen die <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> Eigenschaft von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf "true" und der <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> Eigenschaft <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Skalieren eines gehosteten Steuerelements mithilfe des Standardverhaltens  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement und die umgebenden Elemente werden um den Faktor 0,5 skaliert. Allerdings wird die Schriftart des gehosteten Steuerelements nicht skaliert.  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a>Skalieren eines gehosteten Steuerelements durch Festlegen von IsRedirected auf True  
  
1.  Ersetzen Sie das vorherige Beispiel für die Skalierung durch das folgende XAML.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement, die umgebenden Elemente und die Schriftart des gehosteten Steuerelements werden durch den Faktor 0,5 skaliert.  
  
## <a name="rotating"></a>Drehen  
 Im Gegensatz zu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente unterstützen nicht die Drehung. Wird standardmäßig die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element dreht sich nicht mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente angezeigt, wenn eine Drehtransformation angewendet wird. Jeder andere Drehungswert als 180 Grad löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis.  Legen Sie zum Aktivieren, um einen beliebigen Winkel drehen der <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> Eigenschaft von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf "true" und die <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> Eigenschaft <xref:System.Windows.Interop.CompositionMode.Full> oder <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Anzeigen der Auswirkung der Drehung in einer Hybridanwendung  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement wird nicht gedreht, die umgebenden Elemente werden jedoch um einen Winkel von 180 Grad gedreht. Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a>Anzeigen der Auswirkung der Drehung in einer Hybridanwendung, wenn IsRedirected auf true festgelegt ist  
  
1.  Ersetzen das vorherige Beispiel für die Drehung durch das folgende XAML.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Das gehostete Steuerelement wird gedreht.  Beachten Sie, dass die <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft kann auf einen beliebigen Wert festgelegt werden. Sie müssen möglicherweise die Fenstergröße anpassen, um die Elemente zu sehen.  
  
## <a name="setting-padding-and-margins"></a>Einstellen von Abständen und Rändern  
 Auffüllung und Rändern in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout ähneln Auffüllung und Rändern in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Legen Sie einfach die <xref:System.Windows.Controls.Control.Padding%2A> und <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften auf der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element.  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Festlegen von Abstand und Rändern für ein gehostetes Steuerelement  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die Ränder und Abstände Einstellungen angewendet, das vom gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf die gleiche Weise, die sie werden, in angewendet würden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="using-dynamic-layout-containers"></a>Verwenden von dynamischen Layoutcontainern  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]stellt zwei dynamische Layoutcontainer <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel>. Sie können auch diese Container in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layouts.  
  
#### <a name="to-use-a-dynamic-layout-container"></a>Verwenden von dynamischen Layoutcontainern  
  
1.  Kopieren Sie den folgenden XAML-Code in die <xref:System.Windows.Controls.Grid> Element.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  Kopieren Sie in „MainWindow.xaml.vb“ oder „MainWindow.xaml.cs“ den folgenden Code in die Klassedefinition.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Fügen Sie einen Aufruf an die `InitializeFlowLayoutPanel` -Methode im Konstruktor.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element füllt die <xref:System.Windows.Controls.DockPanel>, und <xref:System.Windows.Forms.FlowLayoutPanel> ordnet seine untergeordneten Steuerelemente in der standardmäßigen <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF-Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Überlegungen zum Layout für das WindowsFormsHost-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
