---
title: "&#220;bersicht &#252;ber Formen und die grundlegenden Funktionen zum Zeichnen in WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Grundlegendes Zeichnen"
  - "Shape-Objekte"
  - "Formen, Informationen über Formen"
  - "Vektorzeichnung, Übersicht"
  - "Vektoren, Zeichnen"
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# &#220;bersicht &#252;ber Formen und die grundlegenden Funktionen zum Zeichnen in WPF
Dieses Thema gibt eine Übersicht über das Zeichnen mit <xref:System.Windows.Shapes.Shape>\-Objekten.  Ein <xref:System.Windows.Shapes.Shape>\-Objekt ist ein <xref:System.Windows.UIElement>\-Typ und ermöglicht Ihnen das Zeichnen von Formen auf dem Bildschirm.  Da es sich hierbei um Benutzeroberflächenelemente handelt, können <xref:System.Windows.Shapes.Shape>\-Objekte innerhalb von <xref:System.Windows.Controls.Panel>\-Elementen und den meisten Steuerelementen verwendet werden.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste.  Auf der obersten Ebene stehen die benutzerfreundlichen <xref:System.Windows.Shapes.Shape>\-Objekte mit einer Vielzahl von nützlichen Features zur Verfügung, z. B. Layout und Teilnahme am [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Ereignissystem.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="shapes"></a>   
## Shape\-Objekte  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Reihe von vorgefertigten <xref:System.Windows.Shapes.Shape>\-Objekten zur Verfügung.  Alle Shape\-Objekte erben von der <xref:System.Windows.Shapes.Shape>\-Klasse.  Zu den verfügbaren Shape\-Objekten gehören <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> und <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape>\-Objekte besitzen alle die folgenden allgemeinen Eigenschaften.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Rand der Form gezeichnet wird.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Randstärke der Form.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form gezeichnet wird.  
  
-   Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, die in [geräteunabhängigen Pixeln](GTMT) gemessen werden.  
  
 Da sie sich vom <xref:System.Windows.UIElement> herleiten, können Shape\-Objekte in Bereichen und den meisten Steuerelementen verwendet werden.  Der <xref:System.Windows.Controls.Canvas>\-Bereich eignet sich besonders gut zur Erstellung komplexer Zeichnungen, da er die absolute Positionierung von untergeordneten Objekten unterstützt.  
  
 Die <xref:System.Windows.Shapes.Line>\-Klasse ermöglicht es Ihnen, eine Linie zwischen zwei Punkten zu zeichnen.  Im folgenden Beispiel werden mehrere Möglichkeiten veranschaulicht, Linienkoordinaten und Stricheigenschaften anzugeben.  
  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Line>.  
  
 ![Liniendarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.png "shape\_ovw\_line2")  
  
 Obwohl die <xref:System.Windows.Shapes.Line>\-Klasse die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft bereitstellt, wirkt sich die Einstellung dieser Eigenschaft nicht aus, da eine <xref:System.Windows.Shapes.Line> über keinen Bereich verfügt.  
  
 Eine weitere allgemeine Form ist die <xref:System.Windows.Shapes.Ellipse>.  Sie erstellen eine <xref:System.Windows.Shapes.Ellipse>, indem Sie die Formeigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> definieren.  Um einen Kreis zu zeichnen, geben Sie eine <xref:System.Windows.Shapes.Ellipse> an, deren Werte für <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> gleich sind.  
  
 [!code-xml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 Die folgende Abbildung zeigt ein Beispiel einer gerenderten <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Ellipsendarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape\_ovw\_ellipse2")  
  
<a name="paths"></a>   
## Verwenden von Pfaden und Geometrien  
 Die <xref:System.Windows.Shapes.Path>\-Klasse ermöglicht es Ihnen, Kurven und komplexe Formen zu zeichnen.  Diese Kurven und Formen werden mithilfe der <xref:System.Windows.Media.Geometry>\-Objekte beschrieben.  Zur Verwendung von <xref:System.Windows.Shapes.Path> erstellen Sie ein <xref:System.Windows.Media.Geometry>\-Objekt und nutzen es, um die <xref:System.Windows.Shapes.Path.Data%2A>\-Eigenschaft des <xref:System.Windows.Shapes.Path>\-Objekts festzulegen.  
  
 Sie können aus einer Vielzahl von <xref:System.Windows.Media.Geometry>\-Objekten auswählen.  Die Klassen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> und <xref:System.Windows.Media.EllipseGeometry> beschreiben relativ einfache Formen.  Um komplexere Formen oder Kurven zu erstellen, verwenden Sie ein <xref:System.Windows.Media.PathGeometry>\-Objekt.  
  
<a name="pathgeometry"></a>   
### PathGeometry und PathSegments  
 <xref:System.Windows.Media.PathGeometry>\-Objekte setzen sich aus einem oder mehreren <xref:System.Windows.Media.PathFigure>\-Objekten zusammen, wobei jedes <xref:System.Windows.Media.PathFigure>\-Objekt eine andere "Abbildung" oder Form darstellt.  Jedes <xref:System.Windows.Media.PathFigure>\-Objekt setzt sich wiederum aus einem oder mehreren <xref:System.Windows.Media.PathSegment>\-Objekten zusammen, die jeweils einen verknüpften Bereich der Abbildung oder Form darstellen.  Zu den Segmenttypen gehören <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment> und <xref:System.Windows.Media.ArcSegment>.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Shapes.Path> zum Zeichnen einer quadratischen Bézierkurve verwendet.  
  
 [!code-xml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Die folgende Abbildung zeigt die gerenderte Form.  
  
 ![Pfaddarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.png "shape\_ovw\_path2")  
  
 Weitere Informationen über <xref:System.Windows.Media.PathGeometry> und die anderen <xref:System.Windows.Media.Geometry>\-Klassen finden Sie unter [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### Abgekürzte Syntax in XAML  
 In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie einen <xref:System.Windows.Shapes.Path> auch mit einer besonderen abgekürzten Syntax beschreiben.  Im folgenden Beispiel wird eine abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.  
  
```xaml  
<Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 Die folgende Abbildung zeigt einen gerenderten <xref:System.Windows.Shapes.Path>.  
  
 ![Pfaddarstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.png "shape\_ovw\_path")  
  
 Die <xref:System.Windows.Shapes.Path.Data%2A>\-Attributzeichenfolge beginnt mit dem Verschiebebefehl, angegeben durch ein "M", der im Koordinatensystem von <xref:System.Windows.Controls.Canvas> einen Startpunkt für den Pfad festlegt.  Bei <xref:System.Windows.Shapes.Path>\-Datenparametern wird die Groß\-\/Kleinschreibung beachtet.  Der großgeschriebene Buchstabe M gibt eine absolute Position für den neuen aktuellen Punkt an.  Ein kleingeschriebenes m gibt relative Koordinaten an.  Das erste Segment ist eine kubische [Bézierkurve](GTMT), die an der Position \(100,200\) beginnt, an der Position \(400,175\) endet und mit den beiden Kontrollpunkten \(100,25\) und \(400,350\) gezeichnet wird.  Dieses Segment wird durch den C\-Befehl in der <xref:System.Windows.Shapes.Path.Data%2A>\-Attributzeichenfolge angegeben.  Auch hier gibt der großgeschriebene Buchstabe C einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.  
  
 Das zweite Segment beginnt mit dem absoluten horizontalen LineTo\-Befehl "H", der eine Linie angibt, die vom Endpunkt \(400,175\) des vorherigen untergeordneten Pfads bis zu einem neuen Endpunkt \(280,175\) gezeichnet wird.  Da es sich um einen horizontalen Linienbefehl handelt, ist der angegebene Wert eine *x*\-Koordinate.  
  
 Die vollständige Pfadsyntax finden Sie in der Referenz für <xref:System.Windows.Shapes.Path.Data%2A> und unter [Erstellen einer Form mithilfe von PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## Zeichnen von Formen  
 <xref:System.Windows.Media.Brush>\-Objekte werden zum Zeichnen von <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.Fill%2A> für eine Form verwendet.  Im folgenden Beispiel werden der Strich und der Füllbereich einer <xref:System.Windows.Shapes.Ellipse> angegeben.  Beachten Sie, dass Pinseleigenschaften entweder über ein Schlüsselwort oder anhand eines hexadezimalen Farbwerts eingegeben werden können.  Weitere Informationen über verfügbare Farbschlüsselwörter finden Sie in den Eigenschaften der <xref:System.Windows.Media.Colors>\-Klasse im <xref:System.Windows.Media>\-Namespace.  
  
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
  
 Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Eine Ellipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.png "shape\_ovw\_ellipsefill")  
  
 Alternativ dazu können Sie die Syntax eines Eigenschaftenelements verwenden, um explizit ein <xref:System.Windows.Media.SolidColorBrush>\-Objekt zum Zeichnen der Form in einer Volltonfarbe zu erstellen.  
  
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
  
 ![SolidColorBrush&#45;Darstellung](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.png "shape\_ovw\_solidcolorbrush")  
  
 Sie können den Strich oder Füllbereich einer Form auch mit Farbverläufen, Bildern, Mustern usw. zeichnen.  Weitere Informationen finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## Gestreckte Formen  
 Die Klassen <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> und <xref:System.Windows.Shapes.Rectangle> verfügen alle über die <xref:System.Windows.Shapes.Shape.Stretch%2A>\-Eigenschaft.  Diese Eigenschaft legt fest, wie der Inhalt \(die zu zeichnende Form\) eines <xref:System.Windows.Shapes.Shape>\-Objekts gestreckt wird, um den Layoutbereich im <xref:System.Windows.Shapes.Shape>\-Objekt auszufüllen.  Der Layoutbereich eines <xref:System.Windows.Shapes.Shape>\-Objekts ist die Bereichsgröße, die dem <xref:System.Windows.Shapes.Shape>\-Objekt vom Layoutsystem zugeordnet wird, und zwar entweder durch die explizite Einstellung von <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> oder aufgrund seiner Einstellungen für <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  Weitere Informationen über das Layout in Windows Presentation Foundation finden Sie in der Übersicht [Layout](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Die Stretch\-Eigenschaft nimmt einen der folgenden Werte an:  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des <xref:System.Windows.Shapes.Shape>\-Objekts wird nicht gestreckt.  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des <xref:System.Windows.Shapes.Shape>\-Objekts wird gestreckt, um dessen Layoutbereich auszufüllen.  Das Seitenverhältnis wird nicht beibehalten.  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des <xref:System.Windows.Shapes.Shape>\-Objekts wird so weit wie möglich gestreckt, um unter Beibehaltung des ursprünglichen Seitenverhältnisses den Layoutbereich auszufüllen.  
  
-   <xref:System.Windows.Media.Stretch>: Der Inhalt des <xref:System.Windows.Shapes.Shape>\-Objekts wird gestreckt, um unter Beibehaltung des ursprünglichen Seitenverhältnisses den Layoutbereich komplett auszufüllen.  
  
 Beachten Sie, dass beim Strecken des Inhalts eines <xref:System.Windows.Shapes.Shape>\-Objekts der Rand des <xref:System.Windows.Shapes.Shape>\-Objekts nach dem Strecken gezeichnet wird.  
  
 Im folgenden Beispiel wird mit einem <xref:System.Windows.Shapes.Polygon> ein sehr kleines Dreieck von \(0,0\) bis \(0,1\) bis \(1,1\) gezeichnet.  Die Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> sind für das <xref:System.Windows.Shapes.Polygon>\-Objekt auf 100 festgelegt; die Stretch\-Eigenschaft ist auf Fill festgelegt.  Das Ergebnis ist, dass der Inhalt \(das Dreieck\) des <xref:System.Windows.Shapes.Polygon>\-Objekts gestreckt wird, um den größeren Bereich auszufüllen.  
  
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
## Transformieren von Formen  
 Die <xref:System.Windows.Media.Transform>\-Klasse stellt die Mittel bereit, Formen in einer zweidimensionalen Ebene zu transformieren.  Zu den unterschiedlichen Transformationstypen gehören die Drehung \(<xref:System.Windows.Media.RotateTransform>\), die Skalierung \(<xref:System.Windows.Media.ScaleTransform>\), die Neigung \(<xref:System.Windows.Media.SkewTransform>\) und die Verschiebung \(<xref:System.Windows.Media.TranslateTransform>\).  
  
 Eine allgemeine, für Formen angewandte Transformation ist die Drehung.  Um eine Form zu drehen, erstellen Sie einen <xref:System.Windows.Media.RotateTransform>\-Typ und geben seinen <xref:System.Windows.Media.RotateTransform.Angle%2A>\-Wert an.  Wenn Sie für <xref:System.Windows.Media.RotateTransform.Angle%2A> den Wert 45 angeben, wird das Element im Uhrzeigersinn um 45 Grad gedreht; ein Winkel von 90 dreht das Element um 90 Grad im Uhrzeigersinn usw.  Legen Sie die <xref:System.Windows.Media.RotateTransform.CenterX%2A>\-Eigenschaft und die <xref:System.Windows.Media.RotateTransform.CenterY%2A>\-Eigenschaft fest, wenn Sie steuern möchten, um welchen Punkt das Element gedreht werden soll.  Diese Eigenschaftswerte werden im Koordinatenraum des Elements ausgedrückt, das transformiert wird.  <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> sind standardmäßig auf den Wert 0 \(null\) gesetzt.  Wenden Sie abschließend <xref:System.Windows.Media.RotateTransform> auf das Element an.  Wenn sich die Transformation nicht auf das Layout auswirken soll, legen Sie die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft der Form fest.  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.RotateTransform> verwendet, um eine Form um 45 Grad um ihre obere linke Ecke \(0,0\) zu drehen.  
  
 [!code-xml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 Im nächsten Beispiel wird eine weitere Form um 45 Grad gedreht; diesmal jedoch um den Punkt \(25,50\).  
  
 [!code-xml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 In der folgenden Abbildung werden die Ergebnisse nach der Anwendung der beiden Transformationen angezeigt.  
  
 ![45&#45;Grad&#45;Drehungen mit unterschiedlichen Mittelpunkten](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
  
 In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape\-Objekt angewendet.  Um mehrere Transformationen auf eine Form \(oder auf ein beliebig anderes Benutzeroberflächenelement\) anzuwenden, verwenden Sie eine <xref:System.Windows.Media.TransformGroup>.  
  
## Siehe auch  
 [2D\-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Übersicht über die Geometrie](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)