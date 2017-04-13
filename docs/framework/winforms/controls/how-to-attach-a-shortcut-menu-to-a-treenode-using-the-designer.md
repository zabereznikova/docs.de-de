---
title: "Gewusst wie: Anf&#252;gen eines Kontextmen&#252;s an einen TreeNode mithilfe des Designers | Microsoft Docs"
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
  - "Kontextmenüs, Anhängen an TreeNodes"
  - "TreeNode, Anfügen eines Kontextmenüs mit dem Designer"
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Anf&#252;gen eines Kontextmen&#252;s an einen TreeNode mithilfe des Designers
Mit dem <xref:System.Windows.Forms.TreeView>\-Steuerelement von Windows Forms wird eine Hierarchie von Knoten angezeigt, die vergleichbar ist mit den Dateien und Ordnern im linken Bereich des Windows Explorer\-Features von Windows\-Betriebssystemen.  Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>\-Eigenschaft können Sie kontextbezogene Operationen für den Benutzer bereitstellen, wenn dieser mit der rechten Maustaste auf das <xref:System.Windows.Forms.TreeView>\-Steuerelement klickt.  Wenn Sie eine <xref:System.Windows.Forms.ContextMenuStrip>\-Komponente einzelnen <xref:System.Windows.Forms.TreeNode>\-Elementen zuordnen, können Sie den <xref:System.Windows.Forms.TreeView>\-Steuerelementen benutzerdefinierte Kontextmenüfunktionen hinzufügen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So ordnen Sie zur Entwurfszeit einem TreeNode ein Kontextmenü zu  
  
1.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.TreeView>\-Steuerelement hinzu, und fügen Sie anschließend der <xref:System.Windows.Forms.TreeView> nach Bedarf Knoten hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.ContextMenuStrip>\-Komponente hinzu, und fügen Sie anschließend dem Kontextmenü Menüelemente hinzu, die Operationen auf Knotenebene darstellen, die Sie zur Laufzeit ausführen möchten.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Menüelementen zu einem ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Öffnen Sie erneut das Dialogfeld **TreeNode\-Editor** für das <xref:System.Windows.Forms.TreeView>\-Steuerelement, wählen Sie den zu bearbeitenden Knoten aus, und legen Sie seine <xref:System.Windows.Forms.ContextMenuStrip>\-Eigenschaft auf das hinzugefügte Kontextmenü fest.  
  
4.  Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn Sie mit der rechten Maustaste auf den Knoten klicken.  
  
     Zusätzlich können Sie Code zum Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignisse für diese Menüelemente schreiben.  
  
## Siehe auch  
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Übersicht über das TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [ContextMenuStrip\-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)