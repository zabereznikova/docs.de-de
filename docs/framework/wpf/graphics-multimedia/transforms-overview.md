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
ms.openlocfilehash: ead1d114f773cba88e8b3e20f395019fbde3ee15
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458594"
---
# <a name="transforms-overview"></a>Übersicht über Transformationen
In diesem Thema wird beschrieben, wie <xref:System.Windows.FrameworkElement> Objekten mithilfe der 2D-<xref:System.Windows.Media.Transform> Klassen gedreht, skaliert, verschoben (übersetzt) und verzerrt werden.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Was ist eine Transformation?  
 Ein <xref:System.Windows.Media.Transform> der definiert, wie Punkte von einem Koordinaten Bereich zu einem anderen Koordinaten Bereich zugeordnet oder transformiert werden. Diese Zuordnung wird durch eine Transformations <xref:System.Windows.Media.Matrix>beschrieben, bei der es sich um eine Sammlung von drei Zeilen mit drei Spalten mit <xref:System.Double> Werten handelt.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF) verwendet Zeilen hauptmatrizen. Vektoren werden als Zeilenvektoren und nicht als Spaltenvektoren ausgedrückt.  
  
 In der folgenden Tabelle wird die Struktur für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Matrix dargestellt.  
  
### <a name="a-2-d-transformation-matrix"></a>2D-Transformationsmatrix  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Standard: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Standard: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Standard: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Standard: 0.0|1,0|  
  
 Durch Bearbeiten der Matrixwerte können Sie ein Objekt drehen, skalieren, neigen und verschieben (übersetzen). Wenn Sie z. b. den Wert in der ersten Spalte der dritten Zeile (den <xref:System.Windows.Media.Matrix.OffsetX%2A> Wert) in 100 ändern, können Sie ihn verwenden, um ein Objekt 100-Einheiten entlang der x-Achse zu verschieben. Wenn Sie den Wert in der zweiten Spalte der zweiten Zeile in 3 ändern, können Sie ein Objekt um das Dreifache seiner aktuellen Höhe strecken. Wenn Sie beide Werte ändern, wird das Objekt 100 Einheiten entlang der x-Achse verschoben und seine Höhe wird um den Faktor 3 gestreckt. Da Windows Presentation Foundation (WPF) nur affine Transformationen unterstützt, lauten die Werte in der rechten Spalte immer 0, 0, 1.  
  
 Obwohl Windows Presentation Foundation (WPF) es Ihnen ermöglicht, Matrix Werte direkt zu bearbeiten, bietet es auch mehrere <xref:System.Windows.Media.Transform> Klassen, die es Ihnen ermöglichen, ein Objekt zu transformieren, ohne zu wissen, wie die zugrunde liegende Matrixstruktur konfiguriert ist. Beispielsweise können Sie mit der <xref:System.Windows.Media.ScaleTransform>-Klasse ein Objekt skalieren, indem Sie dessen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Eigenschaften festlegen, anstatt eine Transformationsmatrix zu manipulieren. Entsprechend können Sie mit der <xref:System.Windows.Media.RotateTransform>-Klasse ein Objekt drehen, indem Sie einfach seine <xref:System.Windows.Media.RotateTransform.Angle%2A>-Eigenschaft festlegen.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Transformationsklassen  
 Windows Presentation Foundation (WPF) stellt die folgenden 2D-<xref:System.Windows.Media.Transform> Klassen für allgemeine Transformations Vorgänge bereit:  
  
