---
title: "Beschleunigungsfunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwenden von mathematischen Formeln auf Animationen [WPF]"
  - "Anwenden von Beschleunigungsfunktionen auf Animationen [WPF]"
  - "Anwenden auf Animationen mathematische Formeln [WPF]"
  - "Animationen [WPF], realistische Bewegung"
  - "Beschleunigungsfunktionen [WPF]"
  - "Anpassen von Beschleunigungsfunktionen [WPF]"
  - "Beschleunigungsfunktionen [WPF], definition"
  - "Anpassen von Beschleunigungsfunktionen [WPF]"
  - "Animationen [WPF], anwenden"
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Beschleunigungsfunktionen
Beschleunigungsfunktionen können Sie benutzerdefinierte mathematische Formeln auf Animationen anwenden. Beispielsweise sollten Sie ein Objekt realistisch springt oder Verhalten, als wäre es auf einer Feder. Sie können Keyframe- oder sogar From/To/By-Animationen verwenden, um diesen Effekten anzunähern, aber es würde eine erhebliche Menge an Arbeit, und die Animation wäre weniger genau als die Verwendung einer mathematischen Formel.  
  
 Neben der Erstellung einer eigene benutzerdefinierte Beschleunigungsfunktion durch Erben von <xref:System.Windows.Media.Animation.EasingFunctionBase>, können Sie eine von mehreren Beschleunigungsfunktionen, die von der Runtime bereitgestellten allgemeiner Effekte erstellen.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Kehrt die Bewegung einer Animation geringfügig, bevor er beginnt im angegebenen Pfad zu animieren.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: erstellt einen Sprungeffekt.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: erstellt eine Animation, die beschleunigt und/oder abbremst mithilfe einer zirkulären Funktion.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: erstellt eine Animation, die beschleunigt oder verlangsamt die Formel *f*( *t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: erstellt eine Animation, die ähnelt eine Feder hin und her oszilliert, bis sie zum Stillstand kommt.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: erstellt eine Animation, die beschleunigt und/oder abbremst mithilfe einer exponentiellen Formel.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: erstellt eine Animation, die beschleunigt oder verlangsamt die Formel *f*( *t*) = *t*<sup>p</sup> wobei p ist gleich der <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: erstellt eine Animation, die beschleunigt oder verlangsamt die Formel *f*( *t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: erstellt eine Animation, die beschleunigt oder verlangsamt die Formel *f*( *t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Animationen erstellen, die beschleunigt oder verlangsamt die Formel *f*( *t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: erstellt eine Animation, die beschleunigt oder verlangsamt einer Sinus-Formel.  
  
 Sie können das Verhalten dieser Beschleunigungsfunktionen mit folgendem Beispiel untersuchen.  
  
 [Führen Sie dieses Beispiel](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Verwenden Sie zum Anwenden einer Beschleunigungsfunktion auf eine Animation die `EasingFunction` -Eigenschaft der Animation die Beschleunigungsfunktion anzugeben, die auf die Animation anzuwenden. Im folgenden Beispiel wird ein <xref:System.Windows.Media.Animation.BounceEase> EasingFunction auf eine <xref:System.Windows.Media.Animation.DoubleAnimation> einen Sprungeffekt zu erstellen.  
  
 [Führen Sie dieses Beispiel](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Im vorherigen Beispiel wurde die Beschleunigungsfunktion auf eine From/To/By angewendet Animation. Sie können diese Beschleunigungsfunktionen auch auf Keyframe-Animationen anwenden. Im folgenden Beispiel wird veranschaulicht, wie mit Keyframes mit Beschleunigungsfunktionen zugeordnet, erstellen Sie eine Animation eines Rechtecks, das Verträge, verlangsamt, und klicken Sie dann nach unten (als ob es fällt) erweitert und dann abprallt.  
  
 [Führen Sie dieses Beispiel](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Sie können die <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> Eigenschaft zum Ändern die Beschleunigungsfunktion, d. h. das Verhalten zu ändern, wie die Animation interpoliert. Es gibt drei mögliche Werte für <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: Interpolation folgt der mathematischen Formel, die der Beschleunigungsfunktion zugeordnet.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: Interpolation folgt der Interpolation zu 100 % minus der Ausgabe der Formel, die der Beschleunigungsfunktion zugeordnet.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: Interpolation verwendet <xref:System.Windows.Media.Animation.EasingMode> für die erste Hälfte der Animation und <xref:System.Windows.Media.Animation.EasingMode> für die zweite Hälfte.  
  
 Die folgenden Diagramme veranschaulichen die unterschiedlichen Werte von <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> , *f*( *x*) stellt den Animationsfortschritt und *t* Zeit darstellt.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![BackEase EasingMode-Diagramme. ] (../Image/BackEase_Graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![BounceEase EasingMode-Diagramme. ] (../Image/BounceEase_Graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![CircleEase EasingMode-Diagramme. ] (../Image/CircleEase_Graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![CubicEase EasingMode-Diagramme. ] (../Image/CubicEase_Graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase mit Diagrammen von anderen Easingmodes. ] (../Image/ElasticEase_Graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![ExponentialEase-Diagramme von anderen Easingmodes. ] (../Image/ExponentialEase_Graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase mit Diagrammen von anderen Easingmodes. ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase mit Diagrammen von anderen Easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase mit Diagrammen von anderen Easingmodes. ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase mit Diagrammen von anderen Easingmodes. ] (../Image/QuinticEase_Graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase für andere EasingMode-Werte](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Können <xref:System.Windows.Media.Animation.PowerEase> erstellen Sie das gleiche Verhalten wie <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, und <xref:System.Windows.Media.Animation.QuinticEase> mithilfe der <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Eigenschaft. Angenommen, Sie verwenden möchten <xref:System.Windows.Media.Animation.PowerEase> als Ersatz für <xref:System.Windows.Media.Animation.CubicEase>, geben Sie einen <xref:System.Windows.Media.Animation.PowerEase.Power%2A> Wert 3.  
  
 Zusätzlich zur Verwendung der in der Laufzeit enthaltenen Beschleunigungsfunktionen, können Sie eigene benutzerdefinierte Beschleunigungsfunktionen erstellen, indem Sie erben von <xref:System.Windows.Media.Animation.EasingFunctionBase>. Im folgenden Beispiel wird veranschaulicht, wie eine einfache benutzerdefinierte Beschleunigungsfunktion erstellt wird. Sie können eigene mathematische Logik für das Verhalten der Beschleunigungsfunktion durch Überschreiben Hinzufügen der <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> Methode.  
  
 [Führen Sie dieses Beispiel](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]