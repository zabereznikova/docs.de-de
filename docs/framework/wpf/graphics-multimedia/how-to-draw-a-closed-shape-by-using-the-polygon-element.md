---
title: 'Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452973"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements
In diesem Beispiel wird gezeigt, wie eine geschlossene Form mithilfe des <xref:System.Windows.Shapes.Polygon>-Elements gezeichnet wird. Um eine geschlossene Form zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Polygon>-Element, und verwenden Sie dessen <xref:System.Windows.Shapes.Polygon.Points%2A>-Eigenschaft, um die Scheitel Punkte einer Form anzugeben. Es wird automatisch eine Linie gezeichnet, die den ersten und den letzten Punkt verbindet. Geben Sie abschließend eine <xref:System.Windows.Shapes.Shape.Fill%2A>, eine <xref:System.Windows.Shapes.Shape.Stroke%2A>oder beides an.  
  
## <a name="example"></a>Beispiel  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ist die gültige Syntax für Punkte eine durch Leerzeichen getrennte Liste mit durch Trennzeichen getrennten x-und y-Koordinatenpaaren.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Obwohl das Beispiel eine <xref:System.Windows.Controls.Canvas> verwendet, um die Polygone zu enthalten, können Sie Polygon-Elemente (und alle anderen Shape-Elemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> verwenden, die nicht Textinhalte unterstützen.  
  
 Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).
