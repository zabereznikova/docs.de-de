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
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="4bcea-102">Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4bcea-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="4bcea-103">Das Windows Forms <xref:System.Windows.Forms.TreeView>-Steuerelement speichert die Knoten der obersten Ebene in der <xref:System.Windows.Forms.TreeView.Nodes%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="4bcea-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="4bcea-104">Jede <xref:System.Windows.Forms.TreeNode> verfügt auch über eine eigene <xref:System.Windows.Forms.TreeNode.Nodes%2A> Sammlung zum Speichern der untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="4bcea-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="4bcea-105">Beide Sammlungs Eigenschaften sind vom Typ <xref:System.Windows.Forms.TreeNodeCollection>, der Standard Auflistungs Elemente bereitstellt, mit denen Sie die Knoten auf einer einzelnen Ebene der Knoten Hierarchie hinzufügen, entfernen und neu anordnen können.</span><span class="sxs-lookup"><span data-stu-id="4bcea-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="4bcea-106">So fügen Sie Knotenprogramm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="4bcea-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="4bcea-107">Verwenden Sie die <xref:System.Windows.Forms.TreeNodeCollection.Add%2A>-Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft der Strukturansicht.</span><span class="sxs-lookup"><span data-stu-id="4bcea-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="4bcea-108">So entfernen Sie Knotenprogramm gesteuert</span><span class="sxs-lookup"><span data-stu-id="4bcea-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="4bcea-109">Verwenden Sie die <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A>-Methode der <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft der Strukturansicht, um einen einzelnen Knoten zu entfernen, oder die <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A>-Methode, um alle Knoten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4bcea-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4bcea-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bcea-110">See also</span></span>

- [<span data-ttu-id="4bcea-111">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4bcea-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="4bcea-112">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4bcea-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="4bcea-113">Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4bcea-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="4bcea-114">Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4bcea-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="4bcea-115">Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="4bcea-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="4bcea-116">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4bcea-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
