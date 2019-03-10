---
title: 'Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: 537593399db7deb775929cd742a749ce47890db6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703613"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="1e72b-102">Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten</span><span class="sxs-lookup"><span data-stu-id="1e72b-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="1e72b-103">Die Windows-Formulare <xref:System.Windows.Forms.TreeView> Steuerelement wird eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e72b-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="1e72b-104">Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie bieten kontextbezogene Vorgänge für den Benutzer sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1e72b-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="1e72b-105">Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit individuellen <xref:System.Windows.Forms.TreeNode> Elemente, Sie können eine benutzerdefinierte Ebene Verknüpfung im Menü-Funktionen zum Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="1e72b-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="1e72b-106">Ein Kontextmenü einen TreeNode programmgesteuert zugeordnet werden soll</span><span class="sxs-lookup"><span data-stu-id="1e72b-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="1e72b-107">Instanziieren einer <xref:System.Windows.Forms.TreeView> steuern Sie mit den entsprechenden eigenschafteneinstellungen, erstellen Sie ein Stamm <xref:System.Windows.Forms.TreeNode>, und fügen Sie dann die untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="1e72b-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="1e72b-108">Instanziieren einer <xref:System.Windows.Forms.ContextMenuStrip> -Komponente, und fügen Sie dann eine <xref:System.Windows.Forms.ToolStripMenuItem> für jeden Vorgang, der zur Laufzeit verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1e72b-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="1e72b-109">Legen Sie die <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> Eigenschaft des entsprechenden <xref:System.Windows.Forms.TreeNode> auf das Kontextmenü, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e72b-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="1e72b-110">Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü per Rechtsklick auf den Knoten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1e72b-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="1e72b-111">Das folgende Codebeispiel erstellt eine grundlegende <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ContextMenuStrip> zugeordnet <xref:System.Windows.Forms.TreeNode> von der <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="1e72b-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="1e72b-112">Sie müssen an die Menüoptionen auf die Anpassen der <xref:System.Windows.Forms.TreeView> Sie entwickeln.</span><span class="sxs-lookup"><span data-stu-id="1e72b-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="1e72b-113">Darüber hinaus sollten Sie zum Schreiben von Code zum Behandeln von der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="1e72b-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1e72b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e72b-114">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="1e72b-115">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1e72b-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
