---
title: "Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b7632f0e89d21d3d82098b21cf17e34847ea3de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="accf1-102">Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="accf1-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="accf1-103">Windows Forms <xref:System.Windows.Forms.TreeView> Steuerelement speichert der Knoten der obersten Ebene in der <xref:System.Windows.Forms.TreeView.Nodes%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="accf1-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="accf1-104">Jede <xref:System.Windows.Forms.TreeNode> hat auch ein eigenes <xref:System.Windows.Forms.TreeNode.Nodes%2A> Auflistung zum Speichern der untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="accf1-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="accf1-105">Beide Auflistungseigenschaften sind vom Typ <xref:System.Windows.Forms.TreeNodeCollection>, standardsammlungsregel-Elemente, die Sie hinzufügen möchten, aktivieren Sie entfernen, und ordnen die Knoten auf einer einzigen Ebene der Knotenhierarchie bietet.</span><span class="sxs-lookup"><span data-stu-id="accf1-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="accf1-106">So fügen Sie Knoten programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="accf1-106">To add nodes programmatically</span></span>  
  
1.  <span data-ttu-id="accf1-107">Verwenden der <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> Methode von der Strukturansicht <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="accf1-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="accf1-108">So entfernen Sie Knoten programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="accf1-108">To remove nodes programmatically</span></span>  
  
1.  <span data-ttu-id="accf1-109">Verwenden der <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> Methode von der Strukturansicht <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft, um einen einzelnen Knoten zu entfernen oder die <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> Methode, um alle Knoten zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="accf1-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="accf1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="accf1-110">See Also</span></span>  
 [<span data-ttu-id="accf1-111">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="accf1-111">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="accf1-112">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="accf1-112">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="accf1-113">Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="accf1-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="accf1-114">Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="accf1-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="accf1-115">Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="accf1-115">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="accf1-116">Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="accf1-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
