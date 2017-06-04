---
title: "Gewusst wie: Verkn&#252;pfen von ToolStripPanels | Microsoft Docs"
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
  - "Symbolleisten [Windows Forms], Miteinander verknüpfen"
  - "ToolStripPanel-Steuerelement [Windows Forms], Miteinander verknüpfen"
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Verkn&#252;pfen von ToolStripPanels
Sie können <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente zur Laufzeit mit einer <xref:System.Windows.Forms.ToolStripPanel>\-Instanz verknüpfen, wodurch Sie die Flexibilität von MDI\-Anwendungen \(Multiple Document Interface, Schnittstelle für mehrere Dokumente\) erhalten.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente mit einer <xref:System.Windows.Forms.ToolStripPanel>\-Instanz verknüpft werden.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripPanel>   
 [Gewusst wie: Verwenden von ToolStripPanels für MDI](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)