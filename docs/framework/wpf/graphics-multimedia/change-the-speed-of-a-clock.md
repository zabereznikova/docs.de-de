---
title: "Gewusst wie: &#196;ndern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu &#228;ndern | Microsoft Docs"
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
  - "Uhren, Ändern des Takts von"
  - "Uhrentakt, Ändern"
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: &#196;ndern der Geschwindigkeit einer Uhr, ohne die Geschwindigkeit ihrer Zeitachse zu &#228;ndern
Mithilfe der <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>\-Eigenschaft eines <xref:System.Windows.Media.Animation.ClockController>\-Objekts können Sie die Geschwindigkeit eines <xref:System.Windows.Media.Animation.Clock>\-Elements anpassen, ohne den <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>\-Wert der <xref:System.Windows.Media.Animation.Timeline> der Uhr zu ändern.  Im folgenden Beispiel wird <xref:System.Windows.Media.Animation.ClockController> verwendet, um den <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>\-Wert einer Uhr interaktiv zu ändern.  Das <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated>\-Ereignis und die <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A>\-Eigenschaft der Uhr werden verwendet, um jeweils die aktuelle globale Geschwindigkeit der Uhr anzuzeigen, wenn ihr interaktiver <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>\-Wert geändert wird.  
  
## Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]