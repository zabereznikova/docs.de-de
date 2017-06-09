---
title: "Gewusst wie: Festlegen der Breiteneigenschaften eines Elements | Microsoft Docs"
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
  - "Panel-Steuerelement, Width-Eigenschaften von Elementen"
  - "Width-Eigenschaften"
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Festlegen der Breiteneigenschaften eines Elements
## Beispiel  
 In diesem Beispiel werden die Unterschiede im Renderingverhalten zwischen den vier breitenbezogenen Eigenschaften in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] visuell veranschaulicht.  
  
 Die Breitenmerkmale eines Elements werden von vier Eigenschaften beschrieben, die von der <xref:System.Windows.FrameworkElement>\-Klasse verfügbar gemacht werden.  Diese vier Eigenschaften können zu Konflikten führen. Sollte dies der Fall sein, wird der vorrangige Wert folgendermaßen definiert: Der <xref:System.Windows.FrameworkElement.MinWidth%2A>\-Wert hat Vorrang vor dem <xref:System.Windows.FrameworkElement.MaxWidth%2A>\-Wert, der wiederum Vorrang vor dem <xref:System.Windows.FrameworkElement.Width%2A>\-Wert hat.  Die vierte Eigenschaft <xref:System.Windows.FrameworkElement.ActualWidth%2A> ist schreibgeschützt und meldet die tatsächliche Breite, wie von Interaktionen mit dem Layoutprozess bestimmt.  
  
 In den folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispielen wird ein <xref:System.Windows.Shapes.Rectangle>\-Element \(`rect1`\) als untergeordnetes Element der <xref:System.Windows.Controls.Canvas> dargestellt.  Die Breiteneigenschaften von einem <xref:System.Windows.Shapes.Rectangle> können mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox>\-Elementen geändert werden, die die Eigenschaftswerte von <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> und <xref:System.Windows.FrameworkElement.Width%2A> darstellen.  Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.  
  
 [!code-xml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 In den folgenden CodeBehind\-Beispielen werden die Ereignisse behandelt, die das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>\-Ereignis auslöst.  Jede benutzerdefinierte Methode übernimmt die Eingabe vom <xref:System.Windows.Controls.ListBox>, analysiert den Wert als <xref:System.Double> und wendet den Wert auf die angegebene breitenbezogene Eigenschaft an.  Die Breitenwerte werden außerdem in eine Zeichenfolge konvertiert und in verschiedene <xref:System.Windows.Controls.TextBlock>\-Elemente geschrieben \(die Definition dieser Elemente wird nicht im ausgewählten XAML angezeigt\).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für den Vergleich von Breiteneigenschaften](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>   
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>   
 <xref:System.Windows.FrameworkElement.MinWidth%2A>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Festlegen der Höheneigenschaften eines Elements](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)   
 [Beispiel für den Vergleich von Breiteneigenschaften](http://go.microsoft.com/fwlink/?LinkID=160050)