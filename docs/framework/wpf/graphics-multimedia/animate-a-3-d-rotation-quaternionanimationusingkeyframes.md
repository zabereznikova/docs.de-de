---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 87176df26405a69cb2c3d63620def0575b750b52
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338019"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Vorgehensweise: Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)
Im folgenden Beispiel <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt gedreht. In dieser Animation werden die folgenden Keyframes verwendet:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> wird verwendet, um einen plötzlichen "springt" zwischen den Werten (keine Interpolation) zu erstellen.  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> wird verwendet, um einen variablen Übergang zwischen Werten, die je erstellt die <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft. Im folgenden Beispiel wird dieser Teil der Animation zunächst langsam gegen Ende des Zeitabschnitts, exponentiell beschleunigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Animieren einer 3D-Drehung mit Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animieren einer 3D-Drehung mit Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animieren einer 3D-Drehung mit Quaternionen](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animieren einer 3D-Drehung mithilfe von Keyframes (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
