---
title: 'Vorgehensweise: Sammeln von Animationen während Wiederholungszyklen'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591472"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="dfec3-102">Vorgehensweise: Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="dfec3-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="dfec3-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft für "accumulate" Animationswerten während Wiederholungszyklen.</span><span class="sxs-lookup"><span data-stu-id="dfec3-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfec3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfec3-104">Example</span></span>  
 <span data-ttu-id="dfec3-105">Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft, um die Basiswerte einer Animation Wiederholungszyklen.</span><span class="sxs-lookup"><span data-stu-id="dfec3-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="dfec3-106">Angenommen, Sie festlegen, dass eine Animation 9-Mal wiederholt werden soll (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 X"), und legen Sie die Eigenschaft animiert zwischen 10 und 15 (From = 10 To = 15), die Eigenschaft von 10 bis 15 animiert während des ersten Zyklus von 15 bis 20, bei der zweiten , von 20 bis 25 während der dritten Zyklus und So weiter.</span><span class="sxs-lookup"><span data-stu-id="dfec3-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="dfec3-107">Daher verwendet jeder Animationszyklus den Endwert der Animation aus der vorherigen Animationszyklus als Basiswert.</span><span class="sxs-lookup"><span data-stu-id="dfec3-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="dfec3-108">Sie können die `IsCumulative` Eigenschaft mit dem meisten grundlegenden und die meisten Keyframe-Animationen.</span><span class="sxs-lookup"><span data-stu-id="dfec3-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="dfec3-109">Weitere Informationen finden Sie unter [Übersicht über Animationen](animation-overview.md) und [Übersicht über Keyframe Animationen](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dfec3-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="dfec3-110">Das folgende Beispiel zeigt dieses Verhalten, indem Sie die Breite von vier Rechtecken animieren.</span><span class="sxs-lookup"><span data-stu-id="dfec3-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="dfec3-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dfec3-111">The example:</span></span>  
  
- <span data-ttu-id="dfec3-112">Erstellt eine Animation die erste Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="dfec3-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="dfec3-113">Animiert das zweite Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft auf den Standardwert des `false`.</span><span class="sxs-lookup"><span data-stu-id="dfec3-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
- <span data-ttu-id="dfec3-114">Animiert die dritte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="dfec3-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="dfec3-115">Animiert die letzte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="dfec3-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dfec3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfec3-116">See also</span></span>

- [<span data-ttu-id="dfec3-117">Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert</span><span class="sxs-lookup"><span data-stu-id="dfec3-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="dfec3-118">Wiederholen einer Animation</span><span class="sxs-lookup"><span data-stu-id="dfec3-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="dfec3-119">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="dfec3-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="dfec3-120">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="dfec3-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="dfec3-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="dfec3-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
