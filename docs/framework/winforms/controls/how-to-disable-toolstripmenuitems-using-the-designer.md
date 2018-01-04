---
title: 'Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f60976ffd42c63307a0fe476cb3dc36a7c657e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="d8f38-102">Gewusst wie: Deaktivieren von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="d8f38-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="d8f38-103">Sie können begrenzen oder erweitern die Befehle, die ein Benutzer durch das Aktivieren und Deaktivieren von Menüelementen in Reaktion auf Benutzeraktivitäten treffen.</span><span class="sxs-lookup"><span data-stu-id="d8f38-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="d8f38-104">Menüelemente sind standardmäßig aktiviert, wenn sie erstellt werden, aber dies die angepasst werden kann, durch die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d8f38-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="d8f38-105">Sie können diese Eigenschaft zur Entwurfszeit im Bearbeiten der **Eigenschaften** Fenster oder programmgesteuert im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="d8f38-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="d8f38-106">Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="d8f38-106">For more information, see [How to: Disable ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8f38-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="d8f38-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d8f38-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d8f38-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d8f38-109">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="d8f38-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="d8f38-110">So deaktivieren Sie ein Menüelement zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="d8f38-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="d8f38-111">Legen Sie mit dem Menüelement, das auf dem Formular ausgewählt, die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="d8f38-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="d8f38-112">Deaktivieren das erste oder der obersten Ebene Menüelement in einem Menü deaktiviert alle Menüelemente, die innerhalb des Menüs enthalten.</span><span class="sxs-lookup"><span data-stu-id="d8f38-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="d8f38-113">Ebenso wird beim Deaktivieren eines Menüelements, das Untermenüelemente verfügt Untermenüelemente deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d8f38-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="d8f38-114">Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, gilt die guten Programmierstil, ausgeblendet und deaktiviert das gesamte Menü, wie dies eine saubere Benutzeroberfläche dar.</span><span class="sxs-lookup"><span data-stu-id="d8f38-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="d8f38-115">Sowohl sollten ausblenden und deaktivieren Sie im Menü aus, da ausblenden allein Zugriff auf einen Menübefehl über eine Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="d8f38-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="d8f38-116">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft für ein Menüelement der obersten Ebene auf `false` das gesamte Menü ausblenden.</span><span class="sxs-lookup"><span data-stu-id="d8f38-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f38-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8f38-117">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="d8f38-118">Gewusst wie: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="d8f38-118">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="d8f38-119">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8f38-119">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
