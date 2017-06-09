---
title: "Gewusst wie: Verwenden von QuickInfos in ToolStrip-Steuerelementen | Microsoft Docs"
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
  - "Symbolleisten [Windows Forms], Hinzufügen von QuickInfos"
  - "ToolStrip-Steuerelement [Windows Forms], Hinzufügen von QuickInfos"
  - "QuickInfo [Windows Forms], Hinzufügen"
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Verwenden von QuickInfos in ToolStrip-Steuerelementen
Sie können eine <xref:System.Windows.Forms.ToolTip> für das gewünschte <xref:System.Windows.Forms.ToolStrip>\-Steuerelement anzeigen, indem Sie die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>\-Eigenschaft des Steuerelements auf `true` festlegen.  
  
### So zeigen Sie eine QuickInfo an  
  
-   Legen Sie für die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>\-Eigenschaft des Steuerelements `true` fest.  
  
     Der Standardwert von <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=fullName> ist `true`, und der Standardwert von <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=fullName> und <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=fullName> ist `false`.  
  
### So verwenden Sie die ToolTipText\-Eigenschaft für den QuickInfo\-Text eines ToolStripButton  
  
1.  Legen Sie die <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>\-Eigenschaft der Schaltfläche auf `true` fest.  
  
2.  Legen Sie die <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=fullName>\-Eigenschaft der Schaltfläche auf `false` fest.  
  
     Die `AutoToolTip`\-Eigenschaft ist für <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> und <xref:System.Windows.Forms.ToolStripSplitButton> standardmäßig auf `true` festgelegt.  
  
     Ein <xref:System.Windows.Forms.ToolStripButton> verwendet die `Text`\-Eigenschaft standardmäßig für den <xref:System.Windows.Forms.ToolTip>\-Text.  Mit dieser Prozedur können Sie in einer <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip> benutzerdefinierten Text anzeigen.  
  
> [!NOTE]
>  Wenn Sie <xref:System.Windows.Forms.ToolStripItemDisplayStyle> auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle> oder <xref:System.Windows.Forms.ToolStripItemDisplayStyle> festlegen, wird auf der Schaltfläche kein Text angezeigt, die QuickInfo wird aber trotzdem angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>   
 <xref:System.Windows.Forms.ToolStripButton>   
 <xref:System.Windows.Forms.ToolStripDropDownButton>   
 <xref:System.Windows.Forms.ToolStripSplitButton>   
 [Übersicht über das ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)