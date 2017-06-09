---
title: "Gewusst wie: Abrufen des Offsets eines visuellen Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Abrufen von Offsetwerten aus visuellen Objekten"
  - "Offset-Werte, Abrufen aus visuellen Objekten"
  - "Abrufen von Offsetwerten aus visuellen Objekten"
  - "Visuelle Objekte, Abrufen von Offsetwerten aus"
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Abrufen des Offsets eines visuellen Objekts
Diese Beispiele zeigen, wie Sie den Offsetwert eines visuellen Objekts abrufen, das relativ zu seinem übergeordneten Element oder einem beliebigen Vorgänger oder Nachfolger angeordnet ist.  
  
## Beispiel  
 Das folgende Markupbeispiel zeigt einen <xref:System.Windows.Controls.TextBlock>, für den unter <xref:System.Windows.FrameworkElement.Margin%2A> der Wert 4 definiert ist.  
  
 [!code-xml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 Im folgenden Codebeispiel wird die Verwendung der <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A>\-Methode zum Abrufen des Offsets für den <xref:System.Windows.Controls.TextBlock> veranschaulicht.  Die Offsetwerte sind im zurückgegebenen <xref:System.Windows.Vector>\-Wert enthalten.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 Für den Offset wird der <xref:System.Windows.FrameworkElement.Margin%2A>\-Wert berücksichtigt.  In diesem Fall hat <xref:System.Windows.Vector.X%2A> den Wert 4 und <xref:System.Windows.Vector.Y%2A> ebenfalls den Wert 4.  
  
 Der zurückgegebene Offsetwert verhält sich relativ zum übergeordneten Element von <xref:System.Windows.Media.Visual>.  Wenn Sie einen Offsetwert zurückgeben möchten, der sich nicht relativ zum übergeordneten Element eines <xref:System.Windows.Media.Visual>\-Elements verhält, verwenden Sie die <xref:System.Windows.Media.Visual.TransformToAncestor%2A>\-Methode.  
  
## Abrufen des Offsetwerts relativ zu einem Vorgänger  
 Das folgende Markupbeispiel zeigt einen <xref:System.Windows.Controls.TextBlock>, der in zwei <xref:System.Windows.Controls.StackPanel>\-Objekten geschachtelt ist.  
  
 [!code-xml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 In der folgenden Abbildung sind die Ergebnisse des Markups dargestellt.  
  
 ![Versatzwerte für Objekte](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset\_01")  
TextBlock in zwei StackPanels geschachtelt  
  
 Das folgende Codebeispiel zeigt, wie Sie die <xref:System.Windows.Media.Visual.TransformToAncestor%2A>\-Methode zum Abrufen des Offsetwerts von <xref:System.Windows.Controls.TextBlock> relativ zum enthaltenden <xref:System.Windows.Window>\-Element verwenden.  Die Offsetwerte sind im zurückgegebenen <xref:System.Windows.Media.GeneralTransform>\-Wert enthalten.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 Beim Offset werden die <xref:System.Windows.FrameworkElement.Margin%2A>\-Werte für alle Objekte innerhalb des enthaltenden <xref:System.Windows.Window>\-Elements berücksichtigt.  In diesem Fall ist <xref:System.Windows.Vector.X%2A> 28 \(16 \+ 8 \+ 4\) und <xref:System.Windows.Vector.Y%2A> ebenfalls 28.  
  
 Der zurückgegebene Offsetwert verhält sich relativ zum Vorgänger von <xref:System.Windows.Media.Visual>.  Wenn Sie einen Offsetwert zurückgeben möchten, der sich relativ zum Nachfolger eines <xref:System.Windows.Media.Visual>\-Elements verhält, verwenden Sie die <xref:System.Windows.Media.Visual.TransformToDescendant%2A>\-Methode.  
  
## Abrufen des Offsetwerts relativ zu einem Nachfolger  
 Das folgende Markupbeispiel zeigt einen <xref:System.Windows.Controls.TextBlock>, der in einem <xref:System.Windows.Controls.StackPanel>\-Objekt enthalten ist.  
  
 [!code-xml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 Im folgenden Codebeispiel wird die Verwendung der <xref:System.Windows.Media.Visual.TransformToDescendant%2A>\-Methode zum Abrufen des Offsets für den <xref:System.Windows.Controls.StackPanel> relativ zu dessen untergeordnetem <xref:System.Windows.Controls.TextBlock> veranschaulicht.  Die Offsetwerte sind im zurückgegebenen <xref:System.Windows.Media.GeneralTransform>\-Wert enthalten.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 Beim Offset werden die <xref:System.Windows.FrameworkElement.Margin%2A>\-Werte für alle Objekte berücksichtigt.  In diesem Fall hat <xref:System.Windows.Vector.X%2A> den Wert \-4 und <xref:System.Windows.Vector.Y%2A> ebenfalls den Wert \-4.  Die Offsetwerte sind negative Werte, da das übergeordnete Objekt relativ zu dessen untergeordnetem Objekt negativ versetzt ist.  
  
## Siehe auch  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)