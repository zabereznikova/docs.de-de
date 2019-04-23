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
ms.openlocfilehash: 39b3ad9bebfc56002f77ad6e9026a4446c95455b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298330"
---
# <a name="brush-transformation-overview"></a>Übersicht über Pinseltransformationen
Die Brush-Klasse bietet zwei Transformationseigenschaften: <xref:System.Windows.Media.Brush.Transform%2A> und <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Diese Eigenschaften ermöglichen Ihnen den Inhalt eines Pinsels zu drehen, zu skalieren, zu neigen und zu übersetzen. Dieses Thema beschreibt die  Unterschiede zwischen diesen beiden Eigenschaften sowie Beispiele für deren Verwendung.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Um dieses Thema zu verstehen, sollten Sie die Features des Pinsels kennen, den Sie transformieren. Für <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush>, finden Sie unter den [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md). Für <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, oder <xref:System.Windows.Media.VisualBrush>, finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md). Sie sollten auch mit den 2D- Transformationen, die unter  [Übersicht über Transformationen](transforms-overview.md) beschrieben werden, vertraut sein.  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Unterschiede zwischen den Eigenschaften Transform und RelativeTransform  
 Wenn Sie eine Transformation auf eines Pinsels anwenden <xref:System.Windows.Media.Brush.Transform%2A> -Eigenschaft müssen Sie die Größe des gezeichneten Bereichs kennen, wenn Sie den Inhalt des Pinsels zu seinen Mittelpunkt transformieren möchten. Angenommen, der gezeichnete Bereich ist 200 geräteunabhängige Pixel breit und 150 hoch.  Bei Verwendung einer <xref:System.Windows.Media.RotateTransform> den Pinsel zu drehen Sie die Ausgabe um 45 Grad um seinen Mittelpunkt, die Sie erhalten würde die <xref:System.Windows.Media.RotateTransform> eine <xref:System.Windows.Media.RotateTransform.CenterX%2A> von 100 und ein <xref:System.Windows.Media.RotateTransform.CenterY%2A> von 75.  
  
 Wenn Sie eine Transformation auf eines Pinsels anwenden <xref:System.Windows.Media.Brush.RelativeTransform%2A> -Eigenschaft, diese Transformation auf den Pinsel angewendet, bevor seine Ausgabe dem gezeichneten Bereich zugeordnet ist. Die folgende Liste beschreibt die Reihenfolge, in welcher der Inhalt eines Pinsels verarbeitet und transformiert wird.  
  
1. Verarbeiten Sie den Inhalt des Pinsels. Für eine <xref:System.Windows.Media.GradientBrush>, dies bedeutet, dass der Farbverlauf Bereich. Für eine <xref:System.Windows.Media.TileBrush>, <xref:System.Windows.Media.TileBrush.Viewbox%2A> zugeordnet ist die <xref:System.Windows.Media.TileBrush.Viewport%2A>. Dies ergibt die Ausgabe des Pinsels.  
  
2. Projizieren Sie die Ausgabe des Pinsels auf das 1 x 1-Transformationsrechteck.  
  
3. Anwenden des Pinsels <xref:System.Windows.Media.Brush.RelativeTransform%2A>, sofern vorhanden.  
  
4. Projizieren Sie die transformierte Ausgabe auf den zu zeichnenden Bereich.  
  
5. Anwenden des Pinsels <xref:System.Windows.Media.Transform>, sofern vorhanden.  
  
 Da die <xref:System.Windows.Media.Brush.RelativeTransform%2A> angewendet wird, während die Ausgabe des Pinsels einem 1 x 1-Rechteck Transformationsmittelpunkts zugeordnet ist und Offset-Werte scheinen relativ sein. Angenommen, Sie verwendet eine <xref:System.Windows.Media.RotateTransform> den Pinsel zu drehen Sie die Ausgabe um 45 Grad um seinen Mittelpunkt, die Sie erhalten würde die <xref:System.Windows.Media.RotateTransform> eine <xref:System.Windows.Media.RotateTransform.CenterX%2A> von 0,5 und ein <xref:System.Windows.Media.RotateTransform.CenterY%2A> von 0,5.  
  
 Die folgende Abbildung zeigt die Ausgabe verschiedener Pinsel, der mit um 45 Grad gedreht wurden die <xref:System.Windows.Media.Brush.RelativeTransform%2A> und <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaften.  
  
 ![RelativeTransform- und Transform-Eigenschaften](./media/graphicsmm-brushrelativetransform-transform-small.png "Graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Verwenden von RelativeTransform mit einem TileBrush-Objekt  
 Da TileBrush-Objekte komplexer als andere Pinsel sind, Anwenden einer <xref:System.Windows.Media.Brush.RelativeTransform%2A> auf eine möglicherweise zu unerwarteten Ergebnissen führen. Ziehen Sie z.B. die folgende Abbildung heran.  
  
 ![Das  Quellbild](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> um einen rechteckigen Bereich mit der obigen Abbildung zu zeichnen. Es gilt eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.ImageBrush> des Objekts <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaften der <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft, um <xref:System.Windows.Media.Stretch.UniformToFill>, das Seitenverhältnis des Bilds beibehalten soll, wenn es zum kompletten Füllen des Rechtecks gestreckt wird.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
 ![Die transformierte  Ausgabe](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Beachten Sie, dass das Bild, obwohl verzerrt ist der des Pinsels <xref:System.Windows.Media.TileBrush.Stretch%2A> wurde <xref:System.Windows.Media.Stretch.UniformToFill>. Das ist da die relative Transformation angewendet wird, nach dem des Pinsels <xref:System.Windows.Media.TileBrush.Viewbox%2A> zugeordnet ist seine <xref:System.Windows.Media.TileBrush.Viewport%2A>. In der folgenden Liste werden die einzelnen Schritte des Prozesses beschrieben:  
  
1. Projizieren Sie den Inhalt des Pinsels (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) auf seine Basiskachel (<xref:System.Windows.Media.TileBrush.Viewport%2A>) mithilfe des Pinsels <xref:System.Windows.Media.TileBrush.Stretch%2A> festlegen.  
  
     ![Dehnen Sie Viewbox, um Viewport einzupassen](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Projizieren Sie die Basiskachel auf das 1 x 1-Transformationsrechteck.  
  
     ![Ordnen Sie Viewport dem Transformationsrechteck zu](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Anwenden der <xref:System.Windows.Media.RotateTransform>.  
  
     ![Wenden Sie die relative  Transformation](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate") an  
  
4. Projizieren Sie die transformierte Basiskachel auf den zu zeichnenden Bereich.  
  
     ![Projizieren Sie den transformierten Pinsel auf den  Ausgabebereich](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Beispiel: Drehen eines ImageBrush um 45 Grad  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft eine <xref:System.Windows.Media.ImageBrush>. Die <xref:System.Windows.Media.RotateTransform> des Objekts <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften sind beide auf 0,5 festgelegt, zeigen Sie die relativen Koordinaten des Inhalts Center. Als Folge, wird der Inhalt des Pinsels wird um seinen Mittelpunkt gedreht.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Im nächste Beispiel gilt auch für eine <xref:System.Windows.Media.RotateTransform> auf eine <xref:System.Windows.Media.ImageBrush>, verwendet jedoch die <xref:System.Windows.Media.Brush.Transform%2A> -Eigenschaft anstelle der <xref:System.Windows.Media.Brush.RelativeTransform%2A> Eigenschaft. Den Pinsel seinen Mittelpunkt zu drehen der <xref:System.Windows.Media.RotateTransform> des Objekts <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> muss auf absolute Koordinaten festgelegt werden. Da das vom Pinsel gezeichnete Rechteck 175 mal 90 Pixel beträgt, liegt sein Mittelpunkt bei (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Die folgende Abbildung zeigt den Pinsel ohne Transformation, mit der Transformation angewendet auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A> -Eigenschaft, und klicken Sie mit der Transformation angewendet auf die <xref:System.Windows.Media.Brush.Transform%2A> Eigenschaft.  
  
 ![RelativeTransform- und Transform-Pinseleinstellungen](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "Wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Dieses Beispiel ist Teil eines umfangreicheren Beispiels. Das vollständige Beispiel finden Sie unter der [Beispiel für Pinsel](https://go.microsoft.com/fwlink/?LinkID=159973). Weitere Informationen zu Pinseln, finden Sie unter der [Übersicht über WPF-Pinsel](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md)
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
- [Übersicht über Transformationen](transforms-overview.md)
