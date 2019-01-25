---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: 30dbe55711d92ea1fdbbbfd147a65b27d0dc9a50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711504"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.TreeView> Steuerelement speichert den Knoten der obersten Ebene in der <xref:System.Windows.Forms.TreeView.Nodes%2A> Auflistung. Jede <xref:System.Windows.Forms.TreeNode> hat auch ein eigenes <xref:System.Windows.Forms.TreeNode.Nodes%2A> Auflistung zum Speichern der untergeordneten Knoten. Beide-Auflistung – Eigenschaften sind vom Typ <xref:System.Windows.Forms.TreeNodeCollection>, dort finden Sie standardmäßige Auflistungsmember, die Sie hinzufügen möchten, können entfernen, und ordnen die Knoten auf einer einzigen Ebene der Hierarchie von Knoten.  
  
### <a name="to-add-nodes-programmatically"></a>Das programmgesteuerte Hinzufügen von Knoten  
  
1.  Verwenden der <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> Methode der Strukturansicht <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Das programmgesteuerte Entfernen von Knoten  
  
1.  Verwenden der <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> Methode der Strukturansicht <xref:System.Windows.Forms.TreeView.Nodes%2A> zu einen einzelnen Knoten zu entfernenden Eigenschaft oder das <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> Methode, um alle Knoten zu löschen.  
  
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
  
## <a name="see-also"></a>Siehe auch
- [TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
