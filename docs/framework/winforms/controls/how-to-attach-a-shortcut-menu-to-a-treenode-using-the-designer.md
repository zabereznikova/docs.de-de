---
title: "Gewusst wie: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3acc1a731fa584a17c8a96f8a02986a504cd302d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="7bf11-102">Gewusst wie: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="7bf11-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="7bf11-103">Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement zeigt eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows Explorer-Features in Windows-Betriebssysteme angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bf11-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="7bf11-104">Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie können kontextbezogene Vorgänge für den Benutzer bereitstellen, wenn sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7bf11-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="7bf11-105">Durch das Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit einzelnen <xref:System.Windows.Forms.TreeNode> Elemente, können Sie eine benutzerdefinierte Ebene Verknüpfung im Menü Funktionen zur Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="7bf11-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bf11-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="7bf11-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7bf11-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7bf11-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7bf11-108">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="7bf11-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="7bf11-109">Zuordnen ein Kontextmenüs zu einem TreeNode zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="7bf11-109">To associate a shortcut menu with a TreeNode at design time</span></span>  
  
1.  <span data-ttu-id="7bf11-110">Hinzufügen einer <xref:System.Windows.Forms.TreeView> in Ihr Formular zu steuern, und fügen Sie dann den Knoten, um die <xref:System.Windows.Forms.TreeView> nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="7bf11-110">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="7bf11-111">Weitere Informationen finden Sie unter [wie: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span><span class="sxs-lookup"><span data-stu-id="7bf11-111">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>  
  
2.  <span data-ttu-id="7bf11-112">Hinzufügen einer <xref:System.Windows.Forms.ContextMenuStrip> -Komponente in Ihr Formular, und klicken Sie dann im Kontextmenü an, die auf Knotenebene Vorgänge darstellen, zur Laufzeit verfügbar machen möchten, Menüelemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7bf11-112">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="7bf11-113">Weitere Informationen finden Sie unter [wie: Hinzufügen von Menüelementen zu einem ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span><span class="sxs-lookup"><span data-stu-id="7bf11-113">For more information, see [How to: Add Menu Items to a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>  
  
3.  <span data-ttu-id="7bf11-114">Öffnen Sie erneut der **TreeNode-Editor** im Dialogfeld für die <xref:System.Windows.Forms.TreeView> steuern, wählen Sie den Knoten bearbeiten, und legen seine <xref:System.Windows.Forms.ContextMenuStrip> Eigenschaft, um das Kontextmenü, das Sie hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7bf11-114">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>  
  
4.  <span data-ttu-id="7bf11-115">Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt werden, wenn Sie den Knoten mit der rechten Maustaste.</span><span class="sxs-lookup"><span data-stu-id="7bf11-115">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
     <span data-ttu-id="7bf11-116">Darüber hinaus sollten so schreiben Sie Code zum Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="7bf11-116">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf11-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bf11-117">See Also</span></span>  
 [<span data-ttu-id="7bf11-118">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7bf11-118">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="7bf11-119">Übersicht über das TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7bf11-119">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="7bf11-120">ContextMenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7bf11-120">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
