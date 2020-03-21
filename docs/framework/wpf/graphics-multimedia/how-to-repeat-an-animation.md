---
title: 'Gewusst wie: Wiederholen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141548"
---
# <a name="how-to-repeat-an-animation"></a>Gewusst wie: Wiederholen einer Animation
In diesem Beispiel wird <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> gezeigt, <xref:System.Windows.Media.Animation.Timeline> wie die Eigenschaft von a verwendet wird, um das Wiederholungsverhalten einer Animation zu steuern.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.Timeline> einer steuert, wie oft eine Animation ihre einfache Dauer wiederholt. Mithilfe <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>von können Sie <xref:System.Windows.Media.Animation.Timeline> angeben, dass ein Wiederholungsvorgang für eine bestimmte Anzahl von Wiederholungen (eine Iterationsanzahl) oder für einen bestimmten Zeitraum wiederholt wird. In beiden Fällen durchläuft die Animation so viele Anfangs-zu-Ende-Ausführungen, wie sie benötigt, um die angeforderte Anzahl oder Dauer zu füllen.  
  
 Standardmäßig haben Zeitachsen eine Wiederholungszahl von 1,0, d. h. sie werden einmal und nicht wiederholt. Wenn Sie jedoch <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> die Eigenschaft <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>von a auf festlegen, wird die Zeitachse auf unbestimmte Zeit wiederholt.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> wie sie die Eigenschaft verwenden, um das Wiederholungsverhalten einer Animation zu steuern. Im Beispiel wird <xref:System.Windows.FrameworkElement.Width%2A> die Eigenschaft von fünf Rechtecken mit jedem Rechteck mit einem anderen Wiederholungsverhalten animiert.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Animations-Timing-Verhaltensbeispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).  
  
## <a name="see-also"></a>Weitere Informationen

- [Sammeln von Animationen während Wiederholungszyklen](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [Festlegen, ob eine Zeitachse automatisch umgekehrt wird](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [Gewusst-wie-Themen zu Animation und Zeitsteuerung](animation-and-timing-how-to-topics.md)
- [Übersicht über Animationen](animation-overview.md)
- [Beispiel zum Verhalten der Animationszeitsteuerung](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
