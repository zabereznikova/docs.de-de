---
title: "Gewusst wie: Erstellen einer kubischen Bézierkurve"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35d4fad0634586d5d0c6ea85f276d6e76edb3f63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="f6866-102">Gewusst wie: Erstellen einer kubischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="f6866-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="f6866-103">Dieses Beispiel zeigt, wie Sie eine kubische Bézier-Kurve zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6866-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="f6866-104">Um eine kubische Bézier-Kurve zu erstellen, verwenden Sie die <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.BezierSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="f6866-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="f6866-105">Verwenden Sie zum Anzeigen der resultierenden Geometrie eine <xref:System.Windows.Shapes.Path> Element, oder verwenden sie eine <xref:System.Windows.Media.GeometryDrawing> oder eine <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="f6866-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="f6866-106">In den folgenden Beispielen wird eine kubische Bézier-Kurve von gezeichnet (10, 100), (300, 100).</span><span class="sxs-lookup"><span data-stu-id="f6866-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="f6866-107">Die Kurve hat Steuerpunkte von (100, 0) und (200, 200).</span><span class="sxs-lookup"><span data-stu-id="f6866-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6866-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6866-108">Example</span></span>  
 <span data-ttu-id="f6866-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f6866-109">[xaml]</span></span>  
  
 <span data-ttu-id="f6866-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können abgekürzte Markupsyntax verwenden, um einen Pfad zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f6866-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="f6866-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f6866-111">[xaml]</span></span>  
  
 <span data-ttu-id="f6866-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine kubische Bézier-Kurve Objekttags zeichnen.</span><span class="sxs-lookup"><span data-stu-id="f6866-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="f6866-113">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f6866-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="f6866-114">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="f6866-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6866-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6866-115">See Also</span></span>  
 [<span data-ttu-id="f6866-116">Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="f6866-116">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="f6866-117">Erstellen eines LineSegment in einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="f6866-117">Create a LineSegment in a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)  
 [<span data-ttu-id="f6866-118">Erstellen einer kubischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="f6866-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)  
 [<span data-ttu-id="f6866-119">Erstellen einer quadratischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="f6866-119">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)
