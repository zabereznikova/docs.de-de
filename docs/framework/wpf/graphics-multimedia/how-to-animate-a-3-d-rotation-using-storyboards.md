---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mit Storyboards'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 03b01205f1a31426a01b09533b350682c384df4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146197"
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a>Vorgehensweise: Animieren einer 3D-Drehung mit Storyboards
Das folgende Beispiel zeigt, wie Sie ein 3D-Objekt gedreht, während es "durch die Animation wackelt" die <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> und <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Eigenschaften eine <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt. Dies <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> Objekt gibt an, die Drehungstransformation des 3D-Objekts, und so animieren dessen Eigenschaften die Auswirkungen der gewünschten Rotation erstellt. In diesem Storyboard <xref:System.Windows.Media.Animation.DoubleAnimation> wird verwendet, um das Animieren der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> Eigenschaft beim <xref:System.Windows.Media.Animation.Vector3DAnimation> wird verwendet, um das Animieren der <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Animieren einer 3D-Drehung mit Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [Animieren einer 3D-Drehung mithilfe von Keyframes (Rotation3DAnimationUsingKeyFrames)](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [Übersicht über 3D-Grafiken](3-d-graphics-overview.md)
- [Übersicht über Storyboards](storyboards-overview.md)
