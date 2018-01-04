---
title: 'Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads (MatrixAnimation)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c001c0969e42c1eaadad6c029ae86009176b9eb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>Gewusst wie: Drehen eines Objekts mithilfe eines geometrischen Pfads (MatrixAnimation)
Dieses Beispiel zeigt, wie eine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> und ein <xref:System.Windows.Media.MatrixTransform> gedreht (PowerPivot) ein Objekt entlang eines geometrischen Pfads definiert durch ein <xref:System.Windows.Media.PathGeometry> Objekt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> zu animierende Objekt die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>. Die <xref:System.Windows.Media.MatrixTransform> wird auf eine Schaltfläche angewendet und bewirkt, dass es entlang eines Kurvenpfads zu verschieben. Da die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> -Eigenschaftensatz auf `true`, das Rechteck entlang der Tangente des Pfads gedreht wird.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Die Codeversion des obigen Beispiels verwendet eine <xref:System.Windows.Media.Animation.Storyboard> zum Animieren der <xref:System.Windows.Media.EllipseGeometry>, obwohl nur eine einzige Animation angewendet wurde. Eine einfachere Möglichkeit zum Anwenden einer einzelnen Animation auf eine Eigenschaft im Code ist die Verwendung der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode. Ein Beispiel finden Sie unter [Vorgehensweise: Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Beispiel zu Textanimation](http://go.microsoft.com/fwlink/?LinkID=160028)
