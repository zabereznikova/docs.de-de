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
ms.openlocfilehash: ddeada8619d1b6c8970f1efb7cca1bc98773d0c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43391970"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Gewusst wie: Zeichnen einer Ellipse oder eines Kreises
In diesem Beispiel wird gezeigt, wie zum Zeichnen von Ellipsen und Kreisen mithilfe der <xref:System.Windows.Shapes.Ellipse> Element. Um eine Ellipse zeichnen, erstellen eine <xref:System.Windows.Shapes.Ellipse> Element, und geben Sie die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>. Verwenden der <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft an die <xref:System.Windows.Media.Brush> , mit dem das Innere der Ellipse gezeichnet werden soll. Verwenden der <xref:System.Windows.Shapes.Shape.Stroke%2A> -Eigenschaft an die <xref:System.Windows.Media.Brush> , wird verwendet, um die Kontur der Ellipse gezeichnet werden soll. Die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft gibt die Stärke der Kontur Ellipse an.  
  
 Um einen Kreis zu zeichnen, stellen die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Shapes.Ellipse> Element, das jeweils anderen.  
  
 Das folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Ellipse> Elemente innerhalb einer <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> um die Ellipsen zu enthalten, können Sie Ellipse Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037)
