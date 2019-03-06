---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 90e982838cb5d5b4488185c041e946c15d1e61e8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369135"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="de10b-102">Vorgehensweise: Animieren einer 3D-Drehung mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="de10b-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="de10b-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt gedreht wird, während die Achse der Drehung eine Animation, was zu einer "bringen".</span><span class="sxs-lookup"><span data-stu-id="de10b-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="de10b-104">In dieser Animation werden die folgenden Keyframes verwendet:</span><span class="sxs-lookup"><span data-stu-id="de10b-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="de10b-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de10b-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="de10b-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> wird verwendet, um einen plötzlichen "springt" zwischen den Werten (keine Interpolation) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de10b-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="de10b-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> wird verwendet, um einen variablen Übergang zwischen Werten, die je erstellt die <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="de10b-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="de10b-108">Im folgenden Beispiel wird dieser Teil der Animation zunächst langsam gegen Ende des Zeitabschnitts, exponentiell beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="de10b-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de10b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de10b-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="de10b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de10b-110">See also</span></span>
- [<span data-ttu-id="de10b-111">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="de10b-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="de10b-112">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="de10b-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="de10b-113">Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="de10b-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="de10b-114">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="de10b-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="de10b-115">Animieren einer 3D-Drehung mit Quaternionen</span><span class="sxs-lookup"><span data-stu-id="de10b-115">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="de10b-116">Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="de10b-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
