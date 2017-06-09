---
title: "Gewusst wie: Animieren einer Eigenschaft mit AnimationClock | Microsoft Docs"
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
  - "Animation, Eigenschaften, Mit AnimationClocks"
  - "AnimationClocks"
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Animieren einer Eigenschaft mit AnimationClock
In diesem Beispiel wird die Verwendung von <xref:System.Windows.Media.Animation.Clock>\-Objekten zum Animieren einer Eigenschaft dargestellt.  
  
 Es gibt drei Möglichkeiten, eine [Abhängigkeitseigenschaft](GTMT) zu animieren:  
  
-   Erstellen Sie eine <xref:System.Windows.Media.Animation.AnimationTimeline>, und ordnen Sie sie dieser Eigenschaft zu, indem Sie ein <xref:System.Windows.Media.Animation.Storyboard> verwenden.  
  
-   Verwenden Sie die <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode des Objekts, um eine einzelne <xref:System.Windows.Media.Animation.AnimationTimeline> auf eine Zieleigenschaft anzuwenden.  
  
-   Erstellen Sie eine <xref:System.Windows.Media.Animation.AnimationClock> aus einer <xref:System.Windows.Media.Animation.AnimationTimeline>, und wenden Sie sie auf eine Eigenschaft an.  
  
 Mit <xref:System.Windows.Media.Animation.Storyboard>\-Objekten und der <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>\-Methode können Sie Eigenschaften animieren, ohne Uhren direkt zu erstellen und zu verteilen \(Beispiele finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) und [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)\). Die Uhren werden automatisch für Sie erstellt und verteilt.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Media.Animation.AnimationClock> erstellt und auf zwei ähnliche Eigenschaften angewendet wird.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Ein Beispiel, das veranschaulicht, wie eine <xref:System.Windows.Media.Animation.Clock> interaktiv gesteuert wird, nachdem sie gestartet wurde, finden Sie unter [Interaktives Steuern einer Uhr](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## Siehe auch  
 [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Animieren einer Eigenschaft ohne Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)   
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)