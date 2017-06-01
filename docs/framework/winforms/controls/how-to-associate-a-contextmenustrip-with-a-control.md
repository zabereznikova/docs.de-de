---
title: "Gewusst wie: Zuordnen eines ContextMenuStrip zu einem Steuerelement | Microsoft Docs"
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
  - "Kontextmenüs, Verknüpfen mit Steuerelementen"
  - "Kontextmenüs, Erstellen von Beziehungen"
  - "ContextMenuStrips, Verknüpfen mit Steuerelementen"
  - "ContextMenuStrips, Erstellen von Beziehungen"
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Zuordnen eines ContextMenuStrip zu einem Steuerelement
Nachdem Sie Ihre Steuerelemente und Kontextmenüs erstellt haben, verwenden Sie die folgenden Verfahren, um ein bestimmtes Kontextmenü anzuzeigen, wenn der Benutzer mit der rechten Maustaste auf das Steuerelement klickt.  In diesen Verfahren wird eine <xref:System.Windows.Forms.ContextMenuStrip>\-Instanz einem Windows Form\-Objekt und einem <xref:System.Windows.Forms.ToolStrip>\-Steuerelement zugeordnet.  
  
### So ordnen Sie eine ContextMenuStrip\-Instanz einem Windows Form\-Objekt zu  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>\-Eigenschaft auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>\-Instanz fest.  
  
### So ordnen Sie eine ContextMenuStrip\-Instanz einem ToolStrip\-Steuerelement zu  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>\-Eigenschaft des Steuerelements auf den Namen der zugeordneten <xref:System.Windows.Forms.ContextMenuStrip>\-Instanz fest.  
  
## Beispiel  
 Im folgenden Codebeispiel werden ein Windows Form\-Objekt und ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement erstellt, und beiden wird jeweils ein anderes <xref:System.Windows.Forms.ContextMenuStrip>\-Steuerelement zugeordnet.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>   
 <xref:System.Windows.Forms.ToolStrip>   
 [Gewusst wie: Hinzufügen von Menüelementen zu einem ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)   
 [ContextMenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)