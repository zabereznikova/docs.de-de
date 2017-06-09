---
title: "Gewusst wie: Behandeln des Opening-Ereignisses von ContextMenuStrip | Microsoft Docs"
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
  - "Kontextmenüs, Ereignisbehandlung"
  - "ContextMenuStrip-Steuerelement [Windows Forms]"
  - "Ereignisbehandlung, Kontextmenüs"
  - "Kontextmenüs, Ereignisbehandlung"
  - "ToolStrip-Steuerelement [Windows Forms]"
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Behandeln des Opening-Ereignisses von ContextMenuStrip
Sie können das Verhalten des <xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelements anpassen, indem Sie das <xref:System.Windows.Forms.ToolStripDropDown.Opening>\-Ereignis behandeln.  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie das <xref:System.Windows.Forms.ToolStripDropDown.Opening>\-Ereignis behandelt wird.  Der Ereignishandler fügt einem <xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelement dynamisch Elemente hinzu.  Das vollständige Codebeispiel finden Sie unter [Gewusst wie: Dynamisches Hinzufügen von ToolStrip\-Elementen](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=fullName>\-Eigenschaft auf `true` fest, um das Öffnen des Menüs zu verhindern.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>   
 <xref:System.Windows.Forms.ToolStripDropDown>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)