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
ms.openlocfilehash: 89b781d3e5b88a66598a301a1d08cf7dfedd57a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962900"
---
# <a name="transforms-overview"></a>Übersicht über Transformationen
In diesem Thema wird beschrieben, wie Sie mit den <xref:System.Windows.Media.Transform> 2D-Klassen <xref:System.Windows.FrameworkElement> Objekte drehen, skalieren, verschieben (übersetzen) und neigen.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>Was ist eine Transformation?  
 Eine <xref:System.Windows.Media.Transform> definiert, wie Punkte von einem Koordinaten Bereich zu einem anderen Koordinaten Bereich zugeordnet oder transformiert werden. Diese Zuordnung wird durch eine Transformation <xref:System.Windows.Media.Matrix>beschrieben, bei der es sich um eine Sammlung von drei Zeilen mit drei Spalten von <xref:System.Double> Werten handelt.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF) verwendet Zeilen hauptmatrizen. Vektoren werden als Zeilenvektoren und nicht als Spaltenvektoren ausgedrückt.  
  
 In der folgenden Tabelle wird die Struktur für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Matrix dargestellt.  
  
### <a name="a-2-d-transformation-matrix"></a>2D-Transformationsmatrix  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Standard: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Standard: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Standard: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Standard: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Standard: 0.0|1.0|  
  
 Durch Bearbeiten der Matrixwerte können Sie ein Objekt drehen, skalieren, neigen und verschieben (übersetzen). Wenn Sie z. b. den Wert in der ersten Spalte der dritten Zeile (den <xref:System.Windows.Media.Matrix.OffsetX%2A> Wert) in 100 ändern, können Sie ihn verwenden, um ein Objekt 100-Einheiten entlang der x-Achse zu verschieben. Wenn Sie den Wert in der zweiten Spalte der zweiten Zeile in 3 ändern, können Sie ein Objekt um das Dreifache seiner aktuellen Höhe strecken. Wenn Sie beide Werte ändern, wird das Objekt 100 Einheiten entlang der x-Achse verschoben und seine Höhe wird um den Faktor 3 gestreckt. Da Windows Presentation Foundation (WPF) nur affine Transformationen unterstützt, lauten die Werte in der rechten Spalte immer 0, 0, 1.  
  
 Obwohl Windows Presentation Foundation (WPF) es Ihnen ermöglicht, Matrix Werte direkt zu bearbeiten, stellt es <xref:System.Windows.Media.Transform> auch mehrere Klassen bereit, die es Ihnen ermöglichen, ein Objekt zu transformieren, ohne zu wissen, wie die zugrunde liegende Matrixstruktur konfiguriert ist. Beispielsweise können Sie <xref:System.Windows.Media.ScaleTransform> mit der-Klasse ein Objekt skalieren, indem <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> Sie <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> die-Eigenschaft und die-Eigenschaft festlegen, anstatt eine Transformationsmatrix zu manipulieren. Entsprechend können Sie <xref:System.Windows.Media.RotateTransform> mithilfe der-Klasse ein Objekt drehen, indem Sie einfach <xref:System.Windows.Media.RotateTransform.Angle%2A> seine-Eigenschaft festlegen.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Transformationsklassen  
 Windows Presentation Foundation (WPF) stellt die folgenden 2D <xref:System.Windows.Media.Transform> -Klassen für allgemeine Transformations Vorgänge bereit:  
  
