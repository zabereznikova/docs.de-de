---
title: 'Gewusst wie: Animieren einer 3D-Rotation mit Key Frames (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112296"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="cfa16-102">Gewusst wie: Animieren einer 3D-Rotation mit Key Frames (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="cfa16-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="cfa16-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt drehen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="cfa16-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="cfa16-104">Diese Animation verwendet die folgenden Schlüsselbilder:</span><span class="sxs-lookup"><span data-stu-id="cfa16-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="cfa16-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfa16-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="cfa16-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um plötzliche "Sprünge" zwischen Werten zu erstellen (keine Interpolation).</span><span class="sxs-lookup"><span data-stu-id="cfa16-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="cfa16-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>wird verwendet, um einen Variablenübergang <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> zwischen Werten je nach Eigenschaft zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfa16-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="cfa16-108">Im folgenden Beispiel beginnt dieser Teil der Animation langsam, aber gegen Ende des Zeitsegments exponentiell.</span><span class="sxs-lookup"><span data-stu-id="cfa16-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfa16-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfa16-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cfa16-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfa16-110">See also</span></span>

- [<span data-ttu-id="cfa16-111">Animieren einer 3D-Rotation mithilfe von Storyboards</span><span class="sxs-lookup"><span data-stu-id="cfa16-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="cfa16-112">Animieren einer 3D-Rotation mithilfe von Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="cfa16-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="cfa16-113">Animieren einer 3D-Rotation mithilfe von Quaternions</span><span class="sxs-lookup"><span data-stu-id="cfa16-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="cfa16-114">Animieren einer 3D-Rotation mithilfe von Key Frames (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="cfa16-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="cfa16-115">3D-Grafikübersicht</span><span class="sxs-lookup"><span data-stu-id="cfa16-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="cfa16-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="cfa16-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
