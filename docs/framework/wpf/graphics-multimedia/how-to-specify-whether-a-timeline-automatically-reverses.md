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
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Vorgehensweise: Festlegen, ob eine Zeitachse automatisch umgekehrt wird
Einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft bestimmt, ob nach Abschluss einer Vorwärtsiteration in umgekehrter Reihenfolge spielt. Das folgende Beispiel zeigt mehrere Animationen mit identischen Dauer und die Zielwerte, jedoch mit unterschiedlichen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Einstellungen. Um zu veranschaulichen wie das <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft verhält sich mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Einstellungen, einige Animationen werden festgelegt, wiederholt werden soll. Die letzten Animation zeigt wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> geschachtelten Zeitachsen Eigenschaft funktioniert.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
