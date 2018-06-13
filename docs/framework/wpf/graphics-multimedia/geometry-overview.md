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
ms.openlocfilehash: 01c460ae18c489a21c860c6d2b10f551e6e68242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558069"
---
# <a name="geometry-overview"></a>Übersicht über die Geometrie
In dieser Übersicht wird beschrieben, wie mithilfe der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> Klassen, die Formen zu beschreiben. In diesem Thema sind auch die Unterschiede zwischen <xref:System.Windows.Media.Geometry> Objekte und <xref:System.Windows.Shapes.Shape> Elemente.  
  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>Was ist eine Geometrie?  
 Die <xref:System.Windows.Media.Geometry> Klasse und die daraus, wie z. B. abgeleiteten Klassen <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>, und <xref:System.Windows.Media.CombinedGeometry>, ermöglichen es Ihnen, die Geometrie einer 2D-Form beschreiben. Diese geometrischen Beschreibungen haben viele Verwendungszwecke, beispielsweise zum Definieren einer am Bildschirm zu zeichnenden Form oder zum Definieren von Treffertest- und Clipbereichen. Sie können mithilfe einer Geometrie sogar einen Animationspfad definieren.  
  
 <xref:System.Windows.Media.Geometry> Objekte können einfach sein, z. B. Rechtecke und Kreise und zusammengesetzte aus mindestens zwei Geometry-Objekten erstellt.  Komplexere Geometrien können erstellt werden, mithilfe der <xref:System.Windows.Media.PathGeometry> und <xref:System.Windows.Media.StreamGeometry> Klassen, die Ihnen ermöglichen, Bögen und Kurven beschreiben.  
  
 Da eine <xref:System.Windows.Media.Geometry> ist eine Art von <xref:System.Windows.Freezable>, <xref:System.Windows.Media.Geometry> Objekte mehrere spezielle Funktionen bereitstellen: kann als deklariert [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)gemeinsam von mehreren Objekten, die zur Verbesserung der Leistung geklont, Schreibschutz versehen wurden und als threadsicher. Weitere Informationen zu den verschiedenen Features von <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Geometrien vs. Formen  
 Die <xref:System.Windows.Media.Geometry> und <xref:System.Windows.Shapes.Shape> Klassen scheinen ähnlich, da sie beide 2D-Formen beschreiben (vergleichen <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Shapes.Ellipse> z. B.), es gibt jedoch wichtige Unterschiede.  
  
 Für ein Modell das <xref:System.Windows.Media.Geometry> Klasse erbt von der <xref:System.Windows.Freezable> Klasse während der <xref:System.Windows.Shapes.Shape> Klasse erbt von <xref:System.Windows.FrameworkElement>. Da diese Elemente sind <xref:System.Windows.Shapes.Shape> Objekte können sich selbst rendern und das Layoutsystem teilnehmen während <xref:System.Windows.Media.Geometry> Objekte können nicht.  
  
 Obwohl <xref:System.Windows.Shapes.Shape> Objekte sind schneller als verwendbaren <xref:System.Windows.Media.Geometry> Objekte <xref:System.Windows.Media.Geometry> Objekte sind flexibler. Während einer <xref:System.Windows.Shapes.Shape> Objekt wird zum Rendern der 2D-Grafik, verwendet eine <xref:System.Windows.Media.Geometry> Objekt kann verwendet werden, um die geometrische Region 2D-Grafik definieren, definieren eine Region für das Clipping oder definieren eine Region für Treffertests, z. B.  
  
### <a name="the-path-shape"></a>Die Path-Form  
 Eine <xref:System.Windows.Shapes.Shape>, <xref:System.Windows.Shapes.Path> Klasse, verwendet eine <xref:System.Windows.Media.Geometry> um seinen Inhalt zu beschreiben. Durch Festlegen der <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft der <xref:System.Windows.Shapes.Path> mit einer <xref:System.Windows.Media.Geometry> verwendet wird und seine <xref:System.Windows.Shapes.Shape.Fill%2A> und <xref:System.Windows.Shapes.Shape.Stroke%2A> Eigenschaften, die Sie rendern eine <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Allgemeine Eigenschaften, die eine Geometrie übernehmen  
 In den vorherigen Abschnitten wurde erwähnt, dass Geometry-Objekte für eine Vielzahl von Zwecken mit anderen Objekten verwendet werden können, z.B. zum Zeichnen von Formen, zum Animieren und für das Clipping. Die folgende Tabelle enthält mehrere Klassen, deren Eigenschaften nehmen eine <xref:System.Windows.Media.Geometry> Objekt.  
  
