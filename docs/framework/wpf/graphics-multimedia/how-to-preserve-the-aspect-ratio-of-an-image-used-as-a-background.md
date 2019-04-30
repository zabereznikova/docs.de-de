---
title: 'Vorgehensweise: Beibehalten des Seitenverhältnisses bei einem als Hintergrund verwendeten Bild'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 4ae6f1242548038bcd54b7218783e5063fa67872
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921756"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Vorgehensweise: Beibehalten des Seitenverhältnisses bei einem als Hintergrund verwendeten Bild
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft eine <xref:System.Windows.Media.ImageBrush> um das Seitenverhältnis des Bilds zu erhalten.  
  
 Standardmäßig wird bei der Verwendung einer <xref:System.Windows.Media.ImageBrush> zum Zeichnen eines Bereichs, dessen Inhalt wird gestreckt, um den Ausgabebereich vollständig ausfüllt. Wenn der Ausgabebereich und das Bild unterschiedliche Seitenverhältnisse aufweisen, wird das Bild durch dieses Strecken verzerrt.  
  
 Vornehmen einer <xref:System.Windows.Media.ImageBrush> das Seitenverhältnis des Bild beizubehalten, legen Sie die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.Stretch.Uniform> oder <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet zwei <xref:System.Windows.Media.ImageBrush> -Objekten, das zwei Rechtecke zu zeichnen. Jedes Rechteck ist 300 x 150 Pixel groß und enthält jeweils ein 300 x 300 Pixel großes Bild. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> des ersten Pinsels-Eigenschaftensatz auf <xref:System.Windows.Media.Stretch.Uniform>, und die <xref:System.Windows.Media.TileBrush.Stretch%2A> des zweiten Pinsels-Eigenschaftensatz auf <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des ersten Pinsels, bei dem ein <xref:System.Windows.Media.TileBrush.Stretch%2A> -Einstellung <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush mit Uniform-Dehnung](./media/graphicsmm-imagebrushuniformstretch.jpg "Graphicsmm_ImageBrushUniformStretch")  
  
 Die folgende Abbildung zeigt die Ausgabe des zweiten Pinsels, bei dem ein <xref:System.Windows.Media.TileBrush.Stretch%2A> -Einstellung <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush mit UniformToFill-Dehnung](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "Graphicsmm_ImageBrushUniformToFillStretch")  
  
 Beachten Sie, dass die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft verhält sich identisch, für die anderen <xref:System.Windows.Media.TileBrush> Objekte, d. h. für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und die andere <xref:System.Windows.Media.TileBrush> Objekten finden Sie [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md).  
  
 Beachten Sie auch, dass, obwohl die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft angezeigt wird, an wie die <xref:System.Windows.Media.TileBrush> -Inhalt gestreckt wird, um den Ausgabebereich passt, es tatsächlich aber angibt, wie die <xref:System.Windows.Media.TileBrush> Inhalt gestreckt wird, um die Basisfläche ausfüllt. Weitere Informationen finden Sie unter <xref:System.Windows.Media.TileBrush>.  
  
 Dieses Codebeispiel ist Teil eines größeren Beispiels, die aus Gründen der <xref:System.Windows.Media.ImageBrush> Klasse. Das vollständige Beispiel finden Sie unter [Beispiel zu ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.TileBrush>
- [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](painting-with-images-drawings-and-visuals.md)
