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
ms.openlocfilehash: ff42e59edd9d98b0b52dc3bdd3ace0c35df60878
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112374"
---
# <a name="geometry-overview"></a>Übersicht über die Geometrie
In dieser Übersicht wird [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> beschrieben, wie die Klassen zum Beschreiben von Shapes verwendet werden. In diesem Thema werden <xref:System.Windows.Media.Geometry> auch <xref:System.Windows.Shapes.Shape> die Unterschiede zwischen Objekten und Elementen kontrastiert.  

<a name="wcpsdk_graphics_geometry_introduction"></a>
## <a name="what-is-a-geometry"></a>Was ist eine Geometrie?  
 Die <xref:System.Windows.Media.Geometry> Klasse und die Klassen, die <xref:System.Windows.Media.EllipseGeometry>daraus <xref:System.Windows.Media.PathGeometry>ableiten, z. B. , und <xref:System.Windows.Media.CombinedGeometry>, ermöglichen es Ihnen, die Geometrie eines 2D-Shapes zu beschreiben. Diese geometrischen Beschreibungen haben viele Verwendungszwecke, beispielsweise zum Definieren einer am Bildschirm zu zeichnenden Form oder zum Definieren von Treffertest- und Clipbereichen. Sie können mithilfe einer Geometrie sogar einen Animationspfad definieren.  
  
 <xref:System.Windows.Media.Geometry>Objekte können einfach sein, z. B. Rechtecke und Kreise, oder zusammengesetzt, die aus zwei oder mehr Geometrieobjekten erstellt werden.  Komplexere Geometrien können mithilfe <xref:System.Windows.Media.PathGeometry> der <xref:System.Windows.Media.StreamGeometry> und-Klassen erstellt werden, mit denen Sie Bogen und Kurven beschreiben können.  
  
 Da <xref:System.Windows.Media.Geometry> es sich <xref:System.Windows.Freezable>bei <xref:System.Windows.Media.Geometry> a um einen Typ von handelt, bieten Objekte mehrere spezielle Features: Sie können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt, schreibgeschützt zur Verbesserung der Leistung hergestellt, geklont und threadsicher gemacht werden. Weitere Informationen zu den verschiedenen <xref:System.Windows.Freezable> Features, die von Objekten bereitgestellt werden, finden Sie in der [Übersicht über freisetzbare Objekte](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>
## <a name="geometries-vs-shapes"></a>Geometrien vs. Formen  
 Die <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Shape> und Klassen scheinen insofern ähnlich zu <xref:System.Windows.Media.EllipseGeometry> sein, als sie beide 2D-Shapes beschreiben (vergleichen sie zum <xref:System.Windows.Shapes.Ellipse> Beispiel), aber es gibt wichtige Unterschiede.  
  
 Zum einen <xref:System.Windows.Media.Geometry> erbt die Klasse <xref:System.Windows.Freezable> von <xref:System.Windows.Shapes.Shape> der Klasse, <xref:System.Windows.FrameworkElement>während die Klasse von erbt. Da es sich <xref:System.Windows.Shapes.Shape> um Elemente handelt, können Objekte <xref:System.Windows.Media.Geometry> sich selbst rendern und am Layoutsystem teilnehmen, objekte jedoch nicht.  
  
 Obwohl <xref:System.Windows.Shapes.Shape> Objekte leichter verwendbar sind als <xref:System.Windows.Media.Geometry> Objekte, <xref:System.Windows.Media.Geometry> sind Objekte vielseitiger. Während <xref:System.Windows.Shapes.Shape> ein Objekt zum Rendern von <xref:System.Windows.Media.Geometry> 2D-Grafiken verwendet wird, kann ein Objekt verwendet werden, um den geometrischen Bereich für 2D-Grafiken zu definieren, einen Bereich für das Zuschneiden zu definieren oder einen Bereich für Treffertests zu definieren.  
  
### <a name="the-path-shape"></a>Die Path-Form  
 Eine <xref:System.Windows.Shapes.Shape>, <xref:System.Windows.Shapes.Path> die Klasse, <xref:System.Windows.Media.Geometry> verwendet tatsächlich eine, um ihren Inhalt zu beschreiben. Durch Festlegen <xref:System.Windows.Shapes.Path.Data%2A> der <xref:System.Windows.Shapes.Path> Eigenschaft <xref:System.Windows.Media.Geometry> des mit <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> a und Festlegen <xref:System.Windows.Media.Geometry>der en und Eigenschaften können Sie eine rendern.  
  
<a name="commonproperties"></a>
## <a name="common-properties-that-take-a-geometry"></a>Allgemeine Eigenschaften, die eine Geometrie übernehmen  
 In den vorherigen Abschnitten wurde erwähnt, dass Geometry-Objekte für eine Vielzahl von Zwecken mit anderen Objekten verwendet werden können, z.B. zum Zeichnen von Formen, zum Animieren und für das Clipping. In der folgenden Tabelle sind mehrere <xref:System.Windows.Media.Geometry> Klassen aufgeführt, die Eigenschaften aufweisen, die ein Objekt annehmen.  
  
|type|Eigenschaft|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>
## <a name="simple-geometry-types"></a>Einfache geometrische Typen  
 Die Basisklasse für alle Geometrien <xref:System.Windows.Media.Geometry>ist die abstrakte Klasse .  Die Klassen, die <xref:System.Windows.Media.Geometry> von der Klasse ableiten, können grob in drei Kategorien gruppiert werden: einfache Geometrien, Pfadgeometrien und zusammengesetzte Geometrien.  
  
 Einfache Geometrieklassen <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>umfassen <xref:System.Windows.Media.EllipseGeometry> , und werden verwendet, um grundlegende geometrische Formen wie Linien, Rechtecke und Kreise zu erstellen.  
  
- A <xref:System.Windows.Media.LineGeometry> wird definiert, indem der Startpunkt der Linie und der Endpunkt angegeben werden.  
  
- A <xref:System.Windows.Media.RectangleGeometry> wird mit <xref:System.Windows.Rect> einer Struktur definiert, die ihre relative Position und ihre Höhe und Breite angibt. Sie können ein abgerundetes <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> Rechteck <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> erstellen, indem Sie die und Eigenschaften festlegen.  
  
- Ein <xref:System.Windows.Media.EllipseGeometry> wird durch einen Mittelpunkt, einen x-Radius und einen y-Radius definiert.  Die folgenden Beispiele zeigen, wie einfache Geometrien für das Rendering und das Clipping erstellt werden können.  
  
 Dieselben Formen sowie komplexere Formen können mithilfe eines <xref:System.Windows.Media.PathGeometry> oder durch Kombinieren von Geometrieobjekten zusammen erstellt werden, aber diese Klassen bieten eine einfachere Möglichkeit, diese grundlegenden geometrischen Formen zu erstellen.  
  
 Das folgende Beispiel zeigt, wie <xref:System.Windows.Media.LineGeometry>eine erstellt und gerendert wird.  Wie bereits erwähnt, kann ein <xref:System.Windows.Media.Geometry> Objekt nicht selbst <xref:System.Windows.Shapes.Path> zeichnen, sodass im Beispiel eine Form zum Rendern der Linie verwendet wird.  Da eine Linie keinen Bereich <xref:System.Windows.Shapes.Shape.Fill%2A> hat, <xref:System.Windows.Shapes.Path> hat das Festlegen der Eigenschaft des keine Auswirkungen. Stattdessen werden <xref:System.Windows.Shapes.Shape.Stroke%2A> nur <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> die und Eigenschaften angegeben. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Eine LineGeometry, gezeichnet von (10,20) bis (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Das nächste Beispiel zeigt, wie <xref:System.Windows.Media.EllipseGeometry>eine erstellt und gerendert wird.  Die Beispiele <xref:System.Windows.Media.EllipseGeometry.Center%2A> legen <xref:System.Windows.Media.EllipseGeometry> fest, dass `50,50` der auf den Punkt gesetzt ist und `50`der x-Radius und der y-Radius auf gesetzt sind, wodurch ein Kreis mit einem Durchmesser von 100 erstellt wird.  Das Innere der Ellipse wird gemalt, indem der Fill-Eigenschaft des Path-Elements, in diesem Fall <xref:System.Windows.Media.Brushes.Gold%2A>, ein Wert zugewiesen wird. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
EllipseGeometry, gezeichnet bei (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Das folgende Beispiel zeigt, wie <xref:System.Windows.Media.RectangleGeometry>eine erstellt und gerendert wird.  Die Position und die Abmessungen des <xref:System.Windows.Rect> Rechtecks werden durch eine Struktur definiert. Die Position ist `50,50` und die Höhe und Breite sind beide `25`, wodurch ein Quadrat erstellt wird. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Eine RectangleGeometry, gezeichnet bei 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Media.EllipseGeometry> wie ein clip-Bereich für ein Bild verwendet wird.  Ein <xref:System.Windows.Controls.Image> Objekt wird <xref:System.Windows.FrameworkElement.Width%2A> mit einem von <xref:System.Windows.FrameworkElement.Height%2A> 200 und einem von 150 definiert.  Ein <xref:System.Windows.Media.EllipseGeometry> mit <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> einem Wert von <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 100, einem <xref:System.Windows.Media.EllipseGeometry.Center%2A> Wert von 75 und einem Wert <xref:System.Windows.UIElement.Clip%2A> von 100,75 wird auf die Eigenschaft des Bildes festgelegt.  Es wird nur der Teil des Bilds angezeigt, der innerhalb des Bereichs der Ellipse liegt. Die folgende Abbildung zeigt die Ausgabe des Beispiels.  
  
 ![Ein Bild mit und ohne Clipping](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Eine EllipseGeometry zum Beschneiden eines Image-Steuerelements  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>
## <a name="path-geometries"></a>Path-Geometrien  
 Die <xref:System.Windows.Media.PathGeometry> Klasse und ihr <xref:System.Windows.Media.StreamGeometry> leichtes Äquivalent, die Klasse, bieten die Möglichkeit, mehrere komplexe Figuren zu beschreiben, die aus Bögen, Kurven und Linien bestehen.  
  
 Im Zentrum von <xref:System.Windows.Media.PathGeometry> a befindet <xref:System.Windows.Media.PathFigure> sich eine Auflistung von Objekten, die <xref:System.Windows.Media.PathGeometry>so benannt sind, weil jede Figur eine diskrete Form im beschreibt. Jedes <xref:System.Windows.Media.PathFigure> besteht aus einem <xref:System.Windows.Media.PathSegment> oder mehreren Objekten, von denen jedes ein Segment der Figur beschreibt.  
  
 Es gibt viele Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|Beispiel|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|[Erstellen eines elliptischen Bogens](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bézierkurve zwischen zwei Punkten.|[Erstellen Sie eine kubische Bézierkurve](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|[Erstellen eines LineSegment in einer PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubischen Bézierkurven.|Siehe <xref:System.Windows.Media.PolyBezierSegment> Typseite.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|Siehe <xref:System.Windows.Media.PolyLineSegment> Typseite.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe quadratischer Bézierkurven.|Siehe <xref:System.Windows.Media.PolyQuadraticBezierSegment> seite.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bézierkurve.|[Erstellen Sie eine quadratische Bézierkurve](how-to-create-a-quadratic-bezier-curve.md).|  
  
 Die Segmente <xref:System.Windows.Media.PathFigure> innerhalb eines werden zu einer einzelnen geometrischen Form kombiniert, wobei der Endpunkt jedes Segments der Startpunkt des nächsten Segments ist. Die <xref:System.Windows.Media.PathFigure.StartPoint%2A> Eigenschaft <xref:System.Windows.Media.PathFigure> eines gibt den Punkt an, von dem das erste Segment gezeichnet wird. Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments. Beispielsweise kann eine vertikale `10,50` `10,150` Linie von zu <xref:System.Windows.Media.PathFigure.StartPoint%2A> definiert `10,50` werden, <xref:System.Windows.Media.LineSegment> indem <xref:System.Windows.Media.LineSegment.Point%2A> die Eigenschaft `10,150`auf und das Erstellen einer mit einer Eigenschaftseinstellung von festgelegt wird.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.PathGeometry> wird eine <xref:System.Windows.Media.PathFigure> einfache <xref:System.Windows.Media.LineSegment> Einzelverbindung mit <xref:System.Windows.Shapes.Path> einem erstellt und mit einem Element angezeigt. Das <xref:System.Windows.Media.PathFigure> Objekt <xref:System.Windows.Media.PathFigure.StartPoint%2A> ist auf `10,20` und <xref:System.Windows.Media.LineSegment> a mit einem `100,130`Endpunkt von definiert. Die folgende Abbildung <xref:System.Windows.Media.PathGeometry> zeigt die von diesem Beispiel erstellte Abbildung.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Eine PathGeometry, die ein einzelnes LineSegment enthält  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Es lohnt sich, dieses Beispiel <xref:System.Windows.Media.LineGeometry> mit dem vorherigen Beispiel zu vergleichen.  Die Syntax, <xref:System.Windows.Media.PathGeometry> die für a verwendet wird, ist <xref:System.Windows.Media.LineGeometry>viel ausführlicher als die <xref:System.Windows.Media.LineGeometry> für eine einfache , und es kann <xref:System.Windows.Media.PathGeometry> sinnvoller sein, die Klasse in diesem Fall zu verwenden, aber die ausführliche Syntax des ermöglicht extrem komplizierte und komplexe geometrische Bereiche.  
  
 Komplexere Geometrien können mithilfe einer <xref:System.Windows.Media.PathSegment> Kombination von Objekten erstellt werden.  
  
 Im nächsten Beispiel <xref:System.Windows.Media.BezierSegment>werden <xref:System.Windows.Media.LineSegment>eine <xref:System.Windows.Media.ArcSegment> , a und eine zum Erstellen einer Form verwendet. Das Beispiel erstellt zuerst eine kubische Bézierkurve, indem vier Punkte definiert werden: ein Startpunkt, der der Endpunkt des vorherigen Segments ist, ein Endpunkt (<xref:System.Windows.Media.BezierSegment.Point3%2A>), und zwei Kontrollpunkte (<xref:System.Windows.Media.BezierSegment.Point1%2A> und <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Die beiden Kontrollpunkte einer kubischen Bézierkurve verhalten sich wie Magnete und ziehen Teile dessen an, was sonst eine gerade Linie zu sich selbst wäre, und erzeugen eine Kurve. Der erste Kontrollpunkt , <xref:System.Windows.Media.BezierSegment.Point1%2A>, wirkt sich auf den Anfangsteil der Kurve aus; der zweite Kontrollpunkt , <xref:System.Windows.Media.BezierSegment.Point2%2A>wirkt sich auf den Endteil der Kurve aus.  
  
 Das Beispiel fügt <xref:System.Windows.Media.LineSegment>dann eine hinzu, die zwischen <xref:System.Windows.Media.BezierSegment> dem Endpunkt des vorherigen, der ihm voranliegt, zu dem Punkt gezeichnet wird, der durch seine <xref:System.Windows.Media.LineSegment> Eigenschaft angegeben wurde.  
  
 Das Beispiel fügt <xref:System.Windows.Media.ArcSegment>dann eine hinzu, die vom <xref:System.Windows.Media.LineSegment> Endpunkt des <xref:System.Windows.Media.ArcSegment.Point%2A> Vorderwerts zu dem Punkt gezeichnet wird, der durch seine Eigenschaft angegeben wird. Das Beispiel gibt auch den x- und y-Radius<xref:System.Windows.Media.ArcSegment.Size%2A>des<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>Bogens ( ), einen Drehwinkel ( ),<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>ein Flag an, das angibt, wie<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>groß der Winkel des resultierenden Bogens sein soll ( ), und einen Wert, der angibt, in welche Richtung der Bogen gezeichnet wird ( ). Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![Eine PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
Eine PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Noch komplexere Geometrien können mithilfe <xref:System.Windows.Media.PathFigure> mehrerer <xref:System.Windows.Media.PathGeometry>Objekte in einem erstellt werden.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.PathGeometry> wird <xref:System.Windows.Media.PathFigure> ein mit zwei <xref:System.Windows.Media.PathSegment> Objekten erstellt, von denen jedes mehrere Objekte enthält.  Die <xref:System.Windows.Media.PathFigure> aus dem obigen <xref:System.Windows.Media.PolyLineSegment> Beispiel <xref:System.Windows.Media.QuadraticBezierSegment> und a <xref:System.Windows.Media.PathFigure> mit a und a werden verwendet.  A <xref:System.Windows.Media.PolyLineSegment> wird mit einem Array <xref:System.Windows.Media.QuadraticBezierSegment> von Punkten und der mit einem Kontrollpunkt und einem Endpunkt definiert. Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![Eine PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Eine PathGeometry mit mehreren Figuren  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Wie <xref:System.Windows.Media.PathGeometry> die Klasse <xref:System.Windows.Media.StreamGeometry> definiert a eine komplexe geometrische Form, die Kurven, Bogen und Linien enthalten kann. Im <xref:System.Windows.Media.PathGeometry>Gegensatz zu einem <xref:System.Windows.Media.StreamGeometry> unterstützt der Inhalt einer datenbindung, Animation oder Änderung nicht. Verwenden <xref:System.Windows.Media.StreamGeometry> Sie eine, wenn Sie eine komplexe Geometrie beschreiben müssen, aber nicht den Aufwand für die Unterstützung von Datenbindung, Animation oder Änderung benötigen. Aufgrund ihrer Effizienz <xref:System.Windows.Media.StreamGeometry> ist die Klasse eine gute Wahl, um Adorner zu beschreiben.  
  
 Ein Beispiel finden Sie unter [Erstellen einer Form mithilfe von StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md).  
  
### <a name="path-markup-syntax"></a>Pfadmarkupsyntax  
 Die <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> und-Typen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] unterstützen eine Attributsyntax mithilfe einer speziellen Reihe von Verschiebungs- und Zeichnungsbefehlen. Weitere Informationen finden Sie unter [Pfadmarkupsyntax](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>
## <a name="composite-geometries"></a>Zusammengesetzte Geometrien  
 Zusammengesetzte Geometrieobjekte können <xref:System.Windows.Media.GeometryGroup>mit <xref:System.Windows.Media.CombinedGeometry>einer erstellt werden, <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.Geometry.Combine%2A>a , oder durch Aufrufen der statischen Methode .  
  
- Das <xref:System.Windows.Media.CombinedGeometry> Objekt <xref:System.Windows.Media.Geometry.Combine%2A> und die Methode führen einen booleschen Vorgang aus, um den durch zwei Geometrien definierten Bereich zu kombinieren. <xref:System.Windows.Media.Geometry>Objekte, die keinen Bereich haben, werden verworfen. Es <xref:System.Windows.Media.Geometry> können nur zwei Objekte kombiniert werden (obwohl es sich bei diesen beiden Geometrien auch um zusammengesetzte Geometrien handelt).  
  
- Die <xref:System.Windows.Media.GeometryGroup> Klasse erstellt eine <xref:System.Windows.Media.Geometry> Verschmelzung der darin enthaltenen Objekte, ohne ihren Bereich zu kombinieren. Eine beliebige <xref:System.Windows.Media.Geometry> Anzahl von Objekten <xref:System.Windows.Media.GeometryGroup>kann zu einer hinzugefügt werden. Ein Beispiel finden Sie unter [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md).  
  
 Da sie keinen Kombinationsvorgang <xref:System.Windows.Media.GeometryGroup> ausführen, bietet die <xref:System.Windows.Media.CombinedGeometry> Verwendung <xref:System.Windows.Media.Geometry.Combine%2A> von Objekten Leistungsvorteile gegenüber der Verwendung von Objekten oder der Methode.  
  
<a name="combindgeometriessection"></a>
## <a name="combined-geometries"></a>Kombinierte Geometrien  
 Im vorherigen Abschnitt <xref:System.Windows.Media.CombinedGeometry> wurde <xref:System.Windows.Media.Geometry.Combine%2A> das Objekt erwähnt, und die Methode kombiniert den Bereich, der durch die darin enthaltenen Geometrien definiert ist. Die <xref:System.Windows.Media.GeometryCombineMode> Enumeration gibt an, wie die Geometrien kombiniert werden. Die möglichen Werte <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> für <xref:System.Windows.Media.GeometryCombineMode.Union>die <xref:System.Windows.Media.GeometryCombineMode.Intersect> <xref:System.Windows.Media.GeometryCombineMode.Exclude>Eigenschaft <xref:System.Windows.Media.GeometryCombineMode.Xor>sind: , , , und .  
  
 Im folgenden Beispiel <xref:System.Windows.Media.CombinedGeometry> wird a mit einem Kombinationsmodus von Union definiert.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> die sind definiert als Kreise mit demselben Radius, jedoch mit Einem Umstand von 50 Zentrierten.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union-Kombinationsmodus](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 Im folgenden Beispiel <xref:System.Windows.Media.CombinedGeometry> wird a mit dem <xref:System.Windows.Media.GeometryCombineMode.Xor>Kombinationsmodus von definiert.  Beide <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> und <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> die sind definiert als Kreise mit demselben Radius, jedoch mit Einem Umstand von 50 Zentrierten.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des Xor-Kombinationsmodus](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Weitere Beispiele finden Sie unter [Erstellen einer zusammengesetzten Form](how-to-create-a-composite-shape.md) und unter [Erstellen von kombinierten Geometrien](how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Features von Freezable  
 Da sie von der <xref:System.Windows.Freezable> Klasse <xref:System.Windows.Media.Geometry> erbt, bietet <xref:System.Windows.Media.Geometry> die Klasse mehrere spezielle Features: Objekte können als [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt, schreibgeschützt gemacht werden, um die Leistung zu verbessern, geklont und threadsicher gemacht werden. Weitere Informationen zu den verschiedenen <xref:System.Windows.Freezable> Features, die von Objekten bereitgestellt werden, finden Sie in der [Übersicht über freisetzbare Objekte](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>
## <a name="other-geometry-features"></a>Andere Geometriefeatures  
 Die <xref:System.Windows.Media.Geometry> Klasse bietet auch nützliche Dienstprogrammmethoden, z. B. die folgenden:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>- Ruft den <xref:System.Windows.Media.Geometry>Bereich der ab.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>- Bestimmt, ob <xref:System.Windows.Media.Geometry>die Geometrie eine andere enthält.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>- Bestimmt, ob <xref:System.Windows.Media.Geometry> der Strich von a einen angegebenen Punkt enthält.  
  
 Eine <xref:System.Windows.Media.Geometry> vollständige Auflistung der Methoden finden Sie in der Klasse.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Pfadmarkupsyntax](path-markup-syntax.md)
- [How-to-Themen](geometries-how-to-topics.md)
- [Übersicht über Animationen](animation-overview.md)
- [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
