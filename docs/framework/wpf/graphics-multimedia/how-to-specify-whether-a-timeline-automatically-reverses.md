---
title: 'Vorgehensweise: Festlegen, ob eine Zeitachse automatisch umgekehrt wird'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024663"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="22d4e-102">Vorgehensweise: Festlegen, ob eine Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="22d4e-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="22d4e-103">Einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft bestimmt, ob nach Abschluss einer Vorwärtsiteration in umgekehrter Reihenfolge spielt.</span><span class="sxs-lookup"><span data-stu-id="22d4e-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="22d4e-104">Das folgende Beispiel zeigt mehrere Animationen mit identischen Dauer und die Zielwerte, jedoch mit unterschiedlichen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="22d4e-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="22d4e-105">Um zu veranschaulichen wie das <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft verhält sich mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Einstellungen, einige Animationen werden festgelegt, wiederholt werden soll.</span><span class="sxs-lookup"><span data-stu-id="22d4e-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="22d4e-106">Die letzten Animation zeigt wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> geschachtelten Zeitachsen Eigenschaft funktioniert.</span><span class="sxs-lookup"><span data-stu-id="22d4e-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d4e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22d4e-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
