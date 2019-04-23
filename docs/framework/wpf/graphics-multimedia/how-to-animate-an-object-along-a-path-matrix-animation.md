---
title: 'Vorgehensweise: Animieren eines Objekts auf einem Pfad (Matrixanimation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: ab15126680b7d8c6936246a7dae2f67c7541233b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190924"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>Vorgehensweise: Animieren eines Objekts auf einem Pfad (Matrixanimation)
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> Klasse, um ein Objekt entlang eines Pfads zu animieren, die von definiert ist eine <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird Folgendes ausgeführt, um ein Objekt entlang eines Pfads zu animieren:  
  
-   Wendet eine <xref:System.Windows.Media.MatrixTransform> auf das Objekt, um es zu verschieben.  
  
-   Definiert den Pfad mit einem <xref:System.Windows.Media.PathGeometry>.  
  
-   Erstellt eine <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> und wird verwendet, um das Animieren der <xref:System.Windows.Media.Matrix> Eigenschaft der <xref:System.Windows.Media.MatrixTransform>. Die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> nimmt die <xref:System.Windows.Media.PathGeometry> und verwendet sie zum Generieren von <xref:System.Windows.Media.Matrix> Werte.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028). Weitere Informationen zu geometrischen Pfaden finden Sie unter den [Übersicht über die Geometrie](geometry-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Beispiel zu Textanimation](https://go.microsoft.com/fwlink/?LinkID=160028)
- [Path Animation How-to Topics (Themen zur Vorgehensweise zur Pfadanimation)](path-animation-how-to-topics.md)
