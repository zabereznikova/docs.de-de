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
ms.openlocfilehash: fb5220082989a9d0a22c4998bb79c0a196067e7e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934959"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="7e03b-102">Vorgehensweise: Zeichnen einer Polylinie mithilfe des Polylinien-Elements</span><span class="sxs-lookup"><span data-stu-id="7e03b-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="7e03b-103">In diesem Beispiel wird gezeigt, wie Sie mithilfe des <xref:System.Windows.Shapes.Polyline> -Elements eine Polylinie zeichnen, bei der es sich um eine Reihe verbundener Linien handelt.</span><span class="sxs-lookup"><span data-stu-id="7e03b-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="7e03b-104">Um eine Polylinie zu zeichnen, erstellen <xref:System.Windows.Shapes.Polyline> Sie ein-Element <xref:System.Windows.Shapes.Polyline.Points%2A> , und verwenden Sie die-Eigenschaft, um die Form Scheitel Punkte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7e03b-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="7e03b-105">Verwenden Sie abschließend die <xref:System.Windows.Shapes.Shape.Stroke%2A> - <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft und die-Eigenschaft, um die polyliniengliederung zu beschreiben, da eine Linie ohne Strich unsichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="7e03b-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e03b-106">Da das <xref:System.Windows.Shapes.Polyline> -Element keine geschlossene Form ist, hat <xref:System.Windows.Shapes.Shape.Fill%2A> die-Eigenschaft keine Auswirkung, auch wenn Sie die Form Gliederung absichtlich schließen.</span><span class="sxs-lookup"><span data-stu-id="7e03b-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="7e03b-107">Um eine geschlossene Form mit einem <xref:System.Windows.Shapes.Shape.Fill%2A>zu erstellen, verwenden Sie ein <xref:System.Windows.Shapes.Polygon> -Element.</span><span class="sxs-lookup"><span data-stu-id="7e03b-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="7e03b-108">Im folgenden Beispiel werden zwei <xref:System.Windows.Shapes.Polyline> -Elemente in <xref:System.Windows.Controls.Canvas>einem-Element gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7e03b-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e03b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e03b-109">Example</span></span>  
 <span data-ttu-id="7e03b-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ist die gültige Syntax für Punkte eine durch Leerzeichen getrennte Liste mit durch Trennzeichen getrennten x-und y-Koordinatenpaaren.</span><span class="sxs-lookup"><span data-stu-id="7e03b-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="7e03b-111">Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> -Element verwendet wird, das die Polylinien enthält, können Sie polylinienelemente (und alle anderen Shape <xref:System.Windows.Controls.Panel> - <xref:System.Windows.Controls.Control> Elemente) mit beliebigen oder verwenden, die nicht Text Inhalt unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7e03b-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="7e03b-112">Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="7e03b-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e03b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e03b-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="7e03b-114">Beispiel für Shape-Elemente</span><span class="sxs-lookup"><span data-stu-id="7e03b-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="7e03b-115">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="7e03b-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