|Typ|Eigenschaft|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Einfache geometrische Typen  
 Die Basisklasse für alle Geometrien ist die abstrakte Klasse <xref:System.Windows.Media.Geometry>.  Die abgeleiteten Klassen der <xref:System.Windows.Media.Geometry> Klasse kann grob in drei Kategorien gruppiert: einfache Geometrien Pfadgeometrien und zusammengesetzte Geometrien.  
  
 Einfache Geometrieklassen umfassen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, und <xref:System.Windows.Media.EllipseGeometry> und werden verwendet, um grundlegende geometrische Formen, z. B. Linien, Rechtecke und Kreise erstellen.  
  
-   Ein <xref:System.Windows.Media.LineGeometry> wird definiert, indem Sie den Startpunkt und den Endpunkt der Linie.  
  
-   Ein <xref:System.Windows.Media.RectangleGeometry> mit definiert eine <xref:System.Windows.Rect> Struktur, die ihre relative Position und die Höhe und Breite angibt. Sie können ein abgerundetes Rechteck erstellen, indem die <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> und <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> Eigenschaften.  
  
-   Ein <xref:System.Windows.Media.EllipseGeometry> wird von einem Mittelpunkt, einen X-Radius und eine y-Radius definiert.  Die folgenden Beispiele zeigen, wie einfache Geometrien für das Rendering und das Clipping erstellt werden können.  
  
 Diese Formen sowie komplexere Formen, können mit erstellt werden ein <xref:System.Windows.Media.PathGeometry> , oder geben Sie durch Kombinieren von Geometry-Objekten, die zusammen eine einfachere Möglichkeit zum Erstellen dieser grundlegenden geometrischen Formen.  
  
 Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.LineGeometry>.  Wie bereits zuvor erwähnt eine <xref:System.Windows.Media.Geometry> Objekt kann nicht selbst zeichnen, damit das Beispiel verwendet eine <xref:System.Windows.Shapes.Path> Form ", um die Zeile zu rendern.  Da eine Linie keinen Bereich aufweist, mit der Festlegung der <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft von der <xref:System.Windows.Shapes.Path> keine Auswirkung; stattdessen nur die <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaften angegeben werden. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "Graphicsmm_line")  
