---
title: Übersicht über Transformationen
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c5f29404a301eb023ff24b2890531dede6440ec4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111958"
---
# <a name="transforms-overview"></a>Übersicht über Transformationen
In diesem Thema wird beschrieben, wie die 2D-Klassen <xref:System.Windows.Media.Transform> zum <xref:System.Windows.FrameworkElement> Drehen, Skalieren, Verschieben (Übersetzen) und Verzerren von Objekten verwendet werden.  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>Was ist eine Transformation?  
 A <xref:System.Windows.Media.Transform> definiert, wie Punkte von einem Koordinatenraum zu einem anderen Koordinatenraum zugeordnet oder transformiert werden. Diese Zuordnung wird durch <xref:System.Windows.Media.Matrix>eine Transformation beschrieben, bei der <xref:System.Double> es sich um eine Auflistung von drei Zeilen mit drei Spalten mit Werten handelt.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF) verwendet Zeilen-Hauptmatrizen. Vektoren werden als Zeilenvektoren und nicht als Spaltenvektoren ausgedrückt.  
  
 In der folgenden Tabelle wird die Struktur für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Matrix dargestellt.  
  
### <a name="a-2d-transformation-matrix"></a>Eine 2D-Transformationsmatrix  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Standard: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Standard: 0.0|0,0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Standard: 1.0|0,0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Standard: 0.0|1.0|  
  
 Durch Bearbeiten der Matrixwerte können Sie ein Objekt drehen, skalieren, neigen und verschieben (übersetzen). Wenn Sie z. B. den Wert in der <xref:System.Windows.Media.Matrix.OffsetX%2A> ersten Spalte der dritten Zeile (den Wert) in 100 ändern, können Sie damit ein Objekt mit 100 Einheiten entlang der x-Achse verschieben. Wenn Sie den Wert in der zweiten Spalte der zweiten Zeile in 3 ändern, können Sie ein Objekt um das Dreifache seiner aktuellen Höhe strecken. Wenn Sie beide Werte ändern, wird das Objekt 100 Einheiten entlang der x-Achse verschoben und seine Höhe wird um den Faktor 3 gestreckt. Da Windows Presentation Foundation (WPF) nur affine Transformationen unterstützt, sind die Werte in der rechten Spalte immer 0, 0, 1.  
  
 Obwohl Windows Presentation Foundation (WPF) es Ihnen ermöglicht, <xref:System.Windows.Media.Transform> Matrixwerte direkt zu bearbeiten, bietet es auch mehrere Klassen, mit denen Sie ein Objekt transformieren können, ohne zu wissen, wie die zugrunde liegende Matrixstruktur konfiguriert ist. Mit der <xref:System.Windows.Media.ScaleTransform> Klasse können Sie z. B. ein Objekt skalieren, indem Sie seine <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften festlegen, anstatt eine Transformationsmatrix zu bearbeiten. Ebenso können <xref:System.Windows.Media.RotateTransform> Sie mit der Klasse ein <xref:System.Windows.Media.RotateTransform.Angle%2A> Objekt drehen, indem Sie nur seine Eigenschaft festlegen.  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>Transformationsklassen  
 Windows Presentation Foundation (WPF) stellt <xref:System.Windows.Media.Transform> die folgenden 2D-Klassen für allgemeine Transformationsvorgänge bereit:  
  
|Klasse|Beschreibung|Beispiel|Darstellung|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Dreht ein Element um <xref:System.Windows.Media.RotateTransform.Angle%2A>die angegebene .|[Drehen eines Objekts](how-to-rotate-an-object.md)|![Abbildung drehen](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Skaliert ein Element nach <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> den angegebenen Beträgen und Beträgen.|[Skalieren eines Elements](how-to-scale-an-element.md)|![Abbildung skalieren](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Verzerrt ein Element um <xref:System.Windows.Media.SkewTransform.AngleX%2A> die <xref:System.Windows.Media.SkewTransform.AngleY%2A> angegebenen Beträge und Beträge.|[Neigen eines Elements](how-to-skew-an-element.md)|![Abbildung neigen](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Verschiebt (übersetzt) ein Element <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform.Y%2A> um die angegebenen Beträge und Beträge.|[Übersetzen eines Elements](how-to-translate-an-element.md)|![Abbildung verschieben](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Zum Erstellen komplexerer Transformationen bietet Windows Presentation Foundation (WPF) die folgenden zwei Klassen:  
  
|Klasse|Beschreibung|Beispiel|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Gruppiert <xref:System.Windows.Media.TransformGroup> mehrere Objekte <xref:System.Windows.Media.Transform> in einem einzelnen Objekt, das Sie dann auf Transformationseigenschaften anwenden können.|[Anwenden mehrerer Transformationen auf ein Objekt](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Erstellt benutzerdefinierte Transformationen, die <xref:System.Windows.Media.Transform> von den anderen Klassen nicht bereitgestellt werden. Wenn Sie <xref:System.Windows.Media.MatrixTransform>eine verwenden, bearbeiten Sie eine Matrix direkt.|[Verwenden eines MatrixTransform-Objekts zum Erstellen benutzerdefinierter Transformationen](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) bietet auch 3D-Transformationen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.Media3D.Transform3D>-Klasse.  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>Allgemeine Transformationseigenschaften  
 Eine Möglichkeit zum Transformieren eines <xref:System.Windows.Media.Transform> Objekts besteht darin, den entsprechenden Typ zu deklarieren und ihn auf die Transformationseigenschaft des Objekts anzuwenden. Verschiedene Typen von Objekten haben unterschiedliche Typen von Transformationseigenschaften. In der folgenden Tabelle sind mehrere häufig verwendete Windows Presentation Foundation-Typen (WPF) und deren Transformationseigenschaften aufgeführt.  
  
|type|Transformationseigenschaften|  
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
 Beim Transformieren eines Objekts wird nicht nur das Objekt transformiert, sondern auch der Koordinatenbereich, in dem dieses Objekt vorhanden ist. Standardmäßig wird eine Transformation am Ursprung des Koordinatensystems des Zielobjekts zentriert: (0,0). Die einzige <xref:System.Windows.Media.TranslateTransform>Ausnahme ist ; a <xref:System.Windows.Media.TranslateTransform> hat keine Center-Eigenschaften festzulegen, da der Übersetzungseffekt unabhängig davon, wo er zentriert ist, identisch ist.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird <xref:System.Windows.Shapes.Rectangle> ein verwendet, <xref:System.Windows.FrameworkElement>um ein Element, einen Typ von , um 45 Grad um den Standardmittelpunkt (0, 0) zu drehen. Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Ein um &#40;0,0&#41; in 45-Grad-Schritten gedrehtes FrameworkElement](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Ein in 45-Grad-Schritten um den Punkt (0,0) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 In der Standardeinstellung dreht das Element um seine obere linke Ecke (0, 0). Die <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ScaleTransform>, <xref:System.Windows.Media.SkewTransform> und -klassen stellen CenterX- und CenterY-Eigenschaften bereit, mit denen Sie den Punkt angeben können, an dem die Transformation angewendet wird.  
  
 Im nächsten Beispiel <xref:System.Windows.Media.RotateTransform> wird auch <xref:System.Windows.Shapes.Rectangle> ein verwendet, um ein Element um 45 Grad zu drehen. Dieses Mal werden <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> jedoch die und <xref:System.Windows.Media.RotateTransform> Eigenschaften so festgelegt, dass der einen Mittelpunkt von (25, 25) hat. Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Eine um &#40;25, 25&#41; in 45-Grad-Schritten gedrehte Geometrie](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Ein in 45-Grad-Schritten um den Punkt (25, 25) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>Transformieren eines FrameworkElement  
 Um Transformationen auf <xref:System.Windows.FrameworkElement>eine <xref:System.Windows.Media.Transform> anzuwenden, erstellen Sie eine, und <xref:System.Windows.FrameworkElement> wenden Sie sie auf eine der beiden Eigenschaften an, die die Klasse bereitstellt:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>– Eine Transformation, die angewendet wird, bevor das Layout übergeben wird. Nachdem die Transformation angewendet wurde, verarbeitet das Layoutsystem die transformierte Größe und Position des Elements.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>– Eine Transformation, die die Darstellung des Elements ändert, aber angewendet wird, nachdem der Layoutdurchlauf abgeschlossen ist. Wenn Sie <xref:System.Windows.UIElement.RenderTransform%2A> die Eigenschaft <xref:System.Windows.FrameworkElement.LayoutTransform%2A> anstelle der Eigenschaft verwenden, können Sie Leistungsvorteile erzielen.  
  
 Welche Eigenschaft sollte verwendet werden? Aufgrund der dadurch bietenden Leistungsvorteile <xref:System.Windows.UIElement.RenderTransform%2A> verwenden Sie die Eigenschaft <xref:System.Windows.Media.Transform> nach Möglichkeit, insbesondere wenn Sie animierte Objekte verwenden. Verwenden <xref:System.Windows.FrameworkElement.LayoutTransform%2A> Sie die Eigenschaft beim Skalieren, Drehen oder Verzerren, und Sie benötigen das übergeordnete Element, um sich an die transformierte Größe des Elements anzupassen. Beachten Sie, dass <xref:System.Windows.FrameworkElement.LayoutTransform%2A> <xref:System.Windows.Media.TranslateTransform> Objekte bei der Verwendung mit der Eigenschaft keine Auswirkungen auf Elemente zu haben scheinen. Das liegt daran, dass das Layoutsystem das übersetzte Element an seiner ursprünglichen Position als Teil der Verarbeitung zurückgibt.  
  
 Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../advanced/layout.md) (Übersicht).  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Beispiel: Drehen eines FrameworkElement um 45 Grad  
 Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird eine verwendet, um eine Schaltfläche im Uhrzeigersinn um 45 Grad zu drehen. Die Schaltfläche ist <xref:System.Windows.Controls.StackPanel> in einer mit zwei weiteren Schaltflächen enthalten.  
  
 Standardmäßig dreht <xref:System.Windows.Media.RotateTransform> sich ein um den Punkt (0, 0). Da im Beispiel kein Wert für den Mittelpunkt angegeben ist, wird die Schaltfläche um den Punkt (0, 0) gedreht, d.h. um die linke obere Ecke. Der <xref:System.Windows.Media.RotateTransform> wird auf <xref:System.Windows.UIElement.RenderTransform%2A> die Eigenschaft angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Drehung im Uhrzeigersinn um 45 Grad von der oberen linken Ecke  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Im nächsten Beispiel <xref:System.Windows.Media.RotateTransform> wird auch eine Taste um 45 Grad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> im Uhrzeigersinn gedreht, aber auch die Schaltfläche auf (0,5, 0,5) festgelegt. Der Wert <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Eigenschaft ist relativ zur Größe der Schaltfläche. Daher wird die Drehung auf die Mitte der Schaltfläche und nicht auf deren obere linke Ecke angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Drehung im Uhrzeigersinn um 45 Grad um die Mitte  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Im folgenden Beispiel <xref:System.Windows.FrameworkElement.LayoutTransform%2A> wird die <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft anstelle der Eigenschaft zum Drehen der Schaltfläche verwendet.  Dies bewirkt, dass sich die Transformation auf das Layout der Schaltfläche auswirkt, was einen vollständigen Durchlauf des Layoutsystems auslöst. Die Schaltfläche wird dann gedreht und anschließend neu positioniert, da ihre Größe geändert wurde. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit LayoutTransform transformierte Schaltfläche](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
LayoutTransform wird zum Drehen der Schaltfläche verwendet  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>Animieren von Transformationen  
 Da sie von der <xref:System.Windows.Media.Animation.Animatable> Klasse <xref:System.Windows.Media.Transform> erben, können die Klassen animiert werden. Um eine <xref:System.Windows.Media.Transform>zu animieren, wenden Sie eine Animation eines kompatiblen Typs auf die Eigenschaft an, die Sie animieren möchten.  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.Storyboard> werden <xref:System.Windows.Media.Animation.DoubleAnimation> a <xref:System.Windows.Media.RotateTransform> und <xref:System.Windows.Controls.Button> a mit einem verwendet, um eine Drehung zu machen, wenn darauf geklickt wird.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms). Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Features von Freezable  
 Da sie von der <xref:System.Windows.Freezable> Klasse <xref:System.Windows.Media.Transform> erbt, bietet <xref:System.Windows.Media.Transform> die Klasse mehrere spezielle Features: Objekte können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt, schreibgeschützt gemacht werden, um die Leistung zu verbessern, geklont und threadsicher gemacht werden. Weitere Informationen zu den verschiedenen Features, die von <xref:System.Windows.Freezable> Objekten bereitgestellt werden, finden Sie in der Übersicht über [freisetzbare Objekte](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [How-to-Themen](transformations-how-to-topics.md)
- [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
