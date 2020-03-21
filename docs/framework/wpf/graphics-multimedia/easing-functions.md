---
title: Beschleunigungsfunktionen
ms.date: 03/30/2017
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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186501"
---
# <a name="easing-functions"></a><span data-ttu-id="2b3e1-102">Beschleunigungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="2b3e1-102">Easing Functions</span></span>
<span data-ttu-id="2b3e1-103">Mit Beschleunigungsfunktionen können Sie benutzerdefinierte mathematische Formeln auf Animationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="2b3e1-104">Beispielsweise sollte Ihr Objekt realistisch springen oder sich so verhalten, als ob es sich auf einer Feder befinden würde.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="2b3e1-105">Sie können Keyframe- oder sogar From/To/By-Animationen verwenden, um sich diesen Effekten anzunähern, aber es würde eine erhebliche Menge an Arbeit bedeuten, und die Animation wäre weniger genau als die Verwendung einer mathematischen Formel.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="2b3e1-106">Neben dem Erstellen Einer eigenen benutzerdefinierten <xref:System.Windows.Media.Animation.EasingFunctionBase>Beschleunigungsfunktion durch Vererben von können Sie eine von mehreren Beschleunigungsfunktionen verwenden, die von der Laufzeit bereitgestellt werden, um allgemeine Effekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="2b3e1-107"><xref:System.Windows.Media.Animation.BackEase>: Zieht die Bewegung einer Animation leicht zurück, bevor sie im angegebenen Pfad zu animieren beginnt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="2b3e1-108"><xref:System.Windows.Media.Animation.BounceEase>: Erzeugt einen hüpfenden Effekt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="2b3e1-109"><xref:System.Windows.Media.Animation.CircleEase>: Erstellt eine Animation, die mit einer kreisförmigen Funktion beschleunigt und/oder verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="2b3e1-110"><xref:System.Windows.Media.Animation.CubicEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t*<sup>3</sup>beschleunigt und/oder verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="2b3e1-111"><xref:System.Windows.Media.Animation.ElasticEase>: Erstellt eine Animation, die einer Feder ähnelt, die hin und her oszilliert, bis sie zur Ruhe kommt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="2b3e1-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Erstellt eine Animation, die mit einer exponentiellen Formel beschleunigt und/oder verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="2b3e1-113"><xref:System.Windows.Media.Animation.PowerEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t* <xref:System.Windows.Media.Animation.PowerEase.Power%2A> <sup>p</sup> beschleunigt und/oder verlangsamt, wobei p gleich der Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="2b3e1-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t*<sup>2</sup>beschleunigt und/oder verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="2b3e1-115"><xref:System.Windows.Media.Animation.QuarticEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t*<sup>4</sup>beschleunigt und/oder verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="2b3e1-116"><xref:System.Windows.Media.Animation.QuinticEase>: Erstellen Sie eine Animation, die beschleunigt und/oder verlangsamt mit der Formel *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="2b3e1-117"><xref:System.Windows.Media.Animation.SineEase>: Erstellt eine Animation, die mit einer Sinusformel beschleunigt und/oder verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="2b3e1-118">Um eine Beschleunigungsfunktion auf eine `EasingFunction` Animation anzuwenden, verwenden Sie die Eigenschaft der Animation, die die Beschleunigungsfunktion angibt, die auf die Animation angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="2b3e1-119">Im folgenden Beispiel <xref:System.Windows.Media.Animation.BounceEase> wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> Beschleunigungsfunktion auf eine angewendet, um einen hüpfenden Effekt zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="2b3e1-120">Im vorherigen Beispiel wurde die Beschleunigungsfunktion auf eine From/To/By-Animation angewendet.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="2b3e1-121">Sie können diese Beschleunigungsfunktionen auch auf Keyframe-Animationen anwenden.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="2b3e1-122">Im folgenden Beispiel wird veranschaulicht, wie mit Keyframes mit zugeordneten Beschleunigungsfunktionen verwendet werden, um eine Animation eines Rechtecks zu erstellen, das nach oben springt, verlangsamt, sich nach unten ausdehnt (als ob es fallen würde) und dann abprallt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="2b3e1-123">Sie können <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> die Eigenschaft verwenden, um das Verhalten der Beschleunigungsfunktion zu ändern, d. h. die Interpolation der Animation.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="2b3e1-124">Es gibt drei mögliche Werte, die Sie geben können für: <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A></span><span class="sxs-lookup"><span data-stu-id="2b3e1-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="2b3e1-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Die Interpolation folgt der mathematischen Formel, die mit der Beschleunigungsfunktion verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="2b3e1-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation folgt 100% Interpolation abzüglich der Ausgabe der Formel, die mit der Lockerungsfunktion verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="2b3e1-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation <xref:System.Windows.Media.Animation.EasingMode.EaseIn> verwendet für die erste <xref:System.Windows.Media.Animation.EasingMode.EaseOut> Hälfte der Animation und für die zweite Hälfte.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="2b3e1-128">Die folgenden Diagramme veranschaulichen <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> die verschiedenen Werte, wobei *f*(*x*) den Animationsfortschritt und *t* die Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="2b3e1-129">![BackEase-EasingMode-Diagramme](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="2b3e1-130">![BounceEase-EasingMode-Diagramme](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="2b3e1-131">![CircleEase-EasingMode-Diagramme](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="2b3e1-132">![CubicEase-EasingMode-Diagramme](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="2b3e1-133">![ElasticEase mit Diagrammen von anderen EasingModes](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="2b3e1-134">![ExponentialEase-Diagramme von anderen EasingModes](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="2b3e1-135">![QuarticEase mit Diagrammen von anderen EasingModes.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="2b3e1-136">![QuadraticEase mit Diagrammen von anderen EasingModes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="2b3e1-137">![QuarticEase mit Diagrammen von anderen EasingModes.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="2b3e1-138">![QuinticEase mit Diagrammen von anderen EasingModes.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="2b3e1-139">![SineEase für andere EasingMode-Werte](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="2b3e1-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b3e1-140">Sie können <xref:System.Windows.Media.Animation.PowerEase> das gleiche Verhalten <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>wie <xref:System.Windows.Media.Animation.QuarticEase>, <xref:System.Windows.Media.Animation.QuinticEase> , <xref:System.Windows.Media.Animation.PowerEase.Power%2A> und die Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="2b3e1-141">Wenn Sie z. B. den <xref:System.Windows.Media.Animation.CubicEase>Wert <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 3 ersetzen möchten, <xref:System.Windows.Media.Animation.PowerEase> geben Sie den Wert 3 an.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="2b3e1-142">Zusätzlich zur Verwendung der in der Laufzeit enthaltenen Beschleunigungsfunktionen können Sie Ihre eigenen <xref:System.Windows.Media.Animation.EasingFunctionBase>benutzerdefinierten Beschleunigungsfunktionen erstellen, indem Sie von erben.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="2b3e1-143">Im folgenden Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Beschleunigungsfunktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="2b3e1-144">Sie können eine eigene mathematische Logik hinzufügen, wie sich <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> die Beschleunigungsfunktion verhält, indem Sie die Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="2b3e1-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
