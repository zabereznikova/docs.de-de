---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040078"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="ce682-102">Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="ce682-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>

<span data-ttu-id="ce682-103">Da das Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement Knoten hierarchisch anzeigt, müssen Sie beim Hinzufügen eines Knotens auf den übergeordneten Knoten achten.</span><span class="sxs-lookup"><span data-stu-id="ce682-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>

<span data-ttu-id="ce682-104">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.TreeView> das ein-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="ce682-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="ce682-105">Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="ce682-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="ce682-106">So können Sie Knoten im Designer hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="ce682-106">To add or remove nodes in the designer</span></span>

1. <span data-ttu-id="ce682-107">Wählen Sie das <xref:System.Windows.Forms.TreeView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ce682-107">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>

2. <span data-ttu-id="ce682-108">Klicken Sie **im Eigenschaften** Fenster auf die Auslassungs Punkte![(die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der](./media/visual-studio-ellipsis-button.png)Eigenschaftenfenster von Visual Studio. <xref:System.Windows.Forms.TreeView.Nodes%2A> ) neben der-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ce682-108">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>

     <span data-ttu-id="ce682-109">Der **treumode-Editor** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce682-109">The **TreeNode Editor** appears.</span></span>

3. <span data-ttu-id="ce682-110">Ein Stamm Knoten muss vorhanden sein, um Knoten hinzuzufügen. Wenn keine vorhanden ist, müssen Sie zuerst einen Stamm hinzufügen, indem Sie auf die Schaltfläche Stamm **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="ce682-110">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="ce682-111">Sie können dann untergeordnete Knoten hinzufügen, indem Sie den Stamm Knoten oder einen anderen Knoten auswählen und auf die Schaltfläche untergeordnetes Element **Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="ce682-111">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>

4. <span data-ttu-id="ce682-112">Zum Löschen von Knoten wählen Sie den zu löschenden Knoten aus, und klicken Sie dann auf die Schaltfläche **Löschen** .</span><span class="sxs-lookup"><span data-stu-id="ce682-112">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce682-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce682-113">See also</span></span>

- [<span data-ttu-id="ce682-114">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ce682-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="ce682-115">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ce682-115">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="ce682-116">Vorgehensweise: Festlegen von Symbolen für das Windows Forms TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ce682-116">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="ce682-117">Vorgehensweise: Iterieren aller Knoten eines Windows Forms TreeView-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="ce682-117">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="ce682-118">Vorgehensweise: Ermitteln, auf welchen TreeView-Knoten geklickt wurde</span><span class="sxs-lookup"><span data-stu-id="ce682-118">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="ce682-119">Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ce682-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
