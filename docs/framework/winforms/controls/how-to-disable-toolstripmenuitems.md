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
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046228"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="74129-102">Vorgehensweise: Deaktivieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="74129-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="74129-103">Sie können die Befehle, die ein Benutzer durchführen kann, einschränken oder erweitern, indem Sie Menü Elemente als Reaktion auf Benutzeraktivitäten aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="74129-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="74129-104">Menü Elemente werden standardmäßig aktiviert, wenn Sie erstellt werden, aber dies kann über die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> -Eigenschaft angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="74129-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="74129-105">Sie können diese Eigenschaft zur Entwurfszeit im **Eigenschaften** Fenster oder Programm gesteuert bearbeiten, indem Sie Sie im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="74129-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="74129-106">So deaktivieren Sie ein Menü Element Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="74129-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="74129-107">Fügen Sie innerhalb der Methode, in der Sie die Eigenschaften des Menü Elements festgelegt haben, <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Code hinzu `false`, um die-Eigenschaft auf festzulegen.</span><span class="sxs-lookup"><span data-stu-id="74129-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    > <span data-ttu-id="74129-108">Wenn Sie das erste Menü Element der obersten Ebene in einem Menü deaktivieren, werden alle im Menü enthaltenen Menü Elemente ausgeblendet, nicht jedoch deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="74129-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="74129-109">Ebenso werden bei der Deaktivierung eines Menü Elements, das unter Menü Elemente enthält, die unter Menü Elemente ausgeblendet, aber nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="74129-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="74129-110">Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, wird als bewährte Programmier Übung empfohlen, das gesamte Menü auszublenden und zu deaktivieren, da dadurch eine saubere Benutzeroberfläche dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="74129-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="74129-111">Sie sollten das Menü ausblenden und deaktivieren und jedes Element und unter Menü Element im Menü deaktivieren, da durch das Ausblenden allein der Zugriff auf einen Menübefehl über eine Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="74129-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="74129-112">Legen Sie <xref:System.Windows.Forms.ToolStripItem.Visible%2A> die-Eigenschaft eines Menü Elements der obersten Ebene `false` auf fest, um das gesamte Menü auszublenden.</span><span class="sxs-lookup"><span data-stu-id="74129-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74129-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74129-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="74129-114">Vorgehensweise: ToolStripMenuItems ausblenden</span><span class="sxs-lookup"><span data-stu-id="74129-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="74129-115">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="74129-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
