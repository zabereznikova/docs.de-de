---
title: 'Gewusst wie: Festlegen von FillBehavior für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141172"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="a11e6-102">Gewusst wie: Festlegen von FillBehavior für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat</span><span class="sxs-lookup"><span data-stu-id="a11e6-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="a11e6-103">In diesem Beispiel wird <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> gezeigt, <xref:System.Windows.Media.Animation.Timeline> wie die für die Inaktivität einer animierten Eigenschaft angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a11e6-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a11e6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a11e6-104">Example</span></span>  
 <span data-ttu-id="a11e6-105">Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.Timeline> von a bestimmt, was mit dem Wert einer animierten Eigenschaft <xref:System.Windows.Media.Animation.Timeline> geschieht, wenn sie <xref:System.Windows.Media.Animation.Timeline> nicht animiert wird, d. h., wenn der inaktiv ist, sich aber sein übergeordnetes Element innerhalb seiner aktiven oder Halteperiode befindet.</span><span class="sxs-lookup"><span data-stu-id="a11e6-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="a11e6-106">Bleibt z. B. eine animierte Eigenschaft nach dem Ende der Animation am Endwert oder kehrt sie zu dem Wert zurück, den sie vor dem Start der Animation hatte?</span><span class="sxs-lookup"><span data-stu-id="a11e6-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="a11e6-107">Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird <xref:System.Windows.FrameworkElement.Width%2A> ein verwendet, um die von zwei Rechtecken zu animieren.</span><span class="sxs-lookup"><span data-stu-id="a11e6-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="a11e6-108">Jedes Rechteck verwendet <xref:System.Windows.Media.Animation.Timeline> ein anderes Objekt.</span><span class="sxs-lookup"><span data-stu-id="a11e6-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="a11e6-109">Eine <xref:System.Windows.Media.Animation.Timeline> hat <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> eine, <xref:System.Windows.Media.Animation.FillBehavior.Stop>die auf festgelegt ist, wodurch die Breite des Rechtecks <xref:System.Windows.Media.Animation.Timeline> zu seinem nicht animierten Wert zurückkehrt, wenn die Enden.</span><span class="sxs-lookup"><span data-stu-id="a11e6-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="a11e6-110">Die <xref:System.Windows.Media.Animation.Timeline> andere <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> hat <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>eine von , die bewirkt, <xref:System.Windows.Media.Animation.Timeline> dass die Breite am Endwert verbleibt, wenn das Ende endet.</span><span class="sxs-lookup"><span data-stu-id="a11e6-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="a11e6-111">Das vollständige Beispiel finden Sie unter [Animationsbeispielgalerie](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="a11e6-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11e6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a11e6-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="a11e6-113">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="a11e6-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a11e6-114">Gewusst-wie-Themen zu Animation und Zeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="a11e6-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
