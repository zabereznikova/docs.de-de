---
title: "Gewusst wie: Festlegen der Dauer einer Animation | Microsoft Docs"
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
  - "Animation, Dauer"
  - "Dauer von Animationen"
  - "Zeitachsen, description"
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Festlegen der Dauer einer Animation
Eine <xref:System.Windows.Media.Animation.Timeline> stellt einen Zeitabschnitt dar, und die Länge dieses Abschnitts wird durch die <xref:System.Windows.Duration> der Zeitachse angegeben.  Wenn eine <xref:System.Windows.Media.Animation.Timeline> das Ende ihrer Dauer erreicht, wird ihre Wiedergabe beendet.  Wenn die <xref:System.Windows.Media.Animation.Timeline> über untergeordnete Zeitachsen verfügt, wird deren Wiedergabe ebenfalls beendet.  Bei einer Animation gibt die <xref:System.Windows.Duration> an, wie viel Zeit die Animation für den Übergang vom Startwert zum Endwert benötigt.  
  
 Sie können entweder eine <xref:System.Windows.Duration> mit einem bestimmten, endlichen Zeitwert oder die speziellen Werte <xref:System.Windows.Duration.Automatic%2A> bzw. <xref:System.Windows.Duration.Forever%2A> angeben.  Die Dauer einer Animation muss immer ein Zeitwert sein, da eine Animation immer über eine definierte, endliche Länge verfügen muss. Andernfalls wüsste die Animation nicht, wie der Übergang zwischen den Zielwerten erfolgen soll.  Containerzeitachsen \(<xref:System.Windows.Media.Animation.TimelineGroup>\-Objekte\) wie <xref:System.Windows.Media.Animation.Storyboard> und <xref:System.Windows.Media.Animation.ParallelTimeline> verfügen standardmäßig über die Dauer <xref:System.Windows.Duration.Automatic%2A>. Das heißt, sie enden automatisch, sobald die Wiedergabe ihres letzten untergeordneten Elements beendet ist.  
  
 Im folgenden Beispiel sind Breite, Höhe und Füllfarbe von einem <xref:System.Windows.Shapes.Rectangle> animiert.  Die Dauer wird für Animations\- und Containerzeitachsen festgelegt, wodurch sich Animationseffekte wie die Steuerung der wahrgenommenen Geschwindigkeit einer Animation oder das Überschreiben der Dauer untergeordneter Zeitachsen mit der Dauer einer Containerzeitachse ergeben.  
  
## Beispiel  
 [!code-xml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Duration>   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)