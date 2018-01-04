---
title: 'Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da1330a8513f43e7543f97838ef8e9be788af396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="fbc2e-102">Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird</span><span class="sxs-lookup"><span data-stu-id="fbc2e-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="fbc2e-103">Einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft bestimmt, ob sie nach Abschluss eine Iteration vorwärts in umgekehrter Reihenfolge abspielt.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="fbc2e-104">Das folgende Beispiel zeigt mehrere Animationen mit identischen Dauer und die Zielwerte, jedoch mit anderen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="fbc2e-105">Zur Veranschaulichung der Funktion wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft verhält sich mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> einige Animationen-Einstellungen werden zur Wiederholung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="fbc2e-106">Die letzte Animation zeigt wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft geschachtelten Zeitachsen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="fbc2e-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbc2e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbc2e-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
