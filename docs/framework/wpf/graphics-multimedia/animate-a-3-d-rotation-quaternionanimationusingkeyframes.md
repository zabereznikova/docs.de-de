---
title: 'Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes (QuaternionAnimationUsingKeyFrames)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 3-D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3-D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89719cbcb72c5c24654962e9eb17a540224fd588
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="009dd-102">Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="009dd-102">How to: Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="009dd-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt drehen.</span><span class="sxs-lookup"><span data-stu-id="009dd-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="009dd-104">Dieser Animation verwendet folgende Keyframes:</span><span class="sxs-lookup"><span data-stu-id="009dd-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="009dd-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="009dd-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="009dd-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um einen plötzlichen "Sprünge" zwischen Werten (keine Interpolation) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="009dd-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="009dd-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>Dient zum Erstellen eines Variablen Übergangs zwischen Werten, je nach den <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="009dd-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="009dd-108">Im folgenden Beispiel wird in diesem Teil der Animation zunächst langsam gegen Ende des Zeitsegments, exponentiell beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="009dd-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="009dd-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="009dd-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="009dd-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="009dd-110">See Also</span></span>  
 [<span data-ttu-id="009dd-111">Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="009dd-111">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="009dd-112">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="009dd-112">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="009dd-113">Animieren einer 3D-Drehung mit Quaternionen</span><span class="sxs-lookup"><span data-stu-id="009dd-113">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [<span data-ttu-id="009dd-114">Animieren einer 3D-Drehung mithilfe von Keyframes (Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="009dd-114">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="009dd-115">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="009dd-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="009dd-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="009dd-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
