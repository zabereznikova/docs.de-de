---
title: Hinzufügen und Entfernen von Knoten mit TreeView Control
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
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142211"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms
Das Windows <xref:System.Windows.Forms.TreeView> Forms-Steuerelement speichert die Knoten <xref:System.Windows.Forms.TreeView.Nodes%2A> der obersten Ebene in seiner Auflistung. Jeder <xref:System.Windows.Forms.TreeNode> hat auch <xref:System.Windows.Forms.TreeNode.Nodes%2A> seine eigene Sammlung, um seine untergeordneten Knoten zu speichern. Beide Auflistungseigenschaften <xref:System.Windows.Forms.TreeNodeCollection>sind vom Typ , der Standardauflistungsmember bereitstellt, mit denen Sie die Knoten auf einer einzelnen Ebene der Knotenhierarchie hinzufügen, entfernen und neu anordnen können.  
  
### <a name="to-add-nodes-programmatically"></a>So fügen Sie Knoten programmgesteuert hinzu  
  
1. Verwenden <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> Sie die Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft der Baumansicht.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>So entfernen Sie Knoten programmgesteuert  
  
1. Verwenden <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> Sie die Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft der Strukturansicht, <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> um einen einzelnen Knoten zu entfernen, oder die Methode zum Löschen aller Knoten.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
