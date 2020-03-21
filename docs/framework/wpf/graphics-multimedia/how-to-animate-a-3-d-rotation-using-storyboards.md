---
title: 'Gewusst wie: Animieren einer 3D-Rotation mithilfe von Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112212"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a>Gewusst wie: Animieren einer 3D-Rotation mithilfe von Storyboards
Das folgende Beispiel zeigt, wie ein 3D-Objekt gedreht wird, während <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> es <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> durch <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Animieren der und Eigenschaften eines Objekts "wackelt". Dieses <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt gibt die Rotationstransformation des 3D-Objekts an, so dass durch Animieren seiner Eigenschaften der Wunschrotationseffekt erzeugt wird. Im Storyboard <xref:System.Windows.Media.Animation.DoubleAnimation> wird verwendet, <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> um <xref:System.Windows.Media.Animation.Vector3DAnimation> die Eigenschaft zu <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> animieren, während sie zum Animieren der Eigenschaft verwendet wird.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animieren einer 3D-Rotation mithilfe von Key Frames (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
