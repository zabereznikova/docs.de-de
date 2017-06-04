---
title: "Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Maus, Erkennen von Bewegungen auf Symbolleisten"
  - "Symbolleisten [Windows Forms], Erkennen von Mausbewegungen"
  - "ToolStrip-Steuerelement [Windows Forms], Erkennen von Mausbewegungen"
  - "ToolStripItem-Klasse, Erkennen von Mausbewegungen"
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Erkennen des Mauszeigers auf einem ToolStripItem
Mithilfe der folgenden Prozedur können Sie erkennen, wann sich der Mauszeiger über einem <xref:System.Windows.Forms.ToolStripItem> befindet.  
  
### So erkennen Sie, wann sich der Mauszeiger über einem ToolStripItem befindet  
  
-   Verwenden Sie die <xref:System.Windows.Forms.ToolStripItem.Selected%2A>\-Eigenschaft für Elemente, in denen <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> auf `true` festgelegt ist.  
  
     Dadurch wird verhindert, dass Sie das <xref:System.Windows.Forms.ToolStripItem.MouseEnter>\-Ereignis und das <xref:System.Windows.Forms.ToolStripItem.MouseLeave>\-Ereignis synchronisieren müssen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)