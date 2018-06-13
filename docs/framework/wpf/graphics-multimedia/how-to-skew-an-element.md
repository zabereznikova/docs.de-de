---
title: 'Gewusst wie: Neigen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 8bd860a71253a55cb3148426dbb61cbd3477e95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561562"
---
# <a name="how-to-skew-an-element"></a>Gewusst wie: Neigen eines Elements
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.SkewTransform> um ein Element zu neigen. Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt. Eine typische Verwendung von einem <xref:System.Windows.Media.SkewTransform> ist zum Simulieren von [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] ausführlich [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] Objekte.  
  
 Verwenden der <xref:System.Windows.Media.SkewTransform.CenterX%2A> und <xref:System.Windows.Media.SkewTransform.CenterY%2A> Eigenschaften zur Angabe der Mittelpunkts des zeigen die <xref:System.Windows.Media.SkewTransform>.  
  
 Verwenden der <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A> Eigenschaften den Neigungswinkel der x-Achse und y-Achse angeben, und klicken Sie auf das aktuelle Koordinatensystem entlang dieser Achsen verzerren.  
  
 In Betracht ziehen, um die Auswirkung der eine Neigungstransformation vorherzusagen, <xref:System.Windows.Media.SkewTransform.AngleX%2A> neigt Werte der x-Achse relativ zum ursprünglichen Koordinatensystems. Aus diesem Grund für ein <xref:System.Windows.Media.SkewTransform.AngleX%2A> 30, die y-Achse dreht 30 Grad über den Ursprung und neigt die Werte in X-von 30 Grad vom Ursprung. Ebenso ein <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 neigt Sie die y-Werte der Form von 30 Grad vom Ursprung. Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen (Bewegen) des Koordinatensystems um 30° in der X- oder Y-Achse.  
  
 Im folgende Beispiel wird eine horizontale Neigung von 45 Grad ein, um eine <xref:System.Windows.Shapes.Rectangle> von einem Mittelpunkt (0,0).  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Im folgende Beispiel wird eine horizontale Neigung von 45 Grad ein, um eine <xref:System.Windows.Shapes.Rectangle> von einem Mittelpunkt (25,25) aus.  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 Im folgende Beispiel wird eine vertikale Neigung von 45 Grad ein, um eine <xref:System.Windows.Shapes.Rectangle> von einem Mittelpunkt (25,25) aus.  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 Die folgenden Abbildungen zeigen die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.  
  
 ![SkewTransform-Beispiele](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "Img_wcpsdk_graphicsmm_skewtransformexample")  
Die drei SkewTransform-Beispiele veranschaulicht  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
