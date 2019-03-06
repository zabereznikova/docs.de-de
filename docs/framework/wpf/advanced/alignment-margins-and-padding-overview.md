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
ms.openlocfilehash: eef28a178f11ea23ac23183c9ec7eb06b7f18a29
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355406"
---
# <a name="alignment-margins-and-padding-overview"></a>Übersicht über Alignment, Margin und Padding
Die <xref:System.Windows.FrameworkElement> Klasse macht mehrere Eigenschaften, die verwendet werden, um die untergeordneten Elemente präzise positionieren. In diesem Thema wird erläutert, vier der wichtigsten Eigenschaften: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. Es ist wichtig, die Auswirkungen dieser Eigenschaften zu verstehen, da Sie die Grundlage für das Steuern der Position von Elementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen bieten.  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>Einführung in die Positionierung des Elements  
 Es gibt zahlreiche Möglichkeiten, Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu positionieren. Jedoch erreichen ideales Layout nicht einfach Auswahl des richtigen <xref:System.Windows.Controls.Panel> Element. Genaue Steuerung der Positionierung erfordert einen Überblick über die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften.  
  
 Die folgende Abbildung zeigt ein Layoutszenario, das verschiedene Positionierungseigenschaften verwendet.  
  
 ![Beispiel für WPF-Positionierungseigenschaften](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 Auf den ersten Blick die <xref:System.Windows.Controls.Button> Elemente in dieser Abbildung können scheinbar zufällig platziert werden. Die Positionen werden jedoch tatsächlich genau mithilfe einer Kombination aus Rändern, Ausrichtungen und Abständen gesteuert.  
  
 Im folgende Beispiel wird beschrieben, wie das Layout in der vorhergehenden Darstellung erstellt wird. Ein <xref:System.Windows.Controls.Border> -Element kapselt ein übergeordnetes <xref:System.Windows.Controls.StackPanel>, mit einem <xref:System.Windows.Controls.Border.Padding%2A> Wert von 15 geräteunabhängigen Pixeln. Diese Konten für die schmale <xref:System.Windows.Media.Brushes.LightBlue%2A> Band, das das untergeordnete Element umgibt <xref:System.Windows.Controls.StackPanel>. Untergeordnete Elemente der <xref:System.Windows.Controls.StackPanel> werden verwendet, um jede der verschiedenen Positionierungseigenschaften, die in diesem Thema aufgeführt sind, zu veranschaulichen. Drei <xref:System.Windows.Controls.Button> Elemente werden verwendet, um beide zeigen die <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaften.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Das folgende Diagramm zeigt eine vergrößerte Ansicht der verschiedenen Positionierungseigenschaften, die im vorhergehenden Beispiel verwendet werden. Die nachfolgenden Abschnitte in diesem Thema beschreiben genauer, wie jede Positionierungseigenschaft verwendet wird.  
  
 ![Positionierungseigenschaften mit Bildschirmbeschriftungen](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>Verstehen von Ausrichtungseigenschaften  
 Die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaften beschreiben, wie ein untergeordnetes Element innerhalb der zugewiesenen Layoutbereich des übergeordneten Elements positioniert werden soll. Indem Sie diese Eigenschaften zusammen verwenden, können Sie untergeordnete Elemente präzise positionieren. Z. B. untergeordnete Elemente des eine <xref:System.Windows.Controls.DockPanel> können vier unterschiedliche horizontale Ausrichtungen angeben: <xref:System.Windows.HorizontalAlignment.Left>, <xref:System.Windows.HorizontalAlignment.Right>, oder <xref:System.Windows.HorizontalAlignment.Center>, oder <xref:System.Windows.HorizontalAlignment.Stretch> zu den verfügbaren Platz auszufüllen. Ähnliche Werte sind für die vertikale Positionierung verfügbar.  
  
> [!NOTE]
>  Explizit festgelegte <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften für ein Element haben Vorrang vor den <xref:System.Windows.HorizontalAlignment.Stretch> -Eigenschaftswert. Beim Festlegen <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, und ein <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert `Stretch` führt die `Stretch` anfordern, werden ignoriert.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>HorizontalAlignment-Eigenschaft  
 Die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft deklariert die Charakteristiken der horizontalen Ausrichtung zum Anwenden von untergeordneten Elementen. Die folgende Tabelle zeigt die möglichen Werte der einzelnen der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Untergeordnete Elemente werden auf der linken Seite des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Untergeordnete Elemente werden rechts vom zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. Explizite <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte haben Vorrang vor.|  
  
 Das folgende Beispiel zeigt, wie Sie anwenden der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft <xref:System.Windows.Controls.Button> Elemente. Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die positionierungseffekte jedes <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert in der Darstellung sichtbar sind.  
  
 ![HorizontalAlignment-Beispiel](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>VerticalAlignment-Eigenschaft  
 Die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft beschreibt die vertikalen ausrichtungsmerkmale zum Anwenden von untergeordneten Elementen. Die folgende Tabelle zeigt die möglichen Werte für jede der <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Untergeordnete Elemente werden oben im zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Untergeordnete Elemente werden am unteren Rand des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. Explizite <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte haben Vorrang vor.|  
  
 Das folgende Beispiel zeigt, wie Sie anwenden der <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft <xref:System.Windows.Controls.Button> Elemente. Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen. Für die Zwecke dieses Beispiels eine <xref:System.Windows.Controls.Grid> -Element mit sichtbaren Rasterlinien als übergeordnetes Element, um das Layoutverhalten jedes Eigenschaftenwerts besser zu veranschaulichen verwendet wird.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die positionierungseffekte jedes <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Wert in der Darstellung sichtbar sind.  
  
 ![Beispiel für VerticalAlignment-Eigenschaft](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>Verstehen von Margin-Eigenschaften  
 Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft beschreibt die Entfernung zwischen einem Element und seine untergeordneten oder Peers. <xref:System.Windows.FrameworkElement.Margin%2A> -Werte können einheitlich sein, mit der Syntax wie `Margin="20"`. Mit dieser Syntax eine einheitliche <xref:System.Windows.FrameworkElement.Margin%2A> 20 Gerät würde geräteunabhängigen Pixeln auf das Element angewendet werden. <xref:System.Windows.FrameworkElement.Margin%2A> Werte können auch haben die Form vier unterschiedlicher Werte, jeden Wert angewendet, die Links, oben, rechts und unten (in dieser Reihenfolge), einen anderen Rand beschreibt wie `Margin="0,10,5,25"`. Richtige Verwendung von der <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft ermöglicht eine präzise Steuerung der Renderingposition eines Elements und dessen benachbarter Elemente sowie die untergeordneten Elemente Renderingposition.  
  
> [!NOTE]
>  Ein Rand ungleich 0 betrifft jeden Bereich außerhalb des Elements <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 Das folgende Beispiel zeigt, wie einheitliche Ränder um eine Gruppe von angewendet <xref:System.Windows.Controls.Button> Elemente. Die <xref:System.Windows.Controls.Button> Elemente werden mit einem 10-Pixel-Rand in jeder Richtung gleichmäßig verteilt.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 In vielen Fällen ist ein einheitlicher Rand nicht geeignet. In diesen Fällen kann ein ungleichmäßiger Abstand angewendet werden. Im folgenden Beispiel wird veranschaulicht, wie ungleichmäßige Randeinstellungen auf untergeordnete Elemente angewendet werden. Ränder werden in dieser Reihenfolge beschrieben: links, oben, rechts, unten.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>Verstehen der Padding-Eigenschaft  
 Padding entspricht <xref:System.Windows.FrameworkElement.Margin%2A> in den meisten Punkten. Die Padding-Eigenschaft ist vor allem aus Gründen der Einfachheit nur in wenigen Klassen verfügbar: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, und <xref:System.Windows.Controls.TextBlock> sind Beispiele für Klassen, die eine Padding-Eigenschaft verfügbar machen. Die <xref:System.Windows.Controls.Border.Padding%2A> -Eigenschaft vergrößert die effektive Größe eines untergeordneten Elements mit dem angegebenen <xref:System.Windows.Thickness> Wert.  
  
 Das folgende Beispiel zeigt, wie Sie anwenden <xref:System.Windows.Controls.Border.Padding%2A> an ein übergeordnetes Element <xref:System.Windows.Controls.Border> Element.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Verwenden von Alignment, Margin und Padding in einer Anwendung  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Geben Sie die zum Erstellen komplexer positionssteuerung [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Sie können die Effekte jeder Eigenschaft verwenden, um die Positionierung untergeordneter Elemente zu ändern, wodurch die Flexibilität beim Erstellen dynamischer Anwendungen und Benutzererfahrungen sichergestellt wird.  
  
 Das folgende Beispiel zeigt die einzelnen Konzepte, die in diesem Thema beschrieben werden. Erstellen in der Infrastruktur finden Sie im ersten Beispiel in diesem Thema, in diesem Beispiel wird eine <xref:System.Windows.Controls.Grid> Element als untergeordnetes Element der <xref:System.Windows.Controls.Border> im ersten Beispiel. <xref:System.Windows.Controls.Border.Padding%2A> gilt für das übergeordnete Element <xref:System.Windows.Controls.Border> Element. Die <xref:System.Windows.Controls.Grid> wird verwendet, um den Abstand zwischen drei untergeordneten partition <xref:System.Windows.Controls.StackPanel> Elemente. <xref:System.Windows.Controls.Button> Elemente werden erneut verwendet, um die unterschiedlichen Effekte von anzuzeigen <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>. <xref:System.Windows.Controls.TextBlock> Elemente werden hinzugefügt, auf die einzelnen <xref:System.Windows.Controls.ColumnDefinition> verschiedene Eigenschaften, die besser definieren die <xref:System.Windows.Controls.Button> Elemente in jeder Spalte.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Nach dem Kompilieren der Anwendung wird eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ausgegeben, die wie die folgende Darstellung aussieht. Die Auswirkungen der verschiedenen Eigenschaftswerte sind in den Abstand zwischen Elementen offensichtlich, und signifikante Eigenschaftswerte für Elemente in jeder Spalte werden angezeigt, in <xref:System.Windows.Controls.TextBlock> Elemente.  
  
 ![Mehrere Positionierungseigenschaften in einer Anwendung](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>Weitere Informationen  
 Positionierung von Eigenschaften, die von definiert die <xref:System.Windows.FrameworkElement> Klasse ermöglichen die genaue Steuerung der elementplatzierung innerhalb [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen. Ihnen sind nun unterschiedliche Techniken bekannt, die Sie verwenden können, um Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besser positionieren zu können.  
  
 Zusätzliche Ressourcen sind verfügbar, die das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Layout ausführlicher erläutern. Die [Panels Overview](../controls/panels-overview.md) Thema enthält weitere Details zu den verschiedenen <xref:System.Windows.Controls.Panel> Elemente. Das Thema [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md) stellt erweiterte Techniken, mit denen Layoutelemente Komponenten positionieren und ihre Aktionen an Datenquellen binden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Übersicht über Panel-Elemente](../controls/panels-overview.md)
- [Layout](layout.md)
- [Beispiel für einen WPF-Layoutkatalog](https://go.microsoft.com/fwlink/?LinkID=160054)
