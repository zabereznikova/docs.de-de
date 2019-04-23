---
title: 'Vorgehensweise: Erstellen einer kubischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: 36544abc774b7fe82c2ff47483cfedd6fb13e344
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115569"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="3289d-102">Vorgehensweise: Erstellen einer kubischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="3289d-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="3289d-103">Dieses Beispiel zeigt, wie Sie eine kubische Bezier-Kurve zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3289d-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="3289d-104">Verwenden Sie zum Erstellen einer kubischen Bezier-Kurve der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.BezierSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="3289d-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="3289d-105">Verwenden Sie zum Anzeigen der resultierenden Geometrie eine <xref:System.Windows.Shapes.Path> -Element, oder verwenden Sie es mit einer <xref:System.Windows.Media.GeometryDrawing> oder ein <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="3289d-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="3289d-106">In den folgenden Beispielen wird von eine kubische Bezier-Kurve gezeichnet (10, 100), (300, 100).</span><span class="sxs-lookup"><span data-stu-id="3289d-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="3289d-107">Die Kurve hat der Control-Punkte ("100", "0") und (200, 200).</span><span class="sxs-lookup"><span data-stu-id="3289d-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3289d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3289d-108">Example</span></span>  
 <span data-ttu-id="3289d-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="3289d-109">[xaml]</span></span>  
  
 <span data-ttu-id="3289d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], können Sie abgekürzte Markupsyntax zum Beschreiben eines Pfads.</span><span class="sxs-lookup"><span data-stu-id="3289d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="3289d-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="3289d-111">[xaml]</span></span>  
  
 <span data-ttu-id="3289d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine kubische Bezier-Kurve Objekttags zeichnen.</span><span class="sxs-lookup"><span data-stu-id="3289d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="3289d-113">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3289d-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="3289d-114">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="3289d-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3289d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3289d-115">See also</span></span>

- [<span data-ttu-id="3289d-116">Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="3289d-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="3289d-117">Erstellen eines LineSegment in einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="3289d-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="3289d-118">Erstellen Sie eine kubische Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="3289d-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="3289d-119">Erstellen einer quadratischen Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="3289d-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
