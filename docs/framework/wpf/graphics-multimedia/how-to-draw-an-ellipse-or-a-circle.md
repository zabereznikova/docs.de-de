---
title: "Gewusst wie: Zeichnen einer Ellipse oder eines Kreises | Microsoft Docs"
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
  - "Kreise, Zeichnen"
  - "Zeichnen von Kreisen"
  - "Zeichnen von Ellipsen"
  - "Ellipsen, Zeichnen"
  - "Grafiken, Zeichnen von Kreisen"
  - "Grafiken, Zeichnen von Ellipsen"
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Zeichnen einer Ellipse oder eines Kreises
In diesem Beispiel wird dargestellt, wie mit dem <xref:System.Windows.Shapes.Ellipse>\-Element Ellipsen und Kreise gezeichnet werden.  Um eine Ellipse zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Ellipse>\-Element und legen dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> fest.  Verwenden Sie die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft, um den <xref:System.Windows.Media.Brush> festzulegen, der zum Zeichnen des Innenbereichs der Ellipse verwendet wird.  Verwenden Sie die <xref:System.Windows.Shapes.Shape.Stroke%2A>\-Eigenschaft, um den <xref:System.Windows.Media.Brush> festzulegen, der zum Zeichnen der Umrisslinie der Ellipse verwendet wird.  Durch die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>\-Eigenschaft wird die Breite der Ellipsenumrisslinie festgelegt.  
  
 Zum Zeichnen eines Kreises müssen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> des <xref:System.Windows.Shapes.Ellipse>\-Elements identisch sein.  
  
 Im folgenden Beispiel werden vier <xref:System.Windows.Shapes.Ellipse>\-Elemente innerhalb eines <xref:System.Windows.Controls.Canvas>\-Elements gezeichnet.  
  
## Beispiel  
 [!code-xml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 In diesem Beispiel sind die Ellipsen in einem <xref:System.Windows.Controls.Canvas>\-Element enthalten, Sie können jedoch Ellipsenelemente wie jedes andere Formelement mit allen <xref:System.Windows.Controls.Panel>\- oder <xref:System.Windows.Controls.Control>\-Elementen verwenden, von denen Inhalte unterstützt werden, bei denen es sich nicht um Text handelt.  
  
 Dieses Beispiel gehört zu einem größeren Beispiel. Das vollständige Beispiel finden Sie unter [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Siehe auch  
 <xref:System.Windows.Shapes.Ellipse>   
 <xref:System.Windows.Shapes.Shape>   
 [Beispiel für Formelemente](http://go.microsoft.com/fwlink/?LinkID=160037)