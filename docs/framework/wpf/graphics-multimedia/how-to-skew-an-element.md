---
title: 'Gewusst wie: Neigen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: f828e4d4e59fa5ed31f81f3e83570a25add19e01
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877079"
---
# <a name="how-to-skew-an-element"></a>Gewusst wie: Neigen eines Elements
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.SkewTransform> auf ein Element zu neigen. Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt. Eine typische Verwendung einer <xref:System.Windows.Media.SkewTransform> ist das simulieren [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Tiefe [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] Objekte.  
  
 Verwenden der <xref:System.Windows.Media.SkewTransform.CenterX%2A> und <xref:System.Windows.Media.SkewTransform.CenterY%2A> Eigenschaften an der Mitte des zeigen die <xref:System.Windows.Media.SkewTransform>.  
  
 Verwenden der <xref:System.Windows.Media.SkewTransform.AngleX%2A> und <xref:System.Windows.Media.SkewTransform.AngleY%2A> Eigenschaften, um den Neigungswinkels der x-Achse und y-Achse anzugeben und um das aktuelle Koordinatensystem entlang dieser Achsen zu neigen.  
  
 Um die Auswirkungen einer Neigungstransformation vorherzusagen, zu berücksichtigen, die <xref:System.Windows.Media.SkewTransform.AngleX%2A> Werte der x-Achse relativ zum ursprünglichen Koordinatensystem neigt. Aus diesem Grund für eine <xref:System.Windows.Media.SkewTransform.AngleX%2A> von 30 die y-Achse dreht 30° durch den Ursprung und neigt die Werte in X-um 30° vom Ursprung. Ebenso ein <xref:System.Windows.Media.SkewTransform.AngleY%2A> neigt Sie 30 die y-Werte der Form um 30° vom Ursprung. Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen (Bewegen) des Koordinatensystems um 30° in der X- oder Y-Achse.  
  
 Im folgenden Beispiel wird eine horizontale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> aus einem Mittelpunkt (0,0).  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Im folgenden Beispiel wird eine horizontale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> aus einem Mittelpunkt (25,25).  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 Im folgenden Beispiel wird eine vertikale Neigung von 45° auf ein <xref:System.Windows.Shapes.Rectangle> aus einem Mittelpunkt (25,25).  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 Die folgenden Abbildungen zeigen die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.  
  
 ![SkewTransform-Beispiele](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "Img_wcpsdk_graphicsmm_skewtransformexample")  
Die drei SkewTransform-Beispiele veranschaulicht  
  
 Das vollständige Beispiel finden Sie im [Beispiel einer 2D-Transformation](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
