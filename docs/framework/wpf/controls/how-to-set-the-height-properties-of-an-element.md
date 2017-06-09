---
title: "Gewusst wie: Festlegen der H&#246;heneigenschaften eines Elements | Microsoft Docs"
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
  - "Height-Eigenschaften"
  - "Panel-Steuerelement, Height-Eigenschaften von Elementen"
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Festlegen der H&#246;heneigenschaften eines Elements
## Beispiel  
 In diesem Beispiel werden die Unterschiede im Renderingverhalten zwischen den vier höhenbezogenen Eigenschaften in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] visuell veranschaulicht.  
  
 Die Höhenmerkmale eines Elements werden von vier Eigenschaften beschrieben, die von der <xref:System.Windows.FrameworkElement>\-Klasse verfügbar gemacht werden.  Diese vier Eigenschaften können zu Konflikten führen. Sollte dies der Fall sein, wird der vorrangige Wert folgendermaßen definiert: Der <xref:System.Windows.FrameworkElement.MinHeight%2A>\-Wert hat Vorrang vor dem <xref:System.Windows.FrameworkElement.MaxHeight%2A>\-Wert, der wiederum Vorrang vor dem <xref:System.Windows.FrameworkElement.Height%2A>\-Wert hat.  Eine vierte Eigenschaft, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, ist schreibgeschützt und meldet die tatsächliche Höhe, wie von Interaktionen mit dem Layoutprozess bestimmt.  
  
 In den folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Beispielen wird ein <xref:System.Windows.Shapes.Rectangle>\-Element \(`rect1`\) als untergeordnetes Element der <xref:System.Windows.Controls.Canvas> dargestellt.  Die Höheneigenschaften von einem <xref:System.Windows.Shapes.Rectangle> können mithilfe einer Reihe von <xref:System.Windows.Controls.ListBox>\-Elementen geändert werden, die die Eigenschaftswerte von <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> und <xref:System.Windows.FrameworkElement.Height%2A> darstellen.  Auf diese Weise wird die Rangfolge jeder Eigenschaft visuell angezeigt.  
  
 [!code-xml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 In den folgenden CodeBehind\-Beispielen werden die Ereignisse behandelt, die das <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>\-Ereignis auslöst.  Jeder Handler übernimmt die Eingabe aus <xref:System.Windows.Controls.ListBox>, analysiert den Wert als <xref:System.Double> und wendet den Wert auf die angegebene höhenbezogene Eigenschaft an.  Die Höhenwerte werden außerdem in eine Zeichenfolge konvertiert und in verschiedene <xref:System.Windows.Controls.TextBlock>\-Elemente geschrieben \(die Definition dieser Elemente wird nicht im ausgewählten XAML angezeigt\).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Height\-Eigenschaften](http://go.microsoft.com/fwlink/?LinkID=159993).  
  
## Siehe auch  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>   
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>   
 <xref:System.Windows.FrameworkElement.MinHeight%2A>   
 <xref:System.Windows.FrameworkElement.Height%2A>   
 [Festlegen der Breiteneigenschaften eines Elements](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Beispiel für Height\-Eigenschaften](http://go.microsoft.com/fwlink/?LinkID=159993)