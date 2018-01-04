---
title: "Gewusst wie: Sammeln von Animationswerten während Wiederholungszyklen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a91856cdfcf1ca7ae87e8e571306170feecb7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="51120-102">Gewusst wie: Sammeln von Animationswerten während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="51120-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="51120-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft, um die Animationswerte Wiederholungszyklen.</span><span class="sxs-lookup"><span data-stu-id="51120-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51120-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51120-104">Example</span></span>  
 <span data-ttu-id="51120-105">Verwenden der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft, um Basiswerte einer Animation Wiederholungszyklen.</span><span class="sxs-lookup"><span data-stu-id="51120-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="51120-106">Angenommen, Sie legen Sie eine Animation auf 9 Mal wiederholt (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 X") und legen Sie die zu animierende zwischen 10 und 15 Eigenschaft (From = 10 To = 15), die Eigenschaft von 10 bis 15 animiert während der ersten Zyklus von 15 bis 20 im zweiten Zyklus , von 20 bis 25 während der dritten Zyklus und So weiter.</span><span class="sxs-lookup"><span data-stu-id="51120-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="51120-107">Daher wird jede Animationszyklus den Endwert der Animation aus der vorherigen Animationszyklus als Basiswert verwendet.</span><span class="sxs-lookup"><span data-stu-id="51120-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="51120-108">Sie können die `IsCumulative` Eigenschaft mit dem meisten grundlegenden und die meisten Keyframes Animationen.</span><span class="sxs-lookup"><span data-stu-id="51120-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="51120-109">Weitere Informationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und [Keyframe-Animationen Übersicht](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="51120-109">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="51120-110">Das folgende Beispiel zeigt dieses Verhalten, indem Sie die Breite von vier Rechtecken animieren.</span><span class="sxs-lookup"><span data-stu-id="51120-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="51120-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51120-111">The example:</span></span>  
  
-   <span data-ttu-id="51120-112">Animiert das erste Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="51120-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="51120-113">Animiert das zweite Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> auf den Standardwert der Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="51120-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="51120-114">Animiert das dritte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="51120-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="51120-115">Animiert das letzte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="51120-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="51120-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51120-116">See Also</span></span>  
 [<span data-ttu-id="51120-117">Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert</span><span class="sxs-lookup"><span data-stu-id="51120-117">Add an Animation Output Value to an Animation Starting Value</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [<span data-ttu-id="51120-118">Wiederholen einer Animation</span><span class="sxs-lookup"><span data-stu-id="51120-118">Repeat an Animation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [<span data-ttu-id="51120-119">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="51120-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="51120-120">Übersicht über Keyframe-Animationen</span><span class="sxs-lookup"><span data-stu-id="51120-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="51120-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="51120-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
