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
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186873"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a>Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads
In diesem Beispiel wird gezeigt, wie ein Objekt entlang eines <xref:System.Windows.Media.PathGeometry> geometrischen Pfads gedreht (pivotiert) wird, der von einem Objekt definiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> werden drei Objekte verwendet, um ein Rechteck entlang eines geometrischen Pfads zu verschieben.  
  
- Die <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> erste animiert eine, <xref:System.Windows.Media.RotateTransform> die auf das Rechteck angewendet wird. Die Animation generiert Winkelwerte. Das Rechteck dreht (schwenkt) sich entlang der Pfadkonturen.  
  
- Die beiden anderen <xref:System.Windows.Media.TranslateTransform.X%2A> Objekte <xref:System.Windows.Media.TranslateTransform.Y%2A> animieren die und Werte von a, <xref:System.Windows.Media.TranslateTransform> die auf das Rechteck angewendet werden. Sie verschieben das Rechteck horizontal und vertikal entlang des Pfads.  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Eine andere Möglichkeit, ein Objekt mithilfe eines <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> geometrischen Pfads zu drehen, besteht darin, ein Objekt zu verwenden und seine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> Eigenschaft auf festzulegen. `true` Weitere Informationen und ein Beispiel finden Sie unter [Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation).](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)  
  
 Das vollständige Beispiel finden Sie unter [Pfadanimationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Beispiel einer Pfadanimation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
