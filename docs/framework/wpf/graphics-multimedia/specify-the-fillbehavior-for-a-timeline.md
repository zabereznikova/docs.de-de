---
title: 'Vorgehensweise: Angeben der FillBehavior-Enumeration für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 9f03c5b8d4585c32e0a9f119649dd15a23523033
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091116"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="c4602-102">Vorgehensweise: Angeben der FillBehavior-Enumeration für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat</span><span class="sxs-lookup"><span data-stu-id="c4602-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="c4602-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> für die inaktiven <xref:System.Windows.Media.Animation.Timeline> über eine animierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c4602-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4602-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4602-104">Example</span></span>  
 <span data-ttu-id="c4602-105">Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> bestimmt, was auf den Wert einer animierten Eigenschaft geschieht, wenn es nicht gerade animiert, d. h., wenn die <xref:System.Windows.Media.Animation.Timeline> ist inaktiv, aber das übergeordnete Element <xref:System.Windows.Media.Animation.Timeline> befindet sich in seinem aktiven oder haltezeitraum befindet.</span><span class="sxs-lookup"><span data-stu-id="c4602-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="c4602-106">Beispielsweise bleibt eine animierte Eigenschaft an ihrem Ende Wert, nachdem die Animation beendet oder es ist in den sie hatte, bevor die Animation gestartet Wert zurückgesetzt?</span><span class="sxs-lookup"><span data-stu-id="c4602-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="c4602-107">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> zum Animieren der <xref:System.Windows.FrameworkElement.Width%2A> von zwei Rechtecken.</span><span class="sxs-lookup"><span data-stu-id="c4602-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="c4602-108">Jedes Rechteck verwendet ein anderes <xref:System.Windows.Media.Animation.Timeline> Objekt.</span><span class="sxs-lookup"><span data-stu-id="c4602-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="c4602-109">Eine <xref:System.Windows.Media.Animation.Timeline> verfügt über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> , die auf festgelegt ist <xref:System.Windows.Media.Animation.FillBehavior.Stop>, der bewirkt, dass der Breite des Rechtecks, das auf die nicht animiert wiederherstellen Wert fest, wenn die <xref:System.Windows.Media.Animation.Timeline> endet.</span><span class="sxs-lookup"><span data-stu-id="c4602-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="c4602-110">Die andere <xref:System.Windows.Media.Animation.Timeline> verfügt über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, der bewirkt, dass der Breite auf seiner Seite bleiben Wert fest, wenn die <xref:System.Windows.Media.Animation.Timeline> endet.</span><span class="sxs-lookup"><span data-stu-id="c4602-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="c4602-111">Das vollständige Beispiel finden Sie unter [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="c4602-111">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4602-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4602-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="c4602-113">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="c4602-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c4602-114">Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="c4602-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
