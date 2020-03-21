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
ms.openlocfilehash: deac1be2fd19703055b76af8173111b4453f0d6b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186526"
---
# <a name="brush-transformation-overview"></a>Übersicht über Pinseltransformationen
Die Brush-Klasse bietet <xref:System.Windows.Media.Brush.Transform%2A> zwei <xref:System.Windows.Media.Brush.RelativeTransform%2A>Transformationseigenschaften: und . Diese Eigenschaften ermöglichen Ihnen den Inhalt eines Pinsels zu drehen, zu skalieren, zu neigen und zu übersetzen. Dieses Thema beschreibt die  Unterschiede zwischen diesen beiden Eigenschaften sowie Beispiele für deren Verwendung.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie die Features des Pinsels kennen, den Sie transformieren. Für <xref:System.Windows.Media.LinearGradientBrush> <xref:System.Windows.Media.RadialGradientBrush>und , siehe [die Übersicht über Malerei mit Vollfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md). Für <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush>oder , siehe [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md). Sie sollten auch mit den 2D- Transformationen, die unter  [Übersicht über Transformationen](transforms-overview.md) beschrieben werden, vertraut sein.  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Unterschiede zwischen den Eigenschaften Transform und RelativeTransform  
 Wenn Sie eine Transformation auf <xref:System.Windows.Media.Brush.Transform%2A> die Eigenschaft eines Pinsels anwenden, müssen Sie die Größe des gezeichneten Bereichs kennen, wenn Sie den Pinselinhalt um seine Mitte transformieren möchten. Angenommen, der gezeichnete Bereich ist 200 geräteunabhängige Pixel breit und 150 hoch.  Wenn Sie <xref:System.Windows.Media.RotateTransform> eine verwendet haben, um die Ausgabe des Pinsels um <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.RotateTransform.CenterX%2A> 45 Grad um <xref:System.Windows.Media.RotateTransform.CenterY%2A> seine Mitte zu drehen, geben Sie die a von 100 und eine von 75.  
  
 Wenn Sie eine Transformation auf <xref:System.Windows.Media.Brush.RelativeTransform%2A> die Eigenschaft eines Pinsels anwenden, wird diese Transformation auf den Pinsel angewendet, bevor seine Ausgabe dem gezeichneten Bereich zugeordnet wird. Die folgende Liste beschreibt die Reihenfolge, in welcher der Inhalt eines Pinsels verarbeitet und transformiert wird.  
  
1. Verarbeiten Sie den Inhalt des Pinsels. Für <xref:System.Windows.Media.GradientBrush>eine bedeutet dies, dass die Farbverlaufsfläche bestimmt wird. Für <xref:System.Windows.Media.TileBrush>eine <xref:System.Windows.Media.TileBrush.Viewbox%2A> wird die der <xref:System.Windows.Media.TileBrush.Viewport%2A>zugeordnet. Dies ergibt die Ausgabe des Pinsels.  
  
2. Projizieren Sie die Ausgabe des Pinsels auf das 1 x 1-Transformationsrechteck.  
  
3. Wenden Sie den <xref:System.Windows.Media.Brush.RelativeTransform%2A>Pinsel an, wenn er einen hat.  
  
4. Projizieren Sie die transformierte Ausgabe auf den zu zeichnenden Bereich.  
  
5. Wenden Sie den <xref:System.Windows.Media.Transform>Pinsel an, wenn er einen hat.  
  
 Da <xref:System.Windows.Media.Brush.RelativeTransform%2A> die angewendet wird, während die Ausgabe des Pinsels einem Rechteck von 1 x 1 zugeordnet wird, scheinen die Transformationsmittelpunkt- und Versatzwerte relativ zu sein. Wenn Sie z. <xref:System.Windows.Media.RotateTransform> B. eine verwendet haben, um die Ausgabe des Pinsels <xref:System.Windows.Media.RotateTransform.CenterX%2A> um 45 <xref:System.Windows.Media.RotateTransform.CenterY%2A> Grad um seine Mitte zu drehen, geben Sie die <xref:System.Windows.Media.RotateTransform> a von 0,5 und eine von 0,5 an.  
  
 Die folgende Abbildung zeigt die Ausgabe mehrerer Pinsel, die mit <xref:System.Windows.Media.Brush.RelativeTransform%2A> den <xref:System.Windows.Media.Brush.Transform%2A> und Eigenschaften um 45 Grad gedreht wurden.  
  
 ![RelativeTransform- und Transformieren-Eigenschaften](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>Verwenden von RelativeTransform mit einem TileBrush-Objekt  
 Da Kachelpinsel komplexer sind als andere Pinsel, kann das Anwenden eines <xref:System.Windows.Media.Brush.RelativeTransform%2A> Pinsels auf einen Pinsel zu unerwarteten Ergebnissen führen. Ziehen Sie z.B. die folgende Abbildung heran.  
  
 ![Das Quellbild](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 Im folgenden Beispiel <xref:System.Windows.Media.ImageBrush> wird ein verwendet, um einen rechteckigen Bereich mit dem vorhergehenden Bild zu zeichnen. Sie wendet <xref:System.Windows.Media.RotateTransform> eine <xref:System.Windows.Media.ImageBrush> auf <xref:System.Windows.Media.Brush.RelativeTransform%2A> die Eigenschaft des <xref:System.Windows.Media.TileBrush.Stretch%2A> Objekts an und legt seine Eigenschaft auf fest, <xref:System.Windows.Media.Stretch.UniformToFill>die das Seitenverhältnis des Bildes beibehalten soll, wenn es gestreckt wird, um das Rechteck vollständig auszufüllen.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Hierdurch wird folgende Ausgabe generiert:  
  
 ![Die transformierte Ausgabe](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Beachten Sie, dass das Bild verzerrt <xref:System.Windows.Media.TileBrush.Stretch%2A> ist, <xref:System.Windows.Media.Stretch.UniformToFill>obwohl der Pinsel auf festgelegt wurde. Das liegt daran, dass die relative Transformation <xref:System.Windows.Media.TileBrush.Viewbox%2A> angewendet wird, <xref:System.Windows.Media.TileBrush.Viewport%2A>nachdem der Pinsel seiner zugeordnet wurde. In der folgenden Liste werden die einzelnen Schritte des Prozesses beschrieben:  
  
1. Projizieren Sie den<xref:System.Windows.Media.TileBrush.Viewbox%2A>Inhalt des Pinsels<xref:System.Windows.Media.TileBrush.Viewport%2A>( ) mithilfe <xref:System.Windows.Media.TileBrush.Stretch%2A> der Einstellung des Pinsels auf die Basiskachel ( ).  
  
     ![Dehnen Sie die Viewbox, um den Viewport einzupassen](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Projizieren Sie die Basiskachel auf das 1 x 1-Transformationsrechteck.  
  
     ![Ordnen Sie den Viewport dem Transformationsrechteck zu](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Wenden <xref:System.Windows.Media.RotateTransform>Sie die an.  
  
     ![Wenden Sie die relative Transformation an](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Projizieren Sie die transformierte Basiskachel auf den zu zeichnenden Bereich.  
  
     ![Projizieren Sie den transformierten Pinsel auf den Ausgabebereich](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Beispiel: Drehen eines ImageBrush um 45 Grad  
 Im folgenden Beispiel <xref:System.Windows.Media.RotateTransform> wird <xref:System.Windows.Media.Brush.RelativeTransform%2A> eine <xref:System.Windows.Media.ImageBrush>auf die Eigenschaft einer angewendet. Die <xref:System.Windows.Media.RotateTransform> Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> des <xref:System.Windows.Media.RotateTransform.CenterY%2A> Objekts und der Eigenschaften sind beide auf 0,5, die relativen Koordinaten des Mittelpunkts des Inhalts, festgelegt. Als Folge, wird der Inhalt des Pinsels wird um seinen Mittelpunkt gedreht.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 The next example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>, but uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property. Um den Pinsel um seine <xref:System.Windows.Media.RotateTransform> Mitte <xref:System.Windows.Media.RotateTransform.CenterX%2A> zu <xref:System.Windows.Media.RotateTransform.CenterY%2A> drehen, wird das Objekt auf absolute Koordinaten gesetzt. Da das vom Pinsel gezeichnete Rechteck 175 mal 90 Pixel beträgt, liegt sein Mittelpunkt bei (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Die folgende Abbildung zeigt den Pinsel ohne Transformation, <xref:System.Windows.Media.Brush.RelativeTransform%2A> wobei die Transformation auf <xref:System.Windows.Media.Brush.Transform%2A> die Eigenschaft angewendet wird und die Transformation auf die Eigenschaft angewendet wird.  
  
 ![RelativeTransform- und Transform-Pinseleinstellungen](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Weitere Informationen zu Pinseln, finden Sie unter der [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Transformationen](transforms-overview.md)
