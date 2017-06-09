---
title: "Gewusst wie: Angeben des &#220;bergabeverhaltens zwischen Storyboard-Animationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Animation, Übergabeverhalten zwischen"
  - "Storyboards, Übergabeverhalten zwischen Animationen"
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Angeben des &#220;bergabeverhaltens zwischen Storyboard-Animationen
In diesem Beispiel wird das Angeben des Übergabeverhaltens zwischen Storyboard\-Animationen veranschaulicht.  Die <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>\-Eigenschaft von <xref:System.Windows.Media.Animation.BeginStoryboard> gibt an, wie neue Animationen mit vorhandenen, bereits auf eine Eigenschaft angewendeten Animationen interagieren.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Schaltflächen erstellt, die vergrößert werden, wenn der Mauszeiger darüber geführt wird, und verkleinert werden, wenn der Mauszeiger entfernt wird.  Wenn Sie den Mauszeiger über eine Schaltfläche bewegen und dann schnell entfernen, wird die zweite Animation angewendet, bevor die erste beendet ist.  Wenn sich zwei Animationen auf diese Weise überschneiden, ist der Unterschied zwischen den <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>\-Werten von <xref:System.Windows.Media.Animation.HandoffBehavior> und <xref:System.Windows.Media.Animation.HandoffBehavior> erkennbar.  Ein Wert von <xref:System.Windows.Media.Animation.HandoffBehavior> kombiniert die sich überschneidenden Animationen und führt zu einem glatteren Übergang zwischen Animationen, während durch einen Wert von <xref:System.Windows.Media.Animation.HandoffBehavior> die vorherige, sich überschneidende Animation sofort durch die neue Animation ersetzt wird.  
  
 [!code-xml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.BeginStoryboard>   
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/de-de/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)