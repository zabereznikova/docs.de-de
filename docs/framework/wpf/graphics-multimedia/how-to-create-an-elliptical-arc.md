---
title: 'Vorgehensweise: Erstellen eines elliptischen Bogens'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: aae304b9963f3a8e5833b4d8ba0a54777a750225
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003365"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="481ce-102">Vorgehensweise: Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="481ce-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="481ce-103">Dieses Beispiel zeigt, wie Sie einen elliptischen Bogen zu zeichnen. Verwenden Sie zum Erstellen eines elliptischen Bogens der <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.ArcSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="481ce-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="481ce-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="481ce-104">Example</span></span>  
 <span data-ttu-id="481ce-105">In den folgenden Beispielen wird ein elliptischen Bogens nach (200,100) von (10,100) gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="481ce-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="481ce-106">Der Bogen verfügt über eine <xref:System.Windows.Media.ArcSegment.Size%2A> von 100 x 50 geräteunabhängige Pixel, ein <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> von 45 Grad ein <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> Festlegen der `true`, und ein <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> von <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="481ce-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="481ce-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="481ce-107">[xaml]</span></span>  
  
 <span data-ttu-id="481ce-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können zum Beschreiben eines Pfads Attributsyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="481ce-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="481ce-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="481ce-109">[xaml]</span></span>  
  
 <span data-ttu-id="481ce-110">(Beachten Sie, die dieser Attributsyntax eigentlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, eine schlankere-Version von einem <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="481ce-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="481ce-111">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="481ce-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="481ce-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch einen elliptischen Bogen zeichnen, verwenden Sie hierzu explizit Objekttags.</span><span class="sxs-lookup"><span data-stu-id="481ce-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="481ce-113">Im folgenden finden Sie im vorhergehenden Abschnitt entspricht [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.</span><span class="sxs-lookup"><span data-stu-id="481ce-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="481ce-114">Dieses Beispiel ist Teil eines umfangreicheren Beispiels.</span><span class="sxs-lookup"><span data-stu-id="481ce-114">This example is part of a larger sample.</span></span> <span data-ttu-id="481ce-115">Das vollständige Beispiel finden Sie unter den [Beispiele zu Geometrie](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="481ce-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481ce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="481ce-116">See also</span></span>

- [<span data-ttu-id="481ce-117">Erstellen einer quadratischen Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="481ce-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="481ce-118">Erstellen Sie eine kubische Bezier-Kurve</span><span class="sxs-lookup"><span data-stu-id="481ce-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
