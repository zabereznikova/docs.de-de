---
title: 'Gewusst wie: Erstellen eines elliptischen Bogens'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: 7ca7d06aa25f8dfae648d8c54c8b95cc277ffbf9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877949"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="befb6-102">Gewusst wie: Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="befb6-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="befb6-103">Dieses Beispiel zeigt, wie Sie einen elliptischen Bogen zu zeichnen. Verwenden Sie zum Erstellen eines elliptischen Bogens der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.ArcSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="befb6-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="befb6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="befb6-104">Example</span></span>  
 <span data-ttu-id="befb6-105">In den folgenden Beispielen wird ein elliptischen Bogens nach (200,100) von (10,100) gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="befb6-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="befb6-106">Der Bogen verfügt über eine <xref:System.Windows.Media.ArcSegment.Size%2A> von 100 x 50 geräteunabhängige Pixel, ein <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> von 45 Grad ein <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> Festlegen der `true`, und ein <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> von <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="befb6-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="befb6-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="befb6-107">[xaml]</span></span>  
  
 <span data-ttu-id="befb6-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können zum Beschreiben eines Pfads Attributsyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="befb6-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="befb6-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="befb6-109">[xaml]</span></span>  
  
 <span data-ttu-id="befb6-110">(Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="befb6-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="befb6-111">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="befb6-111">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="befb6-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch einen elliptischen Bogen zeichnen, verwenden Sie hierzu explizit Objekttags.</span><span class="sxs-lookup"><span data-stu-id="befb6-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="befb6-113">Im folgenden finden Sie im vorhergehenden Abschnitt entspricht [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.</span><span class="sxs-lookup"><span data-stu-id="befb6-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="befb6-114">Dieses Beispiel ist Teil eines umfangreicheren Beispiels.</span><span class="sxs-lookup"><span data-stu-id="befb6-114">This example is part of a larger sample.</span></span> <span data-ttu-id="befb6-115">Das vollständige Beispiel finden Sie unter den [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="befb6-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befb6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="befb6-116">See Also</span></span>  
 [<span data-ttu-id="befb6-117">Erstellen einer quadratischen Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="befb6-117">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [<span data-ttu-id="befb6-118">Erstellen Sie eine kubische Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="befb6-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
