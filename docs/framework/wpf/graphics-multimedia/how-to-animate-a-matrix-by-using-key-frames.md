---
title: 'Gewusst wie: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344921"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Gewusst wie: Animieren einer Matrix mithilfe von Keyframes
In diesem Beispiel wird <xref:System.Windows.Media.MatrixTransform.Matrix%2A> gezeigt, <xref:System.Windows.Media.MatrixTransform> wie die Eigenschaft eines mithilfe von Schlüsselbildern animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Klasse <xref:System.Windows.Media.MatrixTransform>verwendet, um die Eigenschaft einer zu animieren. Im Beispiel <xref:System.Windows.Media.MatrixTransform> wird das Objekt verwendet, <xref:System.Windows.Controls.Button>um die Darstellung und Position einer zu transformieren.  
  
 Diese Animation <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> verwendet die Klasse, um zwei Schlüsselbilder zu erstellen, und führt die folgenden Schritte mit:  
  
1. Animiert <xref:System.Windows.Media.Matrix> die erste in den ersten 0,2 Sekunden. Das Beispiel <xref:System.Windows.Media.Matrix.M11%2A> ändert <xref:System.Windows.Media.Matrix.M12%2A> die <xref:System.Windows.Media.Matrix>und Eigenschaften der . Diese Änderung bewirkt, dass sich die Schaltfläche dehnt und verzerrt wird. Im Beispiel werden <xref:System.Windows.Media.Matrix.OffsetX%2A> <xref:System.Windows.Media.Matrix.OffsetY%2A> auch die und-Eigenschaften so geändert, dass die Schaltfläche die Position ändert.  
  
2. Animiert <xref:System.Windows.Media.Matrix> die Sekunde mit 1,0 Sekunden. Die Schaltfläche wird an eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt ist.  
  
3. Wiederholt die Animation auf unbestimmte Zeit.  
  
> [!NOTE]
> Schlüsselbilder, die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> vom Objekt ableiten, erzeugen plötzliche Sprünge zwischen Werten, d. h., die Bewegung der Animation ist ruckartig.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Themen zur Vorgehensweise mit Keyframes](key-frame-animation-how-to-topics.md)
