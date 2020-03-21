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
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="ddf66-102">Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddf66-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="ddf66-103">Das Windows <xref:System.Windows.Forms.TreeView> Forms-Steuerelement speichert die Knoten <xref:System.Windows.Forms.TreeView.Nodes%2A> der obersten Ebene in seiner Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ddf66-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="ddf66-104">Jeder <xref:System.Windows.Forms.TreeNode> hat auch <xref:System.Windows.Forms.TreeNode.Nodes%2A> seine eigene Sammlung, um seine untergeordneten Knoten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ddf66-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="ddf66-105">Beide Auflistungseigenschaften <xref:System.Windows.Forms.TreeNodeCollection>sind vom Typ , der Standardauflistungsmember bereitstellt, mit denen Sie die Knoten auf einer einzelnen Ebene der Knotenhierarchie hinzufügen, entfernen und neu anordnen können.</span><span class="sxs-lookup"><span data-stu-id="ddf66-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="ddf66-106">So fügen Sie Knoten programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="ddf66-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="ddf66-107">Verwenden <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> Sie die Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft der Baumansicht.</span><span class="sxs-lookup"><span data-stu-id="ddf66-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="ddf66-108">So entfernen Sie Knoten programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="ddf66-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="ddf66-109">Verwenden <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> Sie die Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft der Strukturansicht, <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> um einen einzelnen Knoten zu entfernen, oder die Methode zum Löschen aller Knoten.</span><span class="sxs-lookup"><span data-stu-id="ddf66-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddf66-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddf66-110">See also</span></span>

- [<span data-ttu-id="ddf66-111">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ddf66-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="ddf66-112">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ddf66-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="ddf66-113">Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddf66-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="ddf66-114">Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddf66-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="ddf66-115">Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="ddf66-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="ddf66-116">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ddf66-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
