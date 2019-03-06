---
title: 'Vorgehensweise: Animieren der Breite eines Rahmens mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: b131ce444a91e518f6372b7aeac603687141b262
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360947"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="e4a6d-102">Vorgehensweise: Animieren der Breite eines Rahmens mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="e4a6d-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="e4a6d-103">Dieses Beispiel zeigt, wie Sie animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A> Eigenschaft eine <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4a6d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4a6d-104">Example</span></span>  
 <span data-ttu-id="e4a6d-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Controls.Control.BorderThickness%2A> Eigenschaft eine <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="e4a6d-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="e4a6d-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="e4a6d-107">In der ersten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> Klasse, um die Stärke des Rahmens graduell zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="e4a6d-108">Im Beispiel wird <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> um eine glatte, lineare Erhöhung zwischen Werten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="e4a6d-109">Am Ende der nächsten halben Sekunde wird eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> Klasse, um die Stärke des Rahmens abrupt zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="e4a6d-110">Diskrete Keyframes wie diejenigen, die von abgeleiteten <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, die Verschiebung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="e4a6d-111">In den letzten zwei Sekunden wird eine Instanz von der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> Klasse, um die Breite des Rahmens zu verringern.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="e4a6d-112">Spline-Keyframes wie jene, die von abgeleiteten <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> erzeugen einen variablen Übergang zwischen Werten, die von der <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="e4a6d-113">In diesem Keyframe ist die Animation zunächst langsam und beschleunigt dann exponentiell im letzten Bereich des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="e4a6d-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e4a6d-114">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="e4a6d-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a6d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4a6d-115">See also</span></span>
- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="e4a6d-116">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="e4a6d-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="e4a6d-117">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="e4a6d-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="e4a6d-118">Animieren eines BorderThickness-Werts</span><span class="sxs-lookup"><span data-stu-id="e4a6d-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
