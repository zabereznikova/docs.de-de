---
title: Übersicht über Transformationen
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2-D transform
- transform classes [WPF], 2-D
- 2-D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: 4fd846502fd348222bc1da1c8746f037e9f237fe
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425842"
---
# <a name="transforms-overview"></a>Übersicht über Transformationen
In diesem Thema wird beschrieben, wie Sie mit der [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> Klassen zu drehen, skalieren, verschieben (übersetzen) und Neigen <xref:System.Windows.FrameworkElement> Objekte.  
  
  
<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Was ist eine Transformation?  
 Ein <xref:System.Windows.Media.Transform> definiert, wie die Zuordnung oder Transformation von Punkten aus einem Koordinatenbereich zu einem anderen Koordinatenbereich. Diese Zuordnung wird durch eine Transformation beschrieben <xref:System.Windows.Media.Matrix>, eine Sammlung von drei Zeilen mit drei Spalten von <xref:System.Double> Werte.  
  
> [!NOTE]
>  Windows Presentation Foundation (WPF) wird zeilenmatrizen verwendet. Vektoren werden als Zeilenvektoren und nicht als Spaltenvektoren ausgedrückt.  
  
 In der folgenden Tabelle wird die Struktur für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Matrix dargestellt.  
  
### <a name="a-2-d-transformation-matrix"></a>2D-Transformationsmatrix  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Standard: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Standard: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Standard: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Standard: 0.0|1.0|  
  
 Durch Bearbeiten der Matrixwerte können Sie ein Objekt drehen, skalieren, neigen und verschieben (übersetzen). Angenommen, Sie ändern, dass den Wert in der ersten Spalte der dritten Zeile (die <xref:System.Windows.Media.Matrix.OffsetX%2A> Wert) auf 100 erhöht, können Sie sie ein Objekt 100 Einheiten entlang der x-Achse verschieben. Wenn Sie den Wert in der zweiten Spalte der zweiten Zeile in 3 ändern, können Sie ein Objekt um das Dreifache seiner aktuellen Höhe strecken. Wenn Sie beide Werte ändern, wird das Objekt 100 Einheiten entlang der x-Achse verschoben und seine Höhe wird um den Faktor 3 gestreckt. Da Windows Presentation Foundation (WPF) nur affine Transformationen unterstützt, sind die Werte in der rechten Spalte immer 0, 0, 1.  
  
 Ermöglicht, zwar eine Windows Presentation Foundation (WPF) Werte einer Matrix direkt geändert es bietet außerdem mehrere <xref:System.Windows.Media.Transform> Klassen, mit denen Sie ein Objekt zu transformieren, ohne zu wissen, wie die zugrunde liegende Struktur der Matrix konfiguriert ist. Z. B. die <xref:System.Windows.Media.ScaleTransform> -Klasse können Sie zum Skalieren eines Objekts durch Festlegen seiner <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften, anstatt eine Transformationsmatrix zu bearbeiten. Ebenso die <xref:System.Windows.Media.RotateTransform> -Klasse können Sie zum Drehen eines Objekts durch das Festlegen der <xref:System.Windows.Media.RotateTransform.Angle%2A> Eigenschaft.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Transformationsklassen  
 Windows Presentation Foundation (WPF) bietet die folgenden [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> Klassen für gemeinsame Transformationsvorgänge:  
  
|Klasse|Beschreibung|Beispiel|Darstellung|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Dreht ein Element vom angegebenen <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Drehen eines Objekts](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)|![Abbildung drehen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Skaliert ein Element vom angegebenen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Mengen.|[Skalieren eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)|![Abbildung skalieren](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Neigt ein Element vom angegebenen <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A> Mengen.|[Neigen eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)|![Abbildung neigen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Verschiebt (übersetzt) ein Element vom angegebenen <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Mengen.|[Übersetzen eines Elements](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)|![Abbildung verschieben](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Zum Erstellen komplexerer Transformations, bietet Windows Presentation Foundation (WPF) die folgenden zwei Klassen:  
  
|Klasse|Beschreibung|Beispiel|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Gruppiert mehrere <xref:System.Windows.Media.TransformGroup> Objekte in einem einzelnen <xref:System.Windows.Media.Transform> , dass Sie dann anwenden können, um Eigenschaften zu transformieren.|[Anwenden mehrerer Transformationen auf ein Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Erstellt benutzerdefinierte Transformationen, die nicht von dem anderen bereitgestellt werden <xref:System.Windows.Media.Transform> Klassen. Bei Verwendung einer <xref:System.Windows.Media.MatrixTransform>, eine Matrix direkt bearbeitet.|[Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) bietet auch [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Transformationen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.Media3D.Transform3D>-Klasse.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Allgemeine Transformationseigenschaften  
 Eine Möglichkeit zum Transformieren eines Objekts ist die Deklaration des entsprechenden <xref:System.Windows.Media.Transform> geben, und klicken Sie auf die Transformationseigenschaft des Objekts anzuwenden. Verschiedene Typen von Objekten haben unterschiedliche Typen von Transformationseigenschaften. Die folgende Tabelle enthält einige häufig verwendete Windows Presentation Foundation (WPF)-Typen und deren Transformationseigenschaften.  
  
|Typ|Transformationseigenschaften|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## <a name="transformations-and-coordinate-systems"></a>Transformationen und Koordinatensysteme  
 Beim Transformieren eines Objekts wird nicht nur das Objekt transformiert, sondern auch der Koordinatenbereich, in dem dieses Objekt vorhanden ist. Standardmäßig wird eine Transformation am Ursprung des Koordinatensystems des Zielobjekts zentriert: (0,0). Die einzige Ausnahme ist <xref:System.Windows.Media.TranslateTransform>; ein <xref:System.Windows.Media.TranslateTransform> verfügt über keine Center-Eigenschaften festlegen, da es sich bei der Übersetzung Effekt ist derselbe, unabhängig davon, wo sie zentriert wird.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> Rotieren einer <xref:System.Windows.Shapes.Rectangle> -Element, eine Art von <xref:System.Windows.FrameworkElement>, um 45 Grad um seine standardmitte (0, 0). Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![FrameworkElement um 45 Grad rotiert &#40;0,0&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "Graphicsmm_FE_rotated_about_upperleft_corner")  
Ein in 45-Grad-Schritten um den Punkt (0,0) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 In der Standardeinstellung dreht das Element um seine obere linke Ecke (0, 0). Die <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>, und <xref:System.Windows.Media.SkewTransform> Klassen stellen die Eigenschaften CenterX und CenterY, mit denen Sie an dem Punkt, an dem die Transformation angewendet wird.  
  
 Im nächste Beispiel verwendet auch eine <xref:System.Windows.Media.RotateTransform> Rotieren eine <xref:System.Windows.Shapes.Rectangle> Element um 45 Grad; jedoch diesmal die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften festgelegt werden, damit die <xref:System.Windows.Media.RotateTransform> wurde Mitte (25, 25). Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Eine Schritten gedrehte Geometrie um 45 Grad &#40;25, 25&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "Graphicsmm_FE_rotated_about_center")  
Ein in 45-Grad-Schritten um den Punkt (25, 25) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Transformieren eines FrameworkElement  
 Anwenden von Transformationen auf ein <xref:System.Windows.FrameworkElement>, erstellen eine <xref:System.Windows.Media.Transform> und wenden Sie es auf eine der beiden Eigenschaften, die die <xref:System.Windows.FrameworkElement> Klasse bietet:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> – Eine Transformation, die vor dem Layoutdurchlauf angewendet wird. Nachdem die Transformation angewendet wurde, verarbeitet das Layoutsystem die transformierte Größe und Position des Elements.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> – Eine Transformation, die die Darstellung des Elements ändert, aber nach Abschluss des Layoutdurchlaufs angewendet wird. Mithilfe der <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft anstelle der <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft, können Sie Leistungsvorteile abrufen.  
  
 Welche Eigenschaft sollte verwendet werden? Verwenden Sie aufgrund der Leistungsvorteile, die er bereitstellt, die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft, wann immer möglich, insbesondere bei Verwendung von animiert <xref:System.Windows.Media.Transform> Objekte. Verwenden der <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft beim Skalieren, drehen oder neigen, und Sie benötigen das übergeordnete Element des Elements anpassen, um dessen transformierte Größe des Elements. Beachten Sie, dass bei Verwendung mit werden die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Eigenschaft <xref:System.Windows.Media.TranslateTransform> Objekte haben keine Auswirkungen auf die Elemente angezeigt werden. Das liegt daran, dass das Layoutsystem das übersetzte Element an seiner ursprünglichen Position als Teil der Verarbeitung zurückgibt.  
  
 Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md) (Übersicht).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Beispiel: Drehen eines FrameworkElement um 45 Grad  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf eine Schaltfläche im Uhrzeigersinn um 45 Grad zu drehen. Die Schaltfläche befindet sich einem <xref:System.Windows.Controls.StackPanel> , die zwei weitere Schaltflächen hat.  
  
 Standardmäßig eine <xref:System.Windows.Media.RotateTransform> dreht sich der Punkt (0, 0). Da im Beispiel kein Wert für den Mittelpunkt angegeben ist, wird die Schaltfläche um den Punkt (0, 0) gedreht, d.h. um die linke obere Ecke. Die <xref:System.Windows.Media.RotateTransform> gilt, an die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "Graphicsmm_RenderTransformWithDefaultCenter")  
Drehung im Uhrzeigersinn um 45 Grad von der oberen linken Ecke  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Im nächste Beispiel verwendet auch eine <xref:System.Windows.Media.RotateTransform> auf eine Schaltfläche um 45 Grad im Uhrzeigersinn, sondern auch drehen, setzt der <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf (0.5, 0.5). Der Wert des der <xref:System.Windows.UIElement.RenderTransformOrigin%2A> Eigenschaft ist relativ zur Größe der Schaltfläche. Daher wird die Drehung auf die Mitte der Schaltfläche und nicht auf deren obere linke Ecke angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "Graphicsmm_RenderTransformRelativeCenter")  
Drehung im Uhrzeigersinn um 45 Grad um die Mitte  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft anstelle der <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft zum Drehen der Schaltfläche.  Dies bewirkt, dass sich die Transformation auf das Layout der Schaltfläche auswirkt, was einen vollständigen Durchlauf des Layoutsystems auslöst. Die Schaltfläche wird dann gedreht und anschließend neu positioniert, da ihre Größe geändert wurde. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit LayoutTransform transformierte Schaltfläche](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "Graphicsmm_LayoutTransform")  
LayoutTransform wird zum Drehen der Schaltfläche verwendet  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animieren von Transformationen  
 Da sie von erben die <xref:System.Windows.Media.Animation.Animatable> -Klasse, die <xref:System.Windows.Media.Transform> Klassen animiert werden können. Zum Animieren einer <xref:System.Windows.Media.Transform>, wenden Sie die Animation eines kompatiblen Typs auf die Eigenschaft, die Sie animieren möchten.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.DoubleAnimation> mit einer <xref:System.Windows.Media.RotateTransform> vornehmen einer <xref:System.Windows.Controls.Button> Drehfeld vorhanden, wenn darauf geklickt wird.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252). Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 Da es erbt die <xref:System.Windows.Freezable> -Klasse, die <xref:System.Windows.Media.Transform> Klasse mehrere spezielle Features bereit: <xref:System.Windows.Media.Transform> als Objekte deklariert werden [Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md), von mehreren Objekten, die schreibgeschützt zur Verbesserung der freigegebenen Leistung, geklont und threadsicher gemacht. Weitere Informationen zu den verschiedenen Funktionen, die von bereitgestellten <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Matrix>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [Beispiel für 2D-Transformationen](https://go.microsoft.com/fwlink/?LinkID=158252)
