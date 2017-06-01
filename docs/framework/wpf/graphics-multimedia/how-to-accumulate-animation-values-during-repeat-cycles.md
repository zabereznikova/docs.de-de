---
title: "Gewusst wie: Sammeln von Animationswerten w&#228;hrend Wiederholungszyklen | Microsoft Docs"
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
  - "Sammeln von Animationswerten während Wiederholungszyklen"
  - "Animation, Sammeln von Werten während Wiederholungszyklen"
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Sammeln von Animationswerten w&#228;hrend Wiederholungszyklen
In diesem Beispiel wird das Sammeln von Animationswerten aus verschiedenen Wiederholungszyklen mithilfe der <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>\-Eigenschaft veranschaulicht.  
  
## Beispiel  
 Verwenden Sie die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>\-Eigenschaft, um Basiswerte einer Animation über sich wiederholende Zyklen hinweg zu sammeln.  Wenn Sie z. B. eine Animation so erstellen, dass sie sich neun mal wiederholt \(<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> \= "9x"\) und für die Eigenschaft eine Animation zwischen 10 und 15 festlegen \(From \= 10 To \= 15\), wird die Eigenschaft im ersten Zyklus von 10 bis 15, im zweiten Zyklus von 15 bis 20, im dritten Zyklus von 20 bis 25 usw. animiert.  Somit wird in jedem Animationszyklus der Endwert des vorherigen Animationszyklus als Basiswert verwendet.  
  
 Sie können die `IsCumulative`\-Eigenschaft bei den meisten Basis\- und Keyframe\-Animationen verwenden.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und unter [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Im folgenden Beispiel wird dieses Verhalten veranschaulicht, indem die Breite von vier Rechtecken animiert wird.  Beispiel:  
  
-   Animiert das erste Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>\-Eigenschaft auf `true` fest.  
  
-   Animiert das zweite Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimation> und legt die <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>\-Eigenschaft auf den Standardwert `false` fest.  
  
-   Animiert das dritte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>\-Eigenschaft auf `true` fest.  
  
-   Animiert das letzte Rechteck mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> und legt die <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>\-Eigenschaft auf `false` fest.  
  
 [!code-xml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## Siehe auch  
 [Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)   
 [Wiederholen einer Animation](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)