---
title: 'Gewusst wie: Festlegen von FillBehavior für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141172"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Gewusst wie: Festlegen von FillBehavior für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat
In diesem Beispiel wird <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> gezeigt, <xref:System.Windows.Media.Animation.Timeline> wie die für die Inaktivität einer animierten Eigenschaft angegeben wird.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.Timeline> von a bestimmt, was mit dem Wert einer animierten Eigenschaft <xref:System.Windows.Media.Animation.Timeline> geschieht, wenn sie <xref:System.Windows.Media.Animation.Timeline> nicht animiert wird, d. h., wenn der inaktiv ist, sich aber sein übergeordnetes Element innerhalb seiner aktiven oder Halteperiode befindet. Bleibt z. B. eine animierte Eigenschaft nach dem Ende der Animation am Endwert oder kehrt sie zu dem Wert zurück, den sie vor dem Start der Animation hatte?  
  
 Im folgenden Beispiel <xref:System.Windows.Media.Animation.DoubleAnimation> wird <xref:System.Windows.FrameworkElement.Width%2A> ein verwendet, um die von zwei Rechtecken zu animieren. Jedes Rechteck verwendet <xref:System.Windows.Media.Animation.Timeline> ein anderes Objekt.  
  
 Eine <xref:System.Windows.Media.Animation.Timeline> hat <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> eine, <xref:System.Windows.Media.Animation.FillBehavior.Stop>die auf festgelegt ist, wodurch die Breite des Rechtecks <xref:System.Windows.Media.Animation.Timeline> zu seinem nicht animierten Wert zurückkehrt, wenn die Enden. Die <xref:System.Windows.Media.Animation.Timeline> andere <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> hat <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>eine von , die bewirkt, <xref:System.Windows.Media.Animation.Timeline> dass die Breite am Endwert verbleibt, wenn das Ende endet.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Animationsbeispielgalerie](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Übersicht über Animationen](animation-overview.md)
- [Gewusst-wie-Themen zu Animation und Zeitsteuerung](animation-and-timing-how-to-topics.md)
