---
title: "&#220;bersicht &#252;ber die Geometrie | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen, Geometry"
  - "CombinedGeometry-Klasse"
  - "EllipseGeometry-Klasse"
  - "Geometry-Klassen"
  - "Grafiken, Geometry-Klassen"
  - "LineGeometry-Klasse"
  - "PathGeometry-Klasse"
  - "RectangleGeometry-Klasse"
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# &#220;bersicht &#252;ber die Geometrie
In dieser Übersicht wird beschrieben, wie die <xref:System.Windows.Media.Geometry>\-Klassen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verwendet werden, um Formen zu beschreiben.  In diesem Thema werden auch die Unterschiede zwischen <xref:System.Windows.Media.Geometry>\-Objekten und <xref:System.Windows.Shapes.Shape>\-Elementen verglichen.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## Was ist eine Geometrie?  
 Anhand der <xref:System.Windows.Media.Geometry>\-Klasse und der davon abgeleiteten Klassen, z. B. <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry> und <xref:System.Windows.Media.CombinedGeometry>, können Sie die Geometrie einer 2D\-Form beschreiben.  Diese geometrischen Beschreibungen haben viele Verwendungszwecke. Sie dienen beispielsweise zum Definieren einer am Bildschirm zu zeichnenden Form oder zum Definieren von Treffertest\- und Clipbereichen.  Sie können mithilfe einer Geometrie sogar einen Animationspfad definieren.  
  
 Bei <xref:System.Windows.Media.Geometry>\-Objekten kann es sich um einfache Formen wie Rechtecke und Kreise oder um aus einem oder mehreren geometrischen Objekten zusammengesetzte Formen handeln.  Mithilfe der <xref:System.Windows.Media.PathGeometry>\-Klasse und der <xref:System.Windows.Media.StreamGeometry>\-Klasse, mit denen Sie Bögen und Kurven beschreiben können, lassen sich komplexere Geometrien erstellen.  
  
 Da eine <xref:System.Windows.Media.Geometry> ein Typ von <xref:System.Windows.Freezable> ist, stellen <xref:System.Windows.Media.Geometry>\-Objekte mehrere spezielle Features bereit: Sie können als [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) deklariert, von mehreren Objekten gleichzeitig verwendet, zur Leistungsoptimierung als schreibgeschützt definiert, geklont sowie als threadsicher festgelegt werden.  Weitere Informationen über die verschiedenen von <xref:System.Windows.Freezable>\-Objekten bereitgestellten Features finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## Geometrien im Vergleich zuFormen  
 Die <xref:System.Windows.Media.Geometry>\-Klasse und die <xref:System.Windows.Shapes.Shape>\-Klasse sind scheinbar ähnlich, da sie beide 2D\-Formen beschreiben \(vergleichen Sie z. B. <xref:System.Windows.Media.EllipseGeometry> und <xref:System.Windows.Shapes.Ellipse>\). Sie weisen aber wichtige Unterschiede auf.  
  
 Zum einen erbt die <xref:System.Windows.Media.Geometry>\-Klasse von der <xref:System.Windows.Freezable>\-Klasse, wohingegen die <xref:System.Windows.Shapes.Shape>\-Klasse von <xref:System.Windows.FrameworkElement> erbt.  Da es sich bei <xref:System.Windows.Shapes.Shape>\-Objekten um Elemente handelt, können sie sich selbst rendern und zu Komponenten des Layoutsystems werden. Bei <xref:System.Windows.Media.Geometry>\-Objekten ist dies dagegen nicht möglich.  
  
 <xref:System.Windows.Shapes.Shape>\-Objekte lassen sich zwar leichter verwenden als <xref:System.Windows.Media.Geometry>\-Objekte, doch <xref:System.Windows.Media.Geometry>\-Objekte sind vielseitiger.  Mithilfe eines <xref:System.Windows.Shapes.Shape>\-Objekts werden 2D\-Grafiken gerendert. Ein <xref:System.Windows.Media.Geometry>\-Objekt hingegen kann beispielsweise verwendet werden, um den geometrischen Bereich für 2D\-Grafiken, einen Bereich für das Clipping oder einen Bereich für Treffertests zu definieren.  
  
### Die Form "Path"  
 Eine <xref:System.Windows.Shapes.Shape>, die <xref:System.Windows.Shapes.Path>\-Klasse, verwendet zur Beschreibung des Inhalts eine <xref:System.Windows.Media.Geometry>.  Wenn Sie die <xref:System.Windows.Shapes.Path.Data%2A>\-Eigenschaft von <xref:System.Windows.Shapes.Path> mit einer <xref:System.Windows.Media.Geometry> festlegen und die zugehörige <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft und <xref:System.Windows.Shapes.Shape.Stroke%2A>\-Eigenschaft festlegen, können Sie eine <xref:System.Windows.Media.Geometry> rendern.  
  
<a name="commonproperties"></a>   
## Allgemeine Eigenschaften, die eine Geometrie übernehmen  
 In den vorangegangenen Abschnitten wurde erwähnt, dass Geometry\-Objekte zu verschiedenen Zwecken mit anderen Objekten verwendet werden können, z. B. zum Zeichnen von Formen, zum Animieren und für das Clipping.  In der folgenden Tabelle sind mehrere Klassen mit Eigenschaften aufgeführt, die ein <xref:System.Windows.Media.Geometry>\-Objekt übernehmen.  
  
|Typ|Property|  
|---------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## Einfache geometrische Typen  
 Die Basisklasse für alle Geometrien ist die abstrakte <xref:System.Windows.Media.Geometry>\-Klasse.  Die von der <xref:System.Windows.Media.Geometry>\-Klasse abgeleiteten Klassen lassen sich grob in drei Kategorien unterteilen: einfache Geometrien, Pfadgeometrien und zusammengesetzte Geometrien.  
  
 Zu den Klassen der einfachen Geometrie zählen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> und <xref:System.Windows.Media.EllipseGeometry>. Sie werden zum Erstellen von grundlegenden geometrischen Formen wie Linien, Rechtecken und Kreisen verwendet.  
  
-   Eine <xref:System.Windows.Media.LineGeometry> wird durch die Festlegung des Anfangs\- und Endpunkts der Linie definiert.  
  
-   Eine <xref:System.Windows.Media.RectangleGeometry> wird mit einer <xref:System.Windows.Rect>\-Struktur definiert, die die relative Position sowie die Höhe und Breite festlegt.  Sie können ein abgerundetes Rechteck erstellen, indem Sie die <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>\-Eigenschaft und die <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>\-Eigenschaft festlegen.  
  
-   Eine <xref:System.Windows.Media.EllipseGeometry> wird durch einen Mittelpunkt, einen x\-Radius und einen y\-Radius definiert.  Die folgenden Beispiele veranschaulichen die Erstellung einfacher Geometrien für das Rendering und das Clipping.  
  
 Diese Formen sowie komplexere Formen können mit einer <xref:System.Windows.Media.PathGeometry> oder durch Kombinieren von geometrischen Objekten erstellt werden. Allerdings stellen diese Klassen einfachere Methoden zum Erstellen dieser grundlegenden geometrischen Formen bereit.  
  
 Im folgenden Beispiel wird das Erstellen und Rendern einer <xref:System.Windows.Media.LineGeometry> veranschaulicht.  Wie schon erwähnt, kann ein <xref:System.Windows.Media.Geometry>\-Objekt sich nicht selbst zeichnen. Daher wird in diesem Beispiel zum Rendern der Linie eine <xref:System.Windows.Shapes.Path>\-Form verwendet.  Da eine Linie keinen Bereich aufweist, hätte das Festlegen der <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft von <xref:System.Windows.Shapes.Path> keine Auswirkung. Stattdessen werden daher nur die <xref:System.Windows.Shapes.Shape.Stroke%2A>\-Eigenschaft und die <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>\-Eigenschaft festgelegt.  Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.  
  
 ![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
  
        LineGeometry, gezeichnet von \(10,20\) bis \(100,130\)  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 Im nächsten Beispiel wird das Erstellen und Rendern einer <xref:System.Windows.Media.EllipseGeometry> veranschaulicht.  In den Beispielen wird der <xref:System.Windows.Media.EllipseGeometry.Center%2A> von <xref:System.Windows.Media.EllipseGeometry> auf den Punkt `50,50` festgelegt. Außerdem werden der x\-Radius und der y\-Radius auf `50` festgelegt, wodurch ein Kreis mit einem Durchmesser von 100 erstellt wird.  Das Innere der Ellipse wird gezeichnet, indem der Fill\-Eigenschaft des Path\-Elements ein Wert zugewiesen wird, in diesem Fall <xref:System.Windows.Media.Brushes.Gold%2A>.  Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.  
  
 ![Eine EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.png "graphicsmm\_ellipse")  
  
        EllipseGeometry, gezeichnet bei \(50,50\)  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 Im folgenden Beispiel wird das Erstellen und Rendern einer <xref:System.Windows.Media.RectangleGeometry> veranschaulicht.  Die Position und die Abmessungen des Rechtecks werden durch eine <xref:System.Windows.Rect>\-Struktur definiert.  Die Position lautet `50,50`. Die Höhe und die Breite betragen jeweils `25`, wodurch ein Quadrat erstellt wird.  Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.  
  
 ![Eine RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
  
        RectangleGeometry, gezeichnet bei 50,50  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 Im folgenden Beispiel wird die Verwendung einer <xref:System.Windows.Media.EllipseGeometry> als Clipbereich für ein Bild veranschaulicht.  Ein <xref:System.Windows.Controls.Image>\-Objekt wird mit einer <xref:System.Windows.FrameworkElement.Width%2A> von 200 und einer <xref:System.Windows.FrameworkElement.Height%2A> von 150 erstellt.  Eine <xref:System.Windows.Media.EllipseGeometry> mit einem <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A>\-Wert von 100, einem <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A>\-Wert von 75 und einem <xref:System.Windows.Media.EllipseGeometry.Center%2A>\-Wert von 100,75 wird auf die <xref:System.Windows.UIElement.Clip%2A>\-Eigenschaft des Bilds festgelegt.  Es wird nur der Teil des Bilds angezeigt, der innerhalb des Bereichs der Ellipse liegt.  Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.  
  
 ![Ein Bild mit und ohne Clipping](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm\_clipexample")  
  
        EllipseGeometry zum Beschneiden eines Image\-Steuerelements  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## Pfadgeometrien  
 Die <xref:System.Windows.Media.PathGeometry>\-Klasse und deren Lightweight\-Entsprechung, die <xref:System.Windows.Media.StreamGeometry>\-Klasse, ermöglichen die Beschreibung mehrerer komplexer Figuren, die aus Bögen, Kurven und Linien zusammengesetzt sind.  
  
 Eine <xref:System.Windows.Media.PathGeometry> besteht im Wesentlichen aus einer Auflistung von <xref:System.Windows.Media.PathFigure>\-Objekten. Diese Objekte werden so genannt, da jede Figur eine eigenständige Form in der <xref:System.Windows.Media.PathGeometry> beschreibt.  Jede <xref:System.Windows.Media.PathFigure> besteht aus mindestens einem <xref:System.Windows.Media.PathSegment>\-Objekt, das einen Abschnitt der Figur beschreibt.  
  
 Es gibt viele verschiedene Arten von Segmenten.  
  
|Segmenttyp|Beschreibung|Beispiel|  
|----------------|------------------|--------------|  
|<xref:System.Windows.Media.ArcSegment>|Erstellt einen elliptischen Bogen zwischen zwei Punkten.|[Erstellen eines elliptischen Bogens](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Erstellt eine kubische Bezierkurve zwischen zwei Punkten.|[Erstellen einer kubischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Erstellt eine Linie zwischen zwei Punkten.|[Erstellen eines LineSegment in einer PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Erstellt eine Reihe von kubischen Bezierkurven.|Siehe die <xref:System.Windows.Media.PolyBezierSegment>\-Typseite.|  
|<xref:System.Windows.Media.PolyLineSegment>|Erstellt eine Reihe von Zeilen.|Siehe die <xref:System.Windows.Media.PolyLineSegment>\-Typseite.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Erstellt eine Reihe von quadratischen Bezierkurven.|Siehe die <xref:System.Windows.Media.PolyQuadraticBezierSegment>\-Seite.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Erstellt eine quadratische Bezierkurve.|[Erstellen einer quadratischen Bézierkurve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 Die Segmente innerhalb einer <xref:System.Windows.Media.PathFigure> werden zu einer einzelnen geometrischen Form zusammengesetzt. Dabei bildet der Endpunkt jedes Segments den Startpunkt des nächsten Segments.  Die <xref:System.Windows.Media.PathFigure.StartPoint%2A>\-Eigenschaft einer <xref:System.Windows.Media.PathFigure> gibt den Punkt an, an dem die Zeichnung des ersten Segments beginnt.  Jedes nachfolgende Segment beginnt am Endpunkt des vorherigen Segments.  Beispielsweise kann eine vertikale Linie von `10,50` nach `10,150` definiert werden, indem die <xref:System.Windows.Media.PathFigure.StartPoint%2A>\-Eigenschaft auf `10,50` festgelegt und ein <xref:System.Windows.Media.LineSegment> erstellt wird, dessen <xref:System.Windows.Media.LineSegment.Point%2A>\-Eigenschaft auf `10,150` festgelegt ist.  
  
 Im folgenden Beispiel wird eine einfache <xref:System.Windows.Media.PathGeometry> aus einer einzelnen <xref:System.Windows.Media.PathFigure> mit einem <xref:System.Windows.Media.LineSegment> erstellt und mithilfe eines <xref:System.Windows.Shapes.Path>\-Elements angezeigt.  Der <xref:System.Windows.Media.PathFigure.StartPoint%2A> des <xref:System.Windows.Media.PathFigure>\-Objekts ist auf `10,20` festgelegt. Darüber hinaus wurde ein <xref:System.Windows.Media.LineSegment> mit dem Endpunkt `100,130` definiert.  Die folgende Abbildung zeigt die durch dieses Beispiel erstellte <xref:System.Windows.Media.PathGeometry>.  
  
 ![Eine LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
PathGeometry, die ein einzelnes LineSegment enthält  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Ein Vergleich dieses Beispiels mit dem vorangehenden <xref:System.Windows.Media.LineGeometry>\-Beispiel lohnt sich.  Die für eine <xref:System.Windows.Media.PathGeometry> verwendete Syntax ist wesentlich ausführlicher als die Syntax für eine einfache <xref:System.Windows.Media.LineGeometry>, und es ist möglicherweise sinnvoller, in diesem Fall die <xref:System.Windows.Media.LineGeometry>\-Klasse zu verwenden. Die ausführliche Syntax von <xref:System.Windows.Media.PathGeometry> ermöglicht jedoch äußerst komplizierte und komplexe geometrische Bereiche.  
  
 Komplexere Geometrien können mithilfe einer Kombination von <xref:System.Windows.Media.PathSegment>\-Objekten erstellt werden.  
  
 Im nächsten Beispiel werden zum Erstellen einer Form ein <xref:System.Windows.Media.BezierSegment>, ein <xref:System.Windows.Media.LineSegment> und ein <xref:System.Windows.Media.ArcSegment> verwendet.  Im Beispiel wird zunächst eine kubische Bézierkurve erstellt, indem vier Punkte definiert werden: ein Anfangspunkt, der den Endpunkt des vorherigen Segments bildet, ein Endpunkt \(<xref:System.Windows.Media.BezierSegment.Point3%2A>\) sowie zwei Kontrollpunkte \(<xref:System.Windows.Media.BezierSegment.Point1%2A> und <xref:System.Windows.Media.BezierSegment.Point2%2A>\).  Das Verhalten der beiden Kontrollpunkte einer kubischen Bézierkurve ist mit Magneten vergleichbar, die Abschnitte einer Geraden anziehen, sodass sich eine Krümmung ergibt.  Der erste Kontrollpunkt <xref:System.Windows.Media.BezierSegment.Point1%2A> wirkt sich auf den Anfangsabschnitt der Kurve aus, und der zweite Kontrollpunkt <xref:System.Windows.Media.BezierSegment.Point2%2A> wirkt sich auf den Endabschnitt der Kurve aus.  
  
 Anschließend wird im Beispiel ein <xref:System.Windows.Media.LineSegment> hinzugefügt, das zwischen dem Endpunkt für das vorangehende <xref:System.Windows.Media.BezierSegment> und dem von der zugehörigen <xref:System.Windows.Media.LineSegment>\-Eigenschaft festgelegten Punkt gezeichnet wird.  
  
 Danach wird ein <xref:System.Windows.Media.ArcSegment> hinzugefügt, das vom Endpunkt für das vorangehende <xref:System.Windows.Media.LineSegment> bis zu dem von der zugehörigen <xref:System.Windows.Media.ArcSegment.Point%2A>\-Eigenschaft festgelegten Punkt gezeichnet wird.  Darüber hinaus werden im Beispiel der x\- und y\-Radius des Bogens \(<xref:System.Windows.Media.ArcSegment.Size%2A>\), ein Drehwinkel \(<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>\), ein Kennzeichen zur Angabe der erforderlichen Größe des resultierenden Bogens \(<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>\) und ein Wert festgelegt, der angibt, in welche Richtung der Bogen gezeichnet wird \(<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>\).  Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.png "graphicsmm\_path2")  
  
        PathGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Durch die Verwendung mehrerer <xref:System.Windows.Media.PathFigure>\-Objekte in einer <xref:System.Windows.Media.PathGeometry> können noch komplexere Geometrien erstellt werden.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.PathGeometry> mit zwei <xref:System.Windows.Media.PathFigure>\-Objekten erstellt, von denen jedes mehrere <xref:System.Windows.Media.PathSegment>\-Objekte enthält.  Dabei werden die <xref:System.Windows.Media.PathFigure> aus dem obigen Beispiel und eine <xref:System.Windows.Media.PathFigure> mit einem <xref:System.Windows.Media.PolyLineSegment> und einem <xref:System.Windows.Media.QuadraticBezierSegment> verwendet.  Ein <xref:System.Windows.Media.PolyLineSegment> wird mit einem Array von Punkten definiert, und das <xref:System.Windows.Media.QuadraticBezierSegment> wird mit einem Kontrollpunkt und einem Endpunkt definiert.  Die folgende Abbildung zeigt die durch dieses Beispiel erstellte Form.  
  
 ![Eine PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.png "graphicsmm\_path")  
  
        PathGeometry mit mehreren Figuren  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### StreamGeometry  
 Wie die <xref:System.Windows.Media.PathGeometry>\-Klasse definiert auch <xref:System.Windows.Media.StreamGeometry> eine komplexe geometrische Form, die Kurven, Bögen und Linien enthalten kann.  Im Gegensatz zu einer <xref:System.Windows.Media.PathGeometry> bietet der Inhalt einer <xref:System.Windows.Media.StreamGeometry> keine Unterstützung für eine Datenbindung, Animation oder Änderung.  Verwenden Sie <xref:System.Windows.Media.StreamGeometry>, wenn Sie eine komplexe Geometrie beschreiben müssen, aber ohne den Verwaltungsaufwand zur Unterstützung von Datenbindung, Animation oder Änderungen auskommen möchten.  Aufgrund ihrer Effizienz ist die <xref:System.Windows.Media.StreamGeometry>\-Klasse eine gute Wahl zum Beschreiben von Adornern.  
  
 Ein Beispiel finden Sie unter [Erstellen eines Shapes mit einer StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
### Pfadmarkupsyntax  
 Der <xref:System.Windows.Media.PathGeometry>\-Typ und der <xref:System.Windows.Media.StreamGeometry>\-Typ unterstützen eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Attributsyntax. Hierzu wird eine spezielle Kombination von Befehlen zum Verschieben und Zeichnen verwendet.  Weitere Informationen finden Sie unter [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## Zusammengesetzte Geometrien  
 Zusammengesetzte geometrische Objekte können durch die Verwendung von <xref:System.Windows.Media.GeometryGroup>, <xref:System.Windows.Media.CombinedGeometry> oder den Aufruf der statischen <xref:System.Windows.Media.Geometry>\-Methode <xref:System.Windows.Media.Geometry.Combine%2A> erstellt werden.  
  
-   Das <xref:System.Windows.Media.CombinedGeometry>\-Objekt und die <xref:System.Windows.Media.Geometry.Combine%2A>\-Methode führen zum Kombinieren des von den beiden Geometrien definierten Bereichs eine boolesche Operation durch.  <xref:System.Windows.Media.Geometry>\-Objekte ohne Bereich werden verworfen.  Nur zwei <xref:System.Windows.Media.Geometry>\-Objekte können kombiniert werden \(bei diesen beiden Geometrien kann es sich aber auch um zusammengesetzte Geometrien handeln\).  
  
-   Die <xref:System.Windows.Media.GeometryGroup>\-Klasse erstellt einen Zusammenschluss der enthaltenen <xref:System.Windows.Media.Geometry>\-Objekte, ohne dass ihr Bereich kombiniert wird.  Einer <xref:System.Windows.Media.GeometryGroup> kann eine beliebige Anzahl von <xref:System.Windows.Media.Geometry>\-Objekten hinzugefügt werden.  Ein Beispiel finden Sie unter [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md).  
  
 Da bei <xref:System.Windows.Media.GeometryGroup>\-Objekten keine Kombination stattfindet, lässt sich durch ihre Verwendung eine bessere Leistung erzielen als bei der Verwendung von <xref:System.Windows.Media.CombinedGeometry>\-Objekten oder der <xref:System.Windows.Media.Geometry.Combine%2A>\-Methode.  
  
<a name="combindgeometriessection"></a>   
## Kombinierte Geometrien  
 Im vorherigen Abschnitt wurde erwähnt, dass das <xref:System.Windows.Media.CombinedGeometry>\-Objekt und die <xref:System.Windows.Media.Geometry.Combine%2A>\-Methode den durch die enthaltenen Geometrien definierten Bereich kombinieren.  Die <xref:System.Windows.Media.GeometryCombineMode>\-Enumeration legt fest, wie die Geometrien kombiniert werden.  Die möglichen Werte für die <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A>\-Eigenschaft sind <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode> und <xref:System.Windows.Media.GeometryCombineMode>.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.CombinedGeometry> definiert, wobei der Kombinationsmodus auf Union festgelegt ist.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius definiert, deren Mittelpunkte jedoch um den Wert 50 versetzt sind.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Ergebnisse des Union&#45;Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.CombinedGeometry> definiert, wobei der Kombinationsmodus auf <xref:System.Windows.Media.GeometryCombineMode> festgelegt ist.  Sowohl <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> als auch <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> werden als Kreise mit identischem Radius definiert, deren Mittelpunkte jedoch um den Wert 50 versetzt sind.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Ergebnisse des Xor&#45;Kombinationsmodus](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
  
 Weitere Beispiele finden Sie unter [Erstellen einer zusammengesetzten Form](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) und unter [Erstellen von kombinierten Geometrien](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## Features von Freezable  
 Da die <xref:System.Windows.Media.Geometry>\-Klasse von der <xref:System.Windows.Freezable>\-Klasse erbt, bietet sie mehrere spezielle Features: <xref:System.Windows.Media.Geometry>\-Objekte können als [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) deklariert, von mehreren Objekten gleichzeitig verwendet, zur Leistungsoptimierung als schreibgeschützt definiert, geklont sowie als threadsicher festgelegt werden.  Weitere Informationen über die verschiedenen von <xref:System.Windows.Freezable>\-Objekten bereitgestellten Features finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## Andere Geometriefeatures  
 Die <xref:System.Windows.Media.Geometry>\-Klasse stellt auch nützliche Dienstprogrammmethoden bereit. Hierzu zählen beispielsweise:  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A> – Ruft den Bereich von <xref:System.Windows.Media.Geometry> ab.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A> – Bestimmt, ob die Geometrie eine andere <xref:System.Windows.Media.Geometry> enthält.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A> – Bestimmt, ob der Strich einer <xref:System.Windows.Media.Geometry> einen angegebenen Punkt enthält.  
  
 In der <xref:System.Windows.Media.Geometry>\-Klasse finden Sie eine vollständige Liste der zugehörigen Methoden.  
  
## Siehe auch  
 <xref:System.Windows.Media.Geometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Pfadmarkupsyntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)