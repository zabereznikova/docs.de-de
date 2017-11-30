---
title: 'Gewusst wie: Wiederholen einer Animation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d2f942771e01c2b7fae989f73779672edb8ba2f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="fb5e4-102">Gewusst wie: Wiederholen einer Animation</span><span class="sxs-lookup"><span data-stu-id="fb5e4-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="fb5e4-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> um das Wiederholungsverhalten einer Animation zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb5e4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb5e4-104">Example</span></span>  
 <span data-ttu-id="fb5e4-105">Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft von einem <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft eine Animation ihre einfache Dauer wiederholt.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="fb5e4-106">Mithilfe von <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, können Sie angeben, die eine <xref:System.Windows.Media.Animation.Timeline> für eine bestimmte Anzahl von Malen wiederholt wird (eine Iterationsanzahl) oder für einen angegebenen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="fb5e4-107">In beiden Fällen so viele Anfang-to-End ausgeführt wird, die es benötigt, um die angeforderte Anzahl oder die Dauer ausfüllen durchläuft die Animation.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="fb5e4-108">Standardmäßig verfügen die Zeitachsen eine Wiederholungsanzahl von 1,0 bedeutet, dass sie nur einmal wiedergegeben und nicht wiederholt.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="fb5e4-109">Jedoch wenn Sie festlegen, die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> zu <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, die Zeitachse unendlich wiederholt.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="fb5e4-110">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um das Wiederholungsverhalten einer Animation zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="fb5e4-111">Das Beispiel erstellt eine Animation der <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft fünf Rechtecke mit jedes einen anderen Typ von Wiederholungsverhalten Rechteck.</span><span class="sxs-lookup"><span data-stu-id="fb5e4-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="fb5e4-112">Das vollständige Beispiel finden Sie unter [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="fb5e4-112">For the complete sample, see [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb5e4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb5e4-113">See Also</span></span>  
 [<span data-ttu-id="fb5e4-114">Sammeln von Animationen während Wiederholungszyklen</span><span class="sxs-lookup"><span data-stu-id="fb5e4-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="fb5e4-115">Festlegen, ob eine Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="fb5e4-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [<span data-ttu-id="fb5e4-116">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="fb5e4-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="fb5e4-117">Animation und zeitlichen Steuerung</span><span class="sxs-lookup"><span data-stu-id="fb5e4-117">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="fb5e4-118">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="fb5e4-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="fb5e4-119">Beispiel zum Verhalten der Animationszeitsteuerung</span><span class="sxs-lookup"><span data-stu-id="fb5e4-119">Animation Timing Behavior Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159970)
