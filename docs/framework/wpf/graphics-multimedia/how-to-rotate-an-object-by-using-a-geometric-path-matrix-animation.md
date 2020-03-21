---
title: 'Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads (MatrixAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187416"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads (MatrixAnimation)
In diesem Beispiel wird <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> gezeigt, wie ein und ein <xref:System.Windows.Media.MatrixTransform> zum Drehen <xref:System.Windows.Media.PathGeometry> (Pivoten) eines Objekts entlang eines geometrischen Pfads verwendet wird, der durch ein Objekt definiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> wird das <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Objekt <xref:System.Windows.Media.MatrixTransform>verwendet, um die Eigenschaft einer zu animieren. Der <xref:System.Windows.Media.MatrixTransform> wird auf eine Schaltfläche angewendet und bewirkt, dass er sich entlang eines gekrümmten Pfads bewegt. Da <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> die Eigenschaft `true`auf festgelegt ist, wird das Rechteck entlang der Tangente des Pfads gedreht.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Pfadanimationsbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 Die Codeversion des vorherigen <xref:System.Windows.Media.Animation.Storyboard> Beispiels <xref:System.Windows.Media.EllipseGeometry>verwendet eine zum Animieren der , obwohl nur eine Animation angewendet wurde. Eine einfachere Möglichkeit, eine einzelne Animation auf eine <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Eigenschaft im Code anzuwenden, ist die Verwendung der Methode. Ein Beispiel finden Sie unter [Animieren einer Eigenschaft ohne Verwendung eines Storyboards](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
- [Beispiel einer Pfadanimation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
