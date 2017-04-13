---
title: "Gewusst wie: Steuern eines Storyboards nach dem Start | Microsoft Docs"
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
  - "Storyboards, Steuern nach dem Start"
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Steuern eines Storyboards nach dem Start
In diesem Beispiel wird gezeigt, wie Sie mithilfe von Code ein <xref:System.Windows.Media.Animation.Storyboard> steuern, nachdem es gestartet wurde.  Verwenden Sie zum Steuern eines Storyboards in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die Objekte <xref:System.Windows.Trigger> und <xref:System.Windows.TriggerAction>. Ein Beispiel finden Sie unter [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Zum Starten eines Storyboards verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode, durch die die Animationen des Storyboards an die zu animierenden Eigenschaften verteilt werden und das Storyboard gestartet wird.  
  
 Um ein Storyboard steuerbar zu machen, verwenden Sie die <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>\-Methode und geben als zweiten Parameter **true** an.  Anschließend können Sie das Storyboard mit den interaktiven Methoden anhalten, fortsetzen, suchen, beschleunigen und verlangsamen oder es an das Ende des Füllzeitraums setzen.  Die folgende Liste gibt einen Überblick über die interaktiven Methoden des Storyboards:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Hält das Storyboard an.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Setzt ein angehaltenes Storyboard fort.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Legt die interaktive Geschwindigkeit des Storyboards fest.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Sucht die angegebene Position des Storyboards.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Sucht die angegebene Position des Storyboards.  Im Gegensatz zur <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>\-Methode wird dieser Vorgang vor dem nächsten Teilstrich verarbeitet.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Setzt das Storyboard auf den Füllzeitraum, falls vorhanden.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Beendet das Storyboard.  
  
 Im folgenden Beispiel werden verschiedene Storyboard\-Methoden zur interaktiven Steuerung eines Storyboards verwendet.  
  
 **Hinweis:** Ein Beispiel zum Steuern eines Storyboards mithilfe von Triggern in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] finden Sie unter [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## Siehe auch  
 [Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)