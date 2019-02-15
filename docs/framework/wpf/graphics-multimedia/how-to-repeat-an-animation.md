---
title: 'Vorgehensweise: Wiederholen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 358400c07ec2e96401d95929cbdd22784db630f9
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305141"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="d4cdd-102">Vorgehensweise: Wiederholen einer Animation</span><span class="sxs-lookup"><span data-stu-id="d4cdd-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="d4cdd-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> um das Wiederholungsverhalten einer Animation steuern.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4cdd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4cdd-104">Example</span></span>  
 <span data-ttu-id="d4cdd-105">Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft eine Animation ihre einfache Dauer wiederholt.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="d4cdd-106">Mithilfe von <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, können Sie angeben, die eine <xref:System.Windows.Media.Animation.Timeline> für eine bestimmte Anzahl von Malen wiederholt (eine Iterationsanzahl) oder für einen bestimmten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="d4cdd-107">In beiden Fällen durchläuft die Animation so viele Anfang-to-End ausgeführt wird, die es benötigt, um die angeforderte Anzahl oder Dauer zu füllen.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="d4cdd-108">In der Standardeinstellung haben Zeitachsen eine Wiederholungsanzahl von 1.0, d. h., sie wird einmal abgespielt und nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="d4cdd-109">Allerdings setzen Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> zu <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, die Zeitachse unbegrenzt wiederholt.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="d4cdd-110">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um das Wiederholungsverhalten einer Animation steuern.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="d4cdd-111">Das Beispiel erstellt eine Animation die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft fünf Rechtecke mit jedes Rechtecks mithilfe eines anderen Typs des Wiederholungsverhaltens.</span><span class="sxs-lookup"><span data-stu-id="d4cdd-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="d4cdd-112">Das vollständige Beispiel finden Sie unter [Animation Timing Verhalten Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="d4cdd-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cdd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4cdd-113">See also</span></span>
- [<span data-ttu-id="d4cdd-114">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="d4cdd-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="d4cdd-115">Festlegen, ob eine Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="d4cdd-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="d4cdd-116">Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="d4cdd-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="d4cdd-117">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="d4cdd-117">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="d4cdd-118">Beispiel zum Verhalten der Animationszeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="d4cdd-118">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
