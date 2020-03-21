---
title: 'Gewusst wie: Animieren einer 3D-Rotation mit Quaternions'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112244"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a>Gewusst wie: Animieren einer 3D-Rotation mit Quaternions
In diesem Beispiel wird gezeigt, wie eine Drehung eines 3D-Objekts mithilfe von Quaternionen animiert wird.  
  
 Der folgende Code <xref:System.Windows.Media.Media3D.QuaternionRotation3D> zeigt einen, <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> der als <xref:System.Windows.Media.Media3D.RotateTransform3D>Wert für die Eigenschaft einer verwendet wird.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 Dies <xref:System.Windows.Media.Media3D.QuaternionRotation3D> wird <xref:System.Windows.Media.Animation.QuaternionAnimation> mit <xref:System.Windows.Media.Animation.Storyboard> einem innerhalb a mit dem Untencode animiert.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Animationen](animation-overview.md)
- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Übersicht über Transformationen](transforms-overview.md)
- [Animieren einer 3D-Rotation mithilfe von Storyboards](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
