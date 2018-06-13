---
title: 'Gewusst wie: Erstellen einer quadratischen Bézierkurve'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: 9d389125b6ad09833a16b64cb8f498cc20d4e79c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558890"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="df05d-102">Gewusst wie: Erstellen einer quadratischen Bézierkurve</span><span class="sxs-lookup"><span data-stu-id="df05d-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="df05d-103">Dieses Beispiel zeigt, wie Sie eine quadratische Bézier-Kurve zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df05d-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="df05d-104">Um eine quadratische Bézier-Kurve zu erstellen, verwenden die <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.QuadraticBezierSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="df05d-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df05d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df05d-105">Example</span></span>  
 <span data-ttu-id="df05d-106">In den folgenden Beispielen wird eine quadratische Bézier-Kurve (300,100) von (10,100) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="df05d-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="df05d-107">Die Kurve verfügt über eine Kontrollpunkts (200.200).</span><span class="sxs-lookup"><span data-stu-id="df05d-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="df05d-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="df05d-108">[xaml]</span></span>  
  
 <span data-ttu-id="df05d-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können Attributsyntax verwenden, um einen Pfad zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="df05d-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="df05d-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="df05d-110">[xaml]</span></span>  
  
 <span data-ttu-id="df05d-111">(Beachten Sie, die diese Attributsyntax tatsächlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, einer helleren Gewichtung-Version von einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="df05d-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="df05d-112">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="df05d-112">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="df05d-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], Sie können auch eine quadratische Bézier-Kurve, die mit der Syntax der Object-Element zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="df05d-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="df05d-114">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="df05d-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="df05d-115">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="df05d-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df05d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df05d-116">See Also</span></span>  
 [<span data-ttu-id="df05d-117">Erstellen eines elliptischen Bogens</span><span class="sxs-lookup"><span data-stu-id="df05d-117">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="df05d-118">Erstellen Sie eine kubische Bézier-Kurve</span><span class="sxs-lookup"><span data-stu-id="df05d-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)
