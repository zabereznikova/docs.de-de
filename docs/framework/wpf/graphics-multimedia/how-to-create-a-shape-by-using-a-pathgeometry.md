---
title: 'Gewusst wie: Erstellen einer Form mithilfe von PathGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452044"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="7eb69-102">Gewusst wie: Erstellen einer Form mithilfe von PathGeometry</span><span class="sxs-lookup"><span data-stu-id="7eb69-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="7eb69-103">In diesem Beispiel wird gezeigt, wie eine Form mit der <xref:System.Windows.Media.PathGeometry>-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7eb69-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="7eb69-104"><xref:System.Windows.Media.PathGeometry> Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten. jede <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar.</span><span class="sxs-lookup"><span data-stu-id="7eb69-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="7eb69-105">Jede <xref:System.Windows.Media.PathFigure> besteht aus einem oder mehreren <xref:System.Windows.Media.PathSegment> Objekten, die jeweils einen verbundenen Teil der Abbildung oder Form darstellen.</span><span class="sxs-lookup"><span data-stu-id="7eb69-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="7eb69-106">Zu den Segment Typen zählen <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>und <xref:System.Windows.Media.BezierSegment>.</span><span class="sxs-lookup"><span data-stu-id="7eb69-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb69-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7eb69-107">Example</span></span>  
 <span data-ttu-id="7eb69-108">Im folgenden Beispiel wird ein-<xref:System.Windows.Media.PathGeometry> zum Erstellen eines Dreiecks verwendet.</span><span class="sxs-lookup"><span data-stu-id="7eb69-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="7eb69-109">Die <xref:System.Windows.Media.PathGeometry> wird mit einem <xref:System.Windows.Shapes.Path>-Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7eb69-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="7eb69-110">Die folgende Abbildung zeigt die im vorherigen Beispiel erstellte Form.</span><span class="sxs-lookup"><span data-stu-id="7eb69-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="7eb69-111">![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="7eb69-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="7eb69-112">Ein mit PathGeometry erstelltes Dreieck</span><span class="sxs-lookup"><span data-stu-id="7eb69-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="7eb69-113">Im vorherigen Beispiel wurde gezeigt, wie eine relativ einfache Form, ein Dreieck, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7eb69-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="7eb69-114">Eine <xref:System.Windows.Media.PathGeometry> kann auch verwendet werden, um komplexere Formen zu erstellen, einschließlich Bögen und Kurven.</span><span class="sxs-lookup"><span data-stu-id="7eb69-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="7eb69-115">Beispiele finden Sie unter [Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md), [Erstellen einer kubischen Bezier-Kurve](how-to-create-a-cubic-bezier-curve.md)und [Erstellen einer quadratischen Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md).</span><span class="sxs-lookup"><span data-stu-id="7eb69-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="7eb69-116">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="7eb69-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb69-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eb69-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="7eb69-118">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="7eb69-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="7eb69-119">Beispiel für Geometry</span><span class="sxs-lookup"><span data-stu-id="7eb69-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
