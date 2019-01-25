---
title: 'Vorgehensweise: Zeichnen einer Polylinie mithilfe des Polylinien-Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: c4aab17958180710c392491a27cc22fa006f8c5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688973"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="0996e-102">Vorgehensweise: Zeichnen einer Polylinie mithilfe des Polylinien-Elements</span><span class="sxs-lookup"><span data-stu-id="0996e-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="0996e-103">Dieses Beispiel zeigt, wie Sie das Zeichnen einer Polylinie, wird eine Reihe von miteinander verbundenen Linien mit dem <xref:System.Windows.Shapes.Polyline> Element.</span><span class="sxs-lookup"><span data-stu-id="0996e-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="0996e-104">Zum Zeichnen einer Polylinie erstellen Sie eine <xref:System.Windows.Shapes.Polyline> -Element, und verwenden die <xref:System.Windows.Shapes.Polyline.Points%2A> Eigenschaft, um die Form Scheitelpunkte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0996e-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="0996e-105">Verwenden Sie abschließend die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften, die beschreiben des Polyline-Objekt zu beschreiben, da eine Zeile ohne einen Strich nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="0996e-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0996e-106">Da die <xref:System.Windows.Shapes.Polyline> Element ist keine geschlossene Form, die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft hat keine Auswirkungen, auch wenn Sie absichtlich die Formkontur schließen.</span><span class="sxs-lookup"><span data-stu-id="0996e-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="0996e-107">Erstellen Sie eine geschlossene Form mit einer <xref:System.Windows.Shapes.Shape.Fill%2A>, verwenden Sie eine <xref:System.Windows.Shapes.Polygon> Element.</span><span class="sxs-lookup"><span data-stu-id="0996e-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="0996e-108">Das folgende Beispiel zeichnet zwei <xref:System.Windows.Shapes.Polyline> Elemente innerhalb einer <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="0996e-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0996e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0996e-109">Example</span></span>  
 <span data-ttu-id="0996e-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], gültiger Syntax für Punkte ist eine durch Leerzeichen getrennte Liste von durch Trennzeichen getrennte x und y-Koordinate-Paaren.</span><span class="sxs-lookup"><span data-stu-id="0996e-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="0996e-111">Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Polylinien, können Sie Polyline-Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0996e-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="0996e-112">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="0996e-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0996e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0996e-113">See also</span></span>
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="0996e-114">Formelemente</span><span class="sxs-lookup"><span data-stu-id="0996e-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="0996e-115">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="0996e-115">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
