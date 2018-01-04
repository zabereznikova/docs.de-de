---
title: "Gewusst wie: Festlegen von FillBehavior für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2c1d65ec9fad94fed02bee1f018ae1aa00a8591
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="a74b9-102">Gewusst wie: Festlegen von FillBehavior für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat</span><span class="sxs-lookup"><span data-stu-id="a74b9-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="a74b9-103">In diesem Beispiel wird gezeigt, wie an den <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> für die inaktiven <xref:System.Windows.Media.Animation.Timeline> einer animierten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a74b9-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a74b9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a74b9-104">Example</span></span>  
 <span data-ttu-id="a74b9-105">Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> bestimmt, was auf den Wert einer animierten Eigenschaft geschieht, wenn es nicht gerade animiert, d. h., wenn die <xref:System.Windows.Media.Animation.Timeline> ist inaktiv, aber die übergeordneten <xref:System.Windows.Media.Animation.Timeline> befindet sich innerhalb einer aktiven oder haltezeitraum befindet.</span><span class="sxs-lookup"><span data-stu-id="a74b9-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="a74b9-106">Beispielsweise bleibt eine animierte Eigenschaft an deren Ende Wert nach der Animation beendet oder es ist, den Wert vor der Animation gestartet wiederherstellen?</span><span class="sxs-lookup"><span data-stu-id="a74b9-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="a74b9-107">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> zum Animieren der <xref:System.Windows.FrameworkElement.Width%2A> zweier Rechtecke.</span><span class="sxs-lookup"><span data-stu-id="a74b9-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="a74b9-108">Jedes Rechteck verwendet ein anderes <xref:System.Windows.Media.Animation.Timeline> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a74b9-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="a74b9-109">Eine <xref:System.Windows.Media.Animation.Timeline> hat eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> festgelegt <xref:System.Windows.Media.Animation.FillBehavior.Stop>, die bewirkt, dass der Breite des Rechtecks, das auf die nicht animiert wiederherstellen Wert der <xref:System.Windows.Media.Animation.Timeline> endet.</span><span class="sxs-lookup"><span data-stu-id="a74b9-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="a74b9-110">Die andere <xref:System.Windows.Media.Animation.Timeline> verfügt über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, dies bedeutet, dass die Breite an deren Ende bleiben Wert der <xref:System.Windows.Media.Animation.Timeline> endet.</span><span class="sxs-lookup"><span data-stu-id="a74b9-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="a74b9-111">Das vollständige Beispiel finden Sie unter [Beispielsammlung](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="a74b9-111">For the complete sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74b9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a74b9-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [<span data-ttu-id="a74b9-113">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="a74b9-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a74b9-114">Animation und zeitlichen Steuerung</span><span class="sxs-lookup"><span data-stu-id="a74b9-114">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="a74b9-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="a74b9-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
