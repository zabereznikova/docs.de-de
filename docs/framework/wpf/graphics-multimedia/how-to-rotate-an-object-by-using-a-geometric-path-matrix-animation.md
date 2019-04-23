---
title: 'Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 8f1b0ac42ea7509f8bc22b0bd2f50e2f96b5bee5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087884"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Vorgehensweise: Drehen eines Objekts mithilfe eines geometrischen Pfads (Matrixanimation)
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> und ein <xref:System.Windows.Media.MatrixTransform> gedreht (PowerPivot) eines Objekts entlang eines geometrischen Pfads durch definiert eine <xref:System.Windows.Media.PathGeometry> Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>. Die <xref:System.Windows.Media.MatrixTransform> ist auf eine Schaltfläche angewendet und bewirkt, dass es entlang eines gekrümmten Pfads verschoben. Da die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaftensatz auf `true`, dreht sich das Rechteck entlang der Tangente des Pfads.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Die Codeversion des vorhergehenden Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.Media.EllipseGeometry>, auch wenn nur eine einzige Animation angewendet wurde. Eine einfachere Möglichkeit zum Anwenden einer einzelnen Animation auf eine Eigenschaft im Code ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](path-animation-how-to-topics.md)
- [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028)
