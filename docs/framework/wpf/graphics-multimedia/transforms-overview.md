---
title: "&#220;bersicht &#252;ber Transformationen | Microsoft Docs"
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
  - "2D-Transformationsklassen"
  - "Klassen, 2D-Transformation"
  - "FrameworkElement-Objekte, Drehen"
  - "FrameworkElement-Objekte, Skalieren"
  - "FrameworkElement-Objekte, Zerren"
  - "FrameworkElement-Objekte, Verschieben"
  - "Transformationsklassen, 2D"
  - "Transformationen, Informationen über Transformationen"
  - "Transformationen, Informationen über Transformationen"
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# &#220;bersicht &#252;ber Transformationen
In diesem Thema wird die Verwendung von [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform>\-Klassen zum Drehen, Skalieren, Verschieben \(Übersetzen\) und Neigen von <xref:System.Windows.FrameworkElement>\-Objekten beschrieben.  
  
   
  
<a name="whatIsATransformSection"></a>   
## Was ist eine Transformation?  
 Mit einer <xref:System.Windows.Media.Transform>\-Klasse wird festgelegt, wie Punkte von einem Koordinatenraum zu einem anderen zugeordnet bzw. transformiert werden.  Diese Zuordnung wird durch eine Transformations\-<xref:System.Windows.Media.Matrix> beschrieben. Dabei handelt es sich um eine Auflistung von drei Zeilen mit drei Spalten von <xref:System.Double>\-Werten.  
  
> [!NOTE]
>  Von [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] werden zeilengerichtete Matrizen verwendet.  Vektoren werden als Zeilenvektoren und nicht als Spaltenvektoren ausgedrückt.  
  
 In der folgenden Tabelle wird die Struktur einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Matrix angezeigt.  
  
### 2D\-Transformationsmatrix  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Standard: 1,0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Standard: 0,0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Standard: 0,0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Standard: 1,0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Standard: 0,0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Standard: 0,0|1.0|  
  
 Indem Sie die Werte der Matrix ändern, können Sie ein Objekt drehen, skalieren, neigen und verschieben \(übersetzen\).  Wenn Sie beispielsweise den Wert in der ersten Spalte der dritten Zeile \(<xref:System.Windows.Media.Matrix.OffsetX%2A>\-Wert\) auf 100 ändern, können Sie damit ein Objekt entlang der x\-Achse um 100 Einheiten verschieben.  Wenn der Wert in der zweiten Spalte der zweiten Zeile auf 3 geändert wird, kann damit ein Objekt auf das Dreifache seiner aktuellen Höhe gestreckt werden.  Wenn beide Werte geändert werden, wird das Objekt 100 Einheiten entlang der x\-Achse verschoben und seine Höhe um den Faktor 3 gestreckt.  Da [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] nur affine Transformationen unterstützt, sind die Werte in der rechten Spalte immer auf 0, 0, 1 festgelegt.  
  
 Obwohl die Werte einer Matrix mithilfe von [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] direkt geändert werden können, werden auch mehrere <xref:System.Windows.Media.Transform>\-Klassen bereitgestellt, mit denen Objekte transformiert werden können, ohne dass die Konfiguration der zugrunde liegenden Matrixstruktur bekannt ist.  Beispielsweise können Sie mit der <xref:System.Windows.Media.ScaleTransform>\-Klasse ein Objekt skalieren, indem Sie die zugehörigen Eigenschaften <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> festlegen, anstatt eine Transformationsmatrix zu bearbeiten.  Ebenso können Sie mit der <xref:System.Windows.Media.RotateTransform>\-Klasse ein Objekt drehen, indem Sie die zugehörige <xref:System.Windows.Media.RotateTransform.Angle%2A>\-Eigenschaft festlegen.  
  
<a name="transformClassesSection"></a>   
## Transformationsklassen  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] bietet die folgenden [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform>\-Klassen für allgemeine Transformationsvorgänge:  
  
|Klasse|Beschreibung|Beispiel|Darstellung|  
|------------|------------------|--------------|-----------------|  
|<xref:System.Windows.Media.RotateTransform>|Dreht ein Element anhand des angegebenen Werts für <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Drehen eines Objekts](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)||  
|<xref:System.Windows.Media.ScaleTransform>|Skaliert ein Element anhand der angegebenen Werte für <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>.|[Skalieren eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)||  
|<xref:System.Windows.Media.SkewTransform>|Neigt ein Element anhand der angegebenen Werte für <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A>.|[Neigen eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)||  
|<xref:System.Windows.Media.TranslateTransform>|Verschiebt \(übersetzt\) ein Element anhand der angegebenen Werte für <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A>.|[Übersetzen eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)||  
  
 Zum Erstellen komplexerer Transformationen bietet [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] die beiden folgenden Klassen:  
  
