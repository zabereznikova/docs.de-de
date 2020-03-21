---
title: 'Gewusst wie: Animieren einer 3D-Rotation mithilfe von Key Frames'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112309"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a>Gewusst wie: Animieren einer 3D-Rotation mithilfe von Key Frames
Im folgenden Beispiel <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt drehen zu lassen, während seine Drehachse animiert wird, was zu einem "Wackeln" führt. Diese Animation verwendet die folgenden Schlüsselbilder:  
  
1. <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2. <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um plötzliche "Sprünge" zwischen Werten zu erstellen (keine Interpolation).  
  
3. <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>wird verwendet, um einen Variablenübergang <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> zwischen Werten je nach Eigenschaft zu erstellen. Im folgenden Beispiel beginnt dieser Teil der Animation langsam, aber gegen Ende des Zeitsegments exponentiell.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Keyframe-Animationen](key-frame-animations-overview.md)
- [Animieren einer 3D-Rotation mithilfe von Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animieren einer 3D-Rotation mithilfe von Quaternions](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [Animieren einer 3D-Rotation mithilfe von Key Frames (QuaternionAnimationUsingKeyFrames)](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
