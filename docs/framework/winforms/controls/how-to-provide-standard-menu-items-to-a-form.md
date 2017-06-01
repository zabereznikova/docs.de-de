---
title: "Gewusst wie: Bereitstellen von Standardmen&#252;elementen f&#252;r ein Formular | Microsoft Docs"
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
  - "Menüelemente, Standard"
  - "Symbolleisten [Windows Forms]"
  - "ToolStrip-Steuerelement [Windows Forms]"
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Bereitstellen von Standardmen&#252;elementen f&#252;r ein Formular
Mit dem <xref:System.Windows.Forms.MenuStrip>\-Steuerelement können Sie ein Standardmenü für Formulare bereitstellen.  
  
 In [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] wird dieses Feature umfassend unterstützt.  
  
 Siehe auch [Exemplarische Vorgehensweise: Bereitstellen von Standardmenüelementen für ein Formular](http://msdn.microsoft.com/library/ms233662\(v=vs.110\)).  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie mit dem <xref:System.Windows.Forms.MenuStrip>\-Steuerelement ein Formular mit Standardmenü erstellt wird.  Menüelementauswahlen werden in einem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement angezeigt.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [MenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)