---
title: 'Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344663"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="2ab89-102">Gewusst wie: Animieren von Größenänderungen mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="2ab89-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="2ab89-103">In diesem Beispiel wird das Animieren von Größenänderungen mithilfe von Keyframes veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ab89-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ab89-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ab89-104">Example</span></span>  
 <span data-ttu-id="2ab89-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> wird die <xref:System.Windows.Media.ArcSegment.Size%2A> Klasse <xref:System.Windows.Media.ArcSegment>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="2ab89-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="2ab89-106">In dieser Animation werden drei Keyframes folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="2ab89-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="2ab89-107">Verwendet in der ersten Hälfte der Animation <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> eine Instanz der Klasse, um die Größe des Bogens schrittweise zu erhöhen. Lineare Schlüsselrahmen wie <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> erstellen einen glatten linearen Übergang zwischen Werten.</span><span class="sxs-lookup"><span data-stu-id="2ab89-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="2ab89-108">Verwendet am Ende der nächsten halben Sekunde <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> eine Instanz der Klasse, um die Größe des Bogens plötzlich zu erhöhen. Diskrete Schlüsselrahmen <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> wie plötzliche Sprünge zwischen Werten erstellen, d. h., die Größenänderungen treten plötzlich auf und sind nicht subtil.</span><span class="sxs-lookup"><span data-stu-id="2ab89-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="2ab89-109">Verwendet in den letzten zwei Sekunden <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> eine Instanz der Klasse, um die Größe des Bogens zu erhöhen. Spline-Schlüsselrahmen <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> wie erstellen sie einen variablen Übergang <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> zwischen Werten entsprechend den Werten der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2ab89-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2ab89-110">In diesem Beispiel wächst die Größe des Bogens zunächst nur langsam und steigt dann exponentiell zum Ende des Zeitabschnitts.</span><span class="sxs-lookup"><span data-stu-id="2ab89-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="2ab89-111">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="2ab89-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab89-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ab89-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="2ab89-113">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="2ab89-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="2ab89-114">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="2ab89-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
