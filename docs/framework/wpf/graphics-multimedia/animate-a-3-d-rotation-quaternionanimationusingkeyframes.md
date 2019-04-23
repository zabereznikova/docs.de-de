---
title: 'Vorgehensweise: Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 87176df26405a69cb2c3d63620def0575b750b52
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338019"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="92e60-102">Vorgehensweise: Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="92e60-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="92e60-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt gedreht.</span><span class="sxs-lookup"><span data-stu-id="92e60-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="92e60-104">In dieser Animation werden die folgenden Keyframes verwendet:</span><span class="sxs-lookup"><span data-stu-id="92e60-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="92e60-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92e60-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="92e60-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> wird verwendet, um einen plötzlichen "springt" zwischen den Werten (keine Interpolation) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92e60-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="92e60-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> wird verwendet, um einen variablen Übergang zwischen Werten, die je erstellt die <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="92e60-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="92e60-108">Im folgenden Beispiel wird dieser Teil der Animation zunächst langsam gegen Ende des Zeitabschnitts, exponentiell beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="92e60-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92e60-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92e60-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="92e60-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92e60-110">See also</span></span>

- [<span data-ttu-id="92e60-111">Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="92e60-111">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="92e60-112">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="92e60-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="92e60-113">Animieren einer 3D-Drehung mit Quaternionen</span><span class="sxs-lookup"><span data-stu-id="92e60-113">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="92e60-114">Animieren einer 3D-Drehung mithilfe von Keyframes (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="92e60-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="92e60-115">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="92e60-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="92e60-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="92e60-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
