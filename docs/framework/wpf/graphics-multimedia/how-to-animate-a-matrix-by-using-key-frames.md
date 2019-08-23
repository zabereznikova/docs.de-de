---
title: 'Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963024"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Vorgehensweise: Animieren einer Matrix mithilfe von Keyframes
In diesem Beispiel <xref:System.Windows.Media.MatrixTransform> wird gezeigt, wie <xref:System.Windows.Media.MatrixTransform.Matrix%2A> die-Eigenschaft eines mithilfe von Keyframes animiert wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> -Klasse verwendet, <xref:System.Windows.Media.MatrixTransform.Matrix%2A> um die- <xref:System.Windows.Media.MatrixTransform>Eigenschaft eines zu animieren. Im Beispiel wird das <xref:System.Windows.Media.MatrixTransform> -Objekt verwendet, um die Darstellung und Position <xref:System.Windows.Controls.Button>eines zu transformieren.  
  
 Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> -Klasse, um zwei Keyframes zu erstellen und mit Ihnen die folgenden Aktionen durchführen zu können:  
  
1. Animiert den ersten <xref:System.Windows.Media.Matrix> während der ersten 0,2 Sekunden. Im Beispiel werden die <xref:System.Windows.Media.Matrix.M11%2A> - <xref:System.Windows.Media.Matrix.M12%2A> Eigenschaft und die <xref:System.Windows.Media.Matrix>-Eigenschaft der geändert. Diese Änderung bewirkt, dass die Schaltfläche gestreckt wird und verzerrt wird. Das Beispiel ändert auch die <xref:System.Windows.Media.Matrix.OffsetX%2A> - <xref:System.Windows.Media.Matrix.OffsetY%2A> Eigenschaft und die-Eigenschaft, sodass die Schaltfläche die Position ändert.  
  
2. Animiert den zweiten <xref:System.Windows.Media.Matrix> um 1,0 Sekunden. Die Schaltfläche wird an eine andere Position verschoben, während die Schaltfläche nicht mehr verzerrt oder gestreckt wird.  
  
3. Wiederholt die Animation unbegrenzt.  
  
> [!NOTE]
> Keyframes, die vom <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> -Objekt abgeleitet werden, erzeugen plötzliche Sprünge zwischen Werten, d. h., dass die Bewegung der Animation ruckartig ist.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](key-frame-animation-how-to-topics.md)
