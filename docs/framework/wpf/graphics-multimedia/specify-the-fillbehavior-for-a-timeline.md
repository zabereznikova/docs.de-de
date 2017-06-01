---
title: "Gewusst wie: Festlegen von FillBehavior f&#252;r ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat | Microsoft Docs"
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
  - "FillBehavior-Eigenschaft für inaktive Zeitachsen"
  - "Zeitachsen, FillBehavior-Eigenschaft"
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Festlegen von FillBehavior f&#252;r ein Timeline-Objekt, das das Ende des aktiven Zeitraums erreicht hat
In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> für das inaktive <xref:System.Windows.Media.Animation.Timeline>\-Objekt einer animierten Eigenschaft festgelegt wird.  
  
## Beispiel  
 Die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft eines <xref:System.Windows.Media.Animation.Timeline>\-Objekts bestimmt, was mit dem Wert einer animierten Eigenschaft geschieht, wenn sie nicht animiert, d. h. wenn das <xref:System.Windows.Media.Animation.Timeline>\-Objekt inaktiv ist, das übergeordnete <xref:System.Windows.Media.Animation.Timeline>\-Objekt sich jedoch in einer aktiven oder angehaltenen Phase befindet.  Behält z. B. eine animierte Eigenschaft nach dem Ende der Animation ihren Endwert oder wird ihr Wert auf den Wert vor Beginn der Animation zurückgesetzt?  
  
 Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.DoubleAnimation> verwendet, um die <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft von zwei Rechtecken zu animieren.  Jedes Rechteck verwendet ein anderes <xref:System.Windows.Media.Animation.Timeline>\-Objekt.  
  
 Ein <xref:System.Windows.Media.Animation.Timeline>\-Objekt verfügt über eine <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft mit der Einstellung <xref:System.Windows.Media.Animation.FillBehavior>. Dies führt dazu, dass die Breite des Rechtecks am Ende von <xref:System.Windows.Media.Animation.Timeline> auf den Wert zurückgesetzt wird, den sie vor der Animation hatte.  Das andere <xref:System.Windows.Media.Animation.Timeline>\-Objekt verfügt über die <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>\-Eigenschaft <xref:System.Windows.Media.Animation.FillBehavior>. Daher behält die Breite den Endwert bei, wenn <xref:System.Windows.Media.Animation.Timeline> endet.  
  
 [!code-xml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Das vollständige Beispiel finden Sie unter [Beispielsammlung zu Animationen](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.DoubleAnimation>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/de-de/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)