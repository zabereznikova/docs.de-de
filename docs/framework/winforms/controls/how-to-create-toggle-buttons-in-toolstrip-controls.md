---
title: "Gewusst wie: Erstellen von Umschaltfl&#228;chen in ToolStrip-Steuerelementen | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Symbolleisten"
  - "Umschaltflächen, Erstellen"
  - "ToolStrip-Steuerelement [Windows Forms], Erstellen von Umschaltflächen"
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen von Umschaltfl&#228;chen in ToolStrip-Steuerelementen
Wenn ein Benutzer auf eine Umschaltfläche klickt, wird diese so lange vertieft angezeigt, bis der Benutzer erneut auf die Schaltfläche klickt.  
  
### So erstellen Sie eine ToolStripButton\-Umschaltfläche  
  
-   Verwenden Sie Code wie im folgenden Codebeispiel.  In diesem Code wird davon ausgegangen, dass das Formular ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement und die zugehörige <xref:System.Windows.Forms.ToolStrip.Items%2A>\-Auflistung einen <xref:System.Windows.Forms.ToolStripButton> mit dem Namen `toolStripButton1` enthält.  Es wird außerdem davon ausgegangen, dass Sie über den Ereignishandler `toolStripButton1_CheckedChanged` verfügen.  
  
     \[Visual Basic\]  
  
    ```  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripButton>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)