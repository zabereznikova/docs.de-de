---
title: 'Gewusst wie: Erstellen eines LineSegment in einer PathGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: fc7fbad1e534988a36d85c55c1b6a8249692ad67
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452083"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="d2ed1-102">Gewusst wie: Erstellen eines LineSegment in einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="d2ed1-102">How to: Create a LineSegment in a PathGeometry</span></span>

<span data-ttu-id="d2ed1-103">Dieses Beispiel zeigt, wie ein Liniensegment erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="d2ed1-104">Verwenden Sie zum Erstellen eines Linien Segments die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.LineSegment>.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>

## <a name="example"></a><span data-ttu-id="d2ed1-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2ed1-105">Example</span></span>

<span data-ttu-id="d2ed1-106">In den folgenden Beispielen wird eine <xref:System.Windows.Media.LineSegment> von (10, 50) zu (200, 70) gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="d2ed1-107">In der folgenden Abbildung wird die resultierende <xref:System.Windows.Media.LineSegment>gezeigt. Es wurde ein Raster Hintergrund hinzugefügt, um das Koordinatensystem anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>

<span data-ttu-id="d2ed1-108">![Ein LineSegment in einer PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") Ein LineSegment, gezeichnet von (10, 50) bis (200, 70)</span><span class="sxs-lookup"><span data-stu-id="d2ed1-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") A LineSegment drawn from (10,50) to (200,70)</span></span>

<span data-ttu-id="d2ed1-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="d2ed1-109">[xaml]</span></span>

<span data-ttu-id="d2ed1-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie zum Beschreiben eines Pfads Attributsyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

<span data-ttu-id="d2ed1-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="d2ed1-111">[xaml]</span></span>

<span data-ttu-id="d2ed1-112">(Beachten Sie, dass diese Attribut Syntax tatsächlich einen <xref:System.Windows.Media.StreamGeometry>erstellt, eine hellere Version einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-112">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="d2ed1-113">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="d2ed1-113">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>

<span data-ttu-id="d2ed1-114">Zudem können Sie in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] XAML ein Liniensegment mithilfe von Objektelementsyntax zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-114">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="d2ed1-115">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d2ed1-115">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1">
  <Path.Data>
    <PathGeometry>
      <PathFigure StartPoint="10,50">
        <LineSegment Point="200,70" />
      </PathFigure>
    </PathGeometry>
  </Path.Data>
</Path>
```

```csharp
PathFigure myPathFigure = new PathFigure();
myPathFigure.StartPoint = new Point(10, 50);

LineSegment myLineSegment = new LineSegment();
myLineSegment.Point = new Point(200, 70);

PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();
myPathSegmentCollection.Add(myLineSegment);

myPathFigure.Segments = myPathSegmentCollection;

PathFigureCollection myPathFigureCollection = new PathFigureCollection();
myPathFigureCollection.Add(myPathFigure);

PathGeometry myPathGeometry = new PathGeometry();
myPathGeometry.Figures = myPathFigureCollection;

Path myPath = new Path();
myPath.Stroke = Brushes.Black;
myPath.StrokeThickness = 1;
myPath.Data = myPathGeometry;
```

```vb
Dim myPathFigure As New PathFigure()
myPathFigure.StartPoint = New Point(10, 50)

Dim myLineSegment As New LineSegment()
myLineSegment.Point = New Point(200, 70)

Dim myPathSegmentCollection As New PathSegmentCollection()
myPathSegmentCollection.Add(myLineSegment)

myPathFigure.Segments = myPathSegmentCollection

Dim myPathFigureCollection As New PathFigureCollection()
myPathFigureCollection.Add(myPathFigure)

Dim myPathGeometry As New PathGeometry()
myPathGeometry.Figures = myPathFigureCollection

Dim myPath As New Path()
myPath.Stroke = Brushes.Black
myPath.StrokeThickness = 1
myPath.Data = myPathGeometry
```

<span data-ttu-id="d2ed1-116">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span><span class="sxs-lookup"><span data-stu-id="d2ed1-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2ed1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2ed1-117">See also</span></span>

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="d2ed1-118">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="d2ed1-118">Geometry Overview</span></span>](geometry-overview.md)
