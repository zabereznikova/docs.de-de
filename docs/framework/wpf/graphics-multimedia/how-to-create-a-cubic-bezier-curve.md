---
title: 'Gewusst wie: Erstellen einer kubischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452109"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="7f40d-102">Gewusst wie: Erstellen einer kubischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="7f40d-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="7f40d-103">In diesem Beispiel wird gezeigt, wie eine kubische Bezier-Kurve erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7f40d-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="7f40d-104">Um eine kubische Bezier-Kurve zu erstellen, verwenden Sie die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="7f40d-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="7f40d-105">Verwenden Sie zum Anzeigen der resultierenden Geometrie ein <xref:System.Windows.Shapes.Path>-Element, oder verwenden Sie es mit einem <xref:System.Windows.Media.GeometryDrawing> oder einem <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="7f40d-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="7f40d-106">In den folgenden Beispielen wird eine kubische Bezier-Kurve zwischen (10, 100) und (300, 100) gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7f40d-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="7f40d-107">Die Kurve hat Steuerungs Punkte (100, 0) und (200, 200).</span><span class="sxs-lookup"><span data-stu-id="7f40d-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f40d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f40d-108">Example</span></span>  
 <span data-ttu-id="7f40d-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="7f40d-109">[xaml]</span></span>  
  
 <span data-ttu-id="7f40d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie eine abgekürzte Markup Syntax verwenden, um einen Pfad zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="7f40d-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="7f40d-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="7f40d-111">[xaml]</span></span>  
  
 <span data-ttu-id="7f40d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie auch eine kubische Bezier-Kurve mithilfe von Objekt Tags zeichnen.</span><span class="sxs-lookup"><span data-stu-id="7f40d-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="7f40d-113">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7f40d-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="7f40d-114">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="7f40d-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f40d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f40d-115">See also</span></span>

- [<span data-ttu-id="7f40d-116">Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="7f40d-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="7f40d-117">Erstellen eines LineSegment in einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="7f40d-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="7f40d-118">Erstellen Sie eine kubische Bezier-Kurve.</span><span class="sxs-lookup"><span data-stu-id="7f40d-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="7f40d-119">Erstellen einer quadratischen Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="7f40d-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
