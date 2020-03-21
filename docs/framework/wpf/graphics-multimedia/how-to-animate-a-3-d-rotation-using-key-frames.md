---
title: 'Gewusst wie: Animieren einer 3D-Rotation mithilfe von Key Frames'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112309"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a><span data-ttu-id="fe988-102">Gewusst wie: Animieren einer 3D-Rotation mithilfe von Key Frames</span><span class="sxs-lookup"><span data-stu-id="fe988-102">How to: Animate a 3D Rotation Using Key Frames</span></span>
<span data-ttu-id="fe988-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt drehen zu lassen, während seine Drehachse animiert wird, was zu einem "Wackeln" führt.</span><span class="sxs-lookup"><span data-stu-id="fe988-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="fe988-104">Diese Animation verwendet die folgenden Schlüsselbilder:</span><span class="sxs-lookup"><span data-stu-id="fe988-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="fe988-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe988-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="fe988-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um plötzliche "Sprünge" zwischen Werten zu erstellen (keine Interpolation).</span><span class="sxs-lookup"><span data-stu-id="fe988-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="fe988-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>wird verwendet, um einen Variablenübergang <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> zwischen Werten je nach Eigenschaft zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe988-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="fe988-108">Im folgenden Beispiel beginnt dieser Teil der Animation langsam, aber gegen Ende des Zeitsegments exponentiell.</span><span class="sxs-lookup"><span data-stu-id="fe988-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe988-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe988-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fe988-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe988-110">See also</span></span>

- [<span data-ttu-id="fe988-111">3D-Grafikübersicht</span><span class="sxs-lookup"><span data-stu-id="fe988-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="fe988-112">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="fe988-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="fe988-113">Animieren einer 3D-Rotation mithilfe von Storyboards</span><span class="sxs-lookup"><span data-stu-id="fe988-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="fe988-114">Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="fe988-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="fe988-115">Animieren einer 3D-Rotation mithilfe von Quaternions</span><span class="sxs-lookup"><span data-stu-id="fe988-115">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="fe988-116">Animieren einer 3D-Rotation mithilfe von Key Frames (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="fe988-116">Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
