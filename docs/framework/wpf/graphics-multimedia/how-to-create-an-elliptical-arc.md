---
title: 'Gewusst wie: Erstellen eines elliptischen Bogens'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453064"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="88c50-102">Gewusst wie: Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="88c50-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="88c50-103">In diesem Beispiel wird gezeigt, wie ein elliptischer Bogen gezeichnet wird. Verwenden Sie zum Erstellen eines elliptischen Bogens die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="88c50-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88c50-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88c50-104">Example</span></span>  
 <span data-ttu-id="88c50-105">In den folgenden Beispielen wird ein elliptischer Bogen von (10.100) zu (200.100) gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="88c50-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="88c50-106">Der Bogen verfügt über eine <xref:System.Windows.Media.ArcSegment.Size%2A> von 100 bis 50 geräteunabhängigen Pixeln, eine <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 Grad, eine <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> Einstellung `true`und eine <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="88c50-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="88c50-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="88c50-107">[xaml]</span></span>  
  
 <span data-ttu-id="88c50-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie die Attribut Syntax verwenden, um einen Pfad zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="88c50-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="88c50-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="88c50-109">[xaml]</span></span>  
  
 <span data-ttu-id="88c50-110">(Beachten Sie, dass diese Attribut Syntax tatsächlich einen <xref:System.Windows.Media.StreamGeometry>erstellt, eine hellere Version einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="88c50-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="88c50-111">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="88c50-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="88c50-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]können Sie auch einen elliptischen Bogen zeichnen, indem Sie explizit Objekt Tags verwenden.</span><span class="sxs-lookup"><span data-stu-id="88c50-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="88c50-113">Folgendes entspricht dem vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.</span><span class="sxs-lookup"><span data-stu-id="88c50-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="88c50-114">Dieses Beispiel ist Teil eines umfangreicheren Beispiels.</span><span class="sxs-lookup"><span data-stu-id="88c50-114">This example is part of a larger sample.</span></span> <span data-ttu-id="88c50-115">Das komplette Beispiel finden Sie im [Beispiel zu Geometry](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="88c50-115">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c50-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88c50-116">See also</span></span>

- [<span data-ttu-id="88c50-117">Erstellen einer quadratischen Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="88c50-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="88c50-118">Erstellen Sie eine kubische Bezier-Kurve.</span><span class="sxs-lookup"><span data-stu-id="88c50-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
