---
title: 'Gewusst wie: Zeichnen einer Ellipse oder eines Kreises'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452921"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Gewusst wie: Zeichnen einer Ellipse oder eines Kreises
In diesem Beispiel wird gezeigt, wie Ellipsen und Kreise mithilfe des <xref:System.Windows.Shapes.Ellipse>-Elements gezeichnet werden. Um eine Ellipse zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Ellipse>-Element, und geben Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>an. Verwenden Sie die <xref:System.Windows.Shapes.Shape.Fill%2A>-Eigenschaft, um die <xref:System.Windows.Media.Brush> anzugeben, die verwendet wird, um das Innere der Ellipse zu zeichnen. Verwenden Sie die <xref:System.Windows.Shapes.Shape.Stroke%2A>-Eigenschaft, um die <xref:System.Windows.Media.Brush> anzugeben, die zum Zeichnen der Gliederung der Ellipse verwendet werden. Die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>-Eigenschaft gibt die Stärke der Ellipse-Gliederung an.  
  
 Um einen Kreis zu zeichnen, machen Sie die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> des <xref:System.Windows.Shapes.Ellipse> Elements gleich einander.  
  
 Im folgenden Beispiel werden vier <xref:System.Windows.Shapes.Ellipse> Elemente innerhalb eines <xref:System.Windows.Controls.Canvas>gezeichnet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> mit den Auslassungs Zeichen verwendet wird, können Sie Ellipse-Elemente (und alle anderen Shape-Elemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> verwenden, die nicht Textinhalte unterstützen.  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
