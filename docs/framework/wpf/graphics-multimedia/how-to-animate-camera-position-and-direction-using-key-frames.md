---
title: 'Vorgehensweise: Animieren von Kameraposition und -richtung mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 44464cc314d649516998338e36c1b523101ac4e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651336"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Vorgehensweise: Animieren von Kameraposition und -richtung mithilfe von Keyframes
Im folgenden Beispiel <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> wird verwendet, um die Position des Animieren einer <xref:System.Windows.Media.Media3D.PerspectiveCamera> in einer 3D-Szene. Darüber hinaus <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> wird verwendet, um die Richtung zu animieren, die Kamera in der 3D-Szene verweist. Beide dieser Animationen verwenden mehrere Keyframes, die eine Reihe von Animationseffekten zu erstellen:  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> und <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> und <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> verwendet, um einen plötzlichen "springt" zwischen den Werten (keine Interpolation) zu erstellen.  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> und <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> verwendet, um einen variablen Übergang zwischen Werten, je nach Erstellen der <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> Eigenschaft. Im folgenden Beispiel wird die Animation zunächst langsam gegen Ende des Zeitabschnitts, exponentiell beschleunigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Animieren der Kameraposition und -richtung in 3D-Szenen](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
