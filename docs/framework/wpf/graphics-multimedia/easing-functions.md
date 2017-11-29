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
# <a name="easing-functions"></a>Beschleunigungsfunktionen
Mit Beschleunigungsfunktionen können Sie benutzerdefinierte mathematische Formeln auf Animationen anwenden. Beispielsweise sollte Ihr Objekt realistisch springen oder sich so verhalten, als ob es sich auf einer Feder befinden würde. Sie können Keyframe- oder sogar From/To/By-Animationen verwenden, um sich diesen Effekten anzunähern, aber es würde eine erhebliche Menge an Arbeit bedeuten, und die Animation wäre weniger genau als die Verwendung einer mathematischen Formel.  
  
 Neben der Erstellung Ihrer eigenen benutzerdefinierten Beschleunigungsfunktion durch Erben von <xref:System.Windows.Media.Animation.EasingFunctionBase>, Sie können eine von mehreren Beschleunigungsfunktionen, die von der Runtime bereitgestellten allgemeiner Effekte erstellen.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Wird die Bewegung einer Animation etwas zurückgezogen, bevor sie die zu animierende im angegebenen Pfad beginnt.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: Erstellt eine springenden wirksam.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird mit einer Funktion kreisförmig.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: Erstellt eine Animation, die eine hin-und bis sie zum Stillstand kommt oszilliert Spring ähnelt.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird mithilfe einer exponentiellen Formel.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>p</sup> p ist, in dem die gleich<xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird anhand der Formel *f*(*t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: Erstellt eine Animation, die beschleunigt und/oder verlangsamt wird mit einer Sinusformel.  
  
 Sie können das Verhalten dieser Beschleunigungsfunktionen mit folgendem Beispiel untersuchen.  
  
 [Dieses Beispiel ausführen](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Um eine Beschleunigungsfunktion zu einer Animation anzuwenden, verwenden die `EasingFunction` -Eigenschaft der Animation angeben der Beschleunigungsfunktion, um auf die Animation anzuwenden. Das folgende Beispiel wendet eine <xref:System.Windows.Media.Animation.BounceEase> Beschleunigungsfunktionen-Funktion, um eine <xref:System.Windows.Media.Animation.DoubleAnimation> einen springenden Effekt zu erstellen.  
  
 [Dieses Beispiel ausführen](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Im vorherigen Beispiel wurde die Beschleunigungsfunktion auf eine From/To/By-Animation angewendet. Sie können diese Beschleunigungsfunktionen auch auf Keyframe-Animationen anwenden. Im folgenden Beispiel wird veranschaulicht, wie mit Keyframes mit zugeordneten Beschleunigungsfunktionen verwendet werden, um eine Animation eines Rechtecks zu erstellen, das nach oben springt, verlangsamt, sich nach unten ausdehnt (als ob es fallen würde) und dann abprallt.  
  
 [Dieses Beispiel ausführen](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Sie können die <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> Eigenschaft zum Ändern die Beschleunigungsfunktion, d. h. Verhalten zu ändern, wie die Animation interpoliert. Es gibt drei mögliche Werte, die Sie erhalten können <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Die Interpolation folgt der mathematische Formel, die der Beschleunigungsfunktion zugeordnet.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Die Interpolation folgt Interpolation zu 100 % minus der Ausgabe der Formel, die der Beschleunigungsfunktion zugeordnet.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Die Interpolation verwendet <xref:System.Windows.Media.Animation.EasingMode.EaseIn> für die erste Hälfte der Animation und <xref:System.Windows.Media.Animation.EasingMode.EaseOut> für die zweite Hälfte.  
  
 Die folgenden Diagramme veranschaulichen die unterschiedlichen Werte von <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> , in denen *f*(*x*) den Animationsstatus und *t* Uhrzeit darstellt.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode-Diagramme.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![ExponentialEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase mit Diagrammen von anderen Easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase mit Diagrammen von anderen Easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase für andere EasingMode-Werte](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Sie können <xref:System.Windows.Media.Animation.PowerEase> So erstellen das gleiche Verhalten wie <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, und <xref:System.Windows.Media.Animation.QuinticEase> mithilfe der <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft. Angenommen, Sie verwenden möchten <xref:System.Windows.Media.Animation.PowerEase> als Ersatz für <xref:System.Windows.Media.Animation.CubicEase>, geben Sie einen <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Wert 3.  
  
 Zusätzlich zur Verwendung der in der Laufzeit enthaltenen Beschleunigungsfunktionen, können Sie eigene benutzerdefinierten Beschleunigungsfunktionen erstellen, durch Vererben von <xref:System.Windows.Media.Animation.EasingFunctionBase>. Im folgenden Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Beschleunigungsfunktion erstellt wird. Sie können eine eigene mathematische Logik für das Verhalten der Beschleunigungsfunktion durch Außerkraftsetzen Hinzufügen der <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> Methode.  
  
 [Dieses Beispiel ausführen](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
