---
title: Übersicht über die Geometrie
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: f45c13e1af9bc2d1f75da11b13a2c03936b136c1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455013"
---
# <a name="geometry-overview"></a>Übersicht über die Geometrie
In dieser Übersicht wird beschrieben, wie die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> Klassen zum Beschreiben von Formen verwendet werden. In diesem Thema werden auch die Unterschiede zwischen <xref:System.Windows.Media.Geometry> Objekten und <xref:System.Windows.Shapes.Shape> Elementen erläutert.  

<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>Was ist eine Geometrie?  
 Die <xref:System.Windows.Media.Geometry>-Klasse und die Klassen, die davon abgeleitet werden, z. b. <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>und <xref:System.Windows.Media.CombinedGeometry>, ermöglichen es Ihnen, die Geometrie einer 2D-Form zu beschreiben. Diese geometrischen Beschreibungen haben viele Verwendungszwecke, beispielsweise zum Definieren einer am Bildschirm zu zeichnenden Form oder zum Definieren von Treffertest- und Clipbereichen. Sie können mithilfe einer Geometrie sogar einen Animationspfad definieren.  
  
 <xref:System.Windows.Media.Geometry> Objekte können einfach sein, z. b. Rechtecke und Kreise oder zusammengesetzte, die aus zwei oder mehr Geometrie Objekten erstellt werden.  Komplexere Geometrien können mithilfe der Klassen <xref:System.Windows.Media.PathGeometry> und <xref:System.Windows.Media.StreamGeometry> erstellt werden, die es Ihnen ermöglichen, Bögen und Kurven zu beschreiben.  
  
 Da es sich bei einer <xref:System.Windows.Media.Geometry> um einen <xref:System.Windows.Freezable>handelt, stellen <xref:System.Windows.Media.Geometry> Objekte mehrere besondere Features bereit: Sie können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt und als schreibgeschützt festgestellt werden, um die Leistung zu verbessern, geklont und Thread sicher gemacht zu werden. Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> Objekten bereitgestellt werden, finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Geometrien im Vergleich zu Formen  
 Die <xref:System.Windows.Media.Geometry>-und <xref:System.Windows.Shapes.Shape> Klassen ähneln darin, dass beide zweidimensionalen Formen beschreiben (z. b. vergleichen <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Shapes.Ellipse>), aber es gibt wichtige Unterschiede.  
  
 Für einen erbt die <xref:System.Windows.Media.Geometry>-Klasse von der <xref:System.Windows.Freezable>-Klasse, während die <xref:System.Windows.Shapes.Shape>-Klasse von <xref:System.Windows.FrameworkElement>erbt. Da es sich um Elemente handelt, können sich <xref:System.Windows.Shapes.Shape> Objekte selbst Rendering und am Layoutsystem teilnehmen, während <xref:System.Windows.Media.Geometry> Objekte nicht.  
  
 Obwohl <xref:System.Windows.Shapes.Shape> Objekte leichter verwendbar sind als <xref:System.Windows.Media.Geometry> Objekte, sind <xref:System.Windows.Media.Geometry> Objekte vielseitiger. Während ein <xref:System.Windows.Shapes.Shape> Objekt zum rendering2d-Grafiken verwendet wird, kann ein <xref:System.Windows.Media.Geometry> Objekt verwendet werden, um den geometrischen Bereich für 2D-Grafiken zu definieren, einen Bereich für das Abschneiden zu definieren oder eine Region für Treffer Tests zu definieren, beispielsweise.  
  
### <a name="the-path-shape"></a>Die Path-Form  
 Eine <xref:System.Windows.Shapes.Shape>, die <xref:System.Windows.Shapes.Path>-Klasse, verwendet tatsächlich eine <xref:System.Windows.Media.Geometry>, um ihren Inhalt zu beschreiben. Wenn Sie die <xref:System.Windows.Shapes.Path.Data%2A>-Eigenschaft der <xref:System.Windows.Shapes.Path> auf eine <xref:System.Windows.Media.Geometry> festlegen und deren <xref:System.Windows.Shapes.Shape.Fill%2A>-und <xref:System.Windows.Shapes.Shape.Stroke%2A> Eigenschaften festlegen, können Sie eine <xref:System.Windows.Media.Geometry>Rendering.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Allgemeine Eigenschaften, die eine Geometrie übernehmen  
 In den vorherigen Abschnitten wurde erwähnt, dass Geometry-Objekte für eine Vielzahl von Zwecken mit anderen Objekten verwendet werden können, z.B. zum Zeichnen von Formen, zum Animieren und für das Clipping. In der folgenden Tabelle werden mehrere Klassen aufgelistet, die über Eigenschaften verfügen, die ein <xref:System.Windows.Media.Geometry> Objekt akzeptieren.  
  
