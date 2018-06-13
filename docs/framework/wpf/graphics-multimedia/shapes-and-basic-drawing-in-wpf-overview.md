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
ms.openlocfilehash: adbf982da25ff445d277b7c1b5911217d9825c02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566310"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF
Dieses Thema enthält eine Übersicht über Zeichnen mit <xref:System.Windows.Shapes.Shape> Objekte. Ein <xref:System.Windows.Shapes.Shape> ist eine Art von <xref:System.Windows.UIElement> mit der Sie eine Form auf dem Bildschirm gezeichnet werden soll. Da es sich um Benutzeroberflächenelemente sind <xref:System.Windows.Shapes.Shape> Objekte können verwendet werden, in <xref:System.Windows.Controls.Panel> Elemente und die meisten Steuerelemente.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste. Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> Objekte sind einfach zu verwenden und bieten viele nützliche Features, z. B. Layout und die Teilnahme an der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ereignissystem.  
  
  
<a name="shapes"></a>   
## <a name="shape-objects"></a>Shape-Objekte  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Reihe von Ready to Use <xref:System.Windows.Shapes.Shape> Objekte.  Alle Formobjekte, die von erben die <xref:System.Windows.Shapes.Shape> Klasse. Form "verfügbar" Objekten zählen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape> Objekte werden die folgenden allgemeinen Eigenschaften gemeinsam.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Rand der Form gezeichnet wird.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Stärke der Kontur der Form.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form gezeichnet wird.  
  
-   Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, gemessen in geräteunabhängigen Pixeln.  
  
 Da sie ableiten <xref:System.Windows.UIElement>, Shape-Objekte können in Bereichen und den meisten Steuerelementen verwendet werden. Die <xref:System.Windows.Controls.Canvas> Bereich ist besonders gut für komplexe Zeichnungen erstellen, da es unterstützt die absolute Positionierung seine untergeordneten Objekte.  
  
 Die <xref:System.Windows.Shapes.Line> -Klasse ermöglicht es Ihnen, eine Linie zwischen zwei Punkten zu zeichnen. Das folgende Beispiel zeigt verschiedene Arten, wie Zeilenkoordinaten und Stricheigenschaften angegeben werden können.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Die folgende Abbildung zeigt den gerenderten <xref:System.Windows.Shapes.Line>.  
  
 ![Liniendarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Obwohl die <xref:System.Windows.Shapes.Line> Klasse bietet einen <xref:System.Windows.Shapes.Shape.Fill%2A> Festlegen dieser Eigenschaft hat keine Auswirkung, da eine <xref:System.Windows.Shapes.Line> ist kein Bereich.  
  
 Weitere allgemeine Form "ist die <xref:System.Windows.Shapes.Ellipse>.  Erstellen einer <xref:System.Windows.Shapes.Ellipse> durch die Definition der Form <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften. Zeichnen eines Kreises angeben einer <xref:System.Windows.Shapes.Ellipse> , deren <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte gleich sind.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 Die folgende Abbildung zeigt ein Beispiel eines gerenderten <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Ellipsendarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a>Verwenden von Pfaden und Geometrien  
 Die <xref:System.Windows.Shapes.Path> -Klasse ermöglicht es Ihnen, Kurven und komplexe Formen zu zeichnen. Diese Kurven und Formen werden mithilfe von beschrieben <xref:System.Windows.Media.Geometry> Objekte. Verwenden eine <xref:System.Windows.Shapes.Path>, Sie erstellen eine <xref:System.Windows.Media.Geometry> und Verwendung zur Festlegung der <xref:System.Windows.Shapes.Path> des Objekts <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft.  
  
 Es gibt eine Vielzahl von <xref:System.Windows.Media.Geometry> Objekte zur Auswahl. Die <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, und <xref:System.Windows.Media.EllipseGeometry> Klassen beschreiben relativ einfache Formen. Verwenden Sie zum Erstellen komplexer Formen oder Kurven zu erstellen, eine <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry und PathSegments  
 <xref:System.Windows.Media.PathGeometry> Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> einen anderen "Abbildung" oder eine Form darstellt. Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, die jeweils einen verknüpften Bereich der Abbildung oder Form darstellen. Segmenttypen umfassen Folgendes: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, und <xref:System.Windows.Media.ArcSegment>.  
  
 Im folgenden Beispiel ein <xref:System.Windows.Shapes.Path> wird verwendet, um eine quadratische Bézier-Kurve zu zeichnen.  
  
 [!code-xaml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Die folgende Abbildung zeigt die gerenderte Form.  
  
 ![Pfaddarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> und die andere <xref:System.Windows.Media.Geometry> Klassen, finden Sie unter der [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a>Abgekürzte Syntax in XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können auch eine besondere abgekürzte Syntax zum Beschreiben einer <xref:System.Windows.Shapes.Path>. Im folgenden Beispiel wird abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Die folgende Abbildung zeigt einen gerenderten <xref:System.Windows.Shapes.Path>.  
  
 ![Pfaddarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.PNG "Shape_ovw_path")  
  
 Die <xref:System.Windows.Shapes.Path.Data%2A> Attributzeichenfolge beginnt mit dem Befehl "Moveto" angegeben durch M, die einen Startpunkt für den Pfad in das Koordinatensystem des festlegt der <xref:System.Windows.Controls.Canvas>. <xref:System.Windows.Shapes.Path> Datenparametern Groß-/Kleinschreibung beachtet. Großbuchstaben M gibt eine absolute Position für den neuen aktuellen Punkt an. Ein kleingeschriebenes m würde relative Koordinaten angeben. Das erste Segment ist eine kubische Bézier-Kurve, beginnend am (100,200) und endet (400,175), Punkte (100,25) und (400,350) steuern gezeichneten mit den beiden. Dieses Segment wird angegeben, mit dem Befehl "C" in der <xref:System.Windows.Shapes.Path.Data%2A> -Attribut Zeichenfolge. Ein großes C gibt erneut einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.  
  
 Das zweite Segment beginnt mit einem absoluten horizontalen „Lineto“-Befehl H, der eine Linie vom vorherigen untergeordneten Endpunkt (400,175) zu einem neuen Endpunkt (280,175) zeichnet. Da es sich um eine horizontale "Linie" Befehl handelt, wird der angegebene Wert ist ein *x*-koordinieren.  
  
 Der vollständige Pfad-Syntax finden Sie unter der <xref:System.Windows.Shapes.Path.Data%2A> Verweis und [erstellen Sie eine Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a>Zeichnen von Formen  
 <xref:System.Windows.Media.Brush> Objekte werden verwendet, um einer Form zeichnen <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.Fill%2A>. Im folgenden Beispiel wird die Kontur und Füllung der ein <xref:System.Windows.Shapes.Ellipse> angegeben werden. Beachten Sie, dass Pinseleigenschaften entweder ein Schlüsselwort oder einen hexadezimalen Farbwert werden können. Weitere Informationen zu verfügbaren Farbe Schlüsselwörtern finden Sie unter Eigenschaften von der <xref:System.Windows.Media.Colors> -Klasse in der <xref:System.Windows.Media> Namespace.  
  
```  
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
  
 Die folgende Abbildung zeigt den gerenderten <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Eine Ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.PNG "Shape_ovw_ellipsefill")  
  
 Alternativ können Sie explizit erstellen Eigenschaftenelementsyntax verwenden ein <xref:System.Windows.Media.SolidColorBrush> Objekt, das Zeichnen der Form mit einer Volltonfarbe aus.  
  
```  
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
  
 ![SolidColorBrush-Darstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.PNG "Shape_ovw_solidcolorbrush")  
  
 Sie können die Kontur oder Fläche einer Form auch mit Farbverläufen, Bildern, Mustern und mehr zeichnen. Weitere Informationen finden Sie unter der [Zeichnen mit Volltonfarben und Farbverläufen (Übersicht)](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a>Gestreckte Formen  
 Die <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle> Klassen, die alle haben eine <xref:System.Windows.Shapes.Shape.Stretch%2A> Eigenschaft. Diese Eigenschaft bestimmt, wie eine <xref:System.Windows.Shapes.Shape> Inhalt des Objekts (das zu zeichnende Form) wird gestreckt, um das Ausfüllen der <xref:System.Windows.Shapes.Shape> Layoutbereich des Objekts. Ein <xref:System.Windows.Shapes.Shape> Layoutbereich des Objekts ist die Menge des Speicherplatzes der <xref:System.Windows.Shapes.Shape> erhält vom Layoutsystem, entweder aufgrund von einer expliziten <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Einstellung oder aufgrund von seiner <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Einstellungen. Weitere Informationen zum Layout in Windows Presentation Foundation, finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md) (Übersicht).  
  
 Die Stretch-Eigenschaft nimmt einen der folgenden Werte an:  
  
-   <xref:System.Windows.Media.Stretch.None>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts nicht gestreckt werden.  
  
-   <xref:System.Windows.Media.Stretch.Fill>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts werden gestreckt, um den Layoutbereich auszufüllen.  Das Seitenverhältnis wird nicht beibehalten.  
  
-   <xref:System.Windows.Media.Stretch.Uniform>: Der <xref:System.Windows.Shapes.Shape> werden gestreckt, dass Inhalt des Objekts, dessen Layoutbereich auszufüllen, Beibehaltung des ursprünglichen Seitenverhältnisses so weit wie möglich.  
  
-   <xref:System.Windows.Media.Stretch.UniformToFill>: Der <xref:System.Windows.Shapes.Shape> Inhalt des Objekts werden gestreckt, um den Layoutbereich vollständig auszufüllen, während das ursprüngliche Seitenverhältnis beibehalten.  
  
 Beachten Sie, dass, wenn eine <xref:System.Windows.Shapes.Shape> Inhalt des Objekts werden gestreckt, die <xref:System.Windows.Shapes.Shape> -Objekts nach dem Strecken gezeichnet wird.  
  
 Im folgenden Beispiel eine <xref:System.Windows.Shapes.Polygon> dient zum Zeichnen Sie eines sehr kleinen Dreiecks von (0,0) bis (0,1) bis (1,1). Die <xref:System.Windows.Shapes.Polygon> des Objekts <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf 100 festgelegt sind und die Stretch-Eigenschaft festgelegt. Daher die <xref:System.Windows.Shapes.Polygon> Inhalt des Objekts (das Dreieck) werden gestreckt, um den größeren Platz auszufüllen.  
  
```  
...  
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
...  
```  
  
```  
...  
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
...  
```  
  
<a name="transforms"></a>   
## <a name="transforming-shapes"></a>Transformieren von Formen  
 Die <xref:System.Windows.Media.Transform> -Klasse stellt die Mittel zur Transformation von Formen in einer zweidimensionalen Ebene bereit.  Die verschiedenen Typen von Transformation beinhalten Drehung (<xref:System.Windows.Media.RotateTransform>), Skalierung (<xref:System.Windows.Media.ScaleTransform>), Neigung (<xref:System.Windows.Media.SkewTransform>), und die Übersetzung (<xref:System.Windows.Media.TranslateTransform>).  
  
 Eine allgemeine Transformation einer Form ist die Drehung.  Um eine Form "drehen, erstellen eine <xref:System.Windows.Media.RotateTransform> , und geben Sie ihre <xref:System.Windows.Media.RotateTransform.Angle%2A>. Ein <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 dreht das Element um 45 Grad im Uhrzeigersinn; ein Winkel 90 wird das Element um 90 Grad im Uhrzeigersinn gedreht; und so weiter. Legen Sie die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften, wenn Sie steuern möchten, den Punkt über die das Element gedreht wird. Diese Eigenschaftswerte werden im Koordinatenraum des transformierten Elements ausgedrückt. <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> haben standardmäßig den Wert 0 (null). Wenden Sie schließlich die <xref:System.Windows.Media.RotateTransform> auf das Element. Wenn Sie nicht, dass die Transformation auf das Layout auswirken möchten, legen Sie der Form <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.  
  
 Im folgenden Beispiel ein <xref:System.Windows.Media.RotateTransform> wird verwendet, um eine Form um 45 Grad zur oberen linken Ecke (0,0) drehen.  
  
 [!code-xaml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Im nächsten Beispiel eine andere Form um 45 Grad gedreht wird, aber dieses Mal wird sie über den Punkt (25,50) gedreht.  
  
 [!code-xaml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 In der folgenden Abbildung werden die Ergebnisse der Anwendung der zwei Transformationen dargestellt.  
  
 ![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape-Objekt angewendet. Verwenden Sie zum Anwenden mehrerer Transformationen auf eine Form vom Typ (oder andere UI-Element) einer <xref:System.Windows.Media.TransformGroup>.  
  
## <a name="see-also"></a>Siehe auch  
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Übersicht über Geometrien](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
