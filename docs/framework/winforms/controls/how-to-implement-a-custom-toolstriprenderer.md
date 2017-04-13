---
title: "Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer | Microsoft Docs"
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
  - "Symbolleisten [Windows Forms]"
  - "ToolStrip-Steuerelement [Windows Forms]"
  - "ToolStripRenderer-Klasse"
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Implementieren eines benutzerdefinierten ToolStripRenderer
Sie können die Darstellung des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements anpassen, indem Sie eine von <xref:System.Windows.Forms.ToolStripRenderer> abgeleitete Klasse implementieren.  Damit verfügen Sie über die Flexibilität zum Erstellen einer Darstellung, die sich von der von den Klassen <xref:System.Windows.Forms.ToolStripProfessionalRenderer> und <xref:System.Windows.Forms.ToolStripSystemRenderer> bereitgestellten unterscheidet.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefinierte <xref:System.Windows.Forms.ToolStripRenderer>\-Klasse implementiert wird.  In diesem Beispiel implementiert das `GridStrip`\-Steuerelement ein Puzzle mit gleitenden Kacheln, das es dem Benutzer ermöglicht, die Kacheln in einem Tabellenlayout zu verschieben, um ein Bild zusammenzusetzen.  Ein benutzerdefiniertes <xref:System.Windows.Forms.ToolStrip>\-Steuerelement ordnet seine <xref:System.Windows.Forms.ToolStripButton>\-Steuerelemente in einem Rasterlayout an.  Das Layout enthält eine leere Zelle, in die der Benutzer per Drag&Drop eine benachbarte Kachel ziehen kann.  Kacheln, die vom Benutzer verschoben werden können, sind hervorgehoben.  
  
 Mit der `GridStripRenderer`\-Klasse werden drei Aspekte der Darstellung des `GridStrip`\-Steuerelements angepasst:  
  
-   `GridStrip`\-Rahmen  
  
-   <xref:System.Windows.Forms.ToolStripButton>\-Rahmen  
  
-   <xref:System.Windows.Forms.ToolStripButton>\-Bild  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 <xref:System.Windows.Forms.ToolStripSystemRenderer>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)