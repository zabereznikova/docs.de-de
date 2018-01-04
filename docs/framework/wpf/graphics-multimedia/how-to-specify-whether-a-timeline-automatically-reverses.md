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
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird
Einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft bestimmt, ob sie nach Abschluss eine Iteration vorwärts in umgekehrter Reihenfolge abspielt. Das folgende Beispiel zeigt mehrere Animationen mit identischen Dauer und die Zielwerte, jedoch mit anderen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Einstellungen. Zur Veranschaulichung der Funktion wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft verhält sich mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> einige Animationen-Einstellungen werden zur Wiederholung festgelegt. Die letzte Animation zeigt wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft geschachtelten Zeitachsen funktioniert.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
