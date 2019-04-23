---
title: Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 1ce0e661d88b7c4d5719c4f11ef0912c5bacb587
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189131"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF
Dieses Thema bietet eine Übersicht über das Zeichnen mit <xref:System.Windows.Shapes.Shape> Objekte. Ein <xref:System.Windows.Shapes.Shape> ist eine Art von <xref:System.Windows.UIElement> , mit der Sie eine Form auf dem Bildschirm zu zeichnen. Da sie UI-Elemente sind <xref:System.Windows.Shapes.Shape> Objekte können verwendet werden, in <xref:System.Windows.Controls.Panel> Elemente und die meisten Steuerelemente.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste. Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> Objekte sind einfach zu verwenden und bieten viele nützliche Features, z.B. Layout und Teilnahme an der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ereignissystem.  

<a name="shapes"></a>   
## <a name="shape-objects"></a>Shape-Objekte  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Reihe von sofort zu verwendende <xref:System.Windows.Shapes.Shape> Objekte.  Alle Shape-Objekte erben von der <xref:System.Windows.Shapes.Shape> Klasse. Verfügbare Shape-Objekte sind <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape> Objekte nutzen die folgenden allgemeinen Eigenschaften.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Form gezeichnet wird.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Stärke der Form an.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form gezeichnet wird.  
  
