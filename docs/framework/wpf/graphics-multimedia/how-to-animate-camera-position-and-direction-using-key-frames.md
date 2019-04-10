---
title: 'Vorgehensweise: Animieren von Kameraposition und -richtung mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 44464cc314d649516998338e36c1b523101ac4e2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346079"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="7c20c-102">Vorgehensweise: Animieren von Kameraposition und -richtung mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="7c20c-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="7c20c-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> wird verwendet, um die Position des Animieren einer <xref:System.Windows.Media.Media3D.PerspectiveCamera> in einer 3D-Szene.</span><span class="sxs-lookup"><span data-stu-id="7c20c-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="7c20c-104">Darüber hinaus <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> wird verwendet, um die Richtung zu animieren, die Kamera in der 3D-Szene verweist.</span><span class="sxs-lookup"><span data-stu-id="7c20c-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="7c20c-105">Beide dieser Animationen verwenden mehrere Keyframes, die eine Reihe von Animationseffekten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7c20c-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> <span data-ttu-id="7c20c-106">und <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c20c-106">and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> <span data-ttu-id="7c20c-107">und <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> verwendet, um einen plötzlichen "springt" zwischen den Werten (keine Interpolation) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7c20c-107">and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> <span data-ttu-id="7c20c-108">und <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> verwendet, um einen variablen Übergang zwischen Werten, je nach Erstellen der <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7c20c-108">and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="7c20c-109">Im folgenden Beispiel wird die Animation zunächst langsam gegen Ende des Zeitabschnitts, exponentiell beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="7c20c-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c20c-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c20c-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7c20c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c20c-111">See also</span></span>

- [<span data-ttu-id="7c20c-112">Animieren der Kameraposition und -richtung in 3D-Szenen</span><span class="sxs-lookup"><span data-stu-id="7c20c-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="7c20c-113">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="7c20c-113">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
