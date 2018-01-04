---
title: "Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten"
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
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca251c9dec87db0ecb4b565b522839ace7f44479
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="0b489-102">Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten</span><span class="sxs-lookup"><span data-stu-id="0b489-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="0b489-103">Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement zeigt eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b489-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="0b489-104">Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie können kontextbezogene Vorgänge für den Benutzer bereitstellen, wenn sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0b489-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="0b489-105">Durch das Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit einzelnen <xref:System.Windows.Forms.TreeNode> Elemente, können Sie eine benutzerdefinierte Ebene Verknüpfung im Menü Funktionen zur Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="0b489-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="0b489-106">Um ein Kontextmenü mit einem TreeNode programmgesteuert zu verknüpfen</span><span class="sxs-lookup"><span data-stu-id="0b489-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="0b489-107">Instanziieren einer <xref:System.Windows.Forms.TreeView> mit den entsprechenden eigenschafteneinstellungen gesteuert, erstellen Sie ein Stamm <xref:System.Windows.Forms.TreeNode>, und fügen Sie dann die untergeordneten Knoten hinzu.</span><span class="sxs-lookup"><span data-stu-id="0b489-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="0b489-108">Instanziieren einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente, und fügen Sie dann eine <xref:System.Windows.Forms.ToolStripMenuItem> für jeden Vorgang, der zur Laufzeit verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="0b489-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="0b489-109">Legen Sie die <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> der entsprechenden Eigenschaft <xref:System.Windows.Forms.TreeNode> auf das Kontextmenü, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b489-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="0b489-110">Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt werden, wenn Sie den Knoten mit der rechten Maustaste.</span><span class="sxs-lookup"><span data-stu-id="0b489-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="0b489-111">Das folgende Codebeispiel erstellt einen grundlegenden <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ContextMenuStrip> verknüpft sind, mit dem Stamm <xref:System.Windows.Forms.TreeNode> von der <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="0b489-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="0b489-112">Sie müssen an die Menüoptionen auf solche Anpassen der <xref:System.Windows.Forms.TreeView> Sie entwickeln.</span><span class="sxs-lookup"><span data-stu-id="0b489-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="0b489-113">Darüber hinaus sollten so schreiben Sie Code zum Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="0b489-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0b489-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b489-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="0b489-115">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0b489-115">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
