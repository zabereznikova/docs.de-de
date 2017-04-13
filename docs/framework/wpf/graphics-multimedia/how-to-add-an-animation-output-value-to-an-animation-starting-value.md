---
title: "Gewusst wie: Hinzuf&#252;gen eines Animationsausgabewerts zu einem Animationsstartwert | Microsoft Docs"
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
  - "Animation"
  - "IsAdditive-Eigenschaft"
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen eines Animationsausgabewerts zu einem Animationsstartwert
In diesem Beispiel wird das Hinzufügen eines Animationsausgabewerts zu einem Animationsstartwert veranschaulicht.  
  
## Beispiel  
 Die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>\-Eigenschaft legt fest, ob der Ausgabewert einer Animation dem Startwert \(Basiswert\) einer animierten Eigenschaft hinzugefügt werden soll.  Sie können die <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A>\-Eigenschaft bei den meisten Basis\- und Keyframe\-Animationen verwenden.  Weitere Informationen finden Sie unter [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) und unter [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 Im folgenden Beispiel werden die Auswirkungen der Verwendung der <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=fullName>\-Eigenschaft mit <xref:System.Windows.Media.Animation.DoubleAnimation> und der <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=fullName>\-Eigenschaft mit <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> dargestellt.  
  
 [!code-xml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## Siehe auch  
 [Sammeln von Animationen während Wiederholungszyklen](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Keyframe\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/de-de/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)