---
title: Beschleunigungsfunktionen
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
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 198ec8b8cb0b27e009f01f8e60a47e8086a7dbc7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="easing-functions"></a><span data-ttu-id="7252b-102">Beschleunigungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="7252b-102">Easing Functions</span></span>
<span data-ttu-id="7252b-103">Mit Beschleunigungsfunktionen können Sie benutzerdefinierte mathematische Formeln auf Animationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="7252b-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="7252b-104">Beispielsweise sollte Ihr Objekt realistisch springen oder sich so verhalten, als ob es sich auf einer Feder befinden würde.</span><span class="sxs-lookup"><span data-stu-id="7252b-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="7252b-105">Sie können Keyframe- oder sogar From/To/By-Animationen verwenden, um sich diesen Effekten anzunähern, aber es würde eine erhebliche Menge an Arbeit bedeuten, und die Animation wäre weniger genau als die Verwendung einer mathematischen Formel.</span><span class="sxs-lookup"><span data-stu-id="7252b-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="7252b-106">Neben der Erstellung Ihrer eigenen benutzerdefinierten Beschleunigungsfunktion durch Erben von <xref:System.Windows.Media.Animation.EasingFunctionBase>, Sie können eine von mehreren Beschleunigungsfunktionen, die von der Runtime bereitgestellten allgemeiner Effekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="7252b-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="7252b-107"><xref:System.Windows.Media.Animation.BackEase>: Wird die Bewegung einer Animation etwas zurückgezogen, bevor sie die zu animierende im angegebenen Pfad beginnt.</span><span class="sxs-lookup"><span data-stu-id="7252b-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="7252b-108"><xref:System.Windows.Media.Animation.BounceEase>: Erstellt eine springenden wirksam.</span><span class="sxs-lookup"><span data-stu-id="7252b-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="7252b-109"><xref:System.Windows.Media.Animation.CircleEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird mit einer Funktion kreisförmig.</span><span class="sxs-lookup"><span data-stu-id="7252b-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="7252b-110"><xref:System.Windows.Media.Animation.CubicEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="7252b-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="7252b-111"><xref:System.Windows.Media.Animation.ElasticEase>: Erstellt eine Animation, die eine hin-und bis sie zum Stillstand kommt oszilliert Spring ähnelt.</span><span class="sxs-lookup"><span data-stu-id="7252b-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="7252b-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird mithilfe einer exponentiellen Formel.</span><span class="sxs-lookup"><span data-stu-id="7252b-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="7252b-113"><xref:System.Windows.Media.Animation.PowerEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>p</sup> p ist, in dem die gleich<xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7252b-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="7252b-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="7252b-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="7252b-115"><xref:System.Windows.Media.Animation.QuarticEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="7252b-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="7252b-116"><xref:System.Windows.Media.Animation.QuinticEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="7252b-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="7252b-117"><xref:System.Windows.Media.Animation.SineEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird mit einer Sinusformel.</span><span class="sxs-lookup"><span data-stu-id="7252b-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="7252b-118">Sie können das Verhalten dieser Beschleunigungsfunktionen mit folgendem Beispiel untersuchen.</span><span class="sxs-lookup"><span data-stu-id="7252b-118">You can explore the behavior of these easing functions with the following sample.</span></span>  
  
 [<span data-ttu-id="7252b-119">Dieses Beispiel ausführen</span><span class="sxs-lookup"><span data-stu-id="7252b-119">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 <span data-ttu-id="7252b-120">Um eine Beschleunigungsfunktion zu einer Animation anzuwenden, verwenden die `EasingFunction` -Eigenschaft der Animation angeben der Beschleunigungsfunktion, um auf die Animation anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7252b-120">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="7252b-121">Das folgende Beispiel wendet eine <xref:System.Windows.Media.Animation.BounceEase> Beschleunigungsfunktionen-Funktion, um eine <xref:System.Windows.Media.Animation.DoubleAnimation> einen springenden Effekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7252b-121">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [<span data-ttu-id="7252b-122">Dieses Beispiel ausführen</span><span class="sxs-lookup"><span data-stu-id="7252b-122">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="7252b-123">Im vorherigen Beispiel wurde die Beschleunigungsfunktion auf eine From/To/By-Animation angewendet.</span><span class="sxs-lookup"><span data-stu-id="7252b-123">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="7252b-124">Sie können diese Beschleunigungsfunktionen auch auf Keyframe-Animationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="7252b-124">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="7252b-125">Im folgenden Beispiel wird veranschaulicht, wie mit Keyframes mit zugeordneten Beschleunigungsfunktionen verwendet werden, um eine Animation eines Rechtecks zu erstellen, das nach oben springt, verlangsamt, sich nach unten ausdehnt (als ob es fallen würde) und dann abprallt.</span><span class="sxs-lookup"><span data-stu-id="7252b-125">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [<span data-ttu-id="7252b-126">Dieses Beispiel ausführen</span><span class="sxs-lookup"><span data-stu-id="7252b-126">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="7252b-127">Sie können die <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> Eigenschaft zum Ändern die Beschleunigungsfunktion, d. h. Verhalten zu ändern, wie die Animation interpoliert.</span><span class="sxs-lookup"><span data-stu-id="7252b-127">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="7252b-128">Es gibt drei mögliche Werte, die Sie erhalten können <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="7252b-128">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="7252b-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Die Interpolation folgt der mathematische Formel, die der Beschleunigungsfunktion zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7252b-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="7252b-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Die Interpolation folgt Interpolation zu 100 % minus der Ausgabe der Formel, die der Beschleunigungsfunktion zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7252b-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="7252b-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Die Interpolation verwendet <xref:System.Windows.Media.Animation.EasingMode.EaseIn> für die erste Hälfte der Animation und <xref:System.Windows.Media.Animation.EasingMode.EaseOut> für die zweite Hälfte.</span><span class="sxs-lookup"><span data-stu-id="7252b-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="7252b-132">Die folgenden Diagramme veranschaulichen die unterschiedlichen Werte von <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> , in denen *f*(*x*) den Animationsstatus und *t* Uhrzeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="7252b-132">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="7252b-133">![BackEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-133">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="7252b-134">![BounceEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-134">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="7252b-135">![CircleEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-135">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="7252b-136">![CubicEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-136">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="7252b-137">![ElasticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-137">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="7252b-138">![ExponentialEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-138">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="7252b-139">![QuarticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-139">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="7252b-140">![QuadraticEase mit Diagrammen von anderen Easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-140">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="7252b-141">![QuarticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-141">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="7252b-142">![QuinticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-142">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="7252b-143">![SineEase für andere EasingMode-Werte](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="7252b-143">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7252b-144">Sie können <xref:System.Windows.Media.Animation.PowerEase> So erstellen das gleiche Verhalten wie <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, und <xref:System.Windows.Media.Animation.QuinticEase> mithilfe der <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7252b-144">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="7252b-145">Angenommen, Sie verwenden möchten <xref:System.Windows.Media.Animation.PowerEase> als Ersatz für <xref:System.Windows.Media.Animation.CubicEase>, geben Sie einen <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Wert 3.</span><span class="sxs-lookup"><span data-stu-id="7252b-145">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="7252b-146">Zusätzlich zur Verwendung der in der Laufzeit enthaltenen Beschleunigungsfunktionen, können Sie eigene benutzerdefinierten Beschleunigungsfunktionen erstellen, durch Vererben von <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="7252b-146">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="7252b-147">Im folgenden Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Beschleunigungsfunktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7252b-147">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="7252b-148">Sie können eine eigene mathematische Logik für das Verhalten der Beschleunigungsfunktion durch Außerkraftsetzen Hinzufügen der <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="7252b-148">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>  
  
 [<span data-ttu-id="7252b-149">Dieses Beispiel ausführen</span><span class="sxs-lookup"><span data-stu-id="7252b-149">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
