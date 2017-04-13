---
title: "Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start | Microsoft Docs"
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
  - "Ereignistrigger, Steuern von Storyboards"
  - "Storyboards, Steuern nach dem Start"
  - "Trigger, Steuern von Storyboards"
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start
In diesem Beispiel wird das Steuern eines <xref:System.Windows.Media.Animation.Storyboard> nach dessen Start veranschaulicht.  Zum Starten eines <xref:System.Windows.Media.Animation.Storyboard> mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden Sie <xref:System.Windows.Media.Animation.BeginStoryboard>. Dies verteilt die Animationen an die zu animierenden Objekte und Eigenschaften und startet anschließend das Storyboard.  Wenn Sie <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen geben, indem Sie die entsprechende <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>\-Eigenschaft festlegen, wird dieses Storyboard steuerbar.  Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde.  
  
 Verwenden Sie zum Steuern eines Storyboards die folgenden Storyboard\-Aktionen zusammen mit <xref:System.Windows.EventTrigger>\-Objekten.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltenes Storyboard fort.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Storyboard\-Geschwindigkeit.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard an das Ende seines Füllzeitraums, sofern vorhanden.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Beendet das Storyboard.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard und gibt Ressourcen frei.  
  
## Beispiel  
 Im folgenden Beispiel werden steuerbare Storyboard\-Aktionen zur interaktiven Steuerung eines Storyboards verwendet.  
  
 **Hinweis:** Ein Beispiel zum Steuern eines Storyboards mithilfe von Code finden Sie unter [Interaktives Steuern eines Storyboards, nachdem es gestartet wurde](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Weitere Beispiele finden Sie in der [Beispielsammlung zu Animationen](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## Siehe auch  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>   
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>   
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>   
 <xref:System.Windows.Media.Animation.PauseStoryboard>   
 <xref:System.Windows.Media.Animation.StopStoryboard>   
 <xref:System.Windows.Media.Animation.SeekStoryboard>   
 [Interaktives Steuern eines Storyboards, nachdem es gestartet wurde](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)