---
title: 'Gewusst wie: Beibehalten des Seitenverhältnisses bei einem als Hintergrund verwendeten Bild'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186031"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Gewusst wie: Beibehalten des Seitenverhältnisses bei einem als Hintergrund verwendeten Bild
In diesem Beispiel wird <xref:System.Windows.Media.TileBrush.Stretch%2A> gezeigt, <xref:System.Windows.Media.ImageBrush> wie die Eigenschaft eines verwendet wird, um das Seitenverhältnis des Bildes beizubehalten.  
  
 Wenn Sie einen <xref:System.Windows.Media.ImageBrush> Bereich malen, erstreckt sich der Inhalt standardmäßig, um den Ausgabebereich vollständig zu füllen. Wenn der Ausgabebereich und das Bild unterschiedliche Seitenverhältnisse aufweisen, wird das Bild durch dieses Strecken verzerrt.  
  
 Um das <xref:System.Windows.Media.ImageBrush> Seitenverhältnis des Bildes beizubehalten, <xref:System.Windows.Media.TileBrush.Stretch%2A> legen <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>Sie die Eigenschaft auf oder fest.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.ImageBrush> werden zwei Objekte zum Zeichnen von zwei Rechtecken verwendet. Jedes Rechteck ist 300 x 150 Pixel groß und enthält jeweils ein 300 x 300 Pixel großes Bild. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft des ersten Pinsels ist auf <xref:System.Windows.Media.Stretch.Uniform>festgelegt, und die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft des zweiten Pinsels ist auf <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des <xref:System.Windows.Media.TileBrush.Stretch%2A> ersten <xref:System.Windows.Media.Stretch.Uniform>Pinsels, der eine Einstellung von hat.  
  
 ![ImageBrush mit Uniform-Dehnung](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 Die nächste Abbildung zeigt die Ausgabe des <xref:System.Windows.Media.TileBrush.Stretch%2A> zweiten <xref:System.Windows.Media.Stretch.UniformToFill>Pinsels, der eine Einstellung von hat.  
  
 ![ImageBrush mit UniformToFill-Dehnung](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Beachten Sie, dass sich <xref:System.Windows.Media.TileBrush.Stretch%2A> die Eigenschaft <xref:System.Windows.Media.TileBrush> für die anderen <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush>Objekte, d. h. für und, identisch verhält. Weitere Informationen <xref:System.Windows.Media.ImageBrush> zu und <xref:System.Windows.Media.TileBrush> zu den anderen Objekten finden Sie unter [Malen mit Bildern, Zeichnungen und Visuals](painting-with-images-drawings-and-visuals.md).  
  
 Beachten Sie auch, <xref:System.Windows.Media.TileBrush.Stretch%2A> dass die Eigenschaft <xref:System.Windows.Media.TileBrush> zwar anzugeben scheint, wie der Inhalt <xref:System.Windows.Media.TileBrush> an den Ausgabebereich anpasst, aber tatsächlich angibt, wie der Inhalt dehnt, um seine Basiskachel zu füllen. Weitere Informationen finden Sie unter <xref:System.Windows.Media.TileBrush>.  
  
 Dieses Codebeispiel ist Teil eines größeren Beispiels, das für die <xref:System.Windows.Media.ImageBrush> Klasse bereitgestellt wird. Das vollständige Beispiel finden Sie unter [ImageBrush-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
