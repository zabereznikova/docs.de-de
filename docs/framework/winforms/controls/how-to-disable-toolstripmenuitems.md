---
title: 'Vorgehensweise: Deaktivieren von ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: a480cd29eef1a79a69f702eed7cd02c28d7ea3de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954226"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="54ef0-102">Vorgehensweise: Deaktivieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="54ef0-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="54ef0-103">Können Sie einschränken oder erweitern die Befehle, die ein Benutzer aktivieren und Deaktivieren von Menüelementen in Benutzeraktivitäten herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="54ef0-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="54ef0-104">Menüelemente sind standardmäßig aktiviert, wenn sie erstellt wurden, aber dies die angepasst werden kann, über die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="54ef0-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="54ef0-105">Sie können diese Eigenschaft zur Entwurfszeit im Bearbeiten der **Eigenschaften** Fenster oder programmgesteuert, indem sie im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="54ef0-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="54ef0-106">So deaktivieren Sie ein Menüelement programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="54ef0-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="54ef0-107">Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="54ef0-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="54ef0-108">Deaktivieren das erste oder der obersten Ebene Menüelement in einem Menü Blendet alle Menüelemente im Menü enthalten, aber nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="54ef0-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="54ef0-109">Ebenso Deaktivieren eines Menüelements, das über Untermenüelemente verfügt die Untermenüelemente ausgeblendet, aber nicht deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="54ef0-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="54ef0-110">Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, gilt die guten Programmierstil, ausgeblendet und deaktiviert das gesamte Menü, wie dies führt zu eine sauberen-Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="54ef0-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="54ef0-111">Sie sollten ausblenden und deaktivieren das Menü und jedes Element und ein Untermenüelement, das Sie im Menü deaktiviert werden, da der Zugriff auf einen Menübefehl über eine Tastenkombination ausblenden allein nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="54ef0-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="54ef0-112">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft eines Elements zum Menü der obersten Ebene `false` das gesamte Menü ausblenden.</span><span class="sxs-lookup"><span data-stu-id="54ef0-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ef0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54ef0-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="54ef0-114">Vorgehensweise: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="54ef0-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="54ef0-115">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="54ef0-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
