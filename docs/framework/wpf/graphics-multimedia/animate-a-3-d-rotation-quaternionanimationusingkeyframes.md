---
title: 'Gewusst wie: Animieren einer 3D-Rotation mit Key Frames (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112296"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a>Gewusst wie: Animieren einer 3D-Rotation mit Key Frames (QuaternionAnimationUsingKeyFrames)
Im folgenden Beispiel <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt drehen zu lassen. Diese Animation verwendet die folgenden Schlüsselbilder:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um plötzliche "Sprünge" zwischen Werten zu erstellen (keine Interpolation).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>wird verwendet, um einen Variablenübergang <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> zwischen Werten je nach Eigenschaft zu erstellen. Im folgenden Beispiel beginnt dieser Teil der Animation langsam, aber gegen Ende des Zeitsegments exponentiell.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Animieren einer 3D-Rotation mithilfe von Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animieren einer 3D-Rotation mithilfe von Quaternions](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animieren einer 3D-Rotation mithilfe von Key Frames (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
