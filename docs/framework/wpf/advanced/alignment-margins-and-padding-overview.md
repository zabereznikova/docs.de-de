---
title: Übersicht über Alignment, Margin und Padding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: 70eff35db638c5bfbc9c164dc381e3f58e18957b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541251"
---
# <a name="alignment-margins-and-padding-overview"></a>Übersicht über Alignment, Margin und Padding
Die <xref:System.Windows.FrameworkElement> Klasse macht mehrere Eigenschaften, die verwendet werden, um untergeordnete Elemente genau zu positionieren. In diesem Artikel werden vier wichtigsten Eigenschaften: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. Es ist wichtig, die Auswirkungen dieser Eigenschaften zu verstehen, da Sie die Grundlage für das Steuern der Position von Elementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen bieten.  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>Einführung in die Positionierung des Elements  
 Es gibt zahlreiche Möglichkeiten, Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu positionieren. Allerdings erreichen idealen Layouts hinausgeht einfach Auswahl des richtigen <xref:System.Windows.Controls.Panel> Element. Steuern der Positionierung erfordert einen Überblick über die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften.  
  
 Die folgende Abbildung zeigt ein Layoutszenario, das verschiedene Positionierungseigenschaften verwendet.  
  
 ![Beispiel für WPF-Positionierungseigenschaften](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 Auf den ersten Blick der <xref:System.Windows.Controls.Button> Elemente in dieser Abbildung auftreten nach dem Zufallsprinzip abgelegt werden soll. Die Positionen werden jedoch tatsächlich genau mithilfe einer Kombination aus Rändern, Ausrichtungen und Abständen gesteuert.  
  
 Im folgende Beispiel wird beschrieben, wie das Layout in der vorhergehenden Darstellung erstellt wird. Ein <xref:System.Windows.Controls.Border> Element kapselt einen übergeordneten <xref:System.Windows.Controls.StackPanel>, mit einem <xref:System.Windows.Controls.Border.Padding%2A> Wert 15 geräteunabhängigen Pixeln. Diese Konten der schmale <xref:System.Windows.Media.Brushes.LightBlue%2A> Band, das das untergeordnete Element umgibt <xref:System.Windows.Controls.StackPanel>. Untergeordnete Elemente von der <xref:System.Windows.Controls.StackPanel> werden verwendet, um jede der verschiedenen Positionierungseigenschaften zu erläutern, die in diesem Thema erläutert werden. Drei <xref:System.Windows.Controls.Button> Elemente werden verwendet, um beide veranschaulichen die <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaften.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Das folgende Diagramm zeigt eine vergrößerte Ansicht der verschiedenen Positionierungseigenschaften, die im vorhergehenden Beispiel verwendet werden. Die nachfolgenden Abschnitte in diesem Thema beschreiben genauer, wie jede Positionierungseigenschaft verwendet wird.  
  
 ![Positionierungseigenschaften mit Bildschirmbeschriftungen](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>Verstehen von Ausrichtungseigenschaften  
 Die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften beschreiben, wie ein untergeordnetes Element eines übergeordneten Elements zugewiesenen Layoutbereich positioniert werden soll. Indem Sie diese Eigenschaften zusammen verwenden, können Sie untergeordnete Elemente präzise positionieren. Z. B. untergeordnete Elemente des eine <xref:System.Windows.Controls.DockPanel> können vier verschiedenen horizontalen Ausrichtungen angeben: <xref:System.Windows.HorizontalAlignment.Left>, <xref:System.Windows.HorizontalAlignment.Right>, oder <xref:System.Windows.HorizontalAlignment.Center>, oder auf <xref:System.Windows.HorizontalAlignment.Stretch> zu den verfügbaren Platz auszufüllen. Ähnliche Werte sind für die vertikale Positionierung verfügbar.  
  
> [!NOTE]
>  Explizit festgelegte <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften für ein Element haben Vorrang vor den <xref:System.Windows.HorizontalAlignment.Stretch> Eigenschaftswert. Beim Festlegen <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, und ein <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert `Stretch` führt die `Stretch` anfordern, wird ignoriert.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>HorizontalAlignment-Eigenschaft  
 Die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft deklariert die horizontalen ausrichtungsmerkmale auf untergeordnete Elemente gilt. In der folgenden Tabelle wird veranschaulicht, wie die möglichen Werte für die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Untergeordnete Elemente werden auf der linken Seite des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Untergeordnete Elemente werden rechts vom zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. Explizite <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte haben Vorrang vor.|  
  
 Im folgende Beispiel wird gezeigt, wie zum Anwenden der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.Controls.Button> Elemente. Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die Positionierung Auswirkungen der einzelnen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert in der Abbildung sichtbar sind.  
  
 ![HorizontalAlignment-Beispiel](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>VerticalAlignment-Eigenschaft  
 Die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft beschreibt die vertikalen ausrichtungsmerkmale auf untergeordnete Elemente gilt. In der folgenden Tabelle wird veranschaulicht, wie die möglichen Werte für die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Untergeordnete Elemente werden oben im zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Untergeordnete Elemente werden am unteren Rand des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. Explizite <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte haben Vorrang vor.|  
  
 Im folgende Beispiel wird gezeigt, wie zum Anwenden der <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft <xref:System.Windows.Controls.Button> Elemente. Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen. Für dieses Beispiel eine <xref:System.Windows.Controls.Grid> Element mit Rasterlinien wird als das übergeordnete Element verwendet, um das Layoutverhalten für jeden Eigenschaftswert besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die Positionierung Auswirkungen der einzelnen <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Wert in der Abbildung sichtbar sind.  
  
 ![Beispiel für VerticalAlignment-Eigenschaft](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>Verstehen von Margin-Eigenschaften  
 Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft beschreibt die Entfernung zwischen einem Element und seine untergeordneten oder Peers. <xref:System.Windows.FrameworkElement.Margin%2A> Werte können einheitlich sein, mithilfe von Syntax wie `Margin="20"`. Mit dieser Syntax eine einheitliche <xref:System.Windows.FrameworkElement.Margin%2A> 20 Geräts würde geräteunabhängigen Pixeln auf das Element angewendet werden. <xref:System.Windows.FrameworkElement.Margin%2A> Werte können auch nehmen die Form von vier unterschiedlichen Werten jeder Wert, der einen unterschiedlichen Abstand an, die Links, oben, rechts und unteren Rand (in dieser Reihenfolge), wie `Margin="0,10,5,25"`. Richtige Verwendung von der <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft ermöglicht es, sehr präzise Steuerung der Renderposition eines Elements und die Renderposition seiner Nachbarn Elemente und die untergeordneten Elemente.  
  
> [!NOTE]
>  Ein Rand ungleich 0 (null) gilt Speicherplatz außerhalb des Elements <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 Im folgende Beispiel wird gezeigt, wie einheitliche Ränder um eine Gruppe von anzuwendende <xref:System.Windows.Controls.Button> Elemente. Die <xref:System.Windows.Controls.Button> Elemente werden mit einem 10-Pixel-Rand--Puffer in jede Richtung gleichmäßig platziert.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 In vielen Fällen ist ein einheitlicher Rand nicht geeignet. In diesen Fällen kann ein ungleichmäßiger Abstand angewendet werden. Im folgenden Beispiel wird veranschaulicht, wie ungleichmäßige Randeinstellungen auf untergeordnete Elemente angewendet werden. Ränder werden in dieser Reihenfolge beschrieben: links, oben, rechts, unten.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>Verstehen der Padding-Eigenschaft  
 Auffüllung ähnelt <xref:System.Windows.FrameworkElement.Margin%2A> in vielerlei Hinsicht. Padding-Eigenschaft ist in erster Linie zur Vereinfachung nur auf einige Klassen verfügbar: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, und <xref:System.Windows.Controls.TextBlock> sind Beispiele für Klassen, die Padding-Eigenschaft verfügbar zu machen. Die <xref:System.Windows.Controls.Border.Padding%2A> Eigenschaft vergrößert die effektive Größe eines untergeordneten Elements durch den angegebenen <xref:System.Windows.Thickness> Wert.  
  
 Im folgende Beispiel wird gezeigt, wie anzuwendende <xref:System.Windows.Controls.Border.Padding%2A> zu einem übergeordneten Element <xref:System.Windows.Controls.Border> Element.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Verwenden von Alignment, Margin und Padding in einer Anwendung  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> bieten die Positionierung Kontrolle, die zum Erstellen einer komplexen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Sie können die Effekte jeder Eigenschaft verwenden, um die Positionierung untergeordneter Elemente zu ändern, wodurch die Flexibilität beim Erstellen dynamischer Anwendungen und Benutzererfahrungen sichergestellt wird.  
  
 Das folgende Beispiel zeigt die einzelnen Konzepte, die in diesem Thema beschrieben werden. Basierend auf der Infrastruktur im ersten Beispiel in diesem Thema wird in diesem Beispiel wird eine <xref:System.Windows.Controls.Grid> Element als untergeordnetes Element von der <xref:System.Windows.Controls.Border> im ersten Beispiel. <xref:System.Windows.Controls.Border.Padding%2A> gilt für das übergeordnete Element <xref:System.Windows.Controls.Border> Element. Die <xref:System.Windows.Controls.Grid> wird verwendet, um den Abstand zwischen drei untergeordnete partition <xref:System.Windows.Controls.StackPanel> Elemente. <xref:System.Windows.Controls.Button> Elemente werden erneut zum Anzeigen der verschiedenen Auswirkungen von <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>. <xref:System.Windows.Controls.TextBlock> Elemente werden hinzugefügt, auf die einzelnen <xref:System.Windows.Controls.ColumnDefinition> verschiedene Eigenschaften, die besser definieren die <xref:System.Windows.Controls.Button> Elemente in jeder Spalte.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Nach dem Kompilieren der Anwendung wird eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ausgegeben, die wie die folgende Darstellung aussieht. Die Auswirkungen der verschiedenen Eigenschaftswerte sind allesamt im den Abstand zwischen Elementen und erhebliche Eigenschaftswerte für Elemente in den einzelnen Spalten werden angezeigt, in <xref:System.Windows.Controls.TextBlock> Elemente.  
  
 ![Mehrere Positionierungseigenschaften in einer Anwendung](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>Weitere Informationen  
 Positionieren von definierte Eigenschaften der <xref:System.Windows.FrameworkElement> Klasse aktivieren genaue Steuerung der Element-Platzierung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen. Ihnen sind nun unterschiedliche Techniken bekannt, die Sie verwenden können, um Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besser positionieren zu können.  
  
 Zusätzliche Ressourcen sind verfügbar, die das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Layout ausführlicher erläutern. Die [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md) Thema enthält weitere Details zu den verschiedenen <xref:System.Windows.Controls.Panel> Elemente. Das Thema [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) stellt erweiterte Techniken, mit denen Elemente des Berichtslayouts Positionieren von Komponenten und ihre Aktionen an Datenquellen binden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.Margin%2A>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)  
 [Beispiel für einen WPF-Layoutkatalog](http://go.microsoft.com/fwlink/?LinkID=160054)
