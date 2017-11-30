---
title: 'Gewusst wie: Animieren einer Eigenschaft mit AnimationClock'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47df7aaad45000bc8c761a9bb9022d37e0f0828c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="ab946-102">Gewusst wie: Animieren einer Eigenschaft mit AnimationClock</span><span class="sxs-lookup"><span data-stu-id="ab946-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="ab946-103">Dieses Beispiel zeigt, wie <xref:System.Windows.Media.Animation.Clock> -Objekten, die eine Eigenschaft animiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ab946-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="ab946-104">Es gibt drei Möglichkeiten, eine Abhängigkeitseigenschaft zu animieren:</span><span class="sxs-lookup"><span data-stu-id="ab946-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="ab946-105">Erstellen einer <xref:System.Windows.Media.Animation.AnimationTimeline> und ordnen sie dieser Eigenschaft mit einem <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="ab946-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="ab946-106">Verwenden Sie das Objekt <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode, um ein einzelnes anzuwenden <xref:System.Windows.Media.Animation.AnimationTimeline> auf eine Zieleigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ab946-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="ab946-107">Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> aus einem <xref:System.Windows.Media.Animation.AnimationTimeline> und auf eine Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="ab946-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="ab946-108"><xref:System.Windows.Media.Animation.Storyboard>Objekte und die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> Methode ermöglichen es Ihnen, Eigenschaften animieren, ohne direkt zu erstellen und Verteilen von Uhren (Beispiele finden Sie unter [Animieren einer Eigenschaft eines Drehbuchs mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) und [Animieren einer Eigenschaft ohne Ein Storyboard mit](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); Uhren erstellt und verteilt werden automatisch für Sie.</span><span class="sxs-lookup"><span data-stu-id="ab946-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab946-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ab946-109">Example</span></span>  
 <span data-ttu-id="ab946-110">Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Media.Animation.AnimationClock> und auf zwei ähnliche Eigenschaften angewendet.</span><span class="sxs-lookup"><span data-stu-id="ab946-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="ab946-111">Ein Beispiel, das zeigt, wie Sie interaktiv steuern eine <xref:System.Windows.Media.Animation.Clock> nach dem Start, finden Sie unter [interaktiv steuern eine Uhr](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="ab946-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab946-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab946-112">See Also</span></span>  
 [<span data-ttu-id="ab946-113">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="ab946-113">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="ab946-114">Animieren einer Eigenschaft ohne Storyboard</span><span class="sxs-lookup"><span data-stu-id="ab946-114">Animate a Property Without Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [<span data-ttu-id="ab946-115">Übersicht über die Verfahren zur Animation von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ab946-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
