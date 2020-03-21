---
title: 'Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112209"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen
Das folgende Beispiel zeigt, wie Sie die Position einer Kamera animieren und die Richtung animieren, in der sie in einer 3D-Szene zeigt. Dies geschieht, <xref:System.Windows.Media.Animation.Point3DAnimation> <xref:System.Windows.Media.Animation.Vector3DAnimation> indem sie <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> die bzw. <xref:System.Windows.Media.Media3D.PerspectiveCamera>Eigenschaften der verwendet und animiert. Sie können eine Animation wie diese verwenden, um die Ansicht einer Szene als Reaktion auf ein Ereignis zu ändern.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [Animieren von Kameraposition und -richtung mithilfe von Keyframes](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
