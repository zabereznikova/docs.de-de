---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: e72ec94f830f0f5001a77e7492aa1326a47b309d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762149"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a>Vorgehensweise: Animieren einer 3D-Drehung mithilfe von Keyframes
Im folgenden Beispiel <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt gedreht wird, während die Achse der Drehung eine Animation, was zu einer "bringen". In dieser Animation werden die folgenden Keyframes verwendet:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> wird verwendet, um einen plötzlichen "springt" zwischen den Werten (keine Interpolation) zu erstellen.  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> wird verwendet, um einen variablen Übergang zwischen Werten, die je erstellt die <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft. Im folgenden Beispiel wird dieser Teil der Animation zunächst langsam gegen Ende des Zeitabschnitts, exponentiell beschleunigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Animieren einer 3D-Drehung mit Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animieren einer 3D-Drehung mit Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animieren einer 3D-Drehung mit Quaternionen](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
