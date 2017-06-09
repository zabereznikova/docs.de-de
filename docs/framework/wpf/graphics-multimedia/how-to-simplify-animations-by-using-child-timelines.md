---
title: "Gewusst wie: Vereinfachen von Animationen durch untergeordnete Timeline-Objekte | Microsoft Docs"
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
  - "Animation, Vereinfachen durch untergeordnete Zeitachsen"
  - "Untergeordnete Zeitachsen"
  - "Vereinfachen von Animationen durch untergeordnete Zeitachsen"
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Vereinfachen von Animationen durch untergeordnete Timeline-Objekte
In diesem Beispiel wird gezeigt, wie Animationen durch untergeordnete <xref:System.Windows.Media.Animation.ParallelTimeline>\-Objekte vereinfacht werden.  Bei einem <xref:System.Windows.Media.Animation.Storyboard> handelt es sich um eine Art von <xref:System.Windows.Media.Animation.Timeline>\-Objekt, das die Zielinformationen für die enthaltenen Timeline\-Objekte zur Verfügung stellt.  Verwenden Sie eine <xref:System.Windows.Media.Animation.Storyboard>\-Klasse, um Zielinformationen für Timeline\-Objekte zur Verfügung zu stellen, einschließlich Objekt\- und Eigenschafteninformationen.  
  
 Um eine Animation zu starten, verwenden Sie ein oder mehrere <xref:System.Windows.Media.Animation.ParallelTimeline>\-Objekte als geschachtelte untergeordnete Elemente eines <xref:System.Windows.Media.Animation.Storyboard>.  Diese <xref:System.Windows.Media.Animation.ParallelTimeline>\-Objekte können andere Animationen enthalten und daher die Zeitabfolge in komplexen Animationen besser kapseln.   Wenn Sie beispielsweise einen <xref:System.Windows.Controls.TextBlock> und mehrere Formen im selben <xref:System.Windows.Media.Animation.Storyboard> animieren, können Sie die Animationen für den <xref:System.Windows.Controls.TextBlock> und für die Formen trennen, indem Sie diese jeweils in einer eigenen <xref:System.Windows.Media.Animation.ParallelTimeline> speichern.  Da jede <xref:System.Windows.Media.Animation.ParallelTimeline> über eine eigene <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> verfügt und alle untergeordneten Elemente der <xref:System.Windows.Media.Animation.ParallelTimeline> in Relation zu dieser <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> beginnen, ist die Zeitsteuerung besser gekapselt.  
  
 Im folgenden Beispiel werden zwei Textteile \(<xref:System.Windows.Controls.TextBlock>\-Objekte\) innerhalb des gleichen <xref:System.Windows.Media.Animation.Storyboard> animiert.  Eine <xref:System.Windows.Media.Animation.ParallelTimeline> kapselt die Animationen eines der <xref:System.Windows.Controls.TextBlock>\-Objekte.  
  
 **Leistungshinweis:** Obwohl Timeline\-Objekte von <xref:System.Windows.Media.Animation.Storyboard> ineinander verschachtelt werden können, eignen sich <xref:System.Windows.Media.Animation.ParallelTimeline>\-Objekte wegen des geringeren Aufwands besser zum Verschachteln.  \(Die <xref:System.Windows.Media.Animation.Storyboard>\-Klasse erbt von der <xref:System.Windows.Media.Animation.ParallelTimeline>\-Klasse.\)  
  
## Beispiel  
 [!code-xml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Angeben des Übergabeverhaltens zwischen Storyboard\-Animationen](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)