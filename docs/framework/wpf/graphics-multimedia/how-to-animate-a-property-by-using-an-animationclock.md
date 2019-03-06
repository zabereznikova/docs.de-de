---
title: 'Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: d93f1eb352aef4f5e74512a8deeb0ec3fe7943c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357182"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="bd4f5-102">Vorgehensweise: Animieren einer Eigenschaft mit AnimationClock</span><span class="sxs-lookup"><span data-stu-id="bd4f5-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="bd4f5-103">Dieses Beispiel zeigt, wie Sie mit <xref:System.Windows.Media.Animation.Clock> -Objekte zum Animieren einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bd4f5-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="bd4f5-104">Es gibt drei Möglichkeiten, eine Abhängigkeitseigenschaft zu animieren:</span><span class="sxs-lookup"><span data-stu-id="bd4f5-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="bd4f5-105">Erstellen einer <xref:System.Windows.Media.Animation.AnimationTimeline> und ordnen sie dieser Eigenschaft mit einem <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="bd4f5-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="bd4f5-106">Verwenden des Objekts <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode zum Anwenden einer einzelnes <xref:System.Windows.Media.Animation.AnimationTimeline> auf eine Zieleigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bd4f5-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="bd4f5-107">Erstellen Sie eine <xref:System.Windows.Media.Animation.AnimationClock> aus einer <xref:System.Windows.Media.Animation.AnimationTimeline> und auf eine Eigenschaft anwenden.</span><span class="sxs-lookup"><span data-stu-id="bd4f5-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="bd4f5-108"><xref:System.Windows.Media.Animation.Storyboard> Objekte und die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode können Sie Eigenschaften animieren, ohne direkt zu erstellen und Verteilen von Uhren (Beispiele finden Sie in [Animieren einer Eigenschaft unter Verwendung eines Storyboards](how-to-animate-a-property-by-using-a-storyboard.md) und [Animieren einer Eigenschaft ohne Mit einem Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); Uhren werden erstellt und verteilt automatisch für Sie.</span><span class="sxs-lookup"><span data-stu-id="bd4f5-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd4f5-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd4f5-109">Example</span></span>  
 <span data-ttu-id="bd4f5-110">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Media.Animation.AnimationClock> und auf zwei ähnliche Eigenschaften angewendet.</span><span class="sxs-lookup"><span data-stu-id="bd4f5-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="bd4f5-111">Ein Beispiel, das zeigt, wie Sie interaktiv steuern eine <xref:System.Windows.Media.Animation.Clock> nachdem es gestartet wurde, finden Sie unter [Interaktives Steuern einer Uhr](how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="bd4f5-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd4f5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd4f5-112">See also</span></span>
- [<span data-ttu-id="bd4f5-113">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="bd4f5-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="bd4f5-114">Animieren einer Eigenschaft ohne Storyboard</span><span class="sxs-lookup"><span data-stu-id="bd4f5-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="bd4f5-115">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bd4f5-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
