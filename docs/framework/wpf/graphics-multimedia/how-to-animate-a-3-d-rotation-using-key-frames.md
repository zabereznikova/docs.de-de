---
title: 'Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca1b49277792e89f1d0cc7ca213d02978bb4dee3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a>Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes
Im folgenden Beispiel <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt gedreht wird, während die Achse der Drehung eine Animation, was zu einem "bringen". Dieser Animation verwendet folgende Keyframes:  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um einen plötzlichen "Sprünge" zwischen Werten (keine Interpolation) zu erstellen.  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>Dient zum Erstellen eines Variablen Übergangs zwischen Werten, je nach den <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft. Im folgenden Beispiel wird in diesem Teil der Animation zunächst langsam gegen Ende des Zeitsegments, exponentiell beschleunigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Übersicht über Keyframe-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Animieren einer 3D-Drehung mit Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [Animieren einer 3D-Drehung mit Rotation3DAnimation](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [Animieren einer 3D-Drehung mit Quaternionen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
