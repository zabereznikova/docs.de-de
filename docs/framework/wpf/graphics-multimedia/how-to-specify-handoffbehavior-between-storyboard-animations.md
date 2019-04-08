---
title: 'Vorgehensweise: Angeben der HandoffBehavior-Enumeration zwischen Storyboard-Animationen'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083880"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Vorgehensweise: Angeben der HandoffBehavior-Enumeration zwischen Storyboard-Animationen
Dieses Beispiel zeigt das Angeben des Übergabeverhaltens zwischen Storyboard-Animationen. Die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.BeginStoryboard> gibt an, wie neue Animationen interagieren mit vorhandenen Laufwerknamen unterscheiden, die bereits auf eine Eigenschaft angewendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Schaltflächen, die zu vergrößern, wenn der Mauszeiger darüber bewegt wird und verkleinert werden, wenn der Mauszeiger entfernt wird. Wenn Sie mit der Maus über eine Schaltfläche, und klicken Sie dann den Cursor schnell entfernen, wird die zweite Animation angewendet werden, bevor die erste beendet wird. Es ist, wenn zwei Animationen auf diese Weise überschneiden, die Sie den Unterschied zwischen sehen die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Werte <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> und <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Der Wert <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> kombiniert die überlappenden Animationen und führt zu einem reibungsloseren Übergang zwischen Animationen, während ein Wert von <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> bewirkt, dass die neue Animation sofort die weiter oben sich überschneidende Animation ersetzt.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [Übersicht über Animationen](animation-overview.md)
- [Gewusst-wie-Themen zu Animation und Zeitsteuerung](animation-and-timing-how-to-topics.md)
