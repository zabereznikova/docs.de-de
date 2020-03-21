---
title: 'Gewusst wie: Animieren von Kameraposition und -richtung mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112166"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Gewusst wie: Animieren von Kameraposition und -richtung mithilfe von Keyframes
Im folgenden Beispiel <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> wird verwendet, um <xref:System.Windows.Media.Media3D.PerspectiveCamera> die Position einer in einer 3D-Szene zu animieren. Darüber hinaus <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> wird verwendet, um die Richtung zu animieren, in die die Kamera in der 3D-Szene zeigt. Beide Animationen verwenden mehrere Schlüsselbilder, die eine Reihe von Animationseffekten erzeugen:  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>und <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> werden verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>und <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> werden verwendet, um plötzliche "Sprünge" zwischen Werten zu erstellen (keine Interpolation).  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>und <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> werden verwendet, um einen variablen <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> Übergang zwischen Werten je nach Eigenschaft zu erstellen. Im folgenden Beispiel startet die Animation langsam, aber gegen Ende des Zeitsegments exponentiell.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Animieren der Kameraposition und -richtung in 3D-Szenen](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
