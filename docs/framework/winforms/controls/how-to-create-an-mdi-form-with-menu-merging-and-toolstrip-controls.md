---
title: "Gewusst wie: Erstellen eines MDI-Formulars mit der Zusammenf&#252;hrungsfunktion f&#252;r Men&#252;s und ToolStrip-Steuerelementen | Microsoft Docs"
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
  - "ToolStripPanel-Steuerelement [Windows Forms]"
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen eines MDI-Formulars mit der Zusammenf&#252;hrungsfunktion f&#252;r Men&#252;s und ToolStrip-Steuerelementen
Der <xref:System.Windows.Forms?displayProperty=fullName>\-Namespace unterstützt MDI\-Anwendungen \(Multiple Document Interface, Schnittstelle für mehrere Dokumente\), und das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement unterstützt das Zusammenführen von Menüs.  MDI\-Formulare können auch <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente enthalten.  
  
 In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] wird dieses Feature umfassend unterstützt.  
  
 Siehe auch [Exemplarische Vorgehensweise: Erstellen eines MDI\-Formulars mit der Zusammenführungsfunktion für Menüs und ToolStrip\-Steuerelemente](http://msdn.microsoft.com/library/ms233676%20\(v=vs.110\)).  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie <xref:System.Windows.Forms.ToolStripPanel>\-Steuerelemente mit einem MDI\-Formular verwenden können.  Das Formular unterstützt auch Zusammenführen von Menüs mit untergeordneten Menüs.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Codebeispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)