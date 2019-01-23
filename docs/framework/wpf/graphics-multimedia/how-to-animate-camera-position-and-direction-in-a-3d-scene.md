---
title: 'Vorgehensweise: Animieren der Kameraposition und –richtung in 3D-Szenen'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 18941f32de02b6e281df6c2c54c6c666dae63197
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564171"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Vorgehensweise: Animieren der Kameraposition und –richtung in 3D-Szenen
Das folgende Beispiel zeigt das Animieren der Position der Kamera und die Richtung, die er in einer 3D-Szene verweist zu animieren. Dies erfolgt mithilfe von <xref:System.Windows.Media.Animation.Point3DAnimation> und <xref:System.Windows.Media.Animation.Vector3DAnimation> zum Animieren der <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> Eigenschaften bzw. die <xref:System.Windows.Media.Media3D.PerspectiveCamera>. Sie können eine Animation wie folgt verwenden, um Perspektive Anzeigen einer Szene als Reaktion auf ein Ereignis zu ändern.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Animieren von Kameraposition und -richtung mithilfe von Keyframes](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)
- [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
