---
title: 'Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 3e35169da7297ec62e0114ab21f4ba81c0a656ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229211"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads
In diesem Beispiel wird gezeigt, wie zum Drehen ein Objekts entlang eines geometrischen Pfads, der durch definiert ist eine <xref:System.Windows.Media.PathGeometry> Objekt.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet drei <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Objekte ein Rechteck entlang eines geometrischen Pfads verschoben.  
  
-   Die erste <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animiert ein <xref:System.Windows.Media.RotateTransform> , die auf das Rechteck angewendet wird. Die Animation generiert Winkelwerte. Das Rechteck dreht (schwenkt) sich entlang der Pfadkonturen.  
  
-   Die anderen beiden Objekte animieren das <xref:System.Windows.Media.TranslateTransform.X%2A> und <xref:System.Windows.Media.TranslateTransform.Y%2A> Werte eine <xref:System.Windows.Media.TranslateTransform> , die auf das Rechteck angewendet wird. Sie verschieben das Rechteck horizontal und vertikal entlang des Pfads.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Eine weitere Möglichkeit zum Drehen eines Objekts mithilfe eines geometrischen Pfads ist die Verwendung einer <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Objekt, und legen dessen <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft `true`. Weitere Informationen und ein Beispiel finden Sie unter [Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
