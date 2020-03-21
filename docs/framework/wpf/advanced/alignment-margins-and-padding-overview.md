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
ms.openlocfilehash: bec2d9cd224febb650e2de67bb7406365d075963
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145474"
---
# <a name="alignment-margins-and-padding-overview"></a>Übersicht über Alignment, Margin und Padding
Die <xref:System.Windows.FrameworkElement> Klasse macht mehrere Eigenschaften verfügbar, die zum präzisen Positionieren von untergeordneten Elementen verwendet werden. In diesem Thema werden vier der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.Margin%2A>wichtigsten <xref:System.Windows.Controls.Border.Padding%2A>Eigenschaften <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>behandelt: , , und . Es ist wichtig, die Auswirkungen dieser Eigenschaften zu verstehen, da Sie die Grundlage für das Steuern der Position von Elementen in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen bieten.  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>Einführung in die Positionierung des Elements  
 Es gibt zahlreiche Möglichkeiten, Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu positionieren. Das Erreichen eines idealen Layouts <xref:System.Windows.Controls.Panel> geht jedoch über die einfache Auswahl des richtigen Elements hinaus. Eine feine Positionierung erfordert <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>ein <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>Verständnis <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> der , , und Eigenschaften.  
  
 Die folgende Abbildung zeigt ein Layoutszenario, das verschiedene Positionierungseigenschaften verwendet.  
  
 ![Beispiel für WPF-Positionierungseigenschaften](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 Auf den ersten <xref:System.Windows.Controls.Button> Blick scheinen die Elemente in dieser Abbildung zufällig platziert zu sein. Die Positionen werden jedoch tatsächlich genau mithilfe einer Kombination aus Rändern, Ausrichtungen und Abständen gesteuert.  
  
 Im folgende Beispiel wird beschrieben, wie das Layout in der vorhergehenden Darstellung erstellt wird. Ein <xref:System.Windows.Controls.Border> Element kapselt ein <xref:System.Windows.Controls.StackPanel>übergeordnetes <xref:System.Windows.Controls.Border.Padding%2A> Element mit einem Wert von 15 geräteunabhängigen Pixeln. Dies ist <xref:System.Windows.Media.Brushes.LightBlue%2A> für das schmale <xref:System.Windows.Controls.StackPanel>Band, das das Kind umgibt. Untergeordnete Elemente <xref:System.Windows.Controls.StackPanel> der werden verwendet, um jede der verschiedenen Positionierungseigenschaften zu veranschaulichen, die in diesem Thema detailliert beschrieben werden. Drei <xref:System.Windows.Controls.Button> Elemente werden verwendet, <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> um sowohl die als auch die Eigenschaften zu demonstrieren.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Das folgende Diagramm zeigt eine vergrößerte Ansicht der verschiedenen Positionierungseigenschaften, die im vorhergehenden Beispiel verwendet werden. Die nachfolgenden Abschnitte in diesem Thema beschreiben genauer, wie jede Positionierungseigenschaft verwendet wird.  
  
 ![Positionierungseigenschaften mit Bildschirmaufruf&#45;Outs](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>Verstehen von Ausrichtungseigenschaften  
 Die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> und Eigenschaften beschreiben, wie ein untergeordnetes Element innerhalb des zugewiesenen Layoutbereichs eines übergeordneten Elements positioniert werden soll. Indem Sie diese Eigenschaften zusammen verwenden, können Sie untergeordnete Elemente präzise positionieren. <xref:System.Windows.Controls.DockPanel> Beispielsweise können untergeordnete Elemente eines vier verschiedene horizontale <xref:System.Windows.HorizontalAlignment.Right>Achsen <xref:System.Windows.HorizontalAlignment.Center>angeben: <xref:System.Windows.HorizontalAlignment.Stretch> <xref:System.Windows.HorizontalAlignment.Left>, oder , oder zum Ausfüllen des verfügbaren Raums. Ähnliche Werte sind für die vertikale Positionierung verfügbar.  
  
> [!NOTE]
> Explizit festgelegt <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> und Eigenschaften für ein <xref:System.Windows.HorizontalAlignment.Stretch> Element haben Vorrang vor dem Eigenschaftswert. Der Versuch, <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A>, , <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und `Stretch` einen `Stretch` Wert von Ergebnissen festzulegen, in dem die Anforderung ignoriert wird.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>HorizontalAlignment-Eigenschaft  
 Die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaft deklariert die horizontalen Ausrichtungsmerkmale für untergeordnete Elemente. Die folgende Tabelle zeigt jeden möglichen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Wert der Eigenschaft.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Untergeordnete Elemente werden auf der linken Seite des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Untergeordnete Elemente werden rechts vom zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. <xref:System.Windows.FrameworkElement.Width%2A> Explizite <xref:System.Windows.FrameworkElement.Height%2A> und Werte haben Vorrang.|  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> wie <xref:System.Windows.Controls.Button> die Eigenschaft auf Elemente angewendet wird. Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die Positionierungseffekte <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> der einzelnen Werte sind in der Abbildung sichtbar.  
  
 ![HorizontalAlignment-Beispiel](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>VerticalAlignment-Eigenschaft  
 Die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Eigenschaft beschreibt die vertikalen Ausrichtungsmerkmale, die auf untergeordnete Elemente angewendet werden sollen. Die folgende Tabelle zeigt jeden der <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> möglichen Werte für die Eigenschaft.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Untergeordnete Elemente werden oben im zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Center>|Untergeordnete Elemente werden in der Mitte des zugewiesenen Layoutbereich des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Untergeordnete Elemente werden am unteren Rand des zugewiesenen Layoutbereichs des übergeordneten Elements ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (Standard)|Untergeordnete Elemente werden gestreckt, um zugewiesenen Layoutbereich des übergeordneten Elements auszufüllen. <xref:System.Windows.FrameworkElement.Width%2A> Explizite <xref:System.Windows.FrameworkElement.Height%2A> und Werte haben Vorrang.|  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> wie <xref:System.Windows.Controls.Button> die Eigenschaft auf Elemente angewendet wird. Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen. Für die Zwecke dieses <xref:System.Windows.Controls.Grid> Beispiels wird ein Element mit sichtbaren Rasterlinien als übergeordnetes Element verwendet, um das Layoutverhalten der einzelnen Eigenschaftswerte besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Der vorhergehende Code gibt ein Layout ähnlich dem folgenden aus. Die Positionierungseffekte <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> der einzelnen Werte sind in der Abbildung sichtbar.  
  
 ![Beispiel für VerticalAlignment-Eigenschaft](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>Verstehen von Margin-Eigenschaften  
 Die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft beschreibt den Abstand zwischen einem Element und seinem untergeordneten Element oder Gleichaltrigen. <xref:System.Windows.FrameworkElement.Margin%2A>Werte können einheitlich sein, `Margin="20"`indem Syntax wie verwendet wird. Mit dieser Syntax <xref:System.Windows.FrameworkElement.Margin%2A> würde eine Uniform von 20 geräteunabhängigen Pixeln auf das Element angewendet. <xref:System.Windows.FrameworkElement.Margin%2A>Werte können auch die Form von vier unterschiedlichen Werten annehmen, wobei jeder Wert einen unterschiedlichen Rand `Margin="0,10,5,25"`beschreibt, der auf den linken, oberen, rechten und unteren Wert (in dieser Reihenfolge) angewendet werden soll, z. B. . Die ordnungsgemäße <xref:System.Windows.FrameworkElement.Margin%2A> Verwendung der Eigenschaft ermöglicht eine sehr feine Kontrolle der Renderposition eines Elements und der Renderposition seiner Nachbarelemente und untergeordneten Elemente.  
  
> [!NOTE]
> Ein Rand ungleich Null wendet <xref:System.Windows.FrameworkElement.ActualWidth%2A> Den <xref:System.Windows.FrameworkElement.ActualHeight%2A>Raum außerhalb der Elementelemente und an .  
  
 Das folgende Beispiel zeigt, wie einheitliche <xref:System.Windows.Controls.Button> Ränder um eine Gruppe von Elementen angewendet werden. Die <xref:System.Windows.Controls.Button> Elemente sind gleichmäßig mit einem Zehn-Pixel-Randpuffer in jede Richtung verteilt.  
  
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
 Die Polsterung <xref:System.Windows.FrameworkElement.Margin%2A> ähnelt in den meisten Punkten. Die Padding-Eigenschaft wird nur für wenige Klassen verfügbar <xref:System.Windows.Documents.Block> <xref:System.Windows.Controls.Border>gemacht, hauptsächlich als Bequemlichkeit: , <xref:System.Windows.Controls.Control>, und <xref:System.Windows.Controls.TextBlock> sind Beispiele für Klassen, die eine Padding-Eigenschaft verfügbar machen. Die <xref:System.Windows.Controls.Border.Padding%2A> Eigenschaft vergrößert die effektive Größe eines <xref:System.Windows.Thickness> untergeordneten Elements um den angegebenen Wert.  
  
 Das folgende Beispiel zeigt, wie <xref:System.Windows.Controls.Border> sie auf ein übergeordnetes Element angewendet <xref:System.Windows.Controls.Border.Padding%2A> werden.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Verwenden von Alignment, Margin und Padding in einer Anwendung  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , und stellen Sie die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]Positionierungssteuerung bereit, die zum Erstellen eines komplexen erforderlich ist. Sie können die Effekte jeder Eigenschaft verwenden, um die Positionierung untergeordneter Elemente zu ändern, wodurch die Flexibilität beim Erstellen dynamischer Anwendungen und Benutzererfahrungen sichergestellt wird.  
  
 Das folgende Beispiel zeigt die einzelnen Konzepte, die in diesem Thema beschrieben werden. Aufbauend auf der Infrastruktur, die im ersten Beispiel <xref:System.Windows.Controls.Grid> in diesem Thema <xref:System.Windows.Controls.Border> gefunden wurde, fügt dieses Beispiel ein Element als untergeordnetes Element des im ersten Beispiel hinzu. <xref:System.Windows.Controls.Border.Padding%2A>wird auf das <xref:System.Windows.Controls.Border> übergeordnete Element angewendet. Der <xref:System.Windows.Controls.Grid> wird verwendet, um <xref:System.Windows.Controls.StackPanel> den Speicherplatz zwischen drei untergeordneten Elementen zu partitionieren. <xref:System.Windows.Controls.Button>Elemente werden erneut verwendet, um <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>die verschiedenen Effekte von und zu zeigen. <xref:System.Windows.Controls.TextBlock>Elemente werden jedem <xref:System.Windows.Controls.ColumnDefinition> Element hinzugefügt, um die <xref:System.Windows.Controls.Button> verschiedenen Eigenschaften, die auf die Elemente in jeder Spalte angewendet werden, besser zu definieren.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 Nach dem Kompilieren der Anwendung wird eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ausgegeben, die wie die folgende Darstellung aussieht. Die Auswirkungen der verschiedenen Eigenschaftswerte sind im Abstand zwischen Elementen deutlich, und <xref:System.Windows.Controls.TextBlock> signifikante Eigenschaftswerte für Elemente in jeder Spalte werden in Elementen angezeigt.  
  
 ![Mehrere Positionierungseigenschaften in einer Anwendung](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>Nächste Schritte  
 Positioniereigenschaften, <xref:System.Windows.FrameworkElement> die von der Klasse [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert werden, ermöglichen eine feine Steuerung der Elementplatzierung in Anwendungen. Ihnen sind nun unterschiedliche Techniken bekannt, die Sie verwenden können, um Elemente mithilfe von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] besser positionieren zu können.  
  
 Zusätzliche Ressourcen sind verfügbar, die das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Layout ausführlicher erläutern. Das Thema ["Bedienfeldübersicht"](../controls/panels-overview.md) enthält <xref:System.Windows.Controls.Panel> weitere Details zu den verschiedenen Elementen. Das Thema [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md) führt erweiterte Techniken ein, die Layoutelemente verwenden, um Komponenten zu positionieren und ihre Aktionen an Datenquellen zu binden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Übersicht über Panel-Elemente](../controls/panels-overview.md)
- [Layout](layout.md)
- [Beispiel für einen WPF-Layoutkatalog](https://go.microsoft.com/fwlink/?LinkID=160054)
