---
title: 'Gewusst wie: Angeben des Übergabeverhaltens zwischen Storyboard-Animationen'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: 6846cde9fd0aa93a0ce57fd2da0f9e1df85ec5a4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264453"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>Gewusst wie: Angeben des Übergabeverhaltens zwischen Storyboard-Animationen
Dieses Beispiel zeigt das Angeben des Übergabeverhaltens zwischen Storyboard-Animationen. Die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.BeginStoryboard> gibt an, wie neue Animationen interagieren mit vorhandenen Laufwerknamen unterscheiden, die bereits auf eine Eigenschaft angewendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei Schaltflächen, die zu vergrößern, wenn der Mauszeiger darüber bewegt wird und verkleinert werden, wenn der Mauszeiger entfernt wird. Wenn Sie mit der Maus über eine Schaltfläche, und klicken Sie dann den Cursor schnell entfernen, wird die zweite Animation angewendet werden, bevor die erste beendet wird. Es ist, wenn zwei Animationen auf diese Weise überschneiden, die Sie den Unterschied zwischen sehen die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Werte <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> und <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>. Der Wert <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> kombiniert die überlappenden Animationen und führt zu einem reibungsloseren Übergang zwischen Animationen, während ein Wert von <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> bewirkt, dass die neue Animation sofort die weiter oben sich überschneidende Animation ersetzt.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Animations- und Zeitsteuerungssystem](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
