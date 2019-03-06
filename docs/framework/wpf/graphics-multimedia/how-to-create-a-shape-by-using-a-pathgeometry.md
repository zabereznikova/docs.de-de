---
title: 'Vorgehensweise: Erstellen einer Form mithilfe von PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: ce84f2509116207afa200ddf83dcdc1f8101da13
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356212"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="20d76-102">Vorgehensweise: Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="20d76-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="20d76-103">In diesem Beispiel wird gezeigt, wie zum Erstellen einer Form mithilfe der <xref:System.Windows.Media.PathGeometry> Klasse.</span><span class="sxs-lookup"><span data-stu-id="20d76-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="20d76-104"><xref:System.Windows.Media.PathGeometry> Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar.</span><span class="sxs-lookup"><span data-stu-id="20d76-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="20d76-105">Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jedes einen verknüpften Abschnitt der Figur oder Form darstellt.</span><span class="sxs-lookup"><span data-stu-id="20d76-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="20d76-106">Segmenttypen beinhalten <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, und <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="20d76-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20d76-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20d76-107">Example</span></span>  
 <span data-ttu-id="20d76-108">Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> ein Dreieck erstellen.</span><span class="sxs-lookup"><span data-stu-id="20d76-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="20d76-109">Die <xref:System.Windows.Media.PathGeometry> nutzt eine <xref:System.Windows.Shapes.Path> Element.</span><span class="sxs-lookup"><span data-stu-id="20d76-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="20d76-110">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.</span><span class="sxs-lookup"><span data-stu-id="20d76-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="20d76-111">![Eine PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "Wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="20d76-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="20d76-112">Ein Dreieck mit PathGeometry erstellt</span><span class="sxs-lookup"><span data-stu-id="20d76-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="20d76-113">Im vorherigen Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck zu bilden.</span><span class="sxs-lookup"><span data-stu-id="20d76-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="20d76-114">Ein <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen, einschließlich Bögen und Kurven zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20d76-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="20d76-115">Beispiele finden Sie in [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md), [erstellen Sie eine kubische Bezier-Kurve](how-to-create-a-cubic-bezier-curve.md), und [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="20d76-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="20d76-116">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="20d76-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d76-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20d76-117">See also</span></span>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="20d76-118">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="20d76-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="20d76-119">Beispiele zu Geometrie</span><span class="sxs-lookup"><span data-stu-id="20d76-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
