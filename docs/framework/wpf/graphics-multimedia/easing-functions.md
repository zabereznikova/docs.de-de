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
ms.openlocfilehash: a74142b8d8ee3a68daa9966e3f20f3b8e3becb72
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615398"
---
# <a name="easing-functions"></a>Beschleunigungsfunktionen
Mit Beschleunigungsfunktionen können Sie benutzerdefinierte mathematische Formeln auf Animationen anwenden. Beispielsweise sollte Ihr Objekt realistisch springen oder sich so verhalten, als ob es sich auf einer Feder befinden würde. Sie können Keyframe- oder sogar From/To/By-Animationen verwenden, um sich diesen Effekten anzunähern, aber es würde eine erhebliche Menge an Arbeit bedeuten, und die Animation wäre weniger genau als die Verwendung einer mathematischen Formel.  
  
 Neben der Erstellung Ihrer eigenen benutzerdefinierten Beschleunigungsfunktion durch Erben von <xref:System.Windows.Media.Animation.EasingFunctionBase>, können Sie eine von mehreren Beschleunigungsfunktionen, die von der Runtime bereitgestellten um allgemeine Effekte zu erstellen.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Zieht die Bewegung einer Animation geringfügig zurück, vor dem Beginn im angegebenen Pfad animiert.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Erstellt einen Sprungeffekt.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: Erstellt eine Animation, die mit einer zirkulären Funktion beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Erstellt eine Animation, die mit der Formel beschleunigt und/oder verlangsamt *f*(*t*) = *t*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Erstellt eine Animation, die einer hin-und herschwingenden bis es zum Stillstand kommt Feder ähnelt.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: Erstellt eine Animation, die mit einer exponentiellen Formel beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: Erstellt eine Animation, die mit der Formel beschleunigt und/oder verlangsamt *f*(*t*) = *t*<sup>p</sup> wobei p ist gleich der <xref:System.Windows.Media.Animation.PowerEase.Power%2A>Eigenschaft.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Erstellt eine Animation, die mit der Formel beschleunigt und/oder verlangsamt *f*(*t*) = *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Erstellt eine Animation, die mit der Formel beschleunigt und/oder verlangsamt *f*(*t*) = *t*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Erstellen Sie eine Animation, die mit der Formel beschleunigt und/oder verlangsamt *f*(*t*) = *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: Erstellt eine Animation, die mit einer Sinusformel beschleunigt und/oder verlangsamt.  
  
 Verwenden Sie zum Anwenden einer Beschleunigungsfunktion auf eine Animation die `EasingFunction` -Eigenschaft der Animation die Beschleunigungsfunktion anzugeben, auf die Animation anzuwenden. Im folgenden Beispiel wird eine <xref:System.Windows.Media.Animation.BounceEase> -Beschleunigungsfunktion auf eine <xref:System.Windows.Media.Animation.DoubleAnimation> einen Sprungeffekt zu erstellen.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Im vorherigen Beispiel wurde die Beschleunigungsfunktion auf eine From/To/By-Animation angewendet. Sie können diese Beschleunigungsfunktionen auch auf Keyframe-Animationen anwenden. Im folgenden Beispiel wird veranschaulicht, wie mit Keyframes mit zugeordneten Beschleunigungsfunktionen verwendet werden, um eine Animation eines Rechtecks zu erstellen, das nach oben springt, verlangsamt, sich nach unten ausdehnt (als ob es fallen würde) und dann abprallt.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Sie können die <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> Eigenschaft zum Ändern die Beschleunigungsfunktion, d. h. das Verhalten zu ändern, wie die Animation interpoliert. Es gibt drei mögliche Werte, die Sie für erhalten <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Die Interpolation folgt die mathematische Formel, die der Beschleunigungsfunktion zugeordnet wird.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Die Interpolation folgt, 100 %-Interpolation abzüglich der Ausgabe der Formel, die der Beschleunigungsfunktion zugeordnet wird.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation verwendet <xref:System.Windows.Media.Animation.EasingMode.EaseIn> für die erste Hälfte der Animation und <xref:System.Windows.Media.Animation.EasingMode.EaseOut> für die zweite Hälfte.  
  
 Die folgenden Diagramme veranschaulichen die unterschiedlichen Werte von <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> , in denen *f*(*x*) stellt den Animationsfortschritt und *t* Zeit darstellt.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode-Diagramme.](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode-Diagramme.](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode-Diagramme.](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode-Diagramme.](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase mit Diagrammen von anderen Easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![ExponentialEase mit Diagrammen von anderen Easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase mit Diagrammen von anderen Easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase mit Diagrammen von anderen Easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase mit Diagrammen von anderen Easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase mit Diagrammen von anderen Easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase für andere EasingMode-Werte](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Können Sie <xref:System.Windows.Media.Animation.PowerEase> erstellen Sie das gleiche Verhalten wie <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, und <xref:System.Windows.Media.Animation.QuinticEase> mithilfe der <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft. Angenommen, Sie verwenden möchten <xref:System.Windows.Media.Animation.PowerEase> als Ersatz für <xref:System.Windows.Media.Animation.CubicEase>, geben Sie einen <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Wert 3.  
  
 Zusätzlich zur Verwendung der in der Laufzeit enthaltenen Beschleunigungsfunktionen, können Sie eigene benutzerdefinierten Beschleunigungsfunktionen erstellen, durch Erben von <xref:System.Windows.Media.Animation.EasingFunctionBase>. Im folgenden Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Beschleunigungsfunktion erstellt wird. Sie können eigene mathematische Logik für das Verhalten der Beschleunigungsfunktion durch Überschreiben Hinzufügen der <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> Methode.   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