|Klasse|Beschreibung|Beispiel|Darstellung|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Dreht ein Element um das angegebene <xref:System.Windows.Media.RotateTransform.Angle%2A>-Element.|[Drehen eines Objekts](how-to-rotate-an-object.md)|![Abbildung drehen](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Skaliert ein Element anhand der <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> angegebenen <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> -und-Beträge.|[Skalieren eines Elements](how-to-scale-an-element.md)|![Abbildung skalieren](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Vergrenzt ein Element um die angegebenen <xref:System.Windows.Media.SkewTransform.AngleX%2A> - <xref:System.Windows.Media.SkewTransform.AngleY%2A> und-Beträge.|[Neigen eines Elements](how-to-skew-an-element.md)|![Abbildung neigen](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Verschiebt (übersetzt) ein Element durch die angegebene <xref:System.Windows.Media.TranslateTransform.X%2A> - <xref:System.Windows.Media.TranslateTransform.Y%2A> und-Menge.|[Übersetzen eines Elements](how-to-translate-an-element.md)|![Abbildung verschieben](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Zum Erstellen komplexerer Transformationen bietet Windows Presentation Foundation (WPF) die folgenden beiden Klassen:  
  
|Klasse|Beschreibung|Beispiel|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Gruppiert mehrere <xref:System.Windows.Media.TransformGroup> -Objekte in einem <xref:System.Windows.Media.Transform> einzelnen, das Sie dann auf Transformations Eigenschaften anwenden können.|[Anwenden mehrerer Transformationen auf ein Objekt](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Erstellt benutzerdefinierte Transformationen, die nicht von den anderen <xref:System.Windows.Media.Transform> Klassen bereitgestellt werden. Wenn Sie einen <xref:System.Windows.Media.MatrixTransform>verwenden, bearbeiten Sie eine Matrix direkt.|[Verwenden von MatrixTransform zum Erstellen benutzerdefinierter Transformationen](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) bietet auch 3D-Transformationen. Weitere Informationen finden Sie in den Ausführungen zur <xref:System.Windows.Media.Media3D.Transform3D>-Klasse.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Allgemeine Transformationseigenschaften  
 Eine Möglichkeit zum Transformieren eines Objekts besteht darin, den entsprechenden <xref:System.Windows.Media.Transform> Typ zu deklarieren und ihn auf die Transformations Eigenschaft des Objekts anzuwenden. Verschiedene Typen von Objekten haben unterschiedliche Typen von Transformationseigenschaften. In der folgenden Tabelle werden mehrere häufig verwendete Windows Presentation Foundation Typen (WPF) und ihre Transformations Eigenschaften aufgelistet.  
  
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
 Beim Transformieren eines Objekts wird nicht nur das Objekt transformiert, sondern auch der Koordinatenbereich, in dem dieses Objekt vorhanden ist. Standardmäßig wird eine Transformation am Ursprung des Koordinatensystems des Zielobjekts zentriert: (0,0). Die einzige Ausnahme ist <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform> , dass keine Center-Eigenschaften festgelegt werden können, da der Übersetzungseffekt unabhängig davon, wo er zentriert ist, identisch ist.  
  
 Im folgenden Beispiel wird verwendet <xref:System.Windows.Media.RotateTransform> , um ein <xref:System.Windows.Shapes.Rectangle> - <xref:System.Windows.FrameworkElement>Element, einen Typ, um 45 Grad um das Standard Zentrum (0,0) zu drehen. Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Ein FrameworkElement gedreht um 45 Grad &#40;um 0,&#41; 0](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Ein in 45-Grad-Schritten um den Punkt (0,0) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 In der Standardeinstellung dreht das Element um seine obere linke Ecke (0, 0). Die <xref:System.Windows.Media.RotateTransform>Klassen <xref:System.Windows.Media.ScaleTransform>, und<xref:System.Windows.Media.SkewTransform> stellen CenterX-und CenterY-Eigenschaften bereit, mit denen Sie den Punkt angeben können, an dem die Transformation angewendet wird.  
  
 Im nächsten Beispiel wird ein- <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Shapes.Rectangle> Element ebenfalls um 45 Grad gedreht. <xref:System.Windows.Media.RotateTransform.CenterX%2A> allerdings werden die-Eigenschaft und <xref:System.Windows.Media.RotateTransform.CenterY%2A> die-Eigenschaft so festgelegt <xref:System.Windows.Media.RotateTransform> , dass die über einen Mittelpunkt von (25, 25) verfügt. Die folgende Abbildung veranschaulicht die Drehung.  
  
 ![Eine Geometrie gedreht um 45 Grad &#40;um 25,&#41; 25](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Ein in 45-Grad-Schritten um den Punkt (25, 25) gedrehtes Rechteck-Element  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Transformieren eines FrameworkElement  
 Wenn Sie Transformationen auf eine <xref:System.Windows.FrameworkElement>anwenden möchten, <xref:System.Windows.Media.Transform> erstellen Sie eine und wenden Sie auf eine der beiden Eigenschaften <xref:System.Windows.FrameworkElement> an, die die-Klasse bereitstellt:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>– Eine Transformation, die vor dem Layoutdurchlauf angewendet wird. Nachdem die Transformation angewendet wurde, verarbeitet das Layoutsystem die transformierte Größe und Position des Elements.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>– Eine Transformation, die die Darstellung des Elements ändert, jedoch angewendet wird, nachdem der Layoutdurchlauf abgeschlossen wurde. Wenn Sie die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft anstelle der <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft verwenden, können Sie Leistungsvorteile erzielen.  
  
 Welche Eigenschaft sollte verwendet werden? Aufgrund der Leistungsvorteile, die es bietet, verwenden Sie <xref:System.Windows.UIElement.RenderTransform%2A> die-Eigenschaft, wann immer dies möglich ist <xref:System.Windows.Media.Transform> , insbesondere bei der Verwendung animierter Objekte. Verwenden Sie <xref:System.Windows.FrameworkElement.LayoutTransform%2A> die-Eigenschaft, wenn skaliert, gedreht oder verzerrt wird und das übergeordnete Element des Elements an die transformierte Größe des Elements angepasst werden muss. Beachten Sie, dass Objekte, die mit der <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft <xref:System.Windows.Media.TranslateTransform> verwendet werden, anscheinend keine Auswirkung auf-Elemente haben. Das liegt daran, dass das Layoutsystem das übersetzte Element an seiner ursprünglichen Position als Teil der Verarbeitung zurückgibt.  
  
 Weitere Informationen zum Layout in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] finden Sie unter [Layout](../advanced/layout.md) (Übersicht).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Beispiel: Drehen eines FrameworkElement-45-Grades  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.RotateTransform> verwendet, um eine Schaltfläche um 45 Grad im Uhrzeigersinn zu drehen. Die Schaltfläche ist in einer <xref:System.Windows.Controls.StackPanel> enthalten, die über zwei andere Schaltflächen verfügt.  
  
 Standardmäßig <xref:System.Windows.Media.RotateTransform> dreht sich um den Punkt (0,0). Da im Beispiel kein Wert für den Mittelpunkt angegeben ist, wird die Schaltfläche um den Punkt (0, 0) gedreht, d.h. um die linke obere Ecke. Der <xref:System.Windows.Media.RotateTransform> wird auf die <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit RenderTransform transformierte Schaltfläche](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Drehung im Uhrzeigersinn um 45 Grad von der oberen linken Ecke  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 Im nächsten Beispiel wird auch ein <xref:System.Windows.Media.RotateTransform> verwendet, um eine Schaltfläche 45 Grad im Uhrzeigersinn zu drehen <xref:System.Windows.UIElement.RenderTransformOrigin%2A> , aber auch die der Schaltfläche wird auf (0,5, 0,5) festgelegt. Der Wert <xref:System.Windows.UIElement.RenderTransformOrigin%2A> der-Eigenschaft ist relativ zur Größe der Schaltfläche. Daher wird die Drehung auf die Mitte der Schaltfläche und nicht auf deren obere linke Ecke angewendet. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine umgewandelte Schaltfläche über den Mittelpunkt](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Drehung im Uhrzeigersinn um 45 Grad um die Mitte  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.FrameworkElement.LayoutTransform%2A> -Eigenschaft anstelle der <xref:System.Windows.UIElement.RenderTransform%2A> -Eigenschaft verwendet, um die Schaltfläche zu drehen.  Dies bewirkt, dass sich die Transformation auf das Layout der Schaltfläche auswirkt, was einen vollständigen Durchlauf des Layoutsystems auslöst. Die Schaltfläche wird dann gedreht und anschließend neu positioniert, da ihre Größe geändert wurde. In der folgenden Abbildung wird das Ergebnis der Transformation dargestellt.  
  
 ![Eine mit LayoutTransform transformierte Schaltfläche](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
LayoutTransform wird zum Drehen der Schaltfläche verwendet  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animieren von Transformationen  
 Da Sie von der <xref:System.Windows.Media.Animation.Animatable> -Klasse erben, können die <xref:System.Windows.Media.Transform> Klassen animiert werden. Um einen <xref:System.Windows.Media.Transform>zu animieren, wenden Sie eine Animation eines kompatiblen Typs auf die Eigenschaft an, die Sie animieren möchten.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.Storyboard> -und <xref:System.Windows.Media.Animation.DoubleAnimation> ein- <xref:System.Windows.Media.RotateTransform> Wert mit einem <xref:System.Windows.Controls.Button> -Wert verwendet, um beim Klicken auf einen Drehort zu sorgen.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252). Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animationen](animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Funktionen von Freezable-Objekten  
 <xref:System.Windows.Freezable> Da Sie von der-Klasse erbt, bietet die <xref:System.Windows.Media.Transform> -Klasse mehrere besondere <xref:System.Windows.Media.Transform> Features: Objekte können als [Ressourcen](../advanced/xaml-resources.md)deklariert, von mehreren Objekten gemeinsam genutzt und schreibgeschützt werden, um die Leistung zu verbessern, geklont zu werden. Thread sicher. Weitere Informationen zu den verschiedenen Funktionen, die von <xref:System.Windows.Freezable> -Objekten bereitgestellt werden, finden Sie in der [Übersicht über](../advanced/freezable-objects-overview.md)frei wählbare Objekte.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Themen zu Vorgehensweisen](transformations-how-to-topics.md)
- [Beispiel für 2D-Transformationen](https://go.microsoft.com/fwlink/?LinkID=158252)
