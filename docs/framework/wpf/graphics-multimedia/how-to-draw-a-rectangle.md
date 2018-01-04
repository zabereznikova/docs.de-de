---
title: 'Gewusst wie: Zeichnen eines Rechtecks'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58f29783e48aa7173010ffec6a65f9ac1d8a2b62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-rectangle"></a>Gewusst wie: Zeichnen eines Rechtecks
Dieses Beispiel zeigt, wie Sie ein Rechteck mit dem <xref:System.Windows.Shapes.Rectangle> Element.  
  
 Erstellen Sie ein Rechteck, ein <xref:System.Windows.Shapes.Rectangle> Element, und geben Sie ihre <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>. Um innerhalb des Rechtecks zeichnen, legen Sie dessen <xref:System.Windows.Shapes.Shape.Fill%2A>. Um dem Rechteck eine Gliederung gewähren, verwenden Sie die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften.  
  
 So erteilen Sie das Rechteck abgerundete Ecken, geben Sie den optionalen <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften. Die <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften festlegen, die x- und y-Achse Radien der Ellipse, der zum Abrunden der Ecken des Rechtecks verwendet wird.  
  
 Im folgenden Beispiel zwei <xref:System.Windows.Shapes.Rectangle> Elemente werden in gezeichnet eine <xref:System.Windows.Controls.Canvas>. Die erste Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren. Das zweite Rechteck hat eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren, eine <xref:System.Windows.Media.Brushes.Black%2A> Gliederung und abgerundete Ecken.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Obwohl in diesem Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> Rechtecke enthalten, können Sie Rechteck Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt. In der Tat Rechtecke sind besonders nützlich für das Bereitstellen von Hintergründe für Teile der <xref:System.Windows.Controls.Grid> Bereiche. Ein Beispiel finden Sie die [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Form-Elemente-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Rectangle>  
 [Beispiel für Form-Elemente](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)
