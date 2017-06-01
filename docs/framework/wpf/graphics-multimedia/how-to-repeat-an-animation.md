---
title: "Gewusst wie: Wiederholen einer Animation | Microsoft Docs"
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
  - "Animation, Wiederholen"
  - "RepeatBehavior-Eigenschaft von Zeitachsen"
  - "Wiederholen der Animation"
  - "Zeitachsen-RepeatBehavior-Eigenschaft"
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Wiederholen einer Animation
In diesem Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> zur Steuerung des Wiederholungsverhaltens einer Animation beschrieben.  
  
## Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> legt fest, wie oft eine Animation ihre einfache Dauer wiederholt.  Mit <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> können Sie für <xref:System.Windows.Media.Animation.Timeline> eine bestimmte Anzahl an Wiederholungen \(Iterationszählung\) oder Wiederholungen für eine bestimmte Dauer festlegen.  In beiden Fällen wird die Animation so oft von Anfang bis Ende wiederholt, bis die Vorgaben für die Anzahl bzw. die Zeit der Wiederholungsläufe erfüllt sind.  
  
 Standardmäßig liegt die Anzahl der Wiederholungen für Zeitachsen bei 1,0, d. h. sie wird einmal durchlaufen und nicht wiederholt.  Wenn Sie jedoch die <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft einer <xref:System.Windows.Media.Animation.Timeline> auf <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> festlegen, wird die Zeitachse unbegrenzt wiederholt.  
  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Eigenschaft zur Steuerung des Wiederholungsverhaltens einer Animation beschrieben.  Im Beispiel wird die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft durch fünf Rechtecke animiert, wobei für jedes Rechteck eine andere Art von Wiederholungsverhalten verwendet wird.  
  
 [!code-xml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel zum Verhalten der Animationszeitsteuerung](http://go.microsoft.com/fwlink/?LinkID=159970).  
  
## Siehe auch  
 [Sammeln von Animationen während Wiederholungszyklen](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Festlegen, ob eine Zeitachse automatisch umgekehrt wird](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/de-de/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Beispiel zum Verhalten der Animationszeitsteuerung](http://go.microsoft.com/fwlink/?LinkID=159970)