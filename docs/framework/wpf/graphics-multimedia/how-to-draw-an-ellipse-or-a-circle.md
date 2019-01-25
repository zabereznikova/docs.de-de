---
title: 'Vorgehensweise: Zeichnen einer Ellipse oder eines Kreises'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 7aac743b0cd2119107e48493b3ee9563b81b391d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689116"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="04871-102">Vorgehensweise: Zeichnen einer Ellipse oder eines Kreises</span><span class="sxs-lookup"><span data-stu-id="04871-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="04871-103">In diesem Beispiel wird gezeigt, wie zum Zeichnen von Ellipsen und Kreisen mithilfe der <xref:System.Windows.Shapes.Ellipse> Element.</span><span class="sxs-lookup"><span data-stu-id="04871-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="04871-104">Um eine Ellipse zeichnen, erstellen eine <xref:System.Windows.Shapes.Ellipse> Element, und geben Sie die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="04871-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="04871-105">Verwenden der <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft an die <xref:System.Windows.Media.Brush> , mit dem das Innere der Ellipse gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="04871-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="04871-106">Verwenden der <xref:System.Windows.Shapes.Shape.Stroke%2A> -Eigenschaft an die <xref:System.Windows.Media.Brush> , wird verwendet, um die Kontur der Ellipse gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="04871-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="04871-107">Die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft gibt die Stärke der Kontur Ellipse an.</span><span class="sxs-lookup"><span data-stu-id="04871-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="04871-108">Um einen Kreis zu zeichnen, stellen die <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> von der <xref:System.Windows.Shapes.Ellipse> Element, das jeweils anderen.</span><span class="sxs-lookup"><span data-stu-id="04871-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="04871-109">Das folgende Beispiel zeichnet vier <xref:System.Windows.Shapes.Ellipse> Elemente innerhalb einer <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="04871-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04871-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04871-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="04871-111">Obwohl dieses Beispiel verwendet eine <xref:System.Windows.Controls.Canvas> um die Ellipsen zu enthalten, können Sie Ellipse Elemente (und alle anderen Formelemente) mit einem <xref:System.Windows.Controls.Panel> oder <xref:System.Windows.Controls.Control> , die nicht-Text-Inhalt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="04871-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="04871-112">Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter [Formelemente](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="04871-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04871-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04871-113">See also</span></span>
- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="04871-114">Formelemente</span><span class="sxs-lookup"><span data-stu-id="04871-114">Shape Elements Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160037)
