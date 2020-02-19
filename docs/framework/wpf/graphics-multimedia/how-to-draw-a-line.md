---
title: 'Gewusst wie: Zeichnen einer Linie'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452947"
---
# <a name="how-to-draw-a-line"></a>Gewusst wie: Zeichnen einer Linie
In diesem Beispiel wird gezeigt, wie Sie Linien mit dem <xref:System.Windows.Shapes.Line>-Element zeichnen können.  
  
 Um eine Linie zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Line> Element. Verwenden Sie die Eigenschaften <xref:System.Windows.Shapes.Line.X1%2A> und <xref:System.Windows.Shapes.Line.Y1%2A>, um den Startpunkt festzulegen. und verwenden die Eigenschaften <xref:System.Windows.Shapes.Line.X2%2A> und <xref:System.Windows.Shapes.Line.Y2%2A>, um den Endpunkt festzulegen. Legen Sie abschließend die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> fest, da eine Linie ohne Strich unsichtbar ist.  
  
 Das Festlegen des <xref:System.Windows.Shapes.Shape.Fill%2A>-Elements für eine Linie hat keine Auswirkung, da eine Linie kein innere hat.  
  
 Im folgenden Beispiel werden drei Zeilen innerhalb eines <xref:System.Windows.Controls.Canvas>-Elements gezeichnet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Shapes.Line>
- [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
