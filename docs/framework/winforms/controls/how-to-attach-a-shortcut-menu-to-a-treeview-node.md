---
title: "Gewusst wie: Anf&#252;gen eines Kontextmen&#252;s an einen Strukturansichtsknoten | Microsoft Docs"
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
  - "Kontextmenüs, Hinzufügen zu TreeView-Steuerelementen"
  - "Strukturknoten im TreeView-Steuerelement, Kontextmenüs"
  - "TreeView-Steuerelement [Windows Forms], Hinzufügen von Kontextmenüs"
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Anf&#252;gen eines Kontextmen&#252;s an einen Strukturansichtsknoten
Mit dem <xref:System.Windows.Forms.TreeView>\-Steuerelement in Windows Forms wird eine Hierarchie von Knoten angezeigt, ähnlich wie die Dateien und Ordner im linken Bereich des Windows Explorers.  Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>\-Eigenschaft können Sie kontextbezogene Operationen für den Benutzer bereitstellen, wenn dieser mit der rechten Maustaste auf das <xref:System.Windows.Forms.TreeView>\-Steuerelement klickt.  Wenn Sie eine <xref:System.Windows.Forms.ContextMenuStrip>\-Komponente einzelnen <xref:System.Windows.Forms.TreeNode>\-Elementen zuordnen, können Sie den <xref:System.Windows.Forms.TreeView>\-Steuerelementen benutzerdefinierte Kontextmenüfunktionen hinzufügen.  
  
### So ordnen Sie ein Kontextmenü einem TreeNode programmgesteuert zu  
  
1.  Instanziieren Sie ein <xref:System.Windows.Forms.TreeView>\-Steuerelement mit den entsprechenden Eigenschafteneinstellungen, erstellen Sie einen <xref:System.Windows.Forms.TreeNode>\-Stamm, und fügen Sie dann untergeordnete Knoten hinzu.  
  
2.  Instanziieren Sie eine <xref:System.Windows.Forms.ContextMenuStrip>\-Komponente, und fügen Sie dann ein <xref:System.Windows.Forms.ToolStripMenuItem> für jede Operation hinzu, die Sie zur Laufzeit verfügbar machen möchten.  
  
3.  Legen Sie die <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A>\-Eigenschaft des entsprechenden <xref:System.Windows.Forms.TreeNode> auf das Kontextmenü fest, das Sie erstellen.  
  
4.  Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn Sie mit der rechten Maustaste auf den Knoten klicken.  
  
 Im folgenden Codebeispiel werden eine grundlegende <xref:System.Windows.Forms.TreeView> und ein <xref:System.Windows.Forms.ContextMenuStrip> erstellt, die dem <xref:System.Windows.Forms.TreeNode>\-Stamm der <xref:System.Windows.Forms.TreeView> zugeordnet sind.  Sie müssen die Menüoptionen an die Optionen der von Ihnen entwickelten <xref:System.Windows.Forms.TreeView> anpassen.  Zusätzlich können Sie Code zum Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignisse für diese Menüelemente schreiben.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)