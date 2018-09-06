---
title: 'Gewusst wie: Wiederholen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 176fc9c31f85361a243cd9357d79608e0ff6a4cd
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855295"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="0cf71-102">Gewusst wie: Wiederholen einer Animation</span><span class="sxs-lookup"><span data-stu-id="0cf71-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="0cf71-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> um das Wiederholungsverhalten einer Animation steuern.</span><span class="sxs-lookup"><span data-stu-id="0cf71-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cf71-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cf71-104">Example</span></span>  
 <span data-ttu-id="0cf71-105">Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft eine Animation ihre einfache Dauer wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0cf71-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="0cf71-106">Mithilfe von <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, können Sie angeben, die eine <xref:System.Windows.Media.Animation.Timeline> für eine bestimmte Anzahl von Malen wiederholt (eine Iterationsanzahl) oder für einen bestimmten Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="0cf71-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="0cf71-107">In beiden Fällen durchläuft die Animation so viele Anfang-to-End ausgeführt wird, die es benötigt, um die angeforderte Anzahl oder Dauer zu füllen.</span><span class="sxs-lookup"><span data-stu-id="0cf71-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="0cf71-108">In der Standardeinstellung haben Zeitachsen eine Wiederholungsanzahl von 1.0, d. h., sie wird einmal abgespielt und nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0cf71-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="0cf71-109">Allerdings setzen Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> zu <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, die Zeitachse unbegrenzt wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0cf71-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="0cf71-110">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um das Wiederholungsverhalten einer Animation steuern.</span><span class="sxs-lookup"><span data-stu-id="0cf71-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="0cf71-111">Das Beispiel erstellt eine Animation die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft fünf Rechtecke mit jedes Rechtecks mithilfe eines anderen Typs des Wiederholungsverhaltens.</span><span class="sxs-lookup"><span data-stu-id="0cf71-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="0cf71-112">Das vollständige Beispiel finden Sie unter [Animation Timing Verhalten Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="0cf71-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf71-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cf71-113">See Also</span></span>  
 [<span data-ttu-id="0cf71-114">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="0cf71-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="0cf71-115">Festlegen, ob eine Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="0cf71-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [<span data-ttu-id="0cf71-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0cf71-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="0cf71-117">Animations- und Zeitsteuerungssystem</span><span class="sxs-lookup"><span data-stu-id="0cf71-117">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="0cf71-118">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="0cf71-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="0cf71-119">Beispiel zum Verhalten der Animationszeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="0cf71-119">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
