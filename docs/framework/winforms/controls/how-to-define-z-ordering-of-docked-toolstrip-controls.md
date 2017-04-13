---
title: "Gewusst wie: Definieren der Z-Reihenfolge angedockter ToolStrip-Steuerelemente | Microsoft Docs"
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
  - "Symbolleisten [Windows Forms], Angeben der Z-Reihenfolge"
  - "ToolStrip-Steuerelement [Windows Forms]"
  - "Z-Reihenfolge"
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Definieren der Z-Reihenfolge angedockter ToolStrip-Steuerelemente
Damit ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement ordnungsgemäß angedockt wird, müssen Sie das Steuerelement ordnungsgemäß in der Z\-Reihenfolge des Formulars positionieren.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement und ein angedocktes <xref:System.Windows.Forms.MenuStrip>\-Steuerelement durch Angabe der Z\-Reihenfolge angeordnet werden.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 Die Z\-Reihenfolge wird durch die Reihenfolge bestimmt, in der das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement und das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement  
  
 der <xref:System.Windows.Forms.Control.Controls%2A>\-Auflistung des Formulars hinzugefügt werden.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 Kehren Sie die Reihenfolge dieser Aufrufe der <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>\-Methode um, und beobachten Sie die Auswirkung auf das Layout.  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>   
 <xref:System.Windows.Forms.Control.Controls%2A>   
 <xref:System.Windows.Forms.Control.Dock%2A>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)