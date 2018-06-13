---
title: 'Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird'
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 498aefa16b8a76262c01965b8992ef9a94b7ce28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560064"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="35c06-102">Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="35c06-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="35c06-103">Einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft bestimmt, ob sie nach Abschluss eine Iteration vorwärts in umgekehrter Reihenfolge abspielt.</span><span class="sxs-lookup"><span data-stu-id="35c06-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="35c06-104">Das folgende Beispiel zeigt mehrere Animationen mit identischen Dauer und die Zielwerte, jedoch mit anderen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="35c06-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="35c06-105">Zur Veranschaulichung der Funktion wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft verhält sich mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> einige Animationen-Einstellungen werden zur Wiederholung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="35c06-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="35c06-106">Die letzte Animation zeigt wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft geschachtelten Zeitachsen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="35c06-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35c06-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35c06-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
