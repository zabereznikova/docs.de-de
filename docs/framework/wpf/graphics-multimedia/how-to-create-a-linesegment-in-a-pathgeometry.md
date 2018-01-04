---
title: 'Gewusst wie: Erstellen eines LineSegment in einer PathGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96ad746edc45e7482ac7e8d36a8bb881923c0f04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="ec04b-102">Gewusst wie: Erstellen eines LineSegment in einer PathGeometry</span><span class="sxs-lookup"><span data-stu-id="ec04b-102">How to: Create a LineSegment in a PathGeometry</span></span>
<span data-ttu-id="ec04b-103">Dieses Beispiel zeigt, wie ein Liniensegment erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ec04b-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="ec04b-104">Verwenden Sie zum Erstellen eines Liniensegments die <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, und <xref:System.Windows.Media.LineSegment> Klassen.</span><span class="sxs-lookup"><span data-stu-id="ec04b-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec04b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec04b-105">Example</span></span>  
 <span data-ttu-id="ec04b-106">Zeichnen Sie in den folgenden Beispielen ein <xref:System.Windows.Media.LineSegment> aus (10, 50), (200, 70).</span><span class="sxs-lookup"><span data-stu-id="ec04b-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="ec04b-107">Die folgende Abbildung zeigt die resultierenden <xref:System.Windows.Media.LineSegment>; eine Rasterhintergrund wurde hinzugefügt, um das Koordinatensystem anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec04b-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>  
  
 <span data-ttu-id="ec04b-108">![Ein LineSegment in einer PathFigure](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "Graphicsmm_pathgeometrylinesegment")</span><span class="sxs-lookup"><span data-stu-id="ec04b-108">![A LineSegment in a PathFigure](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span></span>  
<span data-ttu-id="ec04b-109">Ein LineSegment, das von (10,50) bis (200,70) gezeichnet wurde</span><span class="sxs-lookup"><span data-stu-id="ec04b-109">A LineSegment drawn from (10,50) to (200,70)</span></span>  
  
 <span data-ttu-id="ec04b-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ec04b-110">[xaml]</span></span>  
  
 <span data-ttu-id="ec04b-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie zum Beschreiben eines Pfads Attributsyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec04b-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 <span data-ttu-id="ec04b-112">[xaml]</span><span class="sxs-lookup"><span data-stu-id="ec04b-112">[xaml]</span></span>  
  
 <span data-ttu-id="ec04b-113">(Beachten Sie, die diese Attributsyntax tatsächlich erstellt eine <xref:System.Windows.Media.StreamGeometry>, einer helleren Gewichtung-Version von einer <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="ec04b-113">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="ec04b-114">Weitere Informationen finden Sie auf der Seite [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).)</span><span class="sxs-lookup"><span data-stu-id="ec04b-114">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="ec04b-115">Zudem können Sie in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] XAML ein Liniensegment mithilfe von Objektelementsyntax zeichnen.</span><span class="sxs-lookup"><span data-stu-id="ec04b-115">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="ec04b-116">Das folgende Beispiel entspricht dem vorhergehenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ec04b-116">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
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
  
 <span data-ttu-id="ec04b-117">Dieses Beispiel ist Teil eines größeren Beispiels. Das vollständige Beispiel finden Sie unter [Beispiel für Geometrien](http://go.microsoft.com/fwlink/?LinkID=159989).</span><span class="sxs-lookup"><span data-stu-id="ec04b-117">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec04b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec04b-118">See Also</span></span>  
 <xref:System.Windows.Media.PathFigure>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.GeometryDrawing>  
 <xref:System.Windows.Shapes.Path>  
 [<span data-ttu-id="ec04b-119">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="ec04b-119">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
