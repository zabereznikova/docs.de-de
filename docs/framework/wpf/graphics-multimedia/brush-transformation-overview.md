---
title: "&#220;bersicht &#252;ber Pinseltransformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pinsel, Transformationseigenschaften"
  - "Eigenschaften, Transformation"
  - "Transformationseigenschaften von Pinseln"
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber Pinseltransformationen
Die Brush\-Klasse stellt zwei Eigenschaften für Transformationen bereit: <xref:System.Windows.Media.Brush.Transform%2A> und <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  Mit diesen Eigenschaften können Sie den Inhalt eines Pinsels drehen, skalieren, neigen und übersetzen.  In diesem Thema werden die Unterschiede zwischen diesen zwei Eigenschaften beschrieben und Beispiele für ihre Verwendung bereitgestellt.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 Für dieses Thema sollten Sie mit den Features des Pinsels vertraut sein, den Sie transformieren.  Informationen zu <xref:System.Windows.Media.LinearGradientBrush> und <xref:System.Windows.Media.RadialGradientBrush> finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Informationen zu <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> oder <xref:System.Windows.Media.VisualBrush> finden Sie unter [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  Sie sollten auch mit den unter [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md) beschriebenen 2D\-Transformationen vertraut sein.  
  
<a name="transformversusrelativetransform"></a>   
## Unterschiede zwischen den Eigenschaften Transform und RelativeTransform  
 Wenn Sie auf die <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft eines Pinsels eine Transformation anwenden, muss Ihnen die Größe des gezeichneten Bereichs bekannt sein, wenn Sie den Pinselinhalt um seinen Mittelpunkt transformieren möchten.  Angenommen, der gezeichnete Bereich ist 200 [geräteunabhängige Pixel](GTMT) breit und 150 hoch.  Wenn Sie eine <xref:System.Windows.Media.RotateTransform> verwenden, um die Pinselausgabe um 45 Grad um ihren Mittelpunkt zu drehen, legen Sie für <xref:System.Windows.Media.RotateTransform> einen <xref:System.Windows.Media.RotateTransform.CenterX%2A>\-Wert von 100 und einen <xref:System.Windows.Media.RotateTransform.CenterY%2A>\-Wert von 75 fest.  
  
 Wenn Sie auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft eines Pinsels eine Transformation anwenden, wird diese Transformation auf den Pinsel angewendet, bevor seine Ausgabe dem gezeichneten Bereich zugeordnet wird.  Die folgende Liste beschreibt die Reihenfolge, in der der Inhalt eines Pinsels verarbeitet und transformiert wird.  
  
1.  Verarbeiten Sie den Inhalt des Pinsels.  Für einen <xref:System.Windows.Media.GradientBrush> müssen Sie dazu den Farbverlaufsbereich bestimmen.  Für einen <xref:System.Windows.Media.TileBrush> wird <xref:System.Windows.Media.TileBrush.Viewbox%2A> dem <xref:System.Windows.Media.TileBrush.Viewport%2A> zugeordnet.  Dies wird die Ausgabe des Pinsels.  
  
2.  Projizieren Sie die Ausgabe des Pinsels auf das 1x1\-Transformationsrechteck.  
  
3.  Wenden Sie die <xref:System.Windows.Media.Brush.RelativeTransform%2A> des Pinsels an, sofern vorhanden.  
  
4.  Projizieren Sie die transformierte Ausgabe auf den Bereich, der gezeichnet werden soll.  
  
5.  Wenden Sie die <xref:System.Windows.Media.Transform> des Pinsels an, sofern vorhanden.  
  
 Weil die Anwendung der <xref:System.Windows.Media.Brush.RelativeTransform%2A> erfolgt, während die Ausgabe des Pinsels einem 1x1\-Rechteck zugeordnet ist, scheinen die Werte für Mittelpunkt und Offset relativ zu sein.  Wenn Sie beispielsweise eine <xref:System.Windows.Media.RotateTransform> verwenden, um die Pinselausgabe um 45 Grad um ihren Mittelpunkt zu drehen, legen Sie für <xref:System.Windows.Media.RotateTransform> einen <xref:System.Windows.Media.RotateTransform.CenterX%2A>\-Wert von 0,5 und einen <xref:System.Windows.Media.RotateTransform.CenterY%2A>\-Wert von 0,5 fest.  
  
 In der folgenden Abbildung werden die Ausgaben verschiedener Pinsel veranschaulicht, die mit der <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft und der <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft um 45 Grad gedreht wurden.  
  
 ![RelativeTransform&#45; und Transform&#45;Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm\_brushrelativetransform\_transform\_small")  
  
<a name="relativetransformandtilebrush"></a>   
## Verwenden von RelativeTransform mit einem TileBrush\-Objekt  
 Da TileBrush\-Objekte komplexer als andere Pinsel sind, kann die Anwendung einer <xref:System.Windows.Media.Brush.RelativeTransform%2A> zu unerwarteten Ergebnissen führen.  Ein Beispiel hierfür stellt das folgende Bild dar:  
  
 ![Das Quellbild](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.png "graphicsmm\_reltransform\_1\_original\_image")  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.ImageBrush> verwendet, um einen rechteckigen Bereich mit dem vorherigen Bild zu zeichnen.  Dabei wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft des <xref:System.Windows.Media.ImageBrush>\-Objekts angewendet und die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft auf <xref:System.Windows.Media.Stretch> festgelegt. Auf diese Weise sollte das Seitenverhältnis des Bilds beibehalten werden, wenn es zum vollständigen Ausfüllen des Rechtecks gestreckt wird.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Dieses Beispiel erzeugt folgende Ausgabe:  
  
 ![Die transformierte Ausgabe](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm\_reltransform\_6\_output")  
  
 Beachten Sie, dass das Bild verzerrt ist, obwohl die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Eigenschaft des Pinsels auf <xref:System.Windows.Media.Stretch> festgelegt wurde.  Das liegt daran, dass die relative Transformation angewendet wird, nachdem die <xref:System.Windows.Media.TileBrush.Viewbox%2A> des Pinsels seinem <xref:System.Windows.Media.TileBrush.Viewport%2A> zugeordnet wurde.  In der folgenden Liste werden die einzelnen Schritte des Prozesses beschrieben:  
  
1.  Projizieren Sie den Inhalt des Pinsels \(<xref:System.Windows.Media.TileBrush.Viewbox%2A>\) auf seine Basiskachel \(<xref:System.Windows.Media.TileBrush.Viewport%2A>\), und verwenden Sie dazu die <xref:System.Windows.Media.TileBrush.Stretch%2A>\-Einstellung des Pinsels.  
  
     ![Dehnen Sie die Viewbox, um den Viewport einzupassen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm\_reltransform\_2\_viewbox\_to\_viewport")  
  
2.  Projizieren Sie die Basiskachel auf das 1x1\-Transformationsrechteck.  
  
     ![Ordnen Sie den Viewport dem Transformationsrechteck zu](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm\_reltransform\_3\_output\_to\_transform")  
  
3.  Wenden Sie die <xref:System.Windows.Media.RotateTransform> an.  
  
     ![Wenden Sie die relative Transformation an](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm\_reltransform\_4\_transform\_rotate")  
  
4.  Projizieren Sie die transformierte Basiskachel auf den Bereich, der gezeichnet werden soll.  
  
     ![Projizieren Sie den transformierten Pinsel auf den Ausgabebereich](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm\_reltransform\_5\_transform\_to\_output")  
  
<a name="rotateexample"></a>   
## Beispiel: Drehen eines ImageBrush um 45 Grad  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.RotateTransform> auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft eines <xref:System.Windows.Media.ImageBrush>\-Elements angewendet.  Die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> des <xref:System.Windows.Media.RotateTransform>\-Objekts sind beide auf 0,5, d. h. auf die relativen Koordinaten des Inhaltsmittelpunkts, festgelegt.  Als Ergebnis wird der Inhalt des Pinsels um seinen Mittelpunkt gedreht.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Im nächsten Beispiel wird ebenfalls eine <xref:System.Windows.Media.RotateTransform> auf einen <xref:System.Windows.Media.ImageBrush> angewendet. Dieses Beispiel verwendet jedoch die <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft anstelle der <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft.  Um den Pinsel um seinen Mittelpunkt zu drehen, müssen die Eigenschaften <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> des <xref:System.Windows.Media.RotateTransform>\-Objekts auf absolute Koordinaten festgelegt werden.  Da das vom Pinsel gezeichnete Rechteck eine Größe von 175 mal 90 Pixel aufweist, liegt sein Mittelpunkt bei \(87,5\/45\).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Die Abbildung enthält die folgenden Darstellungen: Pinsel ohne Transformation, mit der Transformation angewendet auf die <xref:System.Windows.Media.Brush.RelativeTransform%2A>\-Eigenschaft und mit der Transformation angewendet auf die <xref:System.Windows.Media.Brush.Transform%2A>\-Eigenschaft.  
  
 ![RelativeTransform&#45; und Transform&#45;Pinseleinstellungen](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
 Dieses Beispiel ist ein Teil eines umfangreicheren Beispiels.  Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  Weitere Informationen über Pinsel finden Sie unter [Übersicht über WPF\-Pinsel](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Brush.Transform%2A>   
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>   
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Brush>   
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)