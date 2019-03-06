---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mit Quaternionen'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 079358ec12da803c8aa497bce1c272fa51f1c3b5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368570"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="79e5f-102">Vorgehensweise: Animieren einer 3D-Drehung mit Quaternionen</span><span class="sxs-lookup"><span data-stu-id="79e5f-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="79e5f-103">Dieses Beispiel zeigt, wie eine Drehung um ein 3D-Objekt mit Quaternionen animiert wird.</span><span class="sxs-lookup"><span data-stu-id="79e5f-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="79e5f-104">Der folgende Code zeigt eine <xref:System.Windows.Media.Media3D.QuaternionRotation3D> wird als Wert für die <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="79e5f-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="79e5f-105">Dies <xref:System.Windows.Media.Media3D.QuaternionRotation3D> animiert ist mit einer <xref:System.Windows.Media.Animation.QuaternionAnimation> innerhalb einer <xref:System.Windows.Media.Animation.Storyboard> anhand des folgenden Codes.</span><span class="sxs-lookup"><span data-stu-id="79e5f-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="79e5f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79e5f-106">Example</span></span>  
 <span data-ttu-id="79e5f-107">Der folgende Code zeigt das gesamte Beispiel.</span><span class="sxs-lookup"><span data-stu-id="79e5f-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="79e5f-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79e5f-108">See also</span></span>
- [<span data-ttu-id="79e5f-109">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="79e5f-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="79e5f-110">Erstellen einer 3D-Szene</span><span class="sxs-lookup"><span data-stu-id="79e5f-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="79e5f-111">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="79e5f-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="79e5f-112">Übersicht über Transformationen</span><span class="sxs-lookup"><span data-stu-id="79e5f-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="79e5f-113">Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="79e5f-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="79e5f-114">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="79e5f-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
