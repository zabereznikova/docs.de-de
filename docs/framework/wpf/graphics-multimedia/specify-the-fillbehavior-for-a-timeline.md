---
title: 'Vorgehensweise: Angeben der FillBehavior-Enumeration für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 9f03c5b8d4585c32e0a9f119649dd15a23523033
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091116"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>Vorgehensweise: Angeben der FillBehavior-Enumeration für ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat
Dieses Beispiel zeigt, wie die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> für die inaktiven <xref:System.Windows.Media.Animation.Timeline> über eine animierte Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Eigenschaft eine <xref:System.Windows.Media.Animation.Timeline> bestimmt, was auf den Wert einer animierten Eigenschaft geschieht, wenn es nicht gerade animiert, d. h., wenn die <xref:System.Windows.Media.Animation.Timeline> ist inaktiv, aber das übergeordnete Element <xref:System.Windows.Media.Animation.Timeline> befindet sich in seinem aktiven oder haltezeitraum befindet. Beispielsweise bleibt eine animierte Eigenschaft an ihrem Ende Wert, nachdem die Animation beendet oder es ist in den sie hatte, bevor die Animation gestartet Wert zurückgesetzt?  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> zum Animieren der <xref:System.Windows.FrameworkElement.Width%2A> von zwei Rechtecken. Jedes Rechteck verwendet ein anderes <xref:System.Windows.Media.Animation.Timeline> Objekt.  
  
 Eine <xref:System.Windows.Media.Animation.Timeline> verfügt über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> , die auf festgelegt ist <xref:System.Windows.Media.Animation.FillBehavior.Stop>, der bewirkt, dass der Breite des Rechtecks, das auf die nicht animiert wiederherstellen Wert fest, wenn die <xref:System.Windows.Media.Animation.Timeline> endet. Die andere <xref:System.Windows.Media.Animation.Timeline> verfügt über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> von <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, der bewirkt, dass der Breite auf seiner Seite bleiben Wert fest, wenn die <xref:System.Windows.Media.Animation.Timeline> endet.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [Übersicht über Animationen](animation-overview.md)
- [Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen](animation-and-timing-how-to-topics.md)
