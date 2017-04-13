---
title: "Gewusst wie: Hinzuf&#252;gen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], TreeView-Steuerelement"
  - "Strukturknoten im TreeView-Steuerelement"
  - "TreeView-Steuerelement [Windows Forms], Hinzufügen von Knoten"
  - "TreeView-Steuerelement [Windows Forms], Entfernen von Knoten"
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Hinzuf&#252;gen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows&#160;Forms
Das <xref:System.Windows.Forms.TreeView>\-Steuerelement in Windows Forms speichert die Knoten der obersten Ebene in seiner <xref:System.Windows.Forms.TreeView.Nodes%2A>\-Auflistung.  Pro <xref:System.Windows.Forms.TreeNode> gibt es eine eigene <xref:System.Windows.Forms.TreeNode.Nodes%2A>\-Auflistung zum Speichern der untergeordneten Knoten.  Beide Auflistungseigenschaften sind vom Typ <xref:System.Windows.Forms.TreeNodeCollection>, der standardmäßige Auflistungsmember bereitstellt, mit deren Hilfe Sie Knoten auf einer einzelnen Ebene der Knotenhierarchie hinzufügen, entfernen und neu anordnen können.  
  
### So fügen Sie Knoten programmgesteuert hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.TreeNodeCollection.Add%2A>\-Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A>\-Eigenschaft der Strukturansicht.  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### So entfernen Sie Knoten programmgesteuert  
  
1.  Mithilfe der <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A>\-Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A>\-Eigenschaft der Strukturansicht entfernen Sie einen einzelnen Knoten, mithilfe der <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A>\-Methode löschen Sie alle Knoten.  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## Siehe auch  
 [TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Übersicht über das TreeView\-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Gewusst wie: Festlegen von Symbolen für das TreeView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [Gewusst wie: Durchlaufen aller Knoten eines TreeView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView\-Knotens](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)