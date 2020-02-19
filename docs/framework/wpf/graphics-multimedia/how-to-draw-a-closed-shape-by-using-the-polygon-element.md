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
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="c850e-102">Gewusst wie: Zeichnen einer geschlossener Form mithilfe des Polygon-Elements</span><span class="sxs-lookup"><span data-stu-id="c850e-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="c850e-103">In diesem Beispiel wird gezeigt, wie eine geschlossene Form mithilfe des <xref:System.Windows.Shapes.Polygon>-Elements gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="c850e-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="c850e-104">Um eine geschlossene Form zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Polygon>-Element, und verwenden Sie dessen <xref:System.Windows.Shapes.Polygon.Points%2A>-Eigenschaft, um die Scheitel Punkte einer Form anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c850e-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="c850e-105">Es wird automatisch eine Linie gezeichnet, die den ersten und den letzten Punkt verbindet.</span><span class="sxs-lookup"><span data-stu-id="c850e-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="c850e-106">Geben Sie abschließend eine <xref:System.Windows.Shapes.Shape.Fill%2A>, eine <xref:System.Windows.Shapes.Shape.Stroke%2A>oder beides an.</span><span class="sxs-lookup"><span data-stu-id="c850e-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c850e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c850e-107">Example</span></span>  
 <span data-ttu-id="c850e-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ist die gültige Syntax für Punkte eine durch Leerzeichen getrennte Liste mit durch Trennzeichen getrennten x-und y-Koordinatenpaaren.</span><span class="sxs-lookup"><span data-stu-id="c850e-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="c850e-109">Obwohl das Beispiel eine <xref:System.Windows.Controls.Canvas> verwendet, um die Polygone zu enthalten, können Sie Polygon-Elemente (und alle anderen Shape-Elemente) mit allen <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> verwenden, die nicht Textinhalte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c850e-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="c850e-110">Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="c850e-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>
