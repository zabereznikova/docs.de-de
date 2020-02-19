---
title: 'Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453103"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>Gewusst wie: Animieren eines Objekts auf einem Pfad (Matrixanimation mit Offsetakkumulation)
In diesem Beispiel wird gezeigt, wie die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>-Klasse verwendet wird, um ein Objekt entlang eines Pfads zu animieren, und dass diese Animation ihre offset Werte bei der Wiederholung sammelt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>-Objekt verwendet, um die <xref:System.Windows.Media.MatrixTransform.Matrix%2A>-Eigenschaft einer <xref:System.Windows.Media.MatrixTransform> zu animieren, die auf eine Schaltfläche angewendet wird. Das Ergebnis ist eine Schaltfläche, die entlang eines gekrümmten Pfads verschoben wird.  
  
 Außerdem wird in diesem Beispiel die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>-Eigenschaft auf `true`festgelegt, wodurch der Offset der animierten Matrix bei Wiederholung der Animation akkumuliert wird. Durch die Offsetakkumulation bewegt sich die Schaltfläche bei Wiederholung der Animation weiter über den Bildschirm und wird nicht auf die Startposition zurückgesetzt.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Beachten Sie, dass die <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>-Eigenschaft dazu führt, dass Offset Werte über Wiederholungen akkumuliert werden, sodass keine Rotations Werte gesammelt werden. Legen Sie die Eigenschaften <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> und <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> der Animation auf `true`fest, damit die Rotations Werte akkumuliert werden.  
  
 Das komplette Beispiel finden Sie unter [Beispiel für Pfad Animation](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations). Ein Beispiel, das zeigt, wie Sie einen <xref:System.Windows.Media.Matrix> Wert entlang eines Pfades ohne Offset-Akkumulation animieren, finden Sie unter [Animieren eines Objekts entlang eines Pfads (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Animationen](animation-overview.md)
- [Gewusst-wie-Themen zur Pfadanimation](path-animation-how-to-topics.md)