-   Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, gemessen in geräteunabhängigen Pixeln.  
  
 Da sie von abgeleitet <xref:System.Windows.UIElement>, Shape-Objekte in Bereichen und den meisten Steuerelementen verwendet werden können. Die <xref:System.Windows.Controls.Canvas> Bereich ist eine besonders gute Wahl für das Erstellen von komplexen Zeichnungen, da es die absolute Positionierung der untergeordneten Objekte unterstützt.  
  
 Die <xref:System.Windows.Shapes.Line> -Klasse können Sie eine Linie zwischen zwei Punkten zu zeichnen. Das folgende Beispiel zeigt verschiedene Arten, wie Zeilenkoordinaten und Stricheigenschaften angegeben werden können.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Line>.  
  
 ![Liniendarstellung](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Obwohl die <xref:System.Windows.Shapes.Line> Klasse bietet einen <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft, diese Einstellung hat keine Auswirkungen, da eine <xref:System.Windows.Shapes.Line> ist kein Bereich.  
  
 Eine weitere allgemeine Form ist die <xref:System.Windows.Shapes.Ellipse>.  Erstellen Sie eine <xref:System.Windows.Shapes.Ellipse> durch die Definition der Form <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Um einen Kreis zu zeichnen, geben Sie eine <xref:System.Windows.Shapes.Ellipse> , deren <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte gleich sind.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 Die folgende Abbildung zeigt ein Beispiel eines gerenderten <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Ellipsendarstellung](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a>Verwenden von Pfaden und Geometrien  
 Die <xref:System.Windows.Shapes.Path> Klasse ermöglicht Ihnen, Kurven und komplexe Formen zu zeichnen. Diese Kurven und Formen werden mithilfe von beschrieben <xref:System.Windows.Media.Geometry> Objekte. Verwenden einer <xref:System.Windows.Shapes.Path>, erstellen Sie eine <xref:System.Windows.Media.Geometry> und verwenden sie zum Festlegen der <xref:System.Windows.Shapes.Path> des Objekts <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft.  
  
 Es gibt eine Vielzahl von <xref:System.Windows.Media.Geometry> Objekte zur Auswahl. Die <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, und <xref:System.Windows.Media.EllipseGeometry> Klassen beschreiben relativ einfache Formen. Erstellen Sie eine komplexere Formen oder Kurven zu erstellen, verwenden Sie eine <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry und PathSegments  
 <xref:System.Windows.Media.PathGeometry> -Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar. Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jedes einen verknüpften Abschnitt der Figur oder Form darstellt. Segmenttypen beinhalten Folgendes: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, und <xref:System.Windows.Media.ArcSegment>.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Shapes.Path> zum Zeichnen einer quadratischen Bezierkurve verwendet wird.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Die folgende Abbildung zeigt die gerenderte Form.  
  
 ![Pfaddarstellung](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> und die andere <xref:System.Windows.Media.Geometry> finden Sie unter den [Übersicht über die Geometrie](geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a>Abgekürzte Syntax in XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können auch eine besondere abgekürzte Syntax verwenden, um zu beschreiben eine <xref:System.Windows.Shapes.Path>. Im folgenden Beispiel wird abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Die folgende Abbildung zeigt einen gerenderten <xref:System.Windows.Shapes.Path>.  
  
 ![Pfaddarstellung](./media/shape-ovw-path.PNG "Shape_ovw_path")  
  
 Die <xref:System.Windows.Shapes.Path.Data%2A> -Attributzeichenfolge beginnt mit dem "Moveto"-Befehl, angegeben durch M, der einen Startpunkt für den Pfad im Koordinatensystem der richtet die <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Shapes.Path> -Datenparameter unterscheiden Groß-/Kleinschreibung beachtet. Der Großbuchstabe M gibt eine absolute Position für den neuen aktuellen Punkt. Ein kleingeschriebenes m würde relative Koordinaten angeben. Das erste Segment ist ein kubische Bezier-Kurve ab (100,200) und endet (400,175), Punkte (100,25) und (400,350) steuern gezeichneten mit den beiden. Dieses Segment wird angegeben, mit dem Befehl "C" in der <xref:System.Windows.Shapes.Path.Data%2A> Attribut-Zeichenfolge. Ein großes C gibt erneut einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.  
  
 Das zweite Segment beginnt mit einem absoluten horizontalen „Lineto“-Befehl H, der eine Linie vom vorherigen untergeordneten Endpunkt (400,175) zu einem neuen Endpunkt (280,175) zeichnet. Da es sich um einen horizontalen "Lineto"-Befehl handelt, wird der angegebene Wert ist eine *x*-koordinieren.  
  
 Die vollständige Pfadsyntax finden Sie unter den <xref:System.Windows.Shapes.Path.Data%2A> Verweis und [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a>Zeichnen von Formen  
 <xref:System.Windows.Media.Brush> Objekte werden verwendet, um das Zeichnen einer Form <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.Fill%2A>. Im folgenden Beispiel wird der Strich und Füllung des ein <xref:System.Windows.Shapes.Ellipse> angegeben sind. Beachten Sie, dass Pinseleigenschaften entweder ein Schlüsselwort oder einen hexadezimalen Farbwert werden können. Weitere Informationen über verfügbare Farbschlüsselwörter finden Sie unter Eigenschaften der <xref:System.Windows.Media.Colors> -Klasse in der <xref:System.Windows.Media> Namespace.  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Eine Ellipse](./media/shape-ovw-ellipsefill.PNG "Shape_ovw_ellipsefill")  
  
 Alternativ können Sie Eigenschaftenelement-Syntax verwenden, erstellen Sie explizit eine <xref:System.Windows.Media.SolidColorBrush> Objekt, das die Form mit einer Volltonfarbe zu zeichnen.  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 Die folgende Abbildung zeigt die gerenderte Form.  
  
 ![SolidColorBrush-Darstellung](./media/shape-ovw-solidcolorbrush.PNG "Shape_ovw_solidcolorbrush")  
  
 Sie können die Kontur oder Fläche einer Form auch mit Farbverläufen, Bildern, Mustern und mehr zeichnen. Weitere Informationen finden Sie unter den [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a>Gestreckte Formen  
 Die <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle> Klassen, die alle verfügen über eine <xref:System.Windows.Shapes.Shape.Stretch%2A> Eigenschaft. Diese Eigenschaft bestimmt, wie eine <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts (das zu zeichnende Form) ist Füllbereich der <xref:System.Windows.Shapes.Shape> Layoutbereich des Objekts. Ein <xref:System.Windows.Shapes.Shape> des Objekts ist die Menge des Speicherplatzes der <xref:System.Windows.Shapes.Shape> zugeordnet durch das Layoutsystem aufgrund einer expliziten <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Einstellung oder aufgrund von dessen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Einstellungen. Weitere Informationen zu Layouts in Windows Presentation Foundation, finden Sie unter [Layout](../advanced/layout.md) Übersicht.  
  
 Die Stretch-Eigenschaft nimmt einen der folgenden Werte an:  
  
-   <xref:System.Windows.Media.Stretch.None>: Die <xref:System.Windows.Shapes.Shape> Inhalt des Objekts werden nicht gestreckt.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: Die <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, um den Layoutbereich auszufüllen.  Das Seitenverhältnis wird nicht beibehalten.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: Die <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, so weit wie möglich ist, um den Layoutbereich auszufüllen und gleichzeitig die ursprünglichen Seitenverhältnisse beizubehalten.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: Die <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, um den Layoutbereich vollständig auszufüllen, während gleichzeitig die ursprünglichen Seitenverhältnisse beizubehalten.  
  
 Beachten Sie, dass bei einem <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, die <xref:System.Windows.Shapes.Shape> -Objekts nach dem Strecken gezeichnet wird.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Shapes.Polygon> , die zum Zeichnen eines sehr kleinen Dreiecks von (0,0) bis (0,1) bis (1,1) verwendet wird. Die <xref:System.Windows.Shapes.Polygon> des Objekts <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf 100 festgelegt sind und die Stretch-Eigenschaft auf Fill festgelegt ist. Daher die <xref:System.Windows.Shapes.Polygon> Inhalt des Objekts (das Dreieck) werden gestreckt, um den größeren Bereich auszufüllen.  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a>Transformieren von Formen  
 Die <xref:System.Windows.Media.Transform> -Klasse bietet die Möglichkeit zur Transformation von Formen in einem zweidimensionalen Raum.  Die verschiedenen Typen von Transformation beinhalten Drehung (<xref:System.Windows.Media.RotateTransform>), Skalierung (<xref:System.Windows.Media.ScaleTransform>), Neigung (<xref:System.Windows.Media.SkewTransform>), und die Übersetzung (<xref:System.Windows.Media.TranslateTransform>).  
  
 Eine allgemeine Transformation einer Form ist die Drehung.  Um eine Form zu drehen, erstellen Sie eine <xref:System.Windows.Media.RotateTransform> , und geben Sie die <xref:System.Windows.Media.RotateTransform.Angle%2A>. Ein <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 dreht das Element um 45 Grad im Uhrzeigersinn; ein Winkel von 90 Dreht das Element um 90 Grad im Uhrzeigersinn gedreht; und so weiter. Legen Sie die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften sollten Sie den Punkt zu steuern, den das Element gedreht wird. Diese Eigenschaftswerte werden im Koordinatenraum des transformierten Elements ausgedrückt. <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> haben Standardwerte von 0 (null). Wenden Sie schließlich die <xref:System.Windows.Media.RotateTransform> auf das Element. Wenn Sie nicht, dass die Transformation auf das Layout auswirken möchten, legen Sie der Form des <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Media.RotateTransform> wird verwendet, um eine Form um 45 Grad zur oberen linken Ecke (0,0) drehen.  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Im nächsten Beispiel eine andere Form um 45 Grad gedreht wird, aber dieses Mal wird sie über den Punkt (25,50) gedreht.  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 In der folgenden Abbildung werden die Ergebnisse der Anwendung der zwei Transformationen dargestellt.  
  
 ![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape-Objekt angewendet. Verwenden Sie zum Anwenden mehrerer Transformationen auf eine Form (oder andere Elemente der Benutzeroberfläche) eine <xref:System.Windows.Media.TransformGroup>.  
  
## <a name="see-also"></a>Siehe auch

- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Geometrien](geometry-overview.md)
- [Exemplarische Vorgehensweise: Walkthrough: My first WPF desktop application (Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung)](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Übersicht über Animationen](animation-overview.md)
