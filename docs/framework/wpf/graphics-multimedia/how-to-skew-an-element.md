---
title: 'Gewusst wie: Neigen eines Elements'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112023"
---
# <a name="how-to-skew-an-element"></a>Gewusst wie: Neigen eines Elements
In diesem Beispiel wird <xref:System.Windows.Media.SkewTransform> gezeigt, wie ein verwendet wird, um ein Element zu verzerren. Eine Neigung ist eine Transformation, die den Koordinatenraum auf ungleichmäßige Art ausdehnt. Eine typische Verwendung <xref:System.Windows.Media.SkewTransform> von a ist die Simulation von 3D-Tiefe in 2D-Objekten.  
  
 Verwenden <xref:System.Windows.Media.SkewTransform.CenterX%2A> Sie <xref:System.Windows.Media.SkewTransform.CenterY%2A> die und Eigenschaften, <xref:System.Windows.Media.SkewTransform>um den Mittelpunkt der anzugeben.  
  
 Verwenden <xref:System.Windows.Media.SkewTransform.AngleX%2A> Sie <xref:System.Windows.Media.SkewTransform.AngleY%2A> die und Eigenschaften, um den Neigungswinkel der x-Achse und der y-Achse anzugeben und das aktuelle Koordinatensystem entlang dieser Achsen zu verzerren.  
  
 Um den Effekt einer Schiefentransformation <xref:System.Windows.Media.SkewTransform.AngleX%2A> vorherzusagen, sollten Sie berücksichtigen, dass x-Achsenwerte relativ zum ursprünglichen Koordinatensystem verzerrt werden. Daher dreht <xref:System.Windows.Media.SkewTransform.AngleX%2A> sich bei einer von 30 die y-Achse um 30 Grad durch den Ursprung und verzerrt die Werte in x- um 30 Grad von diesem Ursprung. Ebenso verzerrt <xref:System.Windows.Media.SkewTransform.AngleY%2A> ein von 30 die y-Werte der Form um 30 Grad vom Ursprung. Beachten Sie, dass dieser Vorgang nicht dieselbe Wirkung erzielt, wie das Übersetzen (Bewegen) des Koordinatensystems um 30° in der X- oder Y-Achse.  
  
 Im folgenden Beispiel wird eine horizontale Neigung <xref:System.Windows.Shapes.Rectangle> von 45 Grad auf eine von einem Mittelpunkt von (0,0) angewendet.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 Im folgenden Beispiel wird eine horizontale Neigung <xref:System.Windows.Shapes.Rectangle> von 45 Grad auf eine von einem Mittelpunkt (25,25) angewendet.  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 Im folgenden Beispiel wird eine vertikale Neigung <xref:System.Windows.Shapes.Rectangle> von 45 Grad auf eine von einem Mittelpunkt (25,25) angewendet.  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 Die folgenden Abbildungen zeigen die verschiedenen Neigungen, die in diesem Beispiel verwendet werden.  
  
 ![SkewTransform-Beispiele](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
Die drei SkewTransform-Beispiele veranschaulicht  
  
 Das vollständige Beispiel finden Sie unter [2D-Transformationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [Übersicht über Transformationen](transforms-overview.md)
- [How-to-Themen](transformations-how-to-topics.md)
