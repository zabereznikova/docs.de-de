---
title: 'Gewusst wie: Animieren einer Matrix mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 862e1afdcd823181dff0948fab43b1656b85f721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Gewusst wie: Animieren einer Matrix mithilfe von Keyframes
In diesem Beispiel wird gezeigt, wie zum Animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform> mithilfe von Keyframes.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> Klasse zum Animieren der <xref:System.Windows.Media.MatrixTransform.Matrix%2A> Eigenschaft eine <xref:System.Windows.Media.MatrixTransform>. Im Beispiel wird die <xref:System.Windows.Media.MatrixTransform> Objekt, das die Darstellung und die Position des transformiert eine <xref:System.Windows.Controls.Button>.  
  
 Diese Animation verwendet die <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> -Klasse zum Erstellen von zwei Keyframes und wird mit ihnen Folgendes:  
  
1.  Erstellt eine Animation der ersten <xref:System.Windows.Media.Matrix> während der ersten 0,2 Sekunden. Die Beispiel-Änderungen der <xref:System.Windows.Media.Matrix.M11%2A> und <xref:System.Windows.Media.Matrix.M12%2A> Eigenschaften der <xref:System.Windows.Media.Matrix>. Diese Änderung bewirkt, dass die Schaltfläche, um stretch-verzerrt werden. Im Beispiel ändert sich auch die <xref:System.Windows.Media.Matrix.OffsetX%2A> und <xref:System.Windows.Media.Matrix.OffsetY%2A> Eigenschaften so, dass die Position der Schaltfläche zu ändern.  
  
2.  Erstellt eine Animation der zweiten <xref:System.Windows.Media.Matrix> bei 1,0 Sekunden. Die Schaltfläche bewegt sich in eine andere Position, während die Schaltfläche nicht mehr verzerrt oder gestreckt wird.  
  
3.  Die Animation wiederholt auf unbestimmte Zeit.  
  
> [!NOTE]
>  Keyframes, die Ableitung der <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> Objekt einen plötzlichen Sprünge zwischen Werten, d. h. die Verschiebung der Animation holprig ist.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
