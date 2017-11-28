---
title: 'Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8dad8934dacd64f31cf65d7517d8c48114522505
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="48f85-102">Gewusst wie: Animieren einer 3D-Drehung mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="48f85-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="48f85-103">Im folgenden Beispiel <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> wird verwendet, um ein 3D-Objekt gedreht wird, während die Achse der Drehung eine Animation, was zu einem "bringen".</span><span class="sxs-lookup"><span data-stu-id="48f85-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="48f85-104">Dieser Animation verwendet folgende Keyframes:</span><span class="sxs-lookup"><span data-stu-id="48f85-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="48f85-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>wird verwendet, um eine glatte, lineare Interpolation zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="48f85-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="48f85-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>wird verwendet, um einen plötzlichen "Sprünge" zwischen Werten (keine Interpolation) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="48f85-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="48f85-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>Dient zum Erstellen eines Variablen Übergangs zwischen Werten, je nach den <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="48f85-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="48f85-108">Im folgenden Beispiel wird in diesem Teil der Animation zunächst langsam gegen Ende des Zeitsegments, exponentiell beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="48f85-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48f85-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48f85-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="48f85-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48f85-110">See Also</span></span>  
 [<span data-ttu-id="48f85-111">Übersicht über 3D-Grafiken</span><span class="sxs-lookup"><span data-stu-id="48f85-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="48f85-112">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="48f85-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="48f85-113">Animieren einer 3D-Drehung mit Storyboards</span><span class="sxs-lookup"><span data-stu-id="48f85-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="48f85-114">Animieren einer 3D-Drehung mit Rotation3DAnimation</span><span class="sxs-lookup"><span data-stu-id="48f85-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="48f85-115">Animieren einer 3D-Drehung mit Quaternionen</span><span class="sxs-lookup"><span data-stu-id="48f85-115">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [<span data-ttu-id="48f85-116">Animieren einer 3D-Drehung mit Keyframes (QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="48f85-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
