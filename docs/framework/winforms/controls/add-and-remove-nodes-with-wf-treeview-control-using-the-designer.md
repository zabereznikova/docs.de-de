---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ca8b19e8019c170f1826660e951294b18a25e96d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880624"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="58f9c-102">Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="58f9c-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="58f9c-103">Da die Windows Forms <xref:System.Windows.Forms.TreeView> Steuerelement Knoten auf hierarchische Weise angezeigt, beim Hinzufügen eines Knotens muss darauf geachtet werden, was mit seinem übergeordneten Knoten ist.</span><span class="sxs-lookup"><span data-stu-id="58f9c-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="58f9c-104">Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.TreeView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="58f9c-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="58f9c-105">Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="58f9c-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58f9c-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="58f9c-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="58f9c-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="58f9c-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="58f9c-108">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="58f9c-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="58f9c-109">Hinzufügen oder Entfernen von Knoten im designer</span><span class="sxs-lookup"><span data-stu-id="58f9c-109">To add or remove nodes in the designer</span></span>  
  
1. <span data-ttu-id="58f9c-110">Wählen Sie das <xref:System.Windows.Forms.TreeView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="58f9c-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="58f9c-111">In der **Eigenschaften** Fenster, klicken Sie auf die **mit den Auslassungspunkten** (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.TreeView.Nodes%2A> Eigenschaft .</span><span class="sxs-lookup"><span data-stu-id="58f9c-111">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="58f9c-112">Die **TreeNode-Editor** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58f9c-112">The **TreeNode Editor** appears.</span></span>  
  
3. <span data-ttu-id="58f9c-113">Zum Hinzufügen von Knoten muss ein Stammknoten vorhanden. Wenn Sie noch nicht vorhanden ist, müssen Sie zunächst einen Stamm hinzufügen, indem Sie auf die **Stamm hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="58f9c-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="58f9c-114">Anschließend können Sie untergeordnete Knoten hinzufügen, indem die Stamm- oder einem anderen Knoten und dann auf die **untergeordnetes Element hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="58f9c-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4. <span data-ttu-id="58f9c-115">Zum Löschen von Knoten, wählen Sie den Knoten löschen, und klicken Sie dann auf die **löschen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="58f9c-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f9c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58f9c-116">See also</span></span>

- [<span data-ttu-id="58f9c-117">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="58f9c-117">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="58f9c-118">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="58f9c-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="58f9c-119">Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58f9c-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="58f9c-120">Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="58f9c-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="58f9c-121">Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens</span><span class="sxs-lookup"><span data-stu-id="58f9c-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="58f9c-122">Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="58f9c-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
