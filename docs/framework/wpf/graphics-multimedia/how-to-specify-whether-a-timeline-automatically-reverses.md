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
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a>Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird
Einer Zeitachse <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> -Eigenschaft bestimmt, ob sie nach Abschluss eine Iteration vorwärts in umgekehrter Reihenfolge abspielt. Das folgende Beispiel zeigt mehrere Animationen mit identischen Dauer und die Zielwerte, jedoch mit anderen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Einstellungen. Zur Veranschaulichung der Funktion wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft verhält sich mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> einige Animationen-Einstellungen werden zur Wiederholung festgelegt. Die letzte Animation zeigt wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> Eigenschaft geschachtelten Zeitachsen funktioniert.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
