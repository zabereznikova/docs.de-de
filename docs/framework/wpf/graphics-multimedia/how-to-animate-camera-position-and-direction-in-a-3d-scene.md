---
title: 'Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8e80f1032e886d59240b74281c2ed87ad5743a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="bc07c-102">Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen</span><span class="sxs-lookup"><span data-stu-id="bc07c-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="bc07c-103">Das folgende Beispiel zeigt, wie zum Animieren der Kameraposition und die Richtung, die sie in einer 3D-Szene verweist.</span><span class="sxs-lookup"><span data-stu-id="bc07c-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="bc07c-104">Dies erfolgt mithilfe von <xref:System.Windows.Media.Animation.Point3DAnimation> und <xref:System.Windows.Media.Animation.Vector3DAnimation> zum Animieren der <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> und <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> Eigenschaften bzw. der die <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="bc07c-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="bc07c-105">Sie könnten eine Animation wie folgt verwenden, um eines Betrachters der Szene als Reaktion auf ein Ereignis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bc07c-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc07c-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc07c-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bc07c-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc07c-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [<span data-ttu-id="bc07c-108">Animieren von Kameraposition und -richtung mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="bc07c-108">Animate Camera Position and Direction Using Key Frames</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [<span data-ttu-id="bc07c-109">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="bc07c-109">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
