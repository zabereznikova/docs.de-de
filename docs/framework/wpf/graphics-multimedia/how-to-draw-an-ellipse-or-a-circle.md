---
title: 'Gewusst wie: Zeichnen einer Ellipse oder eines Kreises'
description: Erfahren Sie, wie Sie eine Ellipse oder einen Kreis mit Auswahlmöglichkeiten für die Gliederungs Stärke und innere Farbe in Windows Presentation Foundation (WPF) zeichnen.
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: afa0e7d2af42aaee39dca164f23b1a1cacf430ca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853560"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Gewusst wie: Zeichnen einer Ellipse oder eines Kreises
In diesem Beispiel wird gezeigt, wie Ellipsen und Kreise mithilfe des-Elements gezeichnet werden <xref:System.Windows.Shapes.Ellipse> . Um eine Ellipse zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Ellipse> -Element, und geben Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und an <xref:System.Windows.FrameworkElement.Height%2A> . Verwenden <xref:System.Windows.Shapes.Shape.Fill%2A> Sie die-Eigenschaft, um den anzugeben <xref:System.Windows.Media.Brush> , der zum Zeichnen des Inneren der Ellipse verwendet wird. Verwenden <xref:System.Windows.Shapes.Shape.Stroke%2A> Sie die-Eigenschaft, um das anzugeben <xref:System.Windows.Media.Brush> , das verwendet wird, um die Gliederung der Ellipse zu zeichnen. Die- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft gibt die Stärke der Ellipse-Gliederung an.  
  
 Um einen Kreis zu zeichnen, legen Sie <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> des <xref:System.Windows.Shapes.Ellipse> Elements gleich zueinander.  
  
 Im folgenden Beispiel werden vier- <xref:System.Windows.Shapes.Ellipse> Elemente in einer gezeichnet <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> -Element verwendet wird, das die Ellipsen enthält, können Sie Ellipse-Elemente (und alle anderen Shape-Elemente) mit beliebigen <xref:System.Windows.Controls.Panel> oder verwenden <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalte unterstützen.  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
