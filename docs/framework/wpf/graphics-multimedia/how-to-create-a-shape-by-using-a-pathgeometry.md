---
title: 'Gewusst wie: Erstellen einer Form mithilfe von PathGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 784a8df792ca4dc05e36f5b7e9ec93b02e0e639f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="b64c8-102">Gewusst wie: Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="b64c8-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="b64c8-103">In diesem Beispiel wird gezeigt, wie ein Shape erstellt die <xref:System.Windows.Media.PathGeometry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b64c8-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="b64c8-104"><xref:System.Windows.Media.PathGeometry>Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> einen anderen "Abbildung" oder eine Form darstellt.</span><span class="sxs-lookup"><span data-stu-id="b64c8-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="b64c8-105">Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, die jeweils einen verknüpften Bereich der Abbildung oder Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="b64c8-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="b64c8-106">Segment Anweisungstypen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, und <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="b64c8-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b64c8-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b64c8-107">Example</span></span>  
 <span data-ttu-id="b64c8-108">Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> ein Dreieck erstellen.</span><span class="sxs-lookup"><span data-stu-id="b64c8-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="b64c8-109">Die <xref:System.Windows.Media.PathGeometry> wird angezeigt, mit einem <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="b64c8-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="b64c8-110">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.</span><span class="sxs-lookup"><span data-stu-id="b64c8-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="b64c8-111">![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "Wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="b64c8-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="b64c8-112">Ein Dreieck mit einem PathGeometry erstellt</span><span class="sxs-lookup"><span data-stu-id="b64c8-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="b64c8-113">Im vorherige Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b64c8-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="b64c8-114">Ein <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen, einschließlich Bögen und Kurven zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b64c8-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="b64c8-115">Beispiele finden Sie unter [Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [erstellen Sie eine kubische Bézier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), und [erstellen Sie eine quadratische Bézier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="b64c8-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="b64c8-116">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="b64c8-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64c8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b64c8-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="b64c8-118">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="b64c8-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="b64c8-119">Geometrien-Beispiel</span><span class="sxs-lookup"><span data-stu-id="b64c8-119">Geometries Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159989)
