---
title: 'Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 5a73ee967be0aae7dc3f1ef82229c2bcb2f9ade2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560715"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads
In diesem Beispiel wird gezeigt, wie zum Drehen ein Objekt entlang eines geometrischen Pfads, der durch definiert ist ein <xref:System.Windows.Media.PathGeometry> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet drei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben.  
  
-   Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert eine <xref:System.Windows.Media.RotateTransform> , für das Rechteck angewendet wird. Die Animation generiert Winkelwerte. Das Rechteck dreht (schwenkt) sich entlang der Pfadkonturen.  
  
-   Die anderen beiden Objekte animieren der <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Werte eine <xref:System.Windows.Media.TranslateTransform> , für das Rechteck angewendet wird. Sie verschieben das Rechteck horizontal und vertikal entlang des Pfads.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Eine weitere Möglichkeit zum Drehen eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt, und seine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft `true`. Weitere Informationen und ein Beispiel finden Sie unter [Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Beispiel zu Textanimation](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
