---
title: 'Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344666"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="bafcd-102">Gewusst wie: Animieren einer Zeichenfolge mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="bafcd-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="bafcd-103">In diesem Beispiel wird gezeigt, wie eine <xref:System.Windows.Controls.ContentControl.Content%2A> Zeichenfolge, <xref:System.Windows.Controls.Button> die in diesem Beispiel die Eigenschaft eines Steuerelements ist, mithilfe von Schlüsselrahmen animiert wird.</span><span class="sxs-lookup"><span data-stu-id="bafcd-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bafcd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bafcd-104">Example</span></span>  
 <span data-ttu-id="bafcd-105">Im folgenden Beispiel <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Klasse <xref:System.Windows.Controls.Button>verwendet, um die Eigenschaft einer zu animieren.</span><span class="sxs-lookup"><span data-stu-id="bafcd-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="bafcd-106">Alle Schlüsselbilder in diesem Beispiel verwenden <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> eine Instanz der Klasse, da eine Zeichenfolgenanimation, die mit Schlüsselbildern erstellt wird, nur diskrete Schlüsselrahmen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="bafcd-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="bafcd-107">Diskrete Schlüsselbilder <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> wie plötzliche Sprünge zwischen Werten erstellen, d. h. Änderungen an der Animation treten schnell auf und sind nicht subtil.</span><span class="sxs-lookup"><span data-stu-id="bafcd-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="bafcd-108">Das vollständige Beispiel finden Sie unter [Beispiel für eine Keyframe-Animation](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="bafcd-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafcd-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bafcd-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="bafcd-110">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="bafcd-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="bafcd-111">Themen zur Vorgehensweise mit Keyframes</span><span class="sxs-lookup"><span data-stu-id="bafcd-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