|Klasse|Beschreibung|Beispiel|  
|------------|------------------|--------------|  
|<xref:System.Windows.Media.TransformGroup>|Gruppiert mehrere <xref:System.Windows.Media.TransformGroup>\-Objekte in einer einzelnen <xref:System.Windows.Media.Transform>\-Klasse, auf die Sie dann Transformationseigenschaften anwenden können.|[Anwenden mehrerer Transformationen auf ein Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Erstellt benutzerdefinierte Transformationen, die nicht von den anderen <xref:System.Windows.Media.Transform>\-Klassen bereitgestellt werden.  Durch Verwendung von <xref:System.Windows.Media.MatrixTransform> wird eine Matrix direkt bearbeitet.|[Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] stellt auch [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-Transformationen bereit.  Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.Media3D.Transform3D>\-Klasse.  
  
<a name="transformationproperties"></a>   
## Allgemeine Transformationseigenschaften  
 Eine Möglichkeit zum Transformieren eines Objekts ist die Deklaration des entsprechenden <xref:System.Windows.Media.Transform>\-Typs und dessen Anwendung auf die Transformationseigenschaft des Objekts.  Verschiedene Typen von Objekten haben unterschiedliche Typen von Transformationseigenschaften.  Die folgende Tabelle enthält mehrere häufig verwendete [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Typen sowie die zugehörigen Transformationseigenschaften.  
  
|Typ|Transformationseigenschaften|  
|---------|----------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## Transformationen und Koordinatensysteme  
 Bei der Transformation eines Objekts wird nicht nur das Objekt transformiert, sondern auch der Koordinatenraum, in dem sich das Objekt befindet.  Standardmäßig ist eine Transformation am Ursprung des Koordinatensystems des Zielobjekts zentriert: \(0,0\).  Die einzige Ausnahme ist <xref:System.Windows.Media.TranslateTransform>. Für <xref:System.Windows.Media.TranslateTransform> müssen keine Zentrierungseigenschaften festgelegt werden, da sich die Zentrierung nicht auf die Übersetzung auswirkt.  
  
 Im folgenden Beispiel wird mit einem <xref:System.Windows.Media.RotateTransform>\-Element ein <xref:System.Windows.Shapes.Rectangle>\-Element \(vom Typ <xref:System.Windows.FrameworkElement>\) um 45 Grad um seinen Standardmittelpunkt \(0,0\) gedreht.  In der nachstehenden Abbildung sehen Sie die Auswirkung der Drehung.  
  
 ![Ein um &#40;0, 0&#41; in 45&#45;Grad&#45;Schritten gedrehtes FrameworkElement](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm\_FE\_rotated\_about\_upperleft\_corner")  
  
        Ein 45 Grad um den Punkt \(0,0\) gedrehtes Rectangle\-Element  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 Standardmäßig wird das Element um seine obere linke Ecke \(0, 0\) gedreht.  Die Klassen <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform> und <xref:System.Windows.Media.SkewTransform> enthalten CenterX\- und CenterY\-Eigenschaften, mit denen der Punkt angegeben werden kann, auf den die Transformation angewendet wird.  
  
 Im nächsten Beispiel wird ebenfalls eine <xref:System.Windows.Media.RotateTransform>\-Klasse verwendet, um ein <xref:System.Windows.Shapes.Rectangle>\-Element um 45 Grad zu drehen. Dabei sind die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> jedoch so festgelegt, dass die <xref:System.Windows.Media.RotateTransform>\-Klasse den Mittelpunkt \(25, 25\) hat.  In der nachstehenden Abbildung sehen Sie die Auswirkung der Drehung.  
  
 ![Eine um &#40;25, 25&#41; in 45&#45;Grad&#45;Schritten gedrehte Geometrie](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm\_FE\_rotated\_about\_center")  
  
        Ein 45 Grad um den Punkt \(25, 25\) gedrehtes Rectangle\-Element  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## Transformieren eines FrameworkElement  
 Um Transformationen auf eine <xref:System.Windows.FrameworkElement>\-Klasse anzuwenden, erstellen Sie eine <xref:System.Windows.Media.Transform>\-Klasse und wenden diese auf eine der beiden Eigenschaften der <xref:System.Windows.FrameworkElement>\-Klasse an:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> – Eine Transformation, die vor dem Layoutdurchlauf angewendet wird.  Nach Anwendung der Transformation wird die transformierte Größe und Position des Elements vom Layoutsystem verarbeitet.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> – Eine Transformation, durch die die Darstellung des Elements geändert wird, die jedoch nach Abschluss des Layoutdurchlaufs angewendet wird.  Sie können die Leistung verbessern, indem Sie die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft anstelle der <xref:System.Windows.FrameworkElement.LayoutTransform%2A>\-Eigenschaft verwenden.  
  
 Welche Eigenschaft sollte verwendet werden?  Verwenden Sie aufgrund der Leistungsvorteile nach Möglichkeit die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft, insbesondere dann, wenn Sie mit animierten <xref:System.Windows.Media.Transform>\-Objekten arbeiten.  Verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A>\-Eigenschaft zum Skalieren, Drehen oder Neigen, wenn das übergeordnete Element an die transformierte Größe des Elements angepasst werden muss.  Beachten Sie, dass bei Verwendung mit der <xref:System.Windows.FrameworkElement.LayoutTransform%2A>\-Eigenschaft <xref:System.Windows.Media.TranslateTransform>\-Objekte scheinbar keine Auswirkung auf Elemente haben.  Der Grund hierfür ist, dass das übersetzte Element vom Layoutsystem als Teil der Verarbeitung an seine ursprüngliche Position zurückgesetzt wird.  
  
 Weitere Informationen über das Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## Beispiel: Drehen eines FrameworkElement um 45 Grad  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.RotateTransform>\-Element verwendet, um eine Schaltfläche um 45 Grad im Uhrzeigersinn zu drehen.  Die Schaltfläche ist zusammen mit zwei weiteren Schaltflächen in einer <xref:System.Windows.Controls.StackPanel>\-Klasse enthalten.  
  
 Standardmäßig erfolgt mit <xref:System.Windows.Media.RotateTransform> eine Drehung um den Punkt \(0, 0\).  Da im Beispiel kein Wert für den Mittelpunkt angegeben ist, wird die Schaltfläche um den Punkt \(0, 0\) gedreht, also um ihre linke obere Ecke.  Die <xref:System.Windows.Media.RotateTransform>\-Klasse wird auf die <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft angewendet.  In der folgenden Darstellung wird das Ergebnis der Transformation veranschaulicht.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
  
        45\-Grad\-Drehung im Uhrzeigersinn um die obere linke Ecke  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Im nächsten Beispiel wird ebenfalls eine <xref:System.Windows.Media.RotateTransform>\-Klasse verwendet, um eine Schaltfläche um 45 Grad im Uhrzeigersinn zu drehen. Darüber hinaus wird die <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft der Schaltfläche auf \(0,5, 0,5\) gesetzt.  Der Wert der <xref:System.Windows.UIElement.RenderTransformOrigin%2A>\-Eigenschaft verhält sich relativ zur Größe der Schaltfläche.  Als Ergebnis wird die Drehung anstatt um die obere linke Ecke um den Mittelpunkt der Schaltfläche ausgeführt.  In der folgenden Darstellung wird das Ergebnis der Transformation veranschaulicht.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
  
        45\-Grad\-Drehung im Uhrzeigersinn um den Mittelpunkt  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.FrameworkElement.LayoutTransform%2A>\-Eigenschaft anstelle der <xref:System.Windows.UIElement.RenderTransform%2A>\-Eigenschaft zum Drehen der Schaltfläche verwendet.  Dadurch wirkt sich die Transformation auf das Layout der Schaltfläche aus, wodurch ein vollständiger Durchlauf des Layoutsystems ausgelöst wird.  Als Ergebnis wird die Schaltfläche gedreht und anschließend neu positioniert, da ihre Größe geändert wurde.  In der folgenden Darstellung wird das Ergebnis der Transformation veranschaulicht.  
  
 ![Eine mit LayoutTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm\_LayoutTransform")  
  
        Mit LayoutTransform gedrehte Schaltfläche  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## Animieren von Transformationen  
 Weil sie von der <xref:System.Windows.Media.Animation.Animatable>\-Klasse erben, können die <xref:System.Windows.Media.Transform>\-Klassen animiert werden.  Um eine <xref:System.Windows.Media.Transform>\-Klasse zu animieren, wenden Sie die Animation eines kompatiblen Typs auf die zu animierende Eigenschaft an.  
  
 Im folgenden Beispiel werden ein <xref:System.Windows.Media.Animation.Storyboard> und eine <xref:System.Windows.Media.Animation.DoubleAnimation> zusammen mit einer <xref:System.Windows.Media.RotateTransform>\-Klasse verwendet, um eine <xref:System.Windows.Controls.Button> ohne Positionsänderung zu drehen, wenn darauf geklickt wird.  
  
 [!code-xml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Das vollständige Beispiel finden Sie unter [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
## Features von Freezable  
 Da die <xref:System.Windows.Media.Transform>\-Klasse von der <xref:System.Windows.Freezable>\-Klasse erbt, bietet sie mehrere spezielle Features: <xref:System.Windows.Media.Transform>\-Objekte können als [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md) deklariert, von mehreren Objekten gleichzeitig verwendet, zur Leistungsoptimierung als schreibgeschützt definiert, geklont sowie als threadsicher festgelegt werden.  Weitere Informationen über die verschiedenen Features von <xref:System.Windows.Freezable>\-Objekten finden Sie unter [Übersicht über Freezable\-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Matrix>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [Beispiel für 2D\-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252)