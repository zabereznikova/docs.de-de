---
title: Shapes und grundlegende Zeichnungsübersicht
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
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141327"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF
Dieses Thema gibt einen Überblick <xref:System.Windows.Shapes.Shape> über das Zeichnen mit Objekten. A <xref:System.Windows.Shapes.Shape> ist eine <xref:System.Windows.UIElement> Art von, mit der Sie eine Form auf dem Bildschirm zeichnen können. Da es sich <xref:System.Windows.Shapes.Shape> um UI-Elemente <xref:System.Windows.Controls.Panel> handelt, können Objekte innerhalb von Elementen und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste. Auf der obersten <xref:System.Windows.Shapes.Shape> Ebene sind Objekte einfach zu bedienen und bieten viele [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nützliche Funktionen, wie Layout und Teilnahme am Veranstaltungssystem.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Shape-Objekte  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet eine Reihe gebrauchsfertiger <xref:System.Windows.Shapes.Shape> Objekte.  Alle Shape-Objekte erben <xref:System.Windows.Shapes.Shape> von der Klasse. Verfügbare Shape-Objekte <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>sind <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle>, , , und . <xref:System.Windows.Shapes.Shape>Objekte teilen die folgenden gemeinsamen Eigenschaften.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Umriss des Shapes gezeichnet wird.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Dicke des Umrisses des Shapes.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form lackiert wird.  
  
- Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, gemessen in geräteunabhängigen Pixeln.  
  
 Da sie von <xref:System.Windows.UIElement>ableiten, können Shape-Objekte in Bedienfeldern und den meisten Steuerelementen verwendet werden. Das <xref:System.Windows.Controls.Canvas> Panel ist eine besonders gute Wahl für die Erstellung komplexer Zeichnungen, da es die absolute Positionierung seiner untergeordneten Objekte unterstützt.  
  
 Mit <xref:System.Windows.Shapes.Line> der Klasse können Sie eine Linie zwischen zwei Punkten zeichnen. Das folgende Beispiel zeigt verschiedene Arten, wie Zeilenkoordinaten und Stricheigenschaften angegeben werden können.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Die folgende Abbildung zeigt <xref:System.Windows.Shapes.Line>die gerenderte .  
  
 ![Liniendarstellung](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Obwohl <xref:System.Windows.Shapes.Line> die Klasse <xref:System.Windows.Shapes.Shape.Fill%2A> eine Eigenschaft bietet, hat <xref:System.Windows.Shapes.Line> das Festlegen keine Auswirkungen, da ein Bereich nicht vorhanden ist.  
  
 Eine weitere gemeinsame <xref:System.Windows.Shapes.Ellipse>Form ist die .  Erstellen <xref:System.Windows.Shapes.Ellipse> Sie eine, indem <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> Sie die Eigenschaften und Eigenschaften des Shapes definieren. Um einen Kreis zu <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.FrameworkElement.Width%2A> zeichnen, geben Sie einen an, dessen und <xref:System.Windows.FrameworkElement.Height%2A> die Werte gleich sind.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 Die folgende Abbildung zeigt ein <xref:System.Windows.Shapes.Ellipse>Beispiel für eine gerenderte .  
  
 ![Ellipsendarstellung](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Verwenden von Pfaden und Geometrien  
 Mit <xref:System.Windows.Shapes.Path> der Klasse können Sie Kurven und komplexe Formen zeichnen. Diese Kurven und Formen <xref:System.Windows.Media.Geometry> werden mithilfe von Objekten beschrieben. Um eine <xref:System.Windows.Shapes.Path>zu verwenden, erstellen Sie <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Path> eine und <xref:System.Windows.Shapes.Path.Data%2A> verwenden sie, um die Eigenschaft des Objekts festzulegen.  
  
 Es gibt eine <xref:System.Windows.Media.Geometry> Vielzahl von Objekten zur Auswahl. Die <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>, <xref:System.Windows.Media.EllipseGeometry> und Klassen beschreiben relativ einfache Formen. Um komplexere Formen zu erstellen <xref:System.Windows.Media.PathGeometry>oder Kurven zu erstellen, verwenden Sie eine .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry und PathSegments  
 <xref:System.Windows.Media.PathGeometry>Objekte bestehen aus einem <xref:System.Windows.Media.PathFigure> oder mehreren Objekten; jede <xref:System.Windows.Media.PathFigure> stellt eine andere "Figur" oder Form dar. Jedes <xref:System.Windows.Media.PathFigure> besteht aus einem <xref:System.Windows.Media.PathSegment> oder mehreren Objekten, die jeweils einen verbundenen Teil der Figur oder Form darstellen. Segmenttypen umfassen die <xref:System.Windows.Media.LineSegment> <xref:System.Windows.Media.BezierSegment>folgenden: <xref:System.Windows.Media.ArcSegment>, und .  
  
 Im folgenden Beispiel <xref:System.Windows.Shapes.Path> wird a verwendet, um eine quadratische Bézierkurve zu zeichnen.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Die folgende Abbildung zeigt die gerenderte Form.  
  
 ![Pfaddarstellung](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Weitere Informationen <xref:System.Windows.Media.PathGeometry> zu und <xref:System.Windows.Media.Geometry> zu den anderen Klassen finden Sie in der [Geometrieübersicht](geometry-overview.md).  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Abgekürzte Syntax in XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]können Sie auch eine spezielle abgekürzte <xref:System.Windows.Shapes.Path>Syntax verwenden, um eine zu beschreiben. Im folgenden Beispiel wird abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Die folgende Abbildung zeigt <xref:System.Windows.Shapes.Path>eine gerenderte .  
  
 ![Pfaddarstellung](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 Die <xref:System.Windows.Shapes.Path.Data%2A> Attributzeichenfolge beginnt mit dem Befehl "moveto", der durch M angegeben wird und einen <xref:System.Windows.Controls.Canvas>Startpunkt für den Pfad im Koordinatensystem des festlegt. <xref:System.Windows.Shapes.Path>Datenparameter werden die Groß-/Kleinschreibung berücksichtigt. Die Hauptstadt M gibt eine absolute Position für den neuen aktuellen Punkt an. Ein kleingeschriebenes m würde relative Koordinaten angeben. Das erste Segment ist eine kubische Bézierkurve, die bei (100.200) beginnt und bei (400.175) endet, gezeichnet mit den beiden Kontrollpunkten (100,25) und (400,350). Dieses Segment wird durch den <xref:System.Windows.Shapes.Path.Data%2A> Befehl C in der Attributzeichenfolge angezeigt. Ein großes C gibt erneut einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.  
  
 Das zweite Segment beginnt mit einem absoluten horizontalen „Lineto“-Befehl H, der eine Linie vom vorherigen untergeordneten Endpunkt (400,175) zu einem neuen Endpunkt (280,175) zeichnet. Da es sich um einen horizontalen "lineto"-Befehl handelt, ist der angegebene Wert eine x-Koordinate. *x*  
  
 Die vollständige Pfadsyntax finden <xref:System.Windows.Shapes.Path.Data%2A> Sie im Verweis und [Erstellen einer Form mithilfe einer PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Zeichnen von Formen  
 <xref:System.Windows.Media.Brush>Objekte werden verwendet, um <xref:System.Windows.Shapes.Shape.Stroke%2A> die <xref:System.Windows.Shapes.Shape.Fill%2A>Unden einer Form zu malen. Im folgenden Beispiel werden strichund <xref:System.Windows.Shapes.Ellipse> füllen eines angegeben. Beachten Sie, dass Pinseleigenschaften entweder ein Schlüsselwort oder einen hexadezimalen Farbwert werden können. Weitere Informationen zu verfügbaren Farbschlüsselwörtern <xref:System.Windows.Media.Colors> finden Sie <xref:System.Windows.Media> unter Eigenschaften der Klasse im Namespace.  
  
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
  
 Die folgende Abbildung zeigt <xref:System.Windows.Shapes.Ellipse>die gerenderte .  
  
 ![Eine Ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 Alternativ können Sie die Eigenschaftenelementsyntax verwenden, um explizit ein <xref:System.Windows.Media.SolidColorBrush> Objekt zu erstellen, um die Form mit einer Volltonfarbe zu zeichnen.  
  
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
  
 ![SolidColorBrush-Darstellung](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 Sie können die Kontur oder Fläche einer Form auch mit Farbverläufen, Bildern, Mustern und mehr zeichnen. Weitere Informationen finden Sie unter [Die Übersicht über Das Gemälde mit Vollfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>Gestreckte Formen  
 Die <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>Klassen <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle> , , <xref:System.Windows.Shapes.Shape.Stretch%2A> und Klassen verfügen alle über eine Eigenschaft. Diese Eigenschaft bestimmt, wie der Inhalt eines <xref:System.Windows.Shapes.Shape> Objekts (die zu <xref:System.Windows.Shapes.Shape> zeichnende Form) gestreckt wird, um den Layoutbereich des Objekts zu füllen. Der <xref:System.Windows.Shapes.Shape> Layoutbereich eines Objekts ist <xref:System.Windows.Shapes.Shape> der Platz, der vom Layoutsystem <xref:System.Windows.FrameworkElement.Width%2A> zugewiesen <xref:System.Windows.FrameworkElement.Height%2A> wird, entweder <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> aufgrund einer expliziten Einstellung und aufgrund seiner und Einstellungen. Weitere Informationen zum Layout in Windows Presentation Foundation finden Sie unter [Layoutübersicht.](../advanced/layout.md)  
  
 Die Stretch-Eigenschaft nimmt einen der folgenden Werte an:  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird nicht gestreckt.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird gestreckt, um seinen Layoutbereich zu füllen.  Das Seitenverhältnis wird nicht beibehalten.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird so weit wie möglich gestreckt, um seinen Layoutraum zu füllen und gleichzeitig das ursprüngliche Seitenverhältnis zu erhalten.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> Der Inhalt des Objekts wird gestreckt, um seinen Layoutbereich vollständig zu füllen und gleichzeitig das ursprüngliche Seitenverhältnis zu erhalten.  
  
 Beachten Sie, <xref:System.Windows.Shapes.Shape> dass beim Dehnen des Inhalts <xref:System.Windows.Shapes.Shape> eines Objekts die Umrisslinie des Objekts nach der Dehnung gezeichnet wird.  
  
 Im folgenden Beispiel <xref:System.Windows.Shapes.Polygon> wird a verwendet, um ein sehr kleines Dreieck von (0,0) bis (0,1) bis (1,1) zu zeichnen. Das <xref:System.Windows.Shapes.Polygon> Objekt <xref:System.Windows.FrameworkElement.Width%2A> ist <xref:System.Windows.FrameworkElement.Height%2A> und auf 100 festgelegt ist, und seine Stretch-Eigenschaft ist auf Füllen festgelegt. Daher wird der <xref:System.Windows.Shapes.Polygon> Inhalt des Objekts (das Dreieck) gestreckt, um den größeren Raum zu füllen.  
  
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
 Die <xref:System.Windows.Media.Transform> Klasse bietet die Möglichkeit, Formen in einer zweidimensionalen Ebene zu transformieren.  Zu den verschiedenen Transformationstypen<xref:System.Windows.Media.RotateTransform>gehören Rotation ( ), Skalierung (<xref:System.Windows.Media.ScaleTransform>), Schiefe (<xref:System.Windows.Media.SkewTransform>) und Übersetzung (<xref:System.Windows.Media.TranslateTransform>).  
  
 Eine allgemeine Transformation einer Form ist die Drehung.  Um eine Form zu <xref:System.Windows.Media.RotateTransform> drehen, <xref:System.Windows.Media.RotateTransform.Angle%2A>erstellen Sie eine, und geben Sie ihre an. Eine <xref:System.Windows.Media.RotateTransform.Angle%2A> von 45 dreht das Element um 45 Grad im Uhrzeigersinn; ein Winkel von 90 dreht das Element um 90 Grad im Uhrzeigersinn; Und so weiter. Legen <xref:System.Windows.Media.RotateTransform.CenterX%2A> Sie <xref:System.Windows.Media.RotateTransform.CenterY%2A> die und Eigenschaften fest, wenn Sie den Punkt steuern möchten, um den das Element gedreht wird. Diese Eigenschaftswerte werden im Koordinatenraum des transformierten Elements ausgedrückt. <xref:System.Windows.Media.RotateTransform.CenterX%2A>und <xref:System.Windows.Media.RotateTransform.CenterY%2A> haben Standardwerte von Null. Wenden Sie <xref:System.Windows.Media.RotateTransform> schließlich die auf das Element an. Wenn sie nicht möchten, dass sich die Transformation <xref:System.Windows.UIElement.RenderTransform%2A> auf das Layout auswirkt, legen Sie die Eigenschaft des Shapes fest.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird eine verwendet, um eine Form um 45 Grad um die obere linke Ecke des Shapes (0,0) zu drehen.  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Im nächsten Beispiel eine andere Form um 45 Grad gedreht wird, aber dieses Mal wird sie über den Punkt (25,50) gedreht.  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 In der folgenden Abbildung werden die Ergebnisse der Anwendung der zwei Transformationen dargestellt.  
  
 ![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape-Objekt angewendet. Um mehrere Transformationen auf ein Shape (oder ein <xref:System.Windows.Media.TransformGroup>anderes UI-Element) anzuwenden, verwenden Sie eine .  
  
## <a name="see-also"></a>Weitere Informationen

- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über die Geometrie](geometry-overview.md)
- [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Übersicht über Animationen](animation-overview.md)
