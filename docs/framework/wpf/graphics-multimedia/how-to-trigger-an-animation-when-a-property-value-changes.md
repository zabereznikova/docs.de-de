---
title: "Gewusst wie: Ausl&#246;sen einer Animation bei &#196;nderung eines Eigenschaftswerts | Microsoft Docs"
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
  - "Animation, Starten beim Ändern eines Eigenschaftswerts"
  - "Storyboards, Starten beim Ändern eines Eigenschaftswerts"
  - "Auslösen der Animation"
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Ausl&#246;sen einer Animation bei &#196;nderung eines Eigenschaftswerts
In diesem Beispiel wird gezeigt, wie mit einem <xref:System.Windows.Trigger> ein <xref:System.Windows.Media.Animation.Storyboard> gestartet wird, wenn sich ein Eigenschaftswert ändert.  Sie können einen <xref:System.Windows.Trigger> in einem <xref:System.Windows.Style>, einer <xref:System.Windows.Controls.ControlTemplate> oder einer <xref:System.Windows.DataTemplate> verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Trigger> zum Animieren der <xref:System.Windows.UIElement.Opacity%2A> eines <xref:System.Windows.Controls.Button> verwendet, wenn dessen <xref:System.Windows.UIElement.IsMouseOver%2A>\-Eigenschaft in `true` geändert wird.  
  
 [!code-xml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Von <xref:System.Windows.Trigger>\-Eigenschaftenobjekten angewendete Animationen verhalten sich komplexer als <xref:System.Windows.EventTrigger>\-Animationen oder Animationen, die mithilfe von <xref:System.Windows.Media.Animation.Storyboard>\-Methoden gestartet wurden.  Sie werden mit Animationen "übergeben", die von anderen <xref:System.Windows.Trigger>\-Objekten definiert wurden, setzen sich aber aus <xref:System.Windows.EventTrigger> und durch Methoden ausgelösten Animationen zusammen.  
  
## Siehe auch  
 <xref:System.Windows.Trigger>   
 [Übersicht über die Verfahren zur Animation von Eigenschaften](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Übersicht über Storyboards](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)