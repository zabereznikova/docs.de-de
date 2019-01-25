---
title: 'Vorgehensweise: Zeichnen eines Rechtecks'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: b8434a8935a8e2f79aff17b96d20c8798f96e9fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674676"
---
# <a name="how-to-draw-a-rectangle"></a>Vorgehensweise: Zeichnen eines Rechtecks
In diesem Beispiel wird gezeigt, wie zum Zeichnen eines Rechtecks mit dem <xref:System.Windows.Shapes.Rectangle> Element.  
  
 Um ein Rechteck zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Rectangle> Element, und geben Sie die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>. Um die Fläche des Rechtecks zu zeichnen, legen Sie dessen <xref:System.Windows.Shapes.Shape.Fill%2A>. Um dem Rechteck eine Gliederung zu gewähren, verwenden Sie die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften.  
  
 Um dem Rechteck abgerundete Ecken, geben Sie den optionalen <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften. Die <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften festlegen, die x- und y-Radien der Ellipse, der zum Abrunden der Ecken des Rechtecks verwendet wird.  
  
 Im folgenden Beispiel zwei <xref:System.Windows.Shapes.Rectangle> Elemente gezeichnet werden, einem <xref:System.Windows.Controls.Canvas>. Die erste Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren. Das zweite Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren, eine <xref:System.Windows.Media.Brushes.Black%2A> Kontur und abgerundeten Ecken.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Rechtecken enthalten, können Sie Rechteck Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt. In der Tat Rechtecke eignen sich besonders für die Bereitstellung von Hintergründen für Teile des <xref:System.Windows.Controls.Grid> Bereiche. Ein Beispiel finden Sie unter den [Tabellenübersicht](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Shapes.Rectangle>
- [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über Tabellen](../../../../docs/framework/wpf/advanced/table-overview.md)