|Klasse|Beschreibung|Beispiel|Darstellung|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Dreht ein Element um den angegebenen <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Drehen eines Objekts](how-to-rotate-an-object.md)|![Abbildung drehen](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Skaliert ein Element anhand des angegebenen <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> und <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> Beträge.|[Skalieren eines Elements](how-to-scale-an-element.md)|![Abbildung skalieren](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Vergrenzt ein Element um den angegebenen <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A> Beträge.|[Neigen eines Elements](how-to-skew-an-element.md)|![Darstellung der Schiefe](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Verschiebt (übersetzt) ein Element durch die angegebene <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Beträge.|[Übersetzen eines Elements](how-to-translate-an-element.md)|![Darstellung übersetzen](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Zum Erstellen komplexerer Transformationen bietet Windows Presentation Foundation (WPF) die folgenden beiden Klassen:  
  
|Klasse|Beschreibung|Beispiel|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Gruppiert mehrere <xref:System.Windows.Media.TransformGroup> Objekte in einem einzelnen <xref:System.Windows.Media.Transform>, das Sie dann auf Transformations Eigenschaften anwenden können.|[Anwenden mehrerer Transformationen auf ein Objekt](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Erstellt benutzerdefinierte Transformationen, die nicht von den anderen <xref:System.Windows.Media.Transform>-Klassen bereitgestellt werden. Wenn Sie ein <xref:System.Windows.Media.MatrixTransform>verwenden, bearbeiten Sie eine Matrix direkt.|[Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) bietet auch 3D-Transformationen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.Media3D.Transform3D>-Klasse.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Allgemeine Transformationseigenschaften  
 Eine Möglichkeit zum Transformieren eines Objekts besteht darin, den entsprechenden <xref:System.Windows.Media.Transform> Typ zu deklarieren und ihn auf die Transformations Eigenschaft des-Objekts anzuwenden. Verschiedene Typen von Objekten haben unterschiedliche Typen von Transformationseigenschaften. In der folgenden Tabelle werden mehrere häufig verwendete Windows Presentation Foundation Typen (WPF) und ihre Transformations Eigenschaften aufgelistet.  
  
|Geben Sie Folgendes ein:|Transformationseigenschaften|  
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
 Beim Transformieren eines Objekts wird nicht nur das Objekt transformiert, sondern auch der Koordinatenbereich, in dem dieses Objekt vorhanden ist. Standardmäßig wird eine Transformation am Ursprung des Koordinatensystems des Zielobjekts zentriert: (0,0). Die einzige Ausnahme ist <xref:System.Windows.Media.TranslateTransform>. ein <xref:System.Windows.Media.TranslateTransform> hat keine Center-Eigenschaften festgelegt, da der Übersetzungseffekt unabhängig davon, wo er zentriert ist, identisch ist.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.RotateTransform> verwendet, um ein <xref:System.Windows.Shapes.Rectangle> Element, einen Typ von <xref:System.Windows.FrameworkElement>, um 45 Grad um das Standard Zentrum (0,0) zu drehen. Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Ein um &#40;0,0&#41; in 45-Grad-Schritten gedrehtes FrameworkElement](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Ein in 45-Grad-Schritten um den Punkt (0,0) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 In der Standardeinstellung dreht das Element um seine obere linke Ecke (0, 0). Die Klassen <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>und <xref:System.Windows.Media.SkewTransform> stellen CenterX-und CenterY-Eigenschaften bereit, die es Ihnen ermöglichen, den Punkt anzugeben, an dem die Transformation angewendet wird.  
  
 Im nächsten Beispiel wird auch ein <xref:System.Windows.Media.RotateTransform> verwendet, um ein <xref:System.Windows.Shapes.Rectangle> Element um 45 Grad zu drehen. Diesmal werden jedoch die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> so festgelegt, dass die <xref:System.Windows.Media.RotateTransform> über einen Mittelpunkt (25, 25) verfügt. Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Eine um &#40;25, 25&#41; in 45-Grad-Schritten gedrehte Geometrie](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Ein in 45-Grad-Schritten um den Punkt (25, 25) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Transformieren eines FrameworkElement  
 Wenn Sie Transformationen auf eine <xref:System.Windows.FrameworkElement>anwenden möchten, erstellen Sie eine <xref:System.Windows.Media.Transform>, und wenden Sie Sie auf eine der beiden Eigenschaften an, die die <xref:System.Windows.FrameworkElement>-Klasse bereitstellt:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A> – eine Transformation, die vor dem Layoutdurchlauf angewendet wird. Nachdem die Transformation angewendet wurde, verarbeitet das Layoutsystem die transformierte Größe und Position des Elements.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A> – eine Transformation, die die Darstellung des Elements ändert, aber nach Abschluss des Layoutdurchlaufs angewendet wird. Wenn Sie die <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft anstelle der <xref:System.Windows.FrameworkElement.LayoutTransform%2A>-Eigenschaft verwenden, können Sie Leistungsvorteile erzielen.  
  
 Welche Eigenschaft sollte verwendet werden? Aufgrund der Leistungsvorteile, die es bietet, sollten Sie die <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft verwenden, wann immer dies möglich ist, insbesondere, wenn Sie animierte <xref:System.Windows.Media.Transform> Objekte verwenden. Verwenden Sie die <xref:System.Windows.FrameworkElement.LayoutTransform%2A>-Eigenschaft, wenn skaliert, gedreht oder verzerrt wird und das übergeordnete Element des Elements an die transformierte Größe des Elements angepasst werden muss. Beachten Sie, dass, wenn Sie mit der <xref:System.Windows.FrameworkElement.LayoutTransform%2A>-Eigenschaft verwendet werden, <xref:System.Windows.Media.TranslateTransform> Objekte anscheinend keine Auswirkung auf Elemente haben. Das liegt daran, dass das Layoutsystem das übersetzte Element an seiner ursprünglichen Position als Teil der Verarbeitung zurückgibt.  
  
 Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../advanced/layout.md) (Übersicht).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Beispiel: Drehen eines FrameworkElement um 45 Grad  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.RotateTransform> verwendet, um eine Schaltfläche um 45 Grad im Uhrzeigersinn zu drehen. Die Schaltfläche ist in einem <xref:System.Windows.Controls.StackPanel> enthalten, das über zwei andere Schaltflächen verfügt.  
  
 Standardmäßig wird ein <xref:System.Windows.Media.RotateTransform> um den Punkt (0, 0) rotiert. Da im Beispiel kein Wert für den Mittelpunkt angegeben ist, wird die Schaltfläche um den Punkt (0, 0) gedreht, d.h. um die linke obere Ecke. Der <xref:System.Windows.Media.RotateTransform> wird auf die <xref:System.Windows.UIElement.RenderTransform%2A>-Eigenschaft angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Drehung im Uhrzeigersinn um 45 Grad von der oberen linken Ecke  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Im nächsten Beispiel wird auch ein <xref:System.Windows.Media.RotateTransform> verwendet, um eine Schaltfläche 45 Grad im Uhrzeigersinn zu drehen, aber auch die <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der Schaltfläche auf (0,5, 0,5) festgelegt. Der Wert der <xref:System.Windows.UIElement.RenderTransformOrigin%2A>-Eigenschaft ist relativ zur Größe der Schaltfläche. Daher wird die Drehung auf die Mitte der Schaltfläche und nicht auf deren obere linke Ecke angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine um ihren Mittelpunkt transformierte Schaltfläche](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Drehung im Uhrzeigersinn um 45 Grad um die Mitte  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Im folgenden Beispiel wird die-Schaltfläche mit der <xref:System.Windows.FrameworkElement.LayoutTransform%2A>-Eigenschaft anstelle der Eigenschaft <xref:System.Windows.UIElement.RenderTransform%2A> verwendet.  Dies bewirkt, dass sich die Transformation auf das Layout der Schaltfläche auswirkt, was einen vollständigen Durchlauf des Layoutsystems auslöst. Die Schaltfläche wird dann gedreht und anschließend neu positioniert, da ihre Größe geändert wurde. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit LayoutTransform transformierte Schaltfläche](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
LayoutTransform wird zum Drehen der Schaltfläche verwendet  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animieren von Transformationen  
 Da Sie von der <xref:System.Windows.Media.Animation.Animatable>-Klasse erben, können die <xref:System.Windows.Media.Transform>-Klassen animiert werden. Um einen <xref:System.Windows.Media.Transform>zu animieren, wenden Sie eine Animation eines kompatiblen Typs auf die Eigenschaft an, die Sie animieren möchten.  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.Animation.Storyboard> und ein <xref:System.Windows.Media.Animation.DoubleAnimation> mit einem-<xref:System.Windows.Media.RotateTransform> verwendet, um eine <xref:System.Windows.Controls.Button> beim Klicken auf das Drehfeld zu bringen.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252). Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 Da es von der <xref:System.Windows.Freezable>-Klasse erbt, bietet die <xref:System.Windows.Media.Transform>-Klasse mehrere besondere Features: <xref:System.Windows.Media.Transform> Objekte können als [Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)deklariert, von mehreren Objekten gemeinsam genutzt und als schreibgeschützt festgestellt werden, um die Leistung zu verbessern, geklont und Thread sicher gemacht zu werden. Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> Objekten bereitgestellt werden, finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Themen zu Vorgehensweisen](transformations-how-to-topics.md)
- [Beispiel für 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252)
