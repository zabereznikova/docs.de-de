---
title: 'Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 2c33fa1ebb3c9dd4f05c24db9de42ff47c84f983
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370578"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes
Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>. Im Beispiel wird die <xref:System.Windows.Media.MatrixTransform> Objekt, das die Darstellung und die Position des transformiert eine <xref:System.Windows.Controls.Button>.  
  
 Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> Klasse, um zwei Keyframes und wird mit ihnen Folgendes:  
  
1.  Erstellt eine Animation die erste <xref:System.Windows.Media.Matrix> während der ersten 0,2 Sekunden. Die Beispiel-Änderungen der <xref:System.Windows.Media.Matrix.M11%2A> und <xref:System.Windows.Media.Matrix.M12%2A> Eigenschaften der <xref:System.Windows.Media.Matrix>. Diese Änderung bewirkt, dass die Schaltfläche zum Strecken und verzerrt werden. Im Beispiel ändert sich auch die <xref:System.Windows.Media.Matrix.OffsetX%2A> und <xref:System.Windows.Media.Matrix.OffsetY%2A> Eigenschaften so, dass die Position der Schaltfläche zu ändern.  
  
2.  Die zweite animiert <xref:System.Windows.Media.Matrix> bei 1,0 Sekunden. Die Schaltfläche wird in eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt wird.  
  
3.  Wird für die Animation endlos wiederholt.  
  
> [!NOTE]
>  Keyframes, die Ableiten der <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> objekterstellung abrupte Sprünge zwischen Werten, d. h. die Verschiebung der Animation ist ruckartig.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)
