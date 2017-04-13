---
title: "Gewusst wie: Synchrones Suchen einer Uhr | Microsoft Docs"
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
  - "Uhren, Synchrones Suchen"
  - "Synchrones Suchen von Uhren"
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Synchrones Suchen einer Uhr
Verwenden Sie die <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A>\-Methode, um synchron eine Uhr an einem bestimmten Punkt zu suchen.  Im folgenden Codebeispiel werden die <xref:System.Windows.Media.Animation.ClockController.Seek%2A>\-Methode und die <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A>\-Methode eines <xref:System.Windows.Media.Animation.ClockController> veranschaulicht.  
  
 Dieses Beispiel zeigt, wie <xref:System.Windows.Media.Animation.Clock> gesucht wird. Ein Beispiel für die Suche nach einem Storyboard finden Sie unter [Synchrones Suchen von Storyboards](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md).  
  
## Beispiel  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]