---
title: "&#220;bersicht &#252;ber Alignment, Margin und Padding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ausrichten"
  - "Klassen, FrameworkElement"
  - "FrameworkElement-Klasse"
  - "Ränder"
  - "Abstand"
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# &#220;bersicht &#252;ber Alignment, Margin und Padding
Von der <xref:System.Windows.FrameworkElement>\-Klasse werden verschiedene Eigenschaften verfügbar gemacht, die verwendet werden können, um untergeordnete Elemente genau zu positionieren.  In diesem Thema werden vier der wichtigsten Eigenschaften erläutert: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  Es ist wichtig, die Auswirkungen dieser Eigenschaften zu verstehen, da sie die Grundlage zur Steuerung der Elementpositionierung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen darstellen.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## Einführung in die Elementpositionierung  
 Es gibt zahlreiche Möglichkeiten, Elemente mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zu positionieren.  Zur Erstellung eines idealen Layouts ist es jedoch nicht ausreichend, einfach nur die richtigen <xref:System.Windows.Controls.Panel>\-Elemente auszuwählen.  Zur Feinsteuerung der Positionierung sollten Sie die Eigenschaften <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> verstehen.  
  
 In der folgenden Abbildung ist ein Layoutszenario dargestellt, in dem verschiedene Positionierungseigenschaften verwendet werden.  
  
 ![Beispiel für WPF&#45;Positionierungseigenschaften](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.png "layout\_margins\_padding\_alignment\_graphic1")  
  
 Auf den ersten Blick erscheint die Positionierung der <xref:System.Windows.Controls.Button>\-Elemente in dieser Abbildung zufällig.  Tatsächlich sind ihre Positionen jedoch durch eine Kombination von Rändern, Ausrichtungen und Abständen exakt festgelegt.  
  
 Im folgenden Beispiel wird das Erstellen des Layouts für die oben dargestellte Abbildung beschrieben.  Ein <xref:System.Windows.Controls.Border>\-Element kapselt einen übergeordneten <xref:System.Windows.Controls.StackPanel> mit einem <xref:System.Windows.Controls.Border.Padding%2A>\-Wert von 15 [geräteunabhängigen Pixeln](GTMT).  Hieraus ergibt sich, dass der schmale <xref:System.Windows.Media.Brushes.LightBlue%2A>\-Streifen, das untergeordnete Element <xref:System.Windows.Controls.StackPanel> umgibt.  Die untergeordneten Elemente des <xref:System.Windows.Controls.StackPanel> werden verwendet, um alle der verschiedenen in diesem Thema ausführlich beschriebenen Positionierungseigenschaften darzustellen.  Drei <xref:System.Windows.Controls.Button>\-Elemente werden verwendet, um die Eigenschaften <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> zu veranschaulichen.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Die folgende Abbildung enthält eine vergrößerte Ansicht der verschiedenen Positionierungseigenschaften, die im vorherigen Beispiel verwendet werden.  In den folgenden Abschnitten dieses Themas wird die Verwendung jeder Positionierungseigenschaft ausführlich beschrieben.  
  
 ![Positionierungseigenschaften mit Bildschirmbeschriftungen](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.png "layout\_margins\_padding\_alignment\_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## Alignment\-Eigenschaften  
 Von den Eigenschaften <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> wird festgelegt, an welcher Stelle im zugewiesenen Layoutbereich eines übergeordneten Elements ein untergeordnetes Element positioniert wird.  Untergeordnete Elemente können mit diesen beiden Eigenschaften exakt positioniert werden.  Von den untergeordneten Elementen eines <xref:System.Windows.Controls.DockPanel> können beispielsweise vier verschiedene horizontale Ausrichtungen festgelegt werden: <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment> sowie <xref:System.Windows.HorizontalAlignment>, um den verfügbaren Platz auszufüllen.  Ähnliche Werte sind für die vertikale Positionierung verfügbar.  
  
> [!NOTE]
>  Explizit festgelegte Eigenschaften <xref:System.Windows.FrameworkElement.Height%2A> und <xref:System.Windows.FrameworkElement.Width%2A> haben in einem Element Vorrang vor dem <xref:System.Windows.HorizontalAlignment>\-Eigenschaftswert.  Wenn die Werte für <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> auf `Stretch` festgelegt werden, wird die `Stretch`\-Anforderung ignoriert.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### HorizontalAlignment\-Eigenschaft  
 Von der <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft werden die horizontalen Ausrichtungscharakteristiken deklariert, die auf untergeordnete Elemente angewendet werden.  In der folgenden Tabelle ist jeder mögliche Wert für die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft aufgeführt.  
  
|Member|Beschreibung|  
|------------|------------------|  
|<xref:System.Windows.HorizontalAlignment>|Untergeordnete Elemente werden im übergeordneten Element am linken Rand des zugewiesenen Layoutbereichs ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment>|Untergeordnete Elemente werden im zugewiesenen Layoutbereich des übergeordneten Elements zentriert ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment>|Untergeordnete Elemente werden im übergeordneten Element am rechten Rand des zugewiesenen Layoutbereichs ausgerichtet.|  
|<xref:System.Windows.HorizontalAlignment> \(Standard\)|Untergeordnete Elemente werden gestreckt, sodass sie den zugewiesenen Layoutbereich des übergeordneten Elements ausfüllen.  Explizite Werte für <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> haben Vorrang.|  
  
 Im folgenden Beispiel ist dargestellt, wie die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Button>\-Elemente angewendet wird.  Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Das durch den vorherigen Code erstellte Layout ähnelt der folgenden Abbildung.  In der Abbildung werden die Auswirkungen der einzelnen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>\-Werte auf die Positionierung dargestellt.  
  
 ![HorizontalAlignment&#45;Beispiel](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.png "layout\_horizontal\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### VerticalAlignment\-Eigenschaft  
 Von der <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Eigenschaft werden die vertikalen Ausrichtungscharakteristiken festgelegt, die auf untergeordnete Elemente angewendet werden.  In der folgenden Tabelle ist jeder mögliche Wert für die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Eigenschaft aufgeführt.  
  
|Member|Beschreibung|  
|------------|------------------|  
|<xref:System.Windows.VerticalAlignment>|Untergeordnete Elemente werden im übergeordneten Element am oberen Rand des zugewiesenen Layoutbereichs ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment>|Untergeordnete Elemente werden im zugewiesenen Layoutbereich des übergeordneten Elements zentriert ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment>|Untergeordnete Elemente werden im übergeordneten Element am unteren Rand des zugewiesenen Layoutbereichs ausgerichtet.|  
|<xref:System.Windows.VerticalAlignment> \(Standard\)|Untergeordnete Elemente werden gestreckt, sodass sie den zugewiesenen Layoutbereich des übergeordneten Elements ausfüllen.  Explizite Werte für <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> haben Vorrang.|  
  
 Im folgenden Beispiel ist dargestellt, wie die <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Button>\-Elemente angewendet wird.  Jeder Attributwert wird angezeigt, um die verschiedenen Renderingverhalten besser zu veranschaulichen.  Für dieses Beispiel wird als übergeordnetes Element ein <xref:System.Windows.Controls.Grid>\-Element mit sichtbaren Rasterlinien verwendet, um das Layoutverhalten für jeden Eigenschaftswert besser zu veranschaulichen.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Das durch den vorherigen Code erstellte Layout ähnelt der folgenden Abbildung.  In der Abbildung werden die Auswirkungen der einzelnen <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>\-Werte auf die Positionierung dargestellt.  
  
 ![Beispiel für VerticalAlignment&#45;Eigenschaft](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.png "layout\_vertical\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## Margin\-Eigenschaften  
 Die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft beschreibt die Entfernung zwischen einem Element und seinem untergeordneten Element oder Peers.  <xref:System.Windows.FrameworkElement.Margin%2A>\-Werte können einheitlich sein, mit Syntax wie `Margin="20"`.  Mit dieser Syntax wird ein einheitlicher <xref:System.Windows.FrameworkElement.Margin%2A>\-Wert von 20 [geräteunabhängigen Pixeln](GTMT) auf das Element angewendet.  Sie können auch vier verschiedene <xref:System.Windows.FrameworkElement.Margin%2A>\-Werte festlegen, von denen jeder einen unterschiedlichen Abstand für den linken, oberen, rechten und unteren Rand \(in dieser Reihenfolge\) darstellt, beispielsweise `Margin="0,10,5,25"`.  Wenn Sie die <xref:System.Windows.FrameworkElement.Margin%2A>\-Eigenschaft ordnungsgemäß verwenden, können Sie die Renderingposition eines Elements und dessen unter\- und nebengeordneten Elementen sehr präzise steuern.  
  
> [!NOTE]
>  Wenn der Wert für den Rand ungleich Null ist, wird der entsprechende Abstand außerhalb der <xref:System.Windows.FrameworkElement.ActualWidth%2A> und <xref:System.Windows.FrameworkElement.ActualHeight%2A> des Elements hinzugefügt.  
  
 Im folgenden Beispiel wird dargestellt, wie einheitliche Ränder um eine Gruppe von <xref:System.Windows.Controls.Button>\-Elementen hinzugefügt werden.  Die <xref:System.Windows.Controls.Button>\-Elemente werden gleichmäßig mit einem Randpuffer von zehn Pixel in jeder Richtung platziert.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 In vielen Fällen ist ein einheitlicher Rand nicht geeignet.  In diesen Fällen kann ein ungleichmäßiger Abstand angewendet werden.  Im folgenden Beispiel wird dargestellt, wie ein ungleichmäßiger Abstand auf untergeordnete Elemente angewendet wird.  Die Ränder werden in folgender Reihenfolge festgelegt: links, oben, rechts, unten.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## Padding\-Eigenschaft  
 Padding entspricht <xref:System.Windows.FrameworkElement.Margin%2A> in nahezu jeder Hinsicht.  Die Padding\-Eigenschaft ist vor allem aus Gründen der Einfachheit nur in wenigen Klassen verfügbar: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, und <xref:System.Windows.Controls.TextBlock> sind Beispiele für Klassen, in denen die Padding\-Eigenschaft verfügbar ist.  Die <xref:System.Windows.Controls.Border.Padding%2A>\-Eigenschaft vergrößert die effektive Größe eines untergeordneten Elements um den festgelegten <xref:System.Windows.Thickness>\-Wert.  
  
 Im folgenden Beispiel wird dargestellt, wie die <xref:System.Windows.Controls.Border.Padding%2A>\-Eigenschaft auf ein übergeordnetes <xref:System.Windows.Controls.Border>\-Element angewendet wird.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## Verwenden von Alignment, Margin und Padding in einer Anwendung  
 Mithilfe von <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> kann die Positionierung zum Erstellen einer komplexen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] gesteuert werden.  Sie können diese Eigenschaften verwenden, um die Positionierung untergeordneter Elemente zu ändern und beim Erstellen dynamischer Anwendungen die Flexibilität und Benutzerfreundlichkeit zu erhöhen.  
  
 Im folgenden Beispiel werden alle in diesem Thema beschriebenen Konzepte veranschaulicht.  Ausgehend von der im ersten Beispiel dieses Themas dargestellten Infrastruktur wird in diesem Beispiel ein <xref:System.Windows.Controls.Grid>\-Element als untergeordnetes Element des <xref:System.Windows.Controls.Border>\-Objekts im ersten Beispiel hinzugefügt.  <xref:System.Windows.Controls.Border.Padding%2A> wird auf das übergeordnete <xref:System.Windows.Controls.Border>\-Element angewendet.  Das <xref:System.Windows.Controls.Grid>\-Element wird verwendet, um den Bereich zwischen drei untergeordneten <xref:System.Windows.Controls.StackPanel>\-Elementen aufzuteilen.  Die <xref:System.Windows.Controls.Button>\-Elemente werden auch hier verwendet, um die verschiedenen Auswirkungen der Eigenschaften <xref:System.Windows.FrameworkElement.Margin%2A> und <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> darzustellen.  <xref:System.Windows.Controls.TextBlock>\-Elemente werden jedem <xref:System.Windows.Controls.ColumnDefinition>\-Element hinzugefügt, um die unterschiedlichen Eigenschaften genauer festzulegen, die auf die <xref:System.Windows.Controls.Button>\-Elemente in jeder Spalte angewendet werden.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 In der folgenden Abbildung ist die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung nach der Kompilierung dargestellt.  Die Auswirkungen der unterschiedlichen Eigenschaftswerte sind an den Abständen zwischen den Elementen erkennbar, und wichtige Eigenschaftswerte für die Elemente in jeder Spalte werden in <xref:System.Windows.Controls.TextBlock> angezeigt.  
  
 ![Mehrere Positionierungseigenschaften in einer Anwendung](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.png "layout\_margins\_padding\_aligment\_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## Weitere Informationen  
 Mithilfe der durch die <xref:System.Windows.FrameworkElement>\-Klasse festgelegten Positionierungseigenschaften können Sie die Platzierung von Elementen innerhalb von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen genau steuern.  Es stehen Ihnen nun mehrere Verfahren zur Verfügung, mit denen Sie unter Verwendung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente besser positionieren können.  
  
 Zusätzliche Ressourcen sind verfügbar, in denen das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layout ausführlicher beschrieben wird.  Im Thema [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md) finden Sie weitere Informationen zu den verschiedenen <xref:System.Windows.Controls.Panel>\-Elementen.  Im Thema [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) werden fortgeschrittene Techniken eingeführt, in denen Layoutelemente verwendet werden, um Komponenten zu positionieren und ihre Aktionen an Datenquellen zu binden.  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.Margin%2A>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)   
 [Beispiel für einen WPF\-Layoutkatalog](http://go.microsoft.com/fwlink/?LinkID=160054)