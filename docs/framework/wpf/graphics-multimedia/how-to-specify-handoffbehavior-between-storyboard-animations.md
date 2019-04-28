---
title: 'Vorgehensweise: Angeben der HandoffBehavior-Enumeration zwischen Storyboard-Animationen'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: d7129d6a48bdf31dc4953bb450267ad3b38fdd17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651037"
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="3e373-102">Vorgehensweise: Angeben der HandoffBehavior-Enumeration zwischen Storyboard-Animationen</span><span class="sxs-lookup"><span data-stu-id="3e373-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="3e373-103">Dieses Beispiel zeigt das Angeben des Übergabeverhaltens zwischen Storyboard-Animationen.</span><span class="sxs-lookup"><span data-stu-id="3e373-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="3e373-104">Die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.BeginStoryboard> gibt an, wie neue Animationen interagieren mit vorhandenen Laufwerknamen unterscheiden, die bereits auf eine Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e373-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e373-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3e373-105">Example</span></span>  
 <span data-ttu-id="3e373-106">Das folgende Beispiel erstellt zwei Schaltflächen, die zu vergrößern, wenn der Mauszeiger darüber bewegt wird und verkleinert werden, wenn der Mauszeiger entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="3e373-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="3e373-107">Wenn Sie mit der Maus über eine Schaltfläche, und klicken Sie dann den Cursor schnell entfernen, wird die zweite Animation angewendet werden, bevor die erste beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3e373-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="3e373-108">Es ist, wenn zwei Animationen auf diese Weise überschneiden, die Sie den Unterschied zwischen sehen die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Werte <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> und <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="3e373-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="3e373-109">Der Wert <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> kombiniert die überlappenden Animationen und führt zu einem reibungsloseren Übergang zwischen Animationen, während ein Wert von <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> bewirkt, dass die neue Animation sofort die weiter oben sich überschneidende Animation ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3e373-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3e373-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e373-110">See also</span></span>

- <xref:System.Windows.Media.Animation.BeginStoryboard>
- <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>
- [<span data-ttu-id="3e373-111">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="3e373-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="3e373-112">Das Animations- und Zeitsteuerungssystem Gewusst-wie-Themen</span><span class="sxs-lookup"><span data-stu-id="3e373-112">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
