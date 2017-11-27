---
title: 'Gewusst wie: Festlegen der Dauer einer Animation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9560e9d0a2809ae8f55a060eaec3b271539d5f94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="74bb7-102">Gewusst wie: Festlegen der Dauer einer Animation</span><span class="sxs-lookup"><span data-stu-id="74bb7-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="74bb7-103">Ein <xref:System.Windows.Media.Animation.Timeline> stellt ein Segment der Zeit und die Länge des Abschnitts sich nach der Zeitachse richtet <xref:System.Windows.Duration>.</span><span class="sxs-lookup"><span data-stu-id="74bb7-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="74bb7-104">Wenn eine <xref:System.Windows.Media.Animation.Timeline> Erreichen des Endes des seine Dauer Wiedergabe beendet.</span><span class="sxs-lookup"><span data-stu-id="74bb7-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="74bb7-105">Wenn die <xref:System.Windows.Media.Animation.Timeline> untergeordnete Zeitachsen, hat sie Wiedergabe ebenfalls beendet.</span><span class="sxs-lookup"><span data-stu-id="74bb7-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="74bb7-106">Im Fall einer Animation die <xref:System.Windows.Duration> gibt an, wie lange die Animation für den Übergang vom Startwert zum Endwert benötigt.</span><span class="sxs-lookup"><span data-stu-id="74bb7-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="74bb7-107">Sie können angeben, ein <xref:System.Windows.Duration> mit einem bestimmten, endlichen Zeitwert oder die speziellen Werte <xref:System.Windows.Duration.Automatic%2A> oder <xref:System.Windows.Duration.Forever%2A>.</span><span class="sxs-lookup"><span data-stu-id="74bb7-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="74bb7-108">Die Dauer einer Animation muss immer einen Time-Wert sein, da eine Animation immer eine Länge definierte ist, endliche sein muss, andernfalls die Animation würde nicht wissen, wie Sie zwischen den Zielwerten umgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="74bb7-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="74bb7-109">Container-Zeitplänen (<xref:System.Windows.Media.Animation.TimelineGroup> Objekte), wie z. B. <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline>, haben eine Standarddauer von <xref:System.Windows.Duration.Automatic%2A>, d. h., sie automatisch beendet, wenn das letzte untergeordnete Element Wiedergabe beendet wird.</span><span class="sxs-lookup"><span data-stu-id="74bb7-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="74bb7-110">In der folgenden Beispiel, Breite, Höhe und ausfüllen Farbe ein <xref:System.Windows.Shapes.Rectangle> animiert wird.</span><span class="sxs-lookup"><span data-stu-id="74bb7-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="74bb7-111">Zeitdauern werden für Animationen und Container Zeitachsen, wodurch Animationseffekte einschließlich steuern die wahrgenommene Geschwindigkeit einer Animation und überschreiben die Dauer der untergeordnete Zeitachsen mit der Dauer einer Containerzeitachse festgelegt.</span><span class="sxs-lookup"><span data-stu-id="74bb7-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74bb7-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74bb7-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="74bb7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74bb7-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="74bb7-114">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="74bb7-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
