---
title: 'Vorgehensweise: Zeichnen eines Rechtecks'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 261026b994b432565928b38ff1657115ff7cbe4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947627"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="9634b-102">Vorgehensweise: Zeichnen eines Rechtecks</span><span class="sxs-lookup"><span data-stu-id="9634b-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="9634b-103">In diesem Beispiel wird gezeigt, wie zum Zeichnen eines Rechtecks mit dem <xref:System.Windows.Shapes.Rectangle> Element.</span><span class="sxs-lookup"><span data-stu-id="9634b-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="9634b-104">Um ein Rechteck zu zeichnen, erstellen eine <xref:System.Windows.Shapes.Rectangle> Element, und geben Sie die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="9634b-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="9634b-105">Um die Fläche des Rechtecks zu zeichnen, legen Sie dessen <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="9634b-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="9634b-106">Um dem Rechteck eine Gliederung zu gewähren, verwenden Sie die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9634b-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="9634b-107">Um dem Rechteck abgerundete Ecken, geben Sie den optionalen <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9634b-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="9634b-108">Die <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften festlegen, die x- und y-Radien der Ellipse, der zum Abrunden der Ecken des Rechtecks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9634b-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="9634b-109">Im folgenden Beispiel zwei <xref:System.Windows.Shapes.Rectangle> Elemente gezeichnet werden, einem <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="9634b-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="9634b-110">Die erste Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren.</span><span class="sxs-lookup"><span data-stu-id="9634b-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="9634b-111">Das zweite Rechteck verfügt über eine <xref:System.Windows.Media.Brushes.Blue%2A> inneren, eine <xref:System.Windows.Media.Brushes.Black%2A> Kontur und abgerundeten Ecken.</span><span class="sxs-lookup"><span data-stu-id="9634b-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9634b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9634b-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="9634b-113">Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> die Rechtecken enthalten, können Sie Rechteck Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9634b-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="9634b-114">In der Tat Rechtecke eignen sich besonders für die Bereitstellung von Hintergründen für Teile des <xref:System.Windows.Controls.Grid> Bereiche.</span><span class="sxs-lookup"><span data-stu-id="9634b-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="9634b-115">Ein Beispiel finden Sie unter den [Tabellenübersicht](../advanced/table-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9634b-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="9634b-116">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="9634b-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9634b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9634b-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="9634b-118">Formelemente</span><span class="sxs-lookup"><span data-stu-id="9634b-118">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
- [<span data-ttu-id="9634b-119">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="9634b-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="9634b-120">Übersicht über Tabellen</span><span class="sxs-lookup"><span data-stu-id="9634b-120">Table Overview</span></span>](../advanced/table-overview.md)