|Geben Sie Folgendes ein:|property|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Einfache geometrische Typen  
 Die Basisklasse für alle Geometrien ist die abstrakte Klasse <xref:System.Windows.Media.Geometry>.  Die Klassen, die von der <xref:System.Windows.Media.Geometry>-Klasse abgeleitet werden, können grob in drei Kategorien gruppiert werden: einfache Geometrien, Pfadgeometrien und zusammengesetzte Geometrien.  
  
 Einfache Geometry-Klassen schließen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>und <xref:System.Windows.Media.EllipseGeometry> ein und dienen zum Erstellen grundlegender geometrischer Formen, wie z. b. Linien, Rechtecke und Kreise.  
  
- Eine <xref:System.Windows.Media.LineGeometry> wird durch Angabe des Anfangs Punkts der Linie und des Endpunkts definiert.  
  
- Ein <xref:System.Windows.Media.RectangleGeometry> wird mit einer <xref:System.Windows.Rect> Struktur definiert, die seine relative Position und seine Höhe und Breite angibt. Sie können ein abgerundetes Rechteck erstellen, indem Sie die Eigenschaften <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> festlegen.  
  
- Ein <xref:System.Windows.Media.EllipseGeometry> wird von einem Mittelpunkt, einem x-Radius und einem y-Radius definiert.  Die folgenden Beispiele zeigen, wie einfache Geometrien für das Rendering und das Clipping erstellt werden können.  
  
 Diese Formen sowie komplexere Formen können mithilfe eines <xref:System.Windows.Media.PathGeometry> oder durch Kombinieren von Geometrie Objekten erstellt werden. diese Klassen bieten jedoch eine einfachere Möglichkeit, diese grundlegenden geometrischen Formen zu erstellen.  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.LineGeometry>erstellt und dargestellt wird.  Wie bereits erwähnt, kann ein <xref:System.Windows.Media.Geometry> Objekt sich nicht selbst zeichnen, sodass das Beispiel eine Form vom Typ <xref:System.Windows.Shapes.Path> verwendet, um die Zeile zu renderieren.  Da eine Linie keinen Bereich aufweist, hat das Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A>-Eigenschaft des <xref:System.Windows.Shapes.Path> keine Auswirkung. Stattdessen werden nur die Eigenschaften <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> angegeben. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Eine LineGeometry, gezeichnet von (10,20) bis (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Im nächsten Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.EllipseGeometry>erstellt und dargestellt wird.  In den Beispielen wird die <xref:System.Windows.Media.EllipseGeometry.Center%2A> des <xref:System.Windows.Media.EllipseGeometry> auf den Punkt `50,50` festgelegt, und der x-Radius und der y-Radius sind auf `50`festgelegt, wodurch ein Kreis mit einem Durchmesser von 100 erstellt wird.  Das Innere der Ellipse wird gezeichnet, indem der Fill-Eigenschaft des Path-Elements ein Wert zugewiesen wird, in diesem Fall <xref:System.Windows.Media.Brushes.Gold%2A>. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
EllipseGeometry, gezeichnet bei (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.RectangleGeometry>erstellt und dargestellt wird.  Die Position und die Dimensionen des Rechtecks werden durch eine <xref:System.Windows.Rect> Struktur definiert. Die Position ist `50,50` und die Höhe und Breite sind beide `25`, wodurch ein Quadrat erstellt wird. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Eine RectangleGeometry, gezeichnet bei 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Media.EllipseGeometry> als Clip Bereich für ein Bild verwendet wird.  Ein <xref:System.Windows.Controls.Image>-Objekt wird mit einem <xref:System.Windows.FrameworkElement.Width%2A> von 200 und einem <xref:System.Windows.FrameworkElement.Height%2A> 150 definiert.  Eine <xref:System.Windows.Media.EllipseGeometry> mit dem <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> Wert 100, dem <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> Wert 75 und einem <xref:System.Windows.Media.EllipseGeometry.Center%2A> Wert von 100, 75 wird auf die <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft des Bilds festgelegt.  Es wird nur der Teil des Bilds angezeigt, der innerhalb des Bereichs der Ellipse liegt. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Ein Bild mit und ohne Clipping](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Eine EllipseGeometry zum Beschneiden eines Image-Steuerelements  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Path-Geometrien  
 Die <xref:System.Windows.Media.PathGeometry>-Klasse und ihre Lightweight-Entsprechung, die <xref:System.Windows.Media.StreamGeometry>-Klasse, bieten die Möglichkeit, mehrere komplexe Abbildungen zu beschreiben, die aus Arcs, Kurven und Linien bestehen.  
  
 Das Herzstück eines <xref:System.Windows.Media.PathGeometry> ist eine Auflistung von <xref:System.Windows.Media.PathFigure> Objekten, die so benannt sind, dass jede Abbildung eine diskrete Form im <xref:System.Windows.Media.PathGeometry>beschreibt. Jede <xref:System.Windows.Media.PathFigure> besteht aus einem oder mehreren <xref:System.Windows.Media.PathSegment> Objekten, von denen jedes ein Segment der Abbildung beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|Beispiel|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|[Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bezier-Kurve zwischen zwei Punkten.|[Erstellen Sie eine kubische Bezier-Kurve](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|[Erstellen eines LineSegment in einer PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubischen Bezier-Kurven.|Weitere Informationen finden Sie auf der Seite <xref:System.Windows.Media.PolyBezierSegment> Type.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|Weitere Informationen finden Sie auf der Seite <xref:System.Windows.Media.PolyLineSegment> Type.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe quadratischer Bezier-Kurven.|Informationen finden Sie auf der Seite <xref:System.Windows.Media.PolyQuadraticBezierSegment>.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bezier-Kurve.|[Erstellen Sie eine quadratische Bezier-Kurve](how-to-create-a-quadratic-bezier-curve.md).|  
  
 Die Segmente in einer <xref:System.Windows.Media.PathFigure> werden zu einer einzelnen geometrischen Form zusammengefasst, wobei der Endpunkt jedes Segments der Anfangspunkt des nächsten Segments ist. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A>-Eigenschaft einer <xref:System.Windows.Media.PathFigure> gibt den Punkt an, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Beispielsweise kann eine vertikale Linie von `10,50` zu `10,150` definiert werden, indem die Eigenschaft <xref:System.Windows.Media.PathFigure.StartPoint%2A> auf `10,50` festgelegt und eine <xref:System.Windows.Media.LineSegment> mit der <xref:System.Windows.Media.LineSegment.Point%2A>-Eigenschafts Einstellung `10,150`erstellt wird.  
  
 Im folgenden Beispiel wird eine einfache <xref:System.Windows.Media.PathGeometry> erstellt, die aus einem einzelnen <xref:System.Windows.Media.PathFigure> mit einem <xref:System.Windows.Media.LineSegment> besteht und mit einem <xref:System.Windows.Shapes.Path> Element angezeigt wird. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> des <xref:System.Windows.Media.PathFigure> Objekts ist auf "`10,20`" festgelegt, und eine <xref:System.Windows.Media.LineSegment> wird mit einem Endpunkt `100,130`definiert. Die folgende Abbildung zeigt die <xref:System.Windows.Media.PathGeometry>, die in diesem Beispiel erstellt wurden.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Eine PathGeometry, die ein einzelnes LineSegment enthält  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Es lohnt sich, dieses Beispiel mit dem vorangehenden <xref:System.Windows.Media.LineGeometry> Beispiel zu vergleichen.  Die für eine <xref:System.Windows.Media.PathGeometry> verwendete Syntax ist wesentlich ausführlicher als die für einen einfachen <xref:System.Windows.Media.LineGeometry>verwendete Syntax, und es ist möglicherweise sinnvoller, die <xref:System.Windows.Media.LineGeometry> Klasse in diesem Fall zu verwenden, aber die ausführliche Syntax der <xref:System.Windows.Media.PathGeometry> ermöglicht sehr komplizierte und komplexe geometrische Bereiche.  
  
 Komplexere Geometrien können mithilfe einer Kombination aus <xref:System.Windows.Media.PathSegment> Objekten erstellt werden.  
  
 Im nächsten Beispiel wird eine <xref:System.Windows.Media.BezierSegment>, eine <xref:System.Windows.Media.LineSegment>und eine <xref:System.Windows.Media.ArcSegment> zum Erstellen einer Form verwendet. Im Beispiel wird zuerst eine kubische Bezier-Kurve erstellt, indem vier Punkte definiert werden: ein Startpunkt, der Endpunkt des vorherigen Segments, ein Endpunkt (<xref:System.Windows.Media.BezierSegment.Point3%2A>) und zwei Kontrollpunkte (<xref:System.Windows.Media.BezierSegment.Point1%2A> und <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Die beiden Steuerungs Punkte einer kubischen Bezier-Kurve Verhalten sich wie Magnete und gewinnen Teile davon, was andernfalls eine gerade Linie ist, wodurch eine Kurve erzeugt wird. Der erste Kontrollpunkt, <xref:System.Windows.Media.BezierSegment.Point1%2A>, wirkt sich auf den Anfangs Abschnitt der Kurve aus. der zweite Kontrollpunkt, <xref:System.Windows.Media.BezierSegment.Point2%2A>, wirkt sich auf den Endabschnitt der Kurve aus.  
  
 Im Beispiel wird dann ein <xref:System.Windows.Media.LineSegment>hinzugefügt, das zwischen dem Endpunkt des vorangehenden <xref:System.Windows.Media.BezierSegment> gezeichnet wird, der dem durch seine <xref:System.Windows.Media.LineSegment>-Eigenschaft angegebenen Punkt vorangestellt wird.  
  
 Im Beispiel wird dann ein <xref:System.Windows.Media.ArcSegment>hinzugefügt, der vom Endpunkt der vorhergehenden <xref:System.Windows.Media.LineSegment> bis zu dem Punkt gezeichnet wird, der durch seine <xref:System.Windows.Media.ArcSegment.Point%2A>-Eigenschaft angegeben wird. Im Beispiel wird auch der x-und y-Radius (<xref:System.Windows.Media.ArcSegment.Size%2A>) des Bogens angegeben, ein Drehungs Winkel (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), ein Flag, das angibt, wie groß der Winkel des resultierenden Bogens sein soll (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>), und ein Wert, der angibt, in welcher Richtung der Bogen gezeichnet wird (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
Eine PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Noch komplexere Geometrien können mithilfe mehrerer <xref:System.Windows.Media.PathFigure> Objekte innerhalb einer <xref:System.Windows.Media.PathGeometry>erstellt werden.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> mit zwei <xref:System.Windows.Media.PathFigure> Objekten erstellt, die jeweils mehrere <xref:System.Windows.Media.PathSegment>-Objekte enthalten.  Die <xref:System.Windows.Media.PathFigure> aus dem obigen Beispiel und eine <xref:System.Windows.Media.PathFigure> mit einem <xref:System.Windows.Media.PolyLineSegment> und einem <xref:System.Windows.Media.QuadraticBezierSegment> werden verwendet.  Ein <xref:System.Windows.Media.PolyLineSegment> wird mit einem Array von Punkten definiert, und die <xref:System.Windows.Media.QuadraticBezierSegment> wird mit einem Steuerungspunkt und einem Endpunkt definiert. Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Eine PathGeometry mit mehreren Figuren  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Wie die <xref:System.Windows.Media.PathGeometry>-Klasse definiert ein <xref:System.Windows.Media.StreamGeometry> eine komplexe geometrische Form, die Kurven, Arcs und Linien enthalten kann. Im Gegensatz zu einem <xref:System.Windows.Media.PathGeometry>unterstützt der Inhalt einer <xref:System.Windows.Media.StreamGeometry> keine Datenbindung, Animation oder Änderung. Verwenden Sie eine <xref:System.Windows.Media.StreamGeometry>, wenn Sie eine komplexe Geometrie beschreiben müssen, aber nicht den Aufwand für die Unterstützung von Datenbindung, Animation oder Änderung. Aufgrund der Effizienz ist die <xref:System.Windows.Media.StreamGeometry> Klasse eine gute Wahl zum Beschreiben von Adornern.  
  
 Ein Beispiel finden Sie unter [Erstellen einer Form mithilfe von StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Pfadmarkupsyntax  
 Die <xref:System.Windows.Media.PathGeometry>-und <xref:System.Windows.Media.StreamGeometry> Typen unterstützen eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attribut Syntax mithilfe einer speziellen Reihe von Move-und Draw-Befehlen. Weitere Informationen finden Sie unter [Pfadmarkupsyntax](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Zusammengesetzte Geometrien  
 Zusammengesetzte Geometry-Objekte können mithilfe einer <xref:System.Windows.Media.GeometryGroup>, einer <xref:System.Windows.Media.CombinedGeometry>oder durch Aufrufen der statischen <xref:System.Windows.Media.Geometry>-Methode erstellt werden <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
- Das <xref:System.Windows.Media.CombinedGeometry>-Objekt und die <xref:System.Windows.Media.Geometry.Combine%2A>-Methode führen einen booleschen Vorgang aus, um den durch zwei Geometrien definierten Bereich zu kombinieren. <xref:System.Windows.Media.Geometry> Objekte ohne Bereich werden verworfen. Es können nur zwei <xref:System.Windows.Media.Geometry> Objekte kombiniert werden (obwohl diese beiden Geometrien auch zusammengesetzte Geometrien sein können).  
  
- Die <xref:System.Windows.Media.GeometryGroup>-Klasse erstellt eine Zusammenführung der <xref:System.Windows.Media.Geometry>-Objekte, die Sie enthält, ohne ihren Bereich zu kombinieren. Einer <xref:System.Windows.Media.GeometryGroup>können beliebig viele <xref:System.Windows.Media.Geometry> Objekte hinzugefügt werden. Ein Beispiel finden Sie unter [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md).  
  
 Da Sie keinen kombinierender Vorgang ausführen, bietet die Verwendung von <xref:System.Windows.Media.GeometryGroup>-Objekten Leistungsvorteile gegenüber der Verwendung von <xref:System.Windows.Media.CombinedGeometry> Objekten oder der <xref:System.Windows.Media.Geometry.Combine%2A>-Methode.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Kombinierte Geometrien  
 Im vorherigen Abschnitt wurde das <xref:System.Windows.Media.CombinedGeometry> Objekt und die <xref:System.Windows.Media.Geometry.Combine%2A>-Methode den Bereich kombiniert, der durch die darin enthaltenen Geometrien definiert ist. Die <xref:System.Windows.Media.GeometryCombineMode>-Enumeration gibt an, wie die Geometrien kombiniert werden. Die folgenden Werte sind für die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>-Eigenschaft möglich: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>und <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.CombinedGeometry> mit einem kombinierungsmodus von Union definiert.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch die <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise desselben Radius definiert, wobei die zentriert um 50 liegen.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union-kombinierungsmodus](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.CombinedGeometry> mit dem kombinierungsmodus <xref:System.Windows.Media.GeometryCombineMode.Xor>definiert.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch die <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise desselben Radius definiert, wobei die zentriert um 50 liegen.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des XOR-kombinierungsmodus](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Weitere Beispiele finden Sie unter [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md) und unter [Erstellen von kombinierten Geometrien](how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 Da es von der <xref:System.Windows.Freezable>-Klasse erbt, bietet die <xref:System.Windows.Media.Geometry>-Klasse mehrere besondere Features: <xref:System.Windows.Media.Geometry> Objekte können als [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt und schreibgeschützt werden, um die Leistung zu verbessern, geklont und vorgenommen zu werden. Thread sicher. Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> Objekten bereitgestellt werden, finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Andere Geometriefeatures  
 Die <xref:System.Windows.Media.Geometry>-Klasse bietet auch nützliche Hilfsmethoden, wie z. b. die folgenden:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>: Ruft den Bereich der <xref:System.Windows.Media.Geometry>ab.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>: bestimmt, ob die Geometrie eine andere <xref:System.Windows.Media.Geometry>enthält.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>: bestimmt, ob der Strich eines <xref:System.Windows.Media.Geometry> einen angegebenen Punkt enthält.  
  
 Eine komplette Liste der zugehörigen Methoden finden Sie in der <xref:System.Windows.Media.Geometry>-Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Pfadmarkupsyntax](path-markup-syntax.md)
- [Themen zu Vorgehensweisen](geometries-how-to-topics.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
