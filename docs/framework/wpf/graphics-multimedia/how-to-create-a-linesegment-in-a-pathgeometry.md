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
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a>Gewusst wie: Erstellen eines LineSegment in einer PathGeometry

Dieses Beispiel zeigt, wie ein Liniensegment erstellt wird. Verwenden Sie zum Erstellen eines Linien Segments die Klassen <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>und <xref:System.Windows.Media.LineSegment>.

## <a name="example"></a>Beispiel

In den folgenden Beispielen wird eine <xref:System.Windows.Media.LineSegment> von (10, 50) zu (200, 70) gezeichnet. In der folgenden Abbildung wird die resultierende <xref:System.Windows.Media.LineSegment>gezeigt. Es wurde ein Raster Hintergrund hinzugefügt, um das Koordinatensystem anzuzeigen.

![Ein LineSegment in einer PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") Ein LineSegment, gezeichnet von (10, 50) bis (200, 70)

[xaml]

In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie zum Beschreiben eines Pfads Attributsyntax verwenden.

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

[xaml]

(Beachten Sie, dass diese Attribut Syntax tatsächlich einen <xref:System.Windows.Media.StreamGeometry>erstellt, eine hellere Version einer <xref:System.Windows.Media.PathGeometry>. Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](path-markup-syntax.md).)

Zudem können Sie in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] XAML ein Liniensegment mithilfe von Objektelementsyntax zeichnen. Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.

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

Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [Übersicht über Geometrien](geometry-overview.md)
