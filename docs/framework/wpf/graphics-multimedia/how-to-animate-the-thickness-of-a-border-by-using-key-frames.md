---
title: 'Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344691"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="7cbe3-102">Gewusst wie: Animieren der Breite eines Rahmens mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="7cbe3-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="7cbe3-103">Dieses Beispiel zeigt, <xref:System.Windows.Controls.Control.BorderThickness%2A> wie die <xref:System.Windows.Controls.Border>Eigenschaft einer animiert wird.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cbe3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7cbe3-104">Example</span></span>  
 <span data-ttu-id="7cbe3-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> wird die <xref:System.Windows.Controls.Control.BorderThickness%2A> Klasse <xref:System.Windows.Controls.Border>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="7cbe3-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="7cbe3-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="7cbe3-107">Verwendet in der ersten Hälfte der <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> Sekunde eine Instanz der Klasse, um die Dicke der Grenze schrittweise zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="7cbe3-108">Im Beispiel <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> wird eine glatte lineare Erhöhung zwischen Werten erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="7cbe3-109">Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> eine Instanz der Klasse, um plötzlich die Dicke der Grenze zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="7cbe3-110">Diskrete Schlüsselbilder, wie <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> sie von plötzlichen Sprüngen zwischen Werten abgeleitet werden, d. h. die Bewegung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="7cbe3-111">Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> eine Instanz der Klasse, um die Dicke des Rahmens zu verringern.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="7cbe3-112">Spline-Schlüsselrahmen, wie <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> sie von abgeleitet werden, erstellen <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> einen Variablenübergang zwischen Werten entsprechend den Werten der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="7cbe3-113">In diesem Keyframe ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="7cbe3-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7cbe3-114">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="7cbe3-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbe3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cbe3-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="7cbe3-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="7cbe3-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7cbe3-117">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="7cbe3-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="7cbe3-118">Animieren eines BorderThickness-Werts</span><span class="sxs-lookup"><span data-stu-id="7cbe3-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
