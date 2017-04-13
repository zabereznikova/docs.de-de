---
title: "Gewusst wie: Erstellen eines professionellen ToolStrip-Steuerelements | Microsoft Docs"
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
  - "ToolStripProfessionalRenderer-Klasse [Windows Forms]"
  - "ToolStripRenderer-Klasse [Windows Forms]"
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen eines professionellen ToolStrip-Steuerelements
Sie können den <xref:System.Windows.Forms.ToolStrip>\-Steuerelementen Ihrer Anwendung ein professionelles Aussehen und Verhalten \("Look and Feel"\) verleihen, indem Sie eine eigene Klasse schreiben, die vom Typ <xref:System.Windows.Forms.ToolStripProfessionalRenderer> abgeleitet ist.  
  
 In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] wird dieses Feature umfassend unterstützt.  
  
 Siehe [Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## Beispiel  
 Im folgenden Codebeispiel wird gezeigt, wie die <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente verwendet werden, um ein zusammengesetztes Steuerelement zu erstellen, das den von Microsoft® Outlook® bereitgestellten **Navigationsbereich** imitiert.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Lesen Sie außerdem [Exemplarische Vorgehensweise: Erstellen eines professionellen ToolStrip\-Steuerelements](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip\-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Gewusst wie: Bereitstellen von Standardmenüelementen für ein Formular](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)