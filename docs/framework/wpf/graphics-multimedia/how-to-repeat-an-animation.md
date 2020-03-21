---
title: 'Gewusst wie: Wiederholen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141548"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="36339-102">Gewusst wie: Wiederholen einer Animation</span><span class="sxs-lookup"><span data-stu-id="36339-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="36339-103">In diesem Beispiel wird <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> gezeigt, <xref:System.Windows.Media.Animation.Timeline> wie die Eigenschaft von a verwendet wird, um das Wiederholungsverhalten einer Animation zu steuern.</span><span class="sxs-lookup"><span data-stu-id="36339-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36339-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36339-104">Example</span></span>  
 <span data-ttu-id="36339-105">Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.Timeline> einer steuert, wie oft eine Animation ihre einfache Dauer wiederholt.</span><span class="sxs-lookup"><span data-stu-id="36339-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="36339-106">Mithilfe <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>von können Sie <xref:System.Windows.Media.Animation.Timeline> angeben, dass ein Wiederholungsvorgang für eine bestimmte Anzahl von Wiederholungen (eine Iterationsanzahl) oder für einen bestimmten Zeitraum wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="36339-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="36339-107">In beiden Fällen durchläuft die Animation so viele Anfangs-zu-Ende-Ausführungen, wie sie benötigt, um die angeforderte Anzahl oder Dauer zu füllen.</span><span class="sxs-lookup"><span data-stu-id="36339-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="36339-108">Standardmäßig haben Zeitachsen eine Wiederholungszahl von 1,0, d. h. sie werden einmal und nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="36339-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="36339-109">Wenn Sie jedoch <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> die Eigenschaft <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>von a auf festlegen, wird die Zeitachse auf unbestimmte Zeit wiederholt.</span><span class="sxs-lookup"><span data-stu-id="36339-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="36339-110">Das folgende Beispiel zeigt, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> wie sie die Eigenschaft verwenden, um das Wiederholungsverhalten einer Animation zu steuern.</span><span class="sxs-lookup"><span data-stu-id="36339-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="36339-111">Im Beispiel wird <xref:System.Windows.FrameworkElement.Width%2A> die Eigenschaft von fünf Rechtecken mit jedem Rechteck mit einem anderen Wiederholungsverhalten animiert.</span><span class="sxs-lookup"><span data-stu-id="36339-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="36339-112">Das vollständige Beispiel finden Sie unter [Animations-Timing-Verhaltensbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span><span class="sxs-lookup"><span data-stu-id="36339-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36339-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36339-113">See also</span></span>

- [<span data-ttu-id="36339-114">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="36339-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="36339-115">Festlegen, ob eine Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="36339-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="36339-116">Gewusst-wie-Themen zu Animation und Zeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="36339-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="36339-117">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="36339-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="36339-118">Beispiel zum Verhalten der Animationszeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="36339-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
