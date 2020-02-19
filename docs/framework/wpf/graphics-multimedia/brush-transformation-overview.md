---
title: Übersicht über Pinseltransformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 1d3a56014e0975f3616b7f90021b4290ced5daab
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453129"
---
# <a name="brush-transformation-overview"></a>Übersicht über Pinseltransformationen
Die Brush-Klasse stellt zwei Transformations Eigenschaften bereit: <xref:System.Windows.Media.Brush.Transform%2A> und <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Diese Eigenschaften ermöglichen Ihnen den Inhalt eines Pinsels zu drehen, zu skalieren, zu neigen und zu übersetzen. Dieses Thema beschreibt die  Unterschiede zwischen diesen beiden Eigenschaften sowie Beispiele für deren Verwendung.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Um dieses Thema zu verstehen, sollten Sie die Features des Pinsels kennen, den Sie transformieren. <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush>finden Sie unter [Übersicht über das Zeichnen mit voll Tonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md). Informationen zu <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>oder <xref:System.Windows.Media.VisualBrush>finden Sie unterzeichnen [mit Bildern, Zeichnungen und visuellen](painting-with-images-drawings-and-visuals.md)Elementen. Sie sollten auch mit den 2D- Transformationen, die unter  [Übersicht über Transformationen](transforms-overview.md) beschrieben werden, vertraut sein.  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Unterschiede zwischen den Eigenschaften Transform und RelativeTransform  
 Wenn Sie eine Transformation auf die <xref:System.Windows.Media.Brush.Transform%2A>-Eigenschaft eines Pinsels anwenden, müssen Sie die Größe des gezeichneten Bereichs kennen, wenn Sie den Pinsel Inhalt über seinen Mittelpunkt transformieren möchten. Angenommen, der gezeichnete Bereich ist 200 geräteunabhängige Pixel breit und 150 hoch.  Wenn Sie eine <xref:System.Windows.Media.RotateTransform> verwendet haben, um die Ausgabe des Pinsels um 45 Grad um den Mittelpunkt zu drehen, würden Sie dem <xref:System.Windows.Media.RotateTransform> einen <xref:System.Windows.Media.RotateTransform.CenterX%2A> 100 und einen <xref:System.Windows.Media.RotateTransform.CenterY%2A> 75 geben.  
  
 Wenn Sie eine Transformation auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>-Eigenschaft eines Pinsels anwenden, wird diese Transformation auf den Pinsel angewendet, bevor die Ausgabe dem gezeichneten Bereich zugeordnet wird. Die folgende Liste beschreibt die Reihenfolge, in welcher der Inhalt eines Pinsels verarbeitet und transformiert wird.  
  
1. Verarbeiten Sie den Inhalt des Pinsels. Bei einem <xref:System.Windows.Media.GradientBrush>bedeutet dies, dass der Farbverlaufs Bereich bestimmt wird. Bei einer <xref:System.Windows.Media.TileBrush>wird die <xref:System.Windows.Media.TileBrush.Viewbox%2A> der <xref:System.Windows.Media.TileBrush.Viewport%2A>zugeordnet. Dies ergibt die Ausgabe des Pinsels.  
  
2. Projizieren Sie die Ausgabe des Pinsels auf das 1 x 1-Transformationsrechteck.  
  
3. Wenden Sie den <xref:System.Windows.Media.Brush.RelativeTransform%2A>des Pinsels an, wenn dieser über einen verfügt.  
  
4. Projizieren Sie die transformierte Ausgabe auf den zu zeichnenden Bereich.  
  
5. Wenden Sie den <xref:System.Windows.Media.Transform>des Pinsels an, wenn dieser über einen verfügt.  
  
 Da die <xref:System.Windows.Media.Brush.RelativeTransform%2A> angewendet wird, während die Ausgabe des Pinsels einem 1 x 1-Rechteck zugeordnet ist, scheinen die Werte für Transform Center und Offset relativ zu sein. Wenn Sie z. b. eine <xref:System.Windows.Media.RotateTransform> verwendet haben, um die Ausgabe des Pinsels um 45 Grad um den Mittelpunkt zu drehen, würden Sie dem <xref:System.Windows.Media.RotateTransform> einen <xref:System.Windows.Media.RotateTransform.CenterX%2A> 0,5 und einen <xref:System.Windows.Media.RotateTransform.CenterY%2A> 0,5 geben.  
  
 Die folgende Abbildung zeigt die Ausgabe mehrerer Pinsel, die mit den Eigenschaften <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A> um 45 Grad gedreht wurden.  
  
 ![RelativeTransform-und Transform-Eigenschaften](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Verwenden von RelativeTransform mit einem TileBrush-Objekt  
 Da Kachel Pinsel komplexer als andere Pinsel sind, kann das Anwenden einer <xref:System.Windows.Media.Brush.RelativeTransform%2A> auf eine unerwartete Ergebnisse verursachen. Ziehen Sie z.B. die folgende Abbildung heran.  
  
 ![Das Quell Image](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.ImageBrush> verwendet, um einen rechteckigen Bereich mit dem vorangehenden Bild zu zeichnen. Er wendet eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>-Eigenschaft des <xref:System.Windows.Media.ImageBrush> Objekts an und legt seine <xref:System.Windows.Media.TileBrush.Stretch%2A>-Eigenschaft auf <xref:System.Windows.Media.Stretch.UniformToFill>fest. dabei sollte das Seitenverhältnis des Bilds beibehalten werden, wenn es gestreckt wird, um das Rechteck vollständig auszufüllen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
 ![Die transformierte Ausgabe](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Beachten Sie, dass das Bild verzerrt ist, obwohl der <xref:System.Windows.Media.TileBrush.Stretch%2A> des Pinsels auf <xref:System.Windows.Media.Stretch.UniformToFill>festgelegt wurde. Das liegt daran, dass die relative Transformation angewendet wird, nachdem die <xref:System.Windows.Media.TileBrush.Viewbox%2A> des Pinsels der <xref:System.Windows.Media.TileBrush.Viewport%2A>zugeordnet ist. In der folgenden Liste werden die einzelnen Schritte des Prozesses beschrieben:  
  
1. Projizieren Sie den Inhalt des Pinsels (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) mithilfe der <xref:System.Windows.Media.TileBrush.Stretch%2A> Einstellung des Pinsels auf seine Basis Kachel (<xref:System.Windows.Media.TileBrush.Viewport%2A>).  
  
     ![Die Viewbox auf den Viewport anpassen](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Projizieren Sie die Basiskachel auf das 1 x 1-Transformationsrechteck.  
  
     ![Zuordnen des Viewports zum Transformations Rechteck](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Wenden Sie die <xref:System.Windows.Media.RotateTransform>an.  
  
     ![Relative Transformation anwenden](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Projizieren Sie die transformierte Basiskachel auf den zu zeichnenden Bereich.  
  
     ![Projizieren Sie den transformierten Pinsel auf den Ausgabebereich.](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Beispiel: Drehen eines ImageBrush um 45 Grad  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>-Eigenschaft eines <xref:System.Windows.Media.ImageBrush>angewendet. Die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> des <xref:System.Windows.Media.RotateTransform> Objekts sind auf 0,5 und die relativen Koordinaten des Mittelpunkts des Inhalts festgelegt. Als Folge, wird der Inhalt des Pinsels wird um seinen Mittelpunkt gedreht.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Im nächsten Beispiel wird außerdem eine <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Media.ImageBrush>angewendet, aber die <xref:System.Windows.Media.Brush.Transform%2A>-Eigenschaft anstelle der <xref:System.Windows.Media.Brush.RelativeTransform%2A>-Eigenschaft verwendet. Um den Pinsel um seinen Mittelpunkt zu drehen, müssen die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> des <xref:System.Windows.Media.RotateTransform> Objekts auf absolute Koordinaten festgelegt werden. Da das vom Pinsel gezeichnete Rechteck 175 mal 90 Pixel beträgt, liegt sein Mittelpunkt bei (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 In der folgenden Abbildung ist der Pinsel ohne Transformation dargestellt, wobei die Transformation auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>-Eigenschaft angewendet wird und die Transformation auf die <xref:System.Windows.Media.Brush.Transform%2A>-Eigenschaft angewendet wird.  
  
 ![RelativeTransform-und Transform-Einstellungen für den Pinsel](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Weitere Informationen zu Pinseln, finden Sie unter der [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Transformationen](transforms-overview.md)
