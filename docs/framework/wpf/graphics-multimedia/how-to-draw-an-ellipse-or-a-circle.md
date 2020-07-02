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
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="50557-103">Gewusst wie: Zeichnen einer Ellipse oder eines Kreises</span><span class="sxs-lookup"><span data-stu-id="50557-103">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="50557-104">In diesem Beispiel wird gezeigt, wie Ellipsen und Kreise mithilfe des-Elements gezeichnet werden <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="50557-104">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="50557-105">Um eine Ellipse zu zeichnen, erstellen Sie ein <xref:System.Windows.Shapes.Ellipse> -Element, und geben Sie dessen <xref:System.Windows.FrameworkElement.Width%2A> und an <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="50557-105">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="50557-106">Verwenden <xref:System.Windows.Shapes.Shape.Fill%2A> Sie die-Eigenschaft, um den anzugeben <xref:System.Windows.Media.Brush> , der zum Zeichnen des Inneren der Ellipse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50557-106">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="50557-107">Verwenden <xref:System.Windows.Shapes.Shape.Stroke%2A> Sie die-Eigenschaft, um das anzugeben <xref:System.Windows.Media.Brush> , das verwendet wird, um die Gliederung der Ellipse zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="50557-107">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="50557-108">Die- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft gibt die Stärke der Ellipse-Gliederung an.</span><span class="sxs-lookup"><span data-stu-id="50557-108">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="50557-109">Um einen Kreis zu zeichnen, legen Sie <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> des <xref:System.Windows.Shapes.Ellipse> Elements gleich zueinander.</span><span class="sxs-lookup"><span data-stu-id="50557-109">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="50557-110">Im folgenden Beispiel werden vier- <xref:System.Windows.Shapes.Ellipse> Elemente in einer gezeichnet <xref:System.Windows.Controls.Canvas> .</span><span class="sxs-lookup"><span data-stu-id="50557-110">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50557-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50557-111">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="50557-112">Obwohl in diesem Beispiel ein <xref:System.Windows.Controls.Canvas> -Element verwendet wird, das die Ellipsen enthält, können Sie Ellipse-Elemente (und alle anderen Shape-Elemente) mit beliebigen <xref:System.Windows.Controls.Panel> oder verwenden <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalte unterstützen.</span><span class="sxs-lookup"><span data-stu-id="50557-112">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="50557-113">Dieses Beispiel ist Teil einer größeren Stichprobe. Das komplette Beispiel finden Sie unter [Beispiel für Shape-Elemente](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="50557-113">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50557-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50557-114">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="50557-115">Beispiel für Shape-Elemente</span><span class="sxs-lookup"><span data-stu-id="50557-115">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
