---
title: 'Vorgehensweise: Animieren einer Zeichenfolge mithilfe von Keyframes'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4a37408ad90fda12a95e66c1b44018967b376837
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204171"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="8db57-102">Vorgehensweise: Animieren einer Zeichenfolge mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="8db57-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="8db57-103">Dieses Beispiel zeigt, wie Sie eine Zeichenfolge, animieren, die in diesem Beispiel wird die <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button> -Steuerelement, mithilfe von Keyframes.</span><span class="sxs-lookup"><span data-stu-id="8db57-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8db57-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8db57-104">Example</span></span>  
 <span data-ttu-id="8db57-105">Im folgenden Beispiel wird die <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> -Klasse zum Animieren der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="8db57-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="8db57-106">Alle Keyframes in diesem Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> Klasse, da die Animation einer Zeichenfolge, die mit Keyframes erstellt wird nur diskrete Keyframes verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="8db57-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="8db57-107">Diskrete Keyframes wie <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> abrupte Sprünge zwischen Werten, d. h. erstellen, Änderungen an der Animation schnell erfolgen und nicht subtil.</span><span class="sxs-lookup"><span data-stu-id="8db57-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="8db57-108">Das vollständige Beispiel finden Sie unter [Beispiel für eine KeyFrame-Animation](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="8db57-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8db57-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8db57-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="8db57-110">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="8db57-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="8db57-111">Key-Frame How-to Topics (Themen zur Vorgehensweise zu Keyframes)</span><span class="sxs-lookup"><span data-stu-id="8db57-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
