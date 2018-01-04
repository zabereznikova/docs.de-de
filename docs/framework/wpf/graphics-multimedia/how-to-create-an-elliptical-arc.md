---
title: 'Gewusst wie: Erstellen eines elliptischen Bogens'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e11f3e0035c00bbc280b658c0931d57c37524f93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="ddd49-102">Gewusst wie: Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="ddd49-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="ddd49-103">In diesem Beispiel wird gezeigt, wie einen elliptischen Bogen gezeichnet wird. Verwenden Sie zum Erstellen eines elliptischen Bogens die <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.ArcSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="ddd49-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddd49-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddd49-104">Example</span></span>  
 <span data-ttu-id="ddd49-105">In den folgenden Beispielen wird ein elliptischer Bogen von (10,100) (200,100) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ddd49-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="ddd49-106">Der Bogen verfügt über eine <xref:System.Windows.Media.ArcSegment.Size%2A> 100 x 50 geräteunabhängige Pixel, ein <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> von 45 Grad eine <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> Festlegen von `true`, und ein <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> von <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span><span class="sxs-lookup"><span data-stu-id="ddd49-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="ddd49-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ddd49-107">[xaml]</span></span>  
  
 <span data-ttu-id="ddd49-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können Attributsyntax verwenden, um einen Pfad zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ddd49-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="ddd49-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ddd49-109">[xaml]</span></span>  
  
 <span data-ttu-id="ddd49-110">(Beachten Sie, die diese Attributsyntax tatsächlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, einer helleren Gewichtung-Version von einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ddd49-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="ddd49-111">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="ddd49-111">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="ddd49-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch einen elliptischen Bogen von explizit Objekttags zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ddd49-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="ddd49-113">Folgender Ausdruck ist äquivalent zur vorangehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Markup.</span><span class="sxs-lookup"><span data-stu-id="ddd49-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="ddd49-114">Dieses Beispiel ist Teil eines umfangreicheren Beispiels.</span><span class="sxs-lookup"><span data-stu-id="ddd49-114">This example is part of a larger sample.</span></span> <span data-ttu-id="ddd49-115">Das vollständige Beispiel finden Sie unter der [Geometrien Beispiel](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="ddd49-115">For the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd49-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddd49-116">See Also</span></span>  
 [<span data-ttu-id="ddd49-117">Erstellen Sie eine quadratische Bézier-Kurve</span><span class="sxs-lookup"><span data-stu-id="ddd49-117">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)  
 [<span data-ttu-id="ddd49-118">Erstellen Sie eine kubische Bézier-Kurve</span><span class="sxs-lookup"><span data-stu-id="ddd49-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
