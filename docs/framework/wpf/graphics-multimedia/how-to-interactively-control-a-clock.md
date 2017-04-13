---
title: "Gewusst wie: Interaktives Steuern einer Uhr | Microsoft Docs"
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
  - "Uhren, Interaktives Steuern"
  - "Interaktives Steuern von Uhren"
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Interaktives Steuern einer Uhr
Mithilfe der <xref:System.Windows.Media.Animation.ClockController>\-Eigenschaft eines <xref:System.Windows.Media.Animation.Clock>\-Objekts können Sie die Uhr auf interaktive Weise starten, anhalten, erneut starten, suchen, beenden und auf das Ende ihres Füllzeitraums setzen.  Nur die Stammuhr einer Zeitstruktur kann interaktiv gesteuert werden.  
  
> [!NOTE]
>  Es gibt noch andere Möglichkeiten zum interaktiven Steuern von Animationen, bei denen Sie nicht direkt mit Uhren arbeiten müssen. Sie können als Alternative auch Storyboards verwenden.  Storyboards werden sowohl in Markup als auch in Code unterstützt.  Ein Beispiel hierfür finden Sie unter [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) bzw. [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Im folgenden Beispiel werden mehrere Schaltflächen verwendet, um eine Animationsuhr interaktiv zu steuern.  
  
## Beispiel  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## Siehe auch  
 [Animieren einer Eigenschaft unter Verwendung eines Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)