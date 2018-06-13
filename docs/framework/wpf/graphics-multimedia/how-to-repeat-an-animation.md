---
title: 'Gewusst wie: Wiederholen einer Animation'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: b2281805b62d6d4e639524d9a0959b392006d003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561208"
---
# <a name="how-to-repeat-an-animation"></a>Gewusst wie: Wiederholen einer Animation
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> um das Wiederholungsverhalten einer Animation zu steuern.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft von einem <xref:System.Windows.Media.Animation.Timeline> steuert, wie oft eine Animation ihre einfache Dauer wiederholt. Mithilfe von <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, können Sie angeben, die eine <xref:System.Windows.Media.Animation.Timeline> für eine bestimmte Anzahl von Malen wiederholt wird (eine Iterationsanzahl) oder für einen angegebenen Zeitraum. In beiden Fällen so viele Anfang-to-End ausgeführt wird, die es benötigt, um die angeforderte Anzahl oder die Dauer ausfüllen durchläuft die Animation.  
  
 Standardmäßig verfügen die Zeitachsen eine Wiederholungsanzahl von 1,0 bedeutet, dass sie nur einmal wiedergegeben und nicht wiederholt. Jedoch wenn Sie festlegen, die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> zu <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, die Zeitachse unendlich wiederholt.  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Eigenschaft, um das Wiederholungsverhalten einer Animation zu steuern. Das Beispiel erstellt eine Animation der <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft fünf Rechtecke mit jedes einen anderen Typ von Wiederholungsverhalten Rechteck.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).  
  
## <a name="see-also"></a>Siehe auch  
 [Sammeln von Animationen während Wiederholungszyklen](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Festlegen, ob eine Zeitachse automatisch umgekehrt wird](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [Animation und zeitlichen Steuerung](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Beispiel zum Verhalten der Animationszeitsteuerung](http://go.microsoft.com/fwlink/?LinkID=159970)