Eine LineGeometry, gezeichnet von (10,20) bis (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Im nächste Beispiel wird gezeigt, wie zum Erstellen und Rendern einer <xref:System.Windows.Media.EllipseGeometry>.  Beispielen die <xref:System.Windows.Media.EllipseGeometry.Center%2A> von der <xref:System.Windows.Media.EllipseGeometry> festgelegt ist, zu dem Punkt `50,50` und den X-Radius und der y-Radius werden auf festgelegt `50`, dadurch werden einen Kreis mit einem Durchmesser von 100 erstellt.  Das Innere der Ellipse wird gezeichnet, indem Sie in diesem Fall das Pfadelement Fill-Eigenschaft einen Wert zuweisen <xref:System.Windows.Media.Brushes.Gold%2A>. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Eine EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.gif "Graphicsmm_ellipse")  
EllipseGeometry, gezeichnet bei (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Das folgende Beispiel zeigt das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry>.  Die Position und die Dimensionen des Rechtecks werden definiert, indem eine <xref:System.Windows.Rect> Struktur. Die Position ist `50,50` und die Höhe und Breite sind beide `25`, wodurch ein Quadrat erstellt wird. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Eine RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "Graphicsmm_rectangle")  
Eine RectangleGeometry, gezeichnet bei 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Das folgende Beispiel zeigt, wie Sie eine <xref:System.Windows.Media.EllipseGeometry> als Clip-Bereich für ein Bild.  Ein <xref:System.Windows.Controls.Image> Objekt definiert ist, mit einem <xref:System.Windows.FrameworkElement.Width%2A> 200 und ein <xref:System.Windows.FrameworkElement.Height%2A> 150.  Ein <xref:System.Windows.Media.EllipseGeometry> mit einer <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> Wert von 100, eine <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> Wert von 75, und ein <xref:System.Windows.Media.EllipseGeometry.Center%2A> 100,75 wird Wert wird festgelegt, um die <xref:System.Windows.UIElement.Clip%2A> Eigenschaft des Bilds.  Es wird nur der Teil des Bilds angezeigt, der innerhalb des Bereichs der Ellipse liegt. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Ein Bild mit und ohne Clipping](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "Graphicsmm_clipexample")  
Eine EllipseGeometry zum Beschneiden eines Image-Steuerelements  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Path-Geometrien  
 Die <xref:System.Windows.Media.PathGeometry> Klasse und deren Lightweight-Entsprechung, die <xref:System.Windows.Media.StreamGeometry> Klasse, bieten die Möglichkeit, mehrere komplexe Figuren beschreiben besteht aus Bögen, Kurven und Linien.  
  
 Der Kern von einer <xref:System.Windows.Media.PathGeometry> ist eine Sammlung von <xref:System.Windows.Media.PathFigure> Objekte, die Bezeichnung stammt daher, da jeder Zahl in eine diskrete Form beschreibt die <xref:System.Windows.Media.PathGeometry>. Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jede ein Segment der Abbildung beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|Beispiel|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|[Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bézier-Kurve zwischen zwei Punkten.|[Erstellen Sie eine kubische Bézier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|[Erstellen eines LineSegment in einer PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubische Bézier-Kurven.|Finden Sie unter der <xref:System.Windows.Media.PolyBezierSegment> Seite ".|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|Finden Sie unter der <xref:System.Windows.Media.PolyLineSegment> Seite ".|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe von quadratische Bézier-Kurven.|Finden Sie unter der <xref:System.Windows.Media.PolyQuadraticBezierSegment> Seite.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bézier-Kurve an.|[Erstellen Sie eine quadratische Bézier-Kurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 Die Segmente innerhalb einer <xref:System.Windows.Media.PathFigure> eine einzelne geometrische Form, die mit dem Endpunkt der einzelnen Segmente, die den Anfangspunkt des nächsten Segments wird zusammengefasst werden. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft von einem <xref:System.Windows.Media.PathFigure> gibt den Punkt, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Z. B. eine vertikale Linie von `10,50` auf `10,150` können definiert werden, indem die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft, um `10,50` und erstellen eine <xref:System.Windows.Media.LineSegment> mit einer <xref:System.Windows.Media.LineSegment.Point%2A> eigenschaftseinstellung `10,150`.  
  
 Das folgende Beispiel erstellt eine einfache <xref:System.Windows.Media.PathGeometry> bestehend aus einer einzelnen <xref:System.Windows.Media.PathFigure> mit einer <xref:System.Windows.Media.LineSegment> und zeigt ihn mithilfe einer <xref:System.Windows.Shapes.Path> Element. Die <xref:System.Windows.Media.PathFigure> des Objekts <xref:System.Windows.Media.PathFigure.StartPoint%2A> auf festgelegt ist `10,20` und ein <xref:System.Windows.Media.LineSegment> wird definiert, mit einem Endpunkt eines `100,130`. Die folgende Abbildung zeigt die <xref:System.Windows.Media.PathGeometry> durch dieses Beispiel erstellt.  
  
 ![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "Graphicsmm_line")  
Eine PathGeometry, die ein einzelnes LineSegment enthält  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 In diesem Beispiel mit dem vorangehenden Vergleich lohnt sich <xref:System.Windows.Media.LineGeometry> Beispiel.  Die Syntax für eine <xref:System.Windows.Media.PathGeometry> ist wesentlich ausführlicher als für eine einfache <xref:System.Windows.Media.LineGeometry>, und es ist möglicherweise sinnvoller, verwenden Sie die <xref:System.Windows.Media.LineGeometry> in diesem Fall jedoch die ausführliche Syntax der Klasse die <xref:System.Windows.Media.PathGeometry> ermöglicht die sehr kompliziert und komplex geometrische Regionen.  
  
 Komplexere Geometrien können erstellt werden, mithilfe einer Kombination von <xref:System.Windows.Media.PathSegment> Objekte.  
  
 Im nächste Beispiel wird eine <xref:System.Windows.Media.BezierSegment>, <xref:System.Windows.Media.LineSegment>, und ein <xref:System.Windows.Media.ArcSegment> um Form zu erstellen. Das Beispiel erstellt zuerst eine kubische Bézierkurve durch vier Punkte definiert: einen Startpunkt, also der Endpunkt des vorherigen Abschnitts, einen Endpunkt (<xref:System.Windows.Media.BezierSegment.Point3%2A>), und die beiden Steuerpunkte (<xref:System.Windows.Media.BezierSegment.Point1%2A> und <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Die beiden Steuerpunkte, der eine kubische Bézier-Kurve Verhalten sich wie Magnete attraktiv Abschnitte einer geraden Linie für sich selbst, der eine Kurve erzeugt. Der erste Kontrollpunkt, <xref:System.Windows.Media.BezierSegment.Point1%2A>, wirkt sich auf den Anfang Teil der Kurve; der zweite Kontrollpunkt <xref:System.Windows.Media.BezierSegment.Point2%2A>, wirkt sich auf den Endabschnitt der Kurve.  
  
 Im Beispiel fügt dann ein <xref:System.Windows.Media.LineSegment>, die zwischen dem Endpunkt der vorangehenden gezeichnet wird <xref:System.Windows.Media.BezierSegment> , die auf den vom angegebenen Punkt voranstehen seine <xref:System.Windows.Media.LineSegment> Eigenschaft.  
  
 Im Beispiel fügt dann ein <xref:System.Windows.Media.ArcSegment>, die gezeichnet wird, von dem Endpunkt der vorangehenden <xref:System.Windows.Media.LineSegment> zu dem Punkt, der gemäß seiner <xref:System.Windows.Media.ArcSegment.Point%2A> Eigenschaft. Das Beispiel gibt auch an den Bogen x- und y-Radius (<xref:System.Windows.Media.ArcSegment.Size%2A>), einen Drehwinkel für Bezeichnungen (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), ein Flag, der angibt, wie groß der Winkel des resultierenden Bogens sein soll (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>), und einen Wert, der angibt, in welche Richtung der Bogen gezeichnet wird (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.gif "graphicsmm_path2")  
Eine PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Auch komplexere Geometrien können erstellt werden, mithilfe von mehreren <xref:System.Windows.Media.PathFigure> -Objekte innerhalb einer <xref:System.Windows.Media.PathGeometry>.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Media.PathGeometry> mit zwei <xref:System.Windows.Media.PathFigure> Objekte, von denen jede mehrere enthält <xref:System.Windows.Media.PathSegment> Objekte.  Die <xref:System.Windows.Media.PathFigure> aus dem obigen Beispiel und eine <xref:System.Windows.Media.PathFigure> mit einer <xref:System.Windows.Media.PolyLineSegment> und ein <xref:System.Windows.Media.QuadraticBezierSegment> verwendet werden.  Ein <xref:System.Windows.Media.PolyLineSegment> mit einem Array von Punkten definiert ist und die <xref:System.Windows.Media.QuadraticBezierSegment> mit einem Steuerungspunkt und einen Endpunkt definiert ist. Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.gif "Graphicsmm_path")  
Eine PathGeometry mit mehreren Figuren  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Wie die <xref:System.Windows.Media.PathGeometry> -Klasse, eine <xref:System.Windows.Media.StreamGeometry> definiert eine komplexe geometrische Form, die Kurven, Bögen und Zeilen enthalten kann. Im Gegensatz zu einer <xref:System.Windows.Media.PathGeometry>, den Inhalt einer <xref:System.Windows.Media.StreamGeometry> unterstützen keine datenbindungen, Animationen und Änderungen. Verwenden einer <xref:System.Windows.Media.StreamGeometry> müssen Sie eine komplexe Geometrie beschreiben, aber nicht möchten, den Aufwand für die Unterstützung von datenbindungen, Animationen und Änderungen. Aufgrund der Effizienz der <xref:System.Windows.Media.StreamGeometry> Klasse ist eine gute Wahl zum Beschreiben von Adornern.  
  
 Ein Beispiel finden Sie unter [Erstellen einer Form mithilfe von StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Pfadmarkupsyntax  
 Die <xref:System.Windows.Media.PathGeometry> und <xref:System.Windows.Media.StreamGeometry> Typen unterstützen eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Attributsyntax mithilfe spezieller mehrerer verschieben und draw-Befehle. Weitere Informationen finden Sie unter [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Zusammengesetzte Geometrien  
 Zusammengesetzte Geometrie-Objekte können erstellt werden, mithilfe einer <xref:System.Windows.Media.GeometryGroup>, <xref:System.Windows.Media.CombinedGeometry>, oder durch Aufrufen der statischen <xref:System.Windows.Media.Geometry> Methode <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
-   Die <xref:System.Windows.Media.CombinedGeometry> Objekt und die <xref:System.Windows.Media.Geometry.Combine%2A> Methode führt eine boolesche Operation zum Kombinieren von zwei Geometrien definiert wird. <xref:System.Windows.Media.Geometry> Objekte, die ohne Bereich werden verworfen. Nur zwei <xref:System.Windows.Media.Geometry> Objekte (obwohl diese zwei Geometrien auch zusammengesetzte Geometrien sein können) kombiniert werden können.  
  
-   Die <xref:System.Windows.Media.GeometryGroup> -Klasse erstellt einen Zusammenschluss von der <xref:System.Windows.Media.Geometry> Objekte, ohne dass ihr Bereich kombiniert. Eine beliebige Anzahl von <xref:System.Windows.Media.Geometry> können Objekte hinzugefügt werden, um eine <xref:System.Windows.Media.GeometryGroup>. Ein Beispiel finden Sie unter [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md).  
  
 Verwenden Sie daran, dass diese Kombination nicht ausführen, <xref:System.Windows.Media.GeometryGroup> Objekte bietet Leistungsvorteile gegenüber <xref:System.Windows.Media.CombinedGeometry> Objekte oder die <xref:System.Windows.Media.Geometry.Combine%2A> Methode.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Kombinierte Geometrien  
 Im vorherigen Abschnitt erwähnt die <xref:System.Windows.Media.CombinedGeometry> Objekt und die <xref:System.Windows.Media.Geometry.Combine%2A> Methode kombinieren, durch die darin enthaltenen Geometrien definiert wird. Die <xref:System.Windows.Media.GeometryCombineMode> Enumeration gibt an, wie die Geometrien kombiniert werden. Die möglichen Werte für die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> -Eigenschaft sind: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>, und <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Media.CombinedGeometry> mit der Union-Kombinationsmodus definiert ist.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "Mil_task_combined_geometry_union")  
  
 Im folgenden Beispiel ein <xref:System.Windows.Media.CombinedGeometry> wird definiert, mit der Kombinationsmodus <xref:System.Windows.Media.GeometryCombineMode.Xor>.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius, jedoch mit Rechenzentren Offset von 50 definiert.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des Xor-Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "Mil_task_combined_geometry_xor")  
  
 Weitere Beispiele finden Sie unter [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) und unter [Erstellen von kombinierten Geometrien](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 Da es erbt die <xref:System.Windows.Freezable> -Klasse, die <xref:System.Windows.Media.Geometry> Klasse mehrere spezielle Funktionen bereitstellen: <xref:System.Windows.Media.Geometry> deklarierte Objekte als [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)gemeinsam von mehreren Objekten, die zur Verbesserung der Schreibschutz versehen wurden Leistung, geklont und als threadsicher. Weitere Informationen zu den verschiedenen Features von <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Andere Geometriefeatures  
 Die <xref:System.Windows.Media.Geometry> Klasse enthält auch nützliche Hilfsmethoden, z. B. Folgendes:  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A> -Ruft den Clientbereich der <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A> – Bestimmt, ob die Geometrie eine andere enthält <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A> – Bestimmt, ob der Kontur einer <xref:System.Windows.Media.Geometry> einen angegebenen Punkt enthält.  
  
 Finden Sie unter der <xref:System.Windows.Media.Geometry> Klasse für eine vollständige Liste der Methoden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Geometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
