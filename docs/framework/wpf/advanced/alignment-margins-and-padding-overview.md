---
title: Übersicht über Alignment, Margin und Padding
description: Erfahren Sie mehr über HorizontalAlignment, Margin, Padding und VerticalAlignment, die die Position des untergeordneten Elements in Windows Presentation Foundation Anwendungen steuern.
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
ms.openlocfilehash: 832325086c85a7b044876e825d93e0b680a0b99c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165890"
---
# <a name="alignment-margins-and-padding-overview"></a>Übersicht über Alignment, Margin und Padding
Die- <xref:System.Windows.FrameworkElement> Klasse macht mehrere Eigenschaften verfügbar, die verwendet werden, um untergeordnete Elemente exakt zu positionieren. In diesem Thema werden vier der wichtigsten Eigenschaften erläutert: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> , <xref:System.Windows.FrameworkElement.Margin%2A> , <xref:System.Windows.Controls.Border.Padding%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> . Es ist wichtig, die Auswirkungen dieser Eigenschaften zu verstehen, da Sie die Grundlage für das Steuern der Position von Elementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen bieten.  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>Einführung in die Positionierung des Elements  
 Es gibt zahlreiche Möglichkeiten, Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu positionieren. Das Erreichen des idealen Layouts geht aber über das einfache auswählen des richtigen <xref:System.Windows.Controls.Panel> Elements hinaus. Die genaue Kontrolle der Positionierung erfordert ein Verständnis der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften,, <xref:System.Windows.Controls.Border.Padding%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> .  
  
 Die folgende Abbildung zeigt ein Layoutszenario, das verschiedene Positionierungseigenschaften verwendet.  
  
 ![Beispiel für WPF-Positionierungseigenschaften](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 Auf den ersten Blick <xref:System.Windows.Controls.Button> können die Elemente in dieser Abbildung nach dem Zufallsprinzip angezeigt werden. Die Positionen werden jedoch tatsächlich genau mithilfe einer Kombination aus Rändern, Ausrichtungen und Abständen gesteuert.  
  
 Im folgende Beispiel wird beschrieben, wie das Layout in der vorhergehenden Darstellung erstellt wird. Ein- <xref:System.Windows.Controls.Border> Element kapselt ein <xref:System.Windows.Controls.StackPanel> übergeordnetes Element mit einem <xref:System.Windows.Controls.Border.Padding%2A> Wert von 15 geräteunabhängigen Pixeln. Dies berücksichtigt das schmale <xref:System.Windows.Media.Brushes.LightBlue%2A> Band, das das untergeordnete Element umgibt <xref:System.Windows.Controls.StackPanel> . Untergeordnete Elemente der <xref:System.Windows.Controls.StackPanel> werden verwendet, um jede der verschiedenen Positionierungs Eigenschaften zu veranschaulichen, die in diesem Thema beschrieben werden. Drei <xref:System.Windows.Controls.Button> Elemente werden verwendet, um die-Eigenschaft und die-Eigenschaft zu veranschaulichen <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> .  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Das folgende Diagramm zeigt eine vergrößerte Ansicht der verschiedenen Positionierungseigenschaften, die im vorhergehenden Beispiel verwendet werden. Die nachfolgenden Abschnitte in diesem Thema beschreiben genauer, wie jede Positionierungseigenschaft verwendet wird.  
  
 ![Positionieren von Eigenschaften mit Bildschirm aufrufen&#45;Outs](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>Verstehen von Ausrichtungseigenschaften  
 Die-Eigenschaft und die-Eigenschaft <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> beschreiben, wie ein untergeordnetes Element innerhalb des zugewiesenen layoutraums eines übergeordneten Elements positioniert werden soll. Indem Sie diese Eigenschaften zusammen verwenden, können Sie untergeordnete Elemente präzise positionieren. Beispielsweise können untergeordnete Elemente eines <xref:System.Windows.Controls.DockPanel> vier verschiedene horizontale Ausrichtungen angeben: <xref:System.Windows.HorizontalAlignment.Left> , <xref:System.Windows.HorizontalAlignment.Right> oder <xref:System.Windows.HorizontalAlignment.Center> , oder, um <xref:System.Windows.HorizontalAlignment.Stretch> den verfügbaren Platz auszufüllen. Ähnliche Werte sind für die vertikale Positionierung verfügbar.  
  
> [!NOTE]
> Explizit festgelegte- <xref:System.Windows.FrameworkElement.Height%2A> und- <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaften für ein Element haben Vorrang vor dem <xref:System.Windows.HorizontalAlignment.Stretch> Eigenschafts Wert. Wenn Sie versuchen <xref:System.Windows.FrameworkElement.Height%2A> ,, <xref:System.Windows.FrameworkElement.Width%2A> und den Wert festzulegen, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> `Stretch` `Stretch` wird die Anforderung ignoriert.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>HorizontalAlignment-Eigenschaft  
 Die- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft deklariert die Eigenschaften der horizontalen Ausrichtung, die auf untergeordnete Elemente angewendet werden sollen. In der folgenden Tabelle werden die möglichen Werte der- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft angezeigt.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Untergeordnete Elemente werden auf der linken Seite des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Untergeordnete Elemente werden rechts vom zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. Explizite <xref:System.Windows.FrameworkElement.Width%2A> -und- <xref:System.Windows.FrameworkElement.Height%2A> Werte haben Vorrang.|  
  
 Im folgenden Beispiel wird gezeigt, wie die- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft auf-Elemente angewendet wird <xref:System.Windows.Controls.Button> . Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die Positionierungs Effekte der einzelnen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Werte sind in der Abbildung sichtbar.  
  
 ![HorizontalAlignment-Beispiel](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>VerticalAlignment-Eigenschaft  
 Die- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft beschreibt die Merkmale vertikaler Ausrichtung, die auf untergeordnete Elemente angewendet werden sollen. In der folgenden Tabelle werden die möglichen Werte für die- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft angezeigt.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Untergeordnete Elemente werden oben im zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Untergeordnete Elemente werden am unteren Rand des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. Explizite <xref:System.Windows.FrameworkElement.Width%2A> -und- <xref:System.Windows.FrameworkElement.Height%2A> Werte haben Vorrang.|  
  
 Im folgenden Beispiel wird gezeigt, wie die- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft auf-Elemente angewendet wird <xref:System.Windows.Controls.Button> . Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen. Für dieses Beispiel wird ein- <xref:System.Windows.Controls.Grid> Element mit sichtbarem Gitternetz Linien als übergeordnetes Element verwendet, um das Layoutverhalten der einzelnen Eigenschaftswerte besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die Positionierungs Effekte der einzelnen <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Werte sind in der Abbildung sichtbar.  
  
 ![Beispiel für VerticalAlignment-Eigenschaft](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>Verstehen von Margin-Eigenschaften  
 Die <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft beschreibt den Abstand zwischen einem Element und seinen untergeordneten Elementen oder Peers. <xref:System.Windows.FrameworkElement.Margin%2A>Werte können mithilfe von Syntax wie einheitlich sein `Margin="20"` . Bei dieser Syntax würde eine einheitliche <xref:System.Windows.FrameworkElement.Margin%2A> von 20 geräteunabhängigen Pixeln auf das Element angewendet werden. <xref:System.Windows.FrameworkElement.Margin%2A>Werte können auch die Form von vier unterschiedlichen Werten annehmen, wobei jeder Wert einen unterschiedlichen Rand beschreibt, der auf den linken, oberen, rechten und unteren Rand (in dieser Reihenfolge) angewendet werden soll, wie z `Margin="0,10,5,25"` . b.. Die ordnungsgemäße Verwendung der <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft ermöglicht eine sehr feine Steuerung der Renderingposition eines Elements und der Renderingposition seiner benachbarten Elemente und untergeordneten Elemente.  
  
> [!NOTE]
> Ein Rand ungleich NULL wendet den Bereich außerhalb des-Elements und des-Elements an <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A> .  
  
 Im folgenden Beispiel wird gezeigt, wie Sie einheitliche Ränder um eine Gruppe von <xref:System.Windows.Controls.Button> Elementen anwenden. Die <xref:System.Windows.Controls.Button> Elemente werden gleichmäßig mit einem zehn Pixel großen Rand Puffer in jeder Richtung angeordnet.  
  
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
 Padding ähnelt <xref:System.Windows.FrameworkElement.Margin%2A> in den meisten Punkten. Die Padding-Eigenschaft wird nur für einige Klassen verfügbar gemacht, hauptsächlich als praktische Hilfe: <xref:System.Windows.Documents.Block> , <xref:System.Windows.Controls.Border> , <xref:System.Windows.Controls.Control> und <xref:System.Windows.Controls.TextBlock> sind Beispiele für Klassen, die eine Padding-Eigenschaft verfügbar machen. Die- <xref:System.Windows.Controls.Border.Padding%2A> Eigenschaft vergrößert die effektive Größe eines untergeordneten Elements mit dem angegebenen <xref:System.Windows.Thickness> Wert.  
  
 Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Controls.Border.Padding%2A> auf ein übergeordnetes Element angewendet wird <xref:System.Windows.Controls.Border> .  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Verwenden von Alignment, Margin und Padding in einer Anwendung  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> , <xref:System.Windows.Controls.Border.Padding%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> stellen die positionierungssteuerung zur Verfügung, die zum Erstellen eines komplexen benötigt wird [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . Sie können die Effekte jeder Eigenschaft verwenden, um die Positionierung untergeordneter Elemente zu ändern, wodurch die Flexibilität beim Erstellen dynamischer Anwendungen und Benutzererfahrungen sichergestellt wird.  
  
 Das folgende Beispiel zeigt die einzelnen Konzepte, die in diesem Thema beschrieben werden. Wenn Sie auf der-Infrastruktur aufbauen, die im ersten Beispiel in diesem Thema enthalten ist, wird in diesem Beispiel ein- <xref:System.Windows.Controls.Grid> Element als untergeordnetes Element der im ersten Beispiel hinzugefügt <xref:System.Windows.Controls.Border> . <xref:System.Windows.Controls.Border.Padding%2A>wird auf das übergeordnete <xref:System.Windows.Controls.Border> Element angewendet. <xref:System.Windows.Controls.Grid>Wird verwendet, um den Raum zwischen drei untergeordneten Elementen zu partitionieren <xref:System.Windows.Controls.StackPanel> . <xref:System.Windows.Controls.Button>-Elemente werden erneut verwendet, um die verschiedenen Auswirkungen von <xref:System.Windows.FrameworkElement.Margin%2A> und anzuzeigen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> . <xref:System.Windows.Controls.TextBlock>jeder werden Elemente hinzugefügt <xref:System.Windows.Controls.ColumnDefinition> , um die verschiedenen Eigenschaften besser zu definieren, die auf die <xref:System.Windows.Controls.Button> Elemente in den einzelnen Spalten angewendet werden.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Nach dem Kompilieren der Anwendung wird eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ausgegeben, die wie die folgende Darstellung aussieht. Die Auswirkungen der verschiedenen Eigenschaftswerte sind im Abstand zwischen Elementen ersichtlich, und signifikante Eigenschaftswerte für Elemente in den einzelnen Spalten werden in <xref:System.Windows.Controls.TextBlock> Elementen angezeigt.  
  
 ![Mehrere Positionierungseigenschaften in einer Anwendung](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>Nächste Schritte  
 Positionierungs Eigenschaften, die durch die-Klasse definiert werden, <xref:System.Windows.FrameworkElement> ermöglichen eine Feinsteuerung der Element Platzierung innerhalb von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen. Ihnen sind nun unterschiedliche Techniken bekannt, die Sie verwenden können, um Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besser positionieren zu können.  
  
 Zusätzliche Ressourcen sind verfügbar, die das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Layout ausführlicher erläutern. Das Thema [Übersicht über Panels](../controls/panels-overview.md) enthält weitere Details zu den verschiedenen <xref:System.Windows.Controls.Panel> Elementen. Das Thema Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md) führt erweiterte Techniken ein, die Layoutelemente verwenden, um Komponenten zu positionieren und ihre Aktionen an Datenquellen zu binden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Übersicht über Panel-Elemente](../controls/panels-overview.md)
- [Layout](layout.md)
- [Beispiel für einen WPF-Layoutkatalog](https://go.microsoft.com/fwlink/?LinkID=160054)
