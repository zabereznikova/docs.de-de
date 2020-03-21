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
# <a name="easing-functions"></a>Beschleunigungsfunktionen
Mit Beschleunigungsfunktionen können Sie benutzerdefinierte mathematische Formeln auf Animationen anwenden. Beispielsweise sollte Ihr Objekt realistisch springen oder sich so verhalten, als ob es sich auf einer Feder befinden würde. Sie können Keyframe- oder sogar From/To/By-Animationen verwenden, um sich diesen Effekten anzunähern, aber es würde eine erhebliche Menge an Arbeit bedeuten, und die Animation wäre weniger genau als die Verwendung einer mathematischen Formel.  
  
 Neben dem Erstellen Einer eigenen benutzerdefinierten <xref:System.Windows.Media.Animation.EasingFunctionBase>Beschleunigungsfunktion durch Vererben von können Sie eine von mehreren Beschleunigungsfunktionen verwenden, die von der Laufzeit bereitgestellt werden, um allgemeine Effekte zu erstellen.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Zieht die Bewegung einer Animation leicht zurück, bevor sie im angegebenen Pfad zu animieren beginnt.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Erzeugt einen hüpfenden Effekt.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: Erstellt eine Animation, die mit einer kreisförmigen Funktion beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t*<sup>3</sup>beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Erstellt eine Animation, die einer Feder ähnelt, die hin und her oszilliert, bis sie zur Ruhe kommt.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: Erstellt eine Animation, die mit einer exponentiellen Formel beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t* <xref:System.Windows.Media.Animation.PowerEase.Power%2A> <sup>p</sup> beschleunigt und/oder verlangsamt, wobei p gleich der Eigenschaft ist.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t*<sup>2</sup>beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Erstellt eine Animation, die mit der Formel *f*(*t*) = *t*<sup>4</sup>beschleunigt und/oder verlangsamt.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Erstellen Sie eine Animation, die beschleunigt und/oder verlangsamt mit der Formel *f*(*t*) = *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: Erstellt eine Animation, die mit einer Sinusformel beschleunigt und/oder verlangsamt.  
  
 Um eine Beschleunigungsfunktion auf eine `EasingFunction` Animation anzuwenden, verwenden Sie die Eigenschaft der Animation, die die Beschleunigungsfunktion angibt, die auf die Animation angewendet werden soll. Im folgenden Beispiel <xref:System.Windows.Media.Animation.BounceEase> wird eine <xref:System.Windows.Media.Animation.DoubleAnimation> Beschleunigungsfunktion auf eine angewendet, um einen hüpfenden Effekt zu erzeugen.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Im vorherigen Beispiel wurde die Beschleunigungsfunktion auf eine From/To/By-Animation angewendet. Sie können diese Beschleunigungsfunktionen auch auf Keyframe-Animationen anwenden. Im folgenden Beispiel wird veranschaulicht, wie mit Keyframes mit zugeordneten Beschleunigungsfunktionen verwendet werden, um eine Animation eines Rechtecks zu erstellen, das nach oben springt, verlangsamt, sich nach unten ausdehnt (als ob es fallen würde) und dann abprallt.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Sie können <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> die Eigenschaft verwenden, um das Verhalten der Beschleunigungsfunktion zu ändern, d. h. die Interpolation der Animation. Es gibt drei mögliche Werte, die Sie geben können für: <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Die Interpolation folgt der mathematischen Formel, die mit der Beschleunigungsfunktion verbunden ist.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation folgt 100% Interpolation abzüglich der Ausgabe der Formel, die mit der Lockerungsfunktion verbunden ist.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation <xref:System.Windows.Media.Animation.EasingMode.EaseIn> verwendet für die erste <xref:System.Windows.Media.Animation.EasingMode.EaseOut> Hälfte der Animation und für die zweite Hälfte.  
  
 Die folgenden Diagramme veranschaulichen <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> die verschiedenen Werte, wobei *f*(*x*) den Animationsfortschritt und *t* die Zeit darstellt.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase-EasingMode-Diagramme](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase-EasingMode-Diagramme](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase-EasingMode-Diagramme](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase-EasingMode-Diagramme](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase mit Diagrammen von anderen EasingModes](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![ExponentialEase-Diagramme von anderen EasingModes](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase mit Diagrammen von anderen EasingModes.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase mit Diagrammen von anderen EasingModes](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase mit Diagrammen von anderen EasingModes.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase mit Diagrammen von anderen EasingModes.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase für andere EasingMode-Werte](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> Sie können <xref:System.Windows.Media.Animation.PowerEase> das gleiche Verhalten <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>wie <xref:System.Windows.Media.Animation.QuarticEase>, <xref:System.Windows.Media.Animation.QuinticEase> , <xref:System.Windows.Media.Animation.PowerEase.Power%2A> und die Eigenschaft verwenden. Wenn Sie z. B. den <xref:System.Windows.Media.Animation.CubicEase>Wert <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 3 ersetzen möchten, <xref:System.Windows.Media.Animation.PowerEase> geben Sie den Wert 3 an.  
  
 Zusätzlich zur Verwendung der in der Laufzeit enthaltenen Beschleunigungsfunktionen können Sie Ihre eigenen <xref:System.Windows.Media.Animation.EasingFunctionBase>benutzerdefinierten Beschleunigungsfunktionen erstellen, indem Sie von erben. Im folgenden Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Beschleunigungsfunktion erstellt wird. Sie können eine eigene mathematische Logik hinzufügen, wie sich <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> die Beschleunigungsfunktion verhält, indem Sie die Methode überschreiben.
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
