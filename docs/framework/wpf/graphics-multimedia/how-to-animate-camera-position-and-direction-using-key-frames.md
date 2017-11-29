---
title: 'Gewusst wie: Animieren von Kameraposition und -richtung mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbac99770b5cbb7dacb0468e1a892956fda6b79c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a>Gewusst wie: Animieren von Kameraposition und -richtung mithilfe von Keyframes
Im folgenden Beispiel <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> wird verwendet, um die Position des Animieren einer <xref:System.Windows.Media.Media3D.PerspectiveCamera> in einer 3D-Szene. Darüber hinaus <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> wird verwendet, um die Richtung zu animieren, wird die Kamera in der 3D-Szene zeigt. Beide dieser Animationen verwenden mehrere Keyframes, die eine Reihe von Animationseffekte erstellen:  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>und <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> werden verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>und <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> werden verwendet, um einen plötzlichen "Sprünge" zwischen Werten (keine Interpolation) zu erstellen.  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>und <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> werden verwendet, um einen variablen Übergang zwischen Werten, je nach Erstellen der <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> Eigenschaft. Im folgenden Beispiel wird die Animation zunächst langsam gegen Ende des Zeitsegments, exponentiell beschleunigt.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Animieren der Kameraposition und -richtung in 3D-Szenen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
