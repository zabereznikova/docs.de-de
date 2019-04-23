---
title: 'Vorgehensweise: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 4cbb5fbdb24790a7ddbce5c38060703c7ba7024a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326891"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="ca81b-102">Vorgehensweise: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca81b-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="ca81b-103">Die Windows-Formulare <xref:System.Windows.Forms.TreeView> Steuerelement speichert den Knoten der obersten Ebene in der <xref:System.Windows.Forms.TreeView.Nodes%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ca81b-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="ca81b-104">Jede <xref:System.Windows.Forms.TreeNode> hat auch ein eigenes <xref:System.Windows.Forms.TreeNode.Nodes%2A> Auflistung zum Speichern der untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="ca81b-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="ca81b-105">Beide-Auflistung – Eigenschaften sind vom Typ <xref:System.Windows.Forms.TreeNodeCollection>, dort finden Sie standardmäßige Auflistungsmember, die Sie hinzufügen möchten, können entfernen, und ordnen die Knoten auf einer einzigen Ebene der Hierarchie von Knoten.</span><span class="sxs-lookup"><span data-stu-id="ca81b-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="ca81b-106">Das programmgesteuerte Hinzufügen von Knoten</span><span class="sxs-lookup"><span data-stu-id="ca81b-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="ca81b-107">Verwenden der <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> Methode der Strukturansicht <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ca81b-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="ca81b-108">Das programmgesteuerte Entfernen von Knoten</span><span class="sxs-lookup"><span data-stu-id="ca81b-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="ca81b-109">Verwenden der <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> Methode der Strukturansicht <xref:System.Windows.Forms.TreeView.Nodes%2A> zu einen einzelnen Knoten zu entfernenden Eigenschaft oder das <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> Methode, um alle Knoten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="ca81b-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca81b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca81b-110">See also</span></span>

- [<span data-ttu-id="ca81b-111">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ca81b-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="ca81b-112">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ca81b-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="ca81b-113">Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca81b-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="ca81b-114">Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ca81b-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="ca81b-115">Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="ca81b-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="ca81b-116">Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ca81b-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
