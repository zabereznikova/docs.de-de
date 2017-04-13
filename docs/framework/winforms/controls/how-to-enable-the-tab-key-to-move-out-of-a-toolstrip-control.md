---
title: "Gewusst wie: Aktivieren der TAB-TASTE zum Verlassen eines ToolStrip-Steuerelements | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Bewegen zwischen"
  - "TAB-TASTE, Aktivieren"
  - "ToolStrip-Steuerelement [Windows Forms], Bewegen aus"
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Aktivieren der TAB-TASTE zum Verlassen eines ToolStrip-Steuerelements
Verwenden Sie die folgende Prozedur, damit der Benutzer durch Drücken der TAB\-TASTE einen <xref:System.Windows.Forms.ToolStrip> verlassen und zum nächsten Steuerelement in der Aktivierreihenfolge wechseln kann.  
  
 Der <xref:System.Windows.Forms.ToolStrip> akzeptiert das erste Drücken der TAB\-TASTE, und die Pfeiltasten wählen Elemente innerhalb des <xref:System.Windows.Forms.ToolStrip> aus.  Wenn der Benutzer die TAB\-TASTE ein zweites Mal drückt, gelangt er zum nächsten Steuerelement in der Aktivierreihenfolge.  
  
### So ermöglichen Sie es dem Benutzer, mithilfe der TAB\-TASTE vom ToolStrip\-Steuerelement zum nächsten Steuerelement zu wechseln  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.TabStop%2A>\-Eigenschaft von <xref:System.Windows.Forms.ToolStrip> auf `true` fest.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)