---
title: "Gewusst wie: Strecken einer ToolStripTextBox zum Ausf&#252;llen der verbleibenden Breite eines ToolStrip (Windows Forms) | Microsoft Docs"
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
  - "Textfelder, Vergrößerung im ToolStrip-Steuerelement [Windows Forms]"
  - "ToolStrip-Steuerelement [Windows Forms], Vergrößern eines Textfelds"
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Strecken einer ToolStripTextBox zum Ausf&#252;llen der verbleibenden Breite eines ToolStrip (Windows Forms)
Wenn Sie die <xref:System.Windows.Forms.ToolStrip.Stretch%2A>\-Eigenschaft eines <xref:System.Windows.Forms.ToolStrip>\-Steuerelements auf `true` festlegen, füllt das Steuerelement seinen Container von einem Ende zum anderen Ende und ändert seine Größe, wenn die Größe des Containers geändert wird.  In dieser Konfiguration kann es hilfreich sein, ein Element im Steuerelement zu strecken, wie z. B. eine <xref:System.Windows.Forms.ToolStripTextBox>, um den verfügbaren Bereich auszufüllen und die Größe bei einer Größenänderung des Steuerelements anzupassen.  Mit dieser Streckung können Sie z. B. eine Anzeige und ein Verhalten ähnlich der Adressleiste in Microsoft® Internet Explorer erzielen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine Klasse mit dem Namen `ToolStripSpringTextBox` bereitgestellt, die von <xref:System.Windows.Forms.ToolStripTextBox> abgeleitet wurde.  Diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>\-Methode, um die verfügbare Breite des übergeordneten <xref:System.Windows.Forms.ToolStrip>\-Steuerelements zu berechnen, nachdem die Gesamtbreite aller anderen Elemente subtrahiert wurde.  In diesem Codebeispiel werden auch eine <xref:System.Windows.Forms.Form>\-Klasse und eine `Program`\-Klasse bereitgestellt, um das neue Verhalten zu veranschaulichen.  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf die Assemblys System, System.Drawing und System.Windows.Forms.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ToolStripTextBox>   
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=fullName>   
 [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Gewusst wie: Interaktive Verwendung der Spring\-Eigenschaft in StatusStrip](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)