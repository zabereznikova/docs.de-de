---
title: "Gewusst wie: Zeichnen eines Rechtecks | Microsoft Docs"
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
  - "Zeichnen, Rechtecke"
  - "Grafiken [WPF], Rechtecke"
  - "Rechtecke, Zeichnen"
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Zeichnen eines Rechtecks
In diesem Beispiel wird veranschaulicht, wie Sie mithilfe des <xref:System.Windows.Shapes.Rectangle>\-Elements ein Rechteck zeichnen.  
  
 Um ein Rechteck zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Rectangle>\-Element und legen dessen <xref:System.Windows.FrameworkElement.Width%2A> sowie dessen <xref:System.Windows.FrameworkElement.Height%2A> fest.  Um die Fläche des Rechtecks zu zeichnen, müssen Sie dessen <xref:System.Windows.Shapes.Shape.Fill%2A> festlegen.  Um dem Rechteck einen Rand hinzuzufügen, verwenden Sie die zugehörigen Eigenschaften <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 Um dem Rechteck abgerundete Ecken hinzuzufügen, geben Sie die optionalen Eigenschaften für <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> an.  Die Eigenschaften <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> legen den x\-Achsenradius und den y\-Achsenradius der Ellipse fest, die zum Abrunden der Ecken des Rechtecks verwendet wird.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Shapes.Rectangle>\-Elemente in einer <xref:System.Windows.Controls.Canvas> gezeichnet.  Das erste Rechteck verfügt über einen <xref:System.Windows.Media.Brushes.Blue%2A>\-Innenbereich.  Das zweite Rechteck verfügt über einen <xref:System.Windows.Media.Brushes.Blue%2A>\-Innenbereich, einen <xref:System.Windows.Media.Brushes.Black%2A>\-Rahmen und abgerundete Ecken.  
  
## Beispiel  
 [!code-xml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> als Container für die Polylinien verwendet wird, können Polylinien\-Elemente \(sowie alle anderen Formelemente\) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> verwendet werden, die Inhalte unterstützen, bei denen es sich nicht um Text handelt.  Rechtecke lassen sich besonders gut als Hintergrund für Teile von <xref:System.Windows.Controls.Grid>\-Bereichen einsetzen.  Ein Beispiel hierfür finden Sie unter [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Siehe auch  
 <xref:System.Windows.Shapes.Rectangle>   
 [Beispiel für Formelemente](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)