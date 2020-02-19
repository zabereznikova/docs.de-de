---
title: 'Gewusst wie: Zeichnen eines Rechtecks'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452934"
---
# <a name="how-to-draw-a-rectangle"></a>Gewusst wie: Zeichnen eines Rechtecks
In diesem Beispiel wird gezeigt, wie ein Rechteck mithilfe des <xref:System.Windows.Shapes.Rectangle>-Elements gezeichnet wird.  
  
 Um ein Rechteck zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Rectangle>-Element, und geben Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>an. Um den inneren Bereich des Rechtecks zu zeichnen, legen Sie dessen <xref:System.Windows.Shapes.Shape.Fill%2A>fest. Um dem Rechteck eine Gliederung zuzuweisen, verwenden Sie dessen Eigenschaften für <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 Um den Rechtecke gerundete Ecken zuzuweisen, geben Sie die optionalen Eigenschaften <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> an. Die Eigenschaften "<xref:System.Windows.Shapes.Rectangle.RadiusX%2A>" und "<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>" legen die Basis für die x-Achse und die y-Achse der Ellipse fest, die zum Abrunden der Ecken des Rechtecks verwendet wird.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Shapes.Rectangle> Elemente in einem <xref:System.Windows.Controls.Canvas>gezeichnet. Das erste Rechteck verfügt über einen <xref:System.Windows.Media.Brushes.Blue%2A> Inneren. Das zweite Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> innere, eine <xref:System.Windows.Media.Brushes.Black%2A> Kontur und abgerundete Ecken.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> verwendet wird, um die Rechtecke zu enthalten, können Sie Rechteck Elemente (und alle anderen Shape-Elemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> verwenden, die nicht Text Inhalt unterstützen. In der Tat sind Rechtecke besonders nützlich für die Bereitstellung von Hintergründen für Teile <xref:System.Windows.Controls.Grid> Panels. Ein Beispiel finden Sie in der [Übersicht über die Tabelle](../advanced/table-overview.md).  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Rectangle>
- [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Tabellenübersicht](../advanced/table-overview.md)
