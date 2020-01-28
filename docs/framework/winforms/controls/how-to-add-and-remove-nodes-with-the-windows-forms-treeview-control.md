---
title: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement
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
ms.openlocfilehash: 02b3a7286798c6f2a6426e09c8fc6c18b74a6bf0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731962"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms
Das Windows Forms <xref:System.Windows.Forms.TreeView>-Steuerelement speichert die Knoten der obersten Ebene in der <xref:System.Windows.Forms.TreeView.Nodes%2A> Auflistung. Jede <xref:System.Windows.Forms.TreeNode> verfügt auch über eine eigene <xref:System.Windows.Forms.TreeNode.Nodes%2A> Sammlung zum Speichern der untergeordneten Knoten. Beide Sammlungs Eigenschaften sind vom Typ <xref:System.Windows.Forms.TreeNodeCollection>, der Standard Auflistungs Elemente bereitstellt, mit denen Sie die Knoten auf einer einzelnen Ebene der Knoten Hierarchie hinzufügen, entfernen und neu anordnen können.  
  
### <a name="to-add-nodes-programmatically"></a>So fügen Sie Knotenprogramm gesteuert hinzu  
  
1. Verwenden Sie die <xref:System.Windows.Forms.TreeNodeCollection.Add%2A>-Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft der Strukturansicht.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>So entfernen Sie Knotenprogramm gesteuert  
  
1. Verwenden Sie die <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A>-Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft der Strukturansicht, um einen einzelnen Knoten zu entfernen, oder die <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A>-Methode, um alle Knoten zu löschen.  
  
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

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
