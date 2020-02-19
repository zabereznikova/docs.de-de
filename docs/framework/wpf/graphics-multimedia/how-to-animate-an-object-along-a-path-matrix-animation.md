---
title: 'Gewusst wie: Animieren eines Objekts auf einem Pfad (MatrixAnimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452908"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Gewusst wie: Animieren eines Objekts auf einem Pfad (MatrixAnimation)
In diesem Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>-Klasse verwendet wird, um ein Objekt entlang eines von einem <xref:System.Windows.Media.PathGeometry>definierten Pfads zu animieren.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird Folgendes ausgeführt, um ein Objekt entlang eines Pfads zu animieren:  
  
- Wendet eine <xref:System.Windows.Media.MatrixTransform> auf das-Objekt an, um es zu verschieben.  
  
- Definiert den Pfad mithilfe eines <xref:System.Windows.Media.PathGeometry>.  
  
- Erstellt eine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> und verwendet diese, um die <xref:System.Windows.Media.Matrix>-Eigenschaft der <xref:System.Windows.Media.MatrixTransform>zu animieren. Der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> verwendet den <xref:System.Windows.Media.PathGeometry> und verwendet ihn, um <xref:System.Windows.Media.Matrix> Werte zu generieren.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Das komplette Beispiel finden Sie unter [Beispiel für Pfad Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations). Weitere Informationen zu geometrischen Pfaden finden Sie in der [Übersicht](geometry-overview.md)über die Geometrie.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Beispiel zu Textanimation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
