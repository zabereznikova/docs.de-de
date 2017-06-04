---
title: "Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms | Microsoft Docs"
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
  - "AllowItemReorder-Eigenschaft"
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Symbolleisten [Windows Forms], Neuanordnen von Steuerelementen"
  - "ToolStrip-Steuerelement [Windows Forms], Beispiele"
  - "ToolStrip-Steuerelement [Windows Forms], Neuanordnen von Elementen"
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms
Sie können es dem Benutzer ermöglichen, <xref:System.Windows.Forms.ToolStripItem>\-Steuerelemente auf dem <xref:System.Windows.Forms.ToolStrip> neu anzuordnen.  
  
### So aktivieren Sie die Neuanordnung von ToolStrip\-Elementen zur Laufzeit  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>\-Eigenschaft auf `true` fest.  Standardmäßig ist <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> auf `false` festgelegt.  
  
     Zur Laufzeit hält der Benutzer die ALT\-TASTE und die linke Maustaste gedrückt, um ein <xref:System.Windows.Forms.ToolStripItem> an eine andere Position auf dem <xref:System.Windows.Forms.ToolStrip> zu ziehen.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)