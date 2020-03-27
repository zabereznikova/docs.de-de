---
title: 'Gewusst wie: Animieren eines booleschen Werts mithilfe von Keyframes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344943"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="945c2-102">Gewusst wie: Animieren eines booleschen Werts mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="945c2-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="945c2-103">In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Controls.Button> der boolesche Eigenschaftswert eines Steuerelements mithilfe von Schlüsselrahmen animiert wird.</span><span class="sxs-lookup"><span data-stu-id="945c2-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="945c2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="945c2-104">Example</span></span>  
 <span data-ttu-id="945c2-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> wird die <xref:System.Windows.UIElement.IsEnabled%2A> Klasse <xref:System.Windows.Controls.Button> verwendet, um die Eigenschaft eines Steuerelements zu animieren.</span><span class="sxs-lookup"><span data-stu-id="945c2-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="945c2-106">Alle Schlüsselrahmen in diesem Beispiel verwenden <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> eine Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="945c2-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="945c2-107">Diskrete Tastenbilder <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> wie plötzliche Sprünge zwischen Werten erstellen, das heißt, die Bewegung der Animation ist ruckartig.</span><span class="sxs-lookup"><span data-stu-id="945c2-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="945c2-108">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="945c2-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="945c2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="945c2-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="945c2-110">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="945c2-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="945c2-111">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="945c2-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
