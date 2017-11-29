---
title: "Gewusst wie: Beibehalten des Seitenverhältnisses bei einem als Hintergrund verwendeten Bild"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a34377403a55ba42d9d3f2946ef26ea48982f5d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Gewusst wie: Beibehalten des Seitenverhältnisses bei einem als Hintergrund verwendeten Bild
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft ein <xref:System.Windows.Media.ImageBrush> um das Seitenverhältnis des Bild beizubehalten.  
  
 Standardmäßig wird bei der Verwendung einer <xref:System.Windows.Media.ImageBrush> um einen Bereich zu zeichnen, dessen Inhalt gestreckt wird, um den Ausgabebereich vollständig auszufüllen. Wenn der Ausgabebereich und das Bild unterschiedliche Seitenverhältnisse aufweisen, wird das Bild durch dieses Strecken verzerrt.  
  
 Vornehmen einer <xref:System.Windows.Media.ImageBrush> das Seitenverhältnis des Bild beizubehalten, legen Sie die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft <xref:System.Windows.Media.Stretch.Uniform> oder <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet zwei <xref:System.Windows.Media.ImageBrush> Objekte zum Zeichnen von zwei Rechtecken. Jedes Rechteck ist 300 x 150 Pixel groß und enthält jeweils ein 300 x 300 Pixel großes Bild. Die <xref:System.Windows.Media.TileBrush.Stretch%2A> des ersten Pinsels wird-Eigenschaftensatz auf <xref:System.Windows.Media.Stretch.Uniform>, und die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft des zweiten Pinsels auf festgelegt ist <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 Die folgende Abbildung zeigt die Ausgabe des ersten Pinsels, besitzt eine <xref:System.Windows.Media.TileBrush.Stretch%2A> Einstellung des <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush mit Uniform-Dehnung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "Graphicsmm_ImageBrushUniformStretch")  
  
 Die nächste Abbildung zeigt die Ausgabe des zweiten Pinsels, besitzt eine <xref:System.Windows.Media.TileBrush.Stretch%2A> Einstellung des <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush mit UniformToFill-Dehnung](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "Graphicsmm_ImageBrushUniformToFillStretch")  
  
 Beachten Sie, dass die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft verhält sich ebenso wie für die anderen <xref:System.Windows.Media.TileBrush> Objekte aufweist, d. h. für <xref:System.Windows.Media.DrawingBrush> und <xref:System.Windows.Media.VisualBrush>. Weitere Informationen zu <xref:System.Windows.Media.ImageBrush> und die andere <xref:System.Windows.Media.TileBrush> anzuzeigen, [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Beachten Sie auch, dass, obwohl die <xref:System.Windows.Media.TileBrush.Stretch%2A> Eigenschaft angezeigt wird, um anzugeben wie die <xref:System.Windows.Media.TileBrush> Inhalt gestreckt wird, um den Ausgabebereich passt, es tatsächlich gibt an, wie die <xref:System.Windows.Media.TileBrush> Inhalt wird gestreckt, um seine Basiskachel auszufüllen. Weitere Informationen finden Sie unter <xref:System.Windows.Media.TileBrush>.  
  
 Dieses Codebeispiel ist Teil eines größeren Beispiels, die aus Gründen der <xref:System.Windows.Media.ImageBrush> Klasse. Das vollständige Beispiel finden Sie unter [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.TileBrush>  
 [Zeichnen mit Bildern, Zeichnungen und visuellen Elementen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
