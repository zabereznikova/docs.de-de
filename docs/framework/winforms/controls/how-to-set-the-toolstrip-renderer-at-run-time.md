---
title: "Gewusst wie: Festlegen des ToolStrip-Renderers zur Laufzeit | Microsoft Docs"
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
  - "MenuStrip-Steuerelement [Windows Forms]"
  - "Symbolleisten [Windows Forms]"
  - "ToolStrip-Steuerelement [Windows Forms]"
  - "ToolStripManager-Klasse [Windows Forms]"
  - "ToolStripProfessionalRenderer-Klasse [Windows Forms]"
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Festlegen des ToolStrip-Renderers zur Laufzeit
Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements anpassen, indem Sie eine benutzerdefinierte `ProfessionalColorTable`\-Klasse erstellen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte `ProfessionalColorTable`\-Klasse erstellt wird.  Diese Klasse definiert Farbverläufe für ein <xref:System.Windows.Forms.MenuStrip>\- und ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement.  
  
 Um dieses Codebeispiel zu verwenden, kompilieren Sie die Anwendung, führen Sie die Anwendung aus, und klicken Sie dann auf **Farben ändern**, um die Farbverläufe anzuwenden, die in der benutzerdefinierten `ProfessionalColorTable`\-Klasse definiert sind.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## Definieren einer benutzerdefinierten ProfessionalColorTable\-Klasse  
 Die benutzerdefinierten Farbverläufe sind in der `CustomProfessionalColors`\-Klasse definiert.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## Zuweisen eines benutzerdefinierten Renderers  
 Erstellen Sie eine neue `ToolStripProfessionalRenderer`\-Instanz mit der `CustomProfessionalColors`\-Klasse, und weisen Sie diese Instanz der <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>\-Eigenschaft zu.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.ProfessionalColorTable>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)