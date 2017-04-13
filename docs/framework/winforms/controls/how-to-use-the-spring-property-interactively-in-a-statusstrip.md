---
title: "Gewusst wie: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip | Microsoft Docs"
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
  - "Spring-Eigenschaft [Windows Forms]"
  - "Statusleisten, Beispiele"
  - "StatusStrip-Steuerelement [Windows Forms]"
  - "ToolStrip-Steuerelement [Windows Forms]"
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip
Sie können die Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> verwenden, um ein <xref:System.Windows.Forms.ToolStripStatusLabel>\-Steuerelement in einem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement zu positionieren.  Die Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> bestimmt, ob das <xref:System.Windows.Forms.ToolStripStatusLabel>\-Steuerelement den verfügbaren Platz für das <xref:System.Windows.Forms.StatusStrip>\-Steuerelement ausfüllt.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> zum Positionieren eines <xref:System.Windows.Forms.ToolStripStatusLabel>\-Steuerelements in einem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement verwendet wird.  Der <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignishandler führt einen exklusiven oder Oder\-Vorgang \(XOR\) aus, um den Wert der Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> zu wechseln.  
  
 Um dieses Codebeispiel zu verwenden, kompilieren Sie die Anwendung, und führen Sie sie aus. Klicken Sie dann auf **Middle \(Spring\)** auf dem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement, um den Wert der Eigenschaft <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> zu wechseln.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) bzw. [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)