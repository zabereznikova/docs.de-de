---
title: "Gewusst wie: Festlegen des ToolStrip-Renderers f&#252;r eine Anwendung | Microsoft Docs"
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
  - "Renderer-Eigenschaft [Windows Forms]"
  - "Symbolleisten [Windows Forms], Anpassen"
  - "ToolStrip-Steuerelement [Windows Forms]"
  - "ToolStripProfessionalRenderer-Klasse [Windows Forms]"
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Festlegen des ToolStrip-Renderers f&#252;r eine Anwendung
Sie können die Darstellung von <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen einzeln oder für alle <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente in Ihrer Anwendung anpassen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefinierter Renderer selektiv auf ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement und ein <xref:System.Windows.Forms.MenuStrip>\-Steuerelement angewendet wird.  
  
 Um dieses Codebeispiel zu verwenden, kompilieren Sie die Anwendung, führen Sie diese aus, und wählen Sie dann den Bereich des benutzerdefinierten Renderings im <xref:System.Windows.Forms.ComboBox>\-Steuerelement aus.  Klicken Sie auf **Übernehmen** um den Renderer festzulegen.  
  
 Um das benutzerdefinierte Rendering von Menüelementen zu sehen, wählen Sie die Option <xref:System.Windows.Forms.MenuStrip> im <xref:System.Windows.Forms.ComboBox>\-Steuerelement aus, klicken Sie auf **Übernehmen**, und öffnen Sie dann das Menüelement **Datei**.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Legen Sie die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName>\-Eigenschaft fest, damit ein benutzerdefinierter Renderer auf alle <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente in Ihrer Anwendung angewendet wird.  
  
 Legen Sie die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName>\-Eigenschaft fest, damit ein benutzerdefinierter Renderer auf ein einzelnes <xref:System.Windows.Forms.ToolStrip>\-Steuerelement angewendet wird.  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)