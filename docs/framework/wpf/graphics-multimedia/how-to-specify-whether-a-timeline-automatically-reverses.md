---
title: "Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird | Microsoft Docs"
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
  - "AutoReverse-Eigenschaft von Zeitachsen"
  - "Zeitachsen, AutoReverse-Eigenschaft"
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Angeben, ob die Wiedergaberichtung einer Zeitachse automatisch umgekehrt wird
Die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft einer Zeitachse legt fest, ob ihre Wiedergaberichtung nach Abschluss einer Vorwärtsiteration umgekehrt wird.  Das folgende Beispiel enthält mehrere Animationen mit denselben Dauer\- und Zielwerten, jedoch mit unterschiedlichen <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Einstellungen.  Um zu veranschaulichen, wie sich die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft in Verbindung mit anderen <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>\-Einstellungen verhält, sind einige Animationen auf Wiederholung eingestellt.  In der letzten Animation wird gezeigt, wie die <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>\-Eigenschaft mit geschachtelten Zeitachsen funktioniert.  
  
## Beispiel  
 [!code-xml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]