---
title: 'Gewusst wie: Animieren einer 3D-Drehung mit Quaternionen'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 4c2a46aad1feeefe5c7c31ec192f46b8c891337f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556938"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="cbf13-102">Gewusst wie: Animieren einer 3D-Drehung mit Quaternionen</span><span class="sxs-lookup"><span data-stu-id="cbf13-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="cbf13-103">In diesem Beispiel wird gezeigt, wie eine Drehung ein 3D-Objekt mit Quaternionen animiert wird.</span><span class="sxs-lookup"><span data-stu-id="cbf13-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="cbf13-104">Der folgende Code zeigt eine <xref:System.Windows.Media.Media3D.QuaternionRotation3D> verwendet als der Wert für die <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="cbf13-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="cbf13-105">Dies <xref:System.Windows.Media.Media3D.QuaternionRotation3D> animiert wird, mit einem <xref:System.Windows.Media.Animation.QuaternionAnimation> innerhalb einer <xref:System.Windows.Media.Animation.Storyboard> mit den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="cbf13-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="cbf13-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbf13-106">Example</span></span>  
 <span data-ttu-id="cbf13-107">Der folgende Code zeigt das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cbf13-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cbf13-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbf13-108">See Also</span></span>  
 [<span data-ttu-id="cbf13-109">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="cbf13-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="cbf13-110">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="cbf13-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="cbf13-111">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="cbf13-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="cbf13-112">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="cbf13-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="cbf13-113">Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="cbf13-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="cbf13-114">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="cbf13-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
