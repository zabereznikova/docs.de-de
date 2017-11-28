---
title: "Gewusst wie: Angeben des Übergabeverhaltens zwischen Storyboard-Animationen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 323ea563aec7bc7ad0abec2372e3af977c7e38eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="045e3-102">Gewusst wie: Angeben des Übergabeverhaltens zwischen Storyboard-Animationen</span><span class="sxs-lookup"><span data-stu-id="045e3-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="045e3-103">Dieses Beispiel zeigt, wie-Übergabeverhalten zwischen Storyboard-Animationen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="045e3-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="045e3-104">Die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Eigenschaft <xref:System.Windows.Media.Animation.BeginStoryboard> gibt an, wie neue Animationen interagieren mit vorhandenen, die bereits auf eine Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="045e3-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="045e3-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="045e3-105">Example</span></span>  
 <span data-ttu-id="045e3-106">Das folgende Beispiel erstellt zwei Schaltflächen, die zum Vergrößern, wenn der Mauszeiger darüber bewegt wird, und verkleinert werden, wenn der Mauszeiger entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="045e3-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="045e3-107">Wenn Sie die Maus auf eine Schaltfläche, und Sie dann den Cursor schnell entfernen, wird die zweite Animation angewendet werden, vor der ersten Aktivität abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="045e3-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="045e3-108">Wenn zwei Animationen wie folgt überschneiden, die daraufhin die Differenz zwischen der <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> Werte <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> und <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span><span class="sxs-lookup"><span data-stu-id="045e3-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="045e3-109">Der Wert <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> kombiniert die überlappenden Animationen und führt einen glatteren Übergang zwischen Animationen, während ein Wert von <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> bewirkt, dass die neue Animation unmittelbar zuvor überlappende Animation ersetzt.</span><span class="sxs-lookup"><span data-stu-id="045e3-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="045e3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="045e3-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="045e3-111">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="045e3-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="045e3-112">Animation und zeitlichen Steuerung</span><span class="sxs-lookup"><span data-stu-id="045e3-112">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="045e3-113">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="045e3-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
