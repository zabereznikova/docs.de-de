---
title: 'Gewusst wie: Deaktivieren von ToolStripMenuItems'
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
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0432c59979f8f595b481154f5b339e448ee66b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="c3530-102">Gewusst wie: Deaktivieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="c3530-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="c3530-103">Sie können begrenzen oder erweitern die Befehle, die ein Benutzer durch das Aktivieren und Deaktivieren von Menüelementen in Reaktion auf Benutzeraktivitäten treffen.</span><span class="sxs-lookup"><span data-stu-id="c3530-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="c3530-104">Menüelemente sind standardmäßig aktiviert, wenn sie erstellt werden, aber dies die angepasst werden kann, durch die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c3530-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="c3530-105">Sie können diese Eigenschaft zur Entwurfszeit im Bearbeiten der **Eigenschaften** Fenster oder programmgesteuert im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="c3530-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="c3530-106">So deaktivieren Sie ein Menüelement programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="c3530-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="c3530-107">Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft `false`.</span><span class="sxs-lookup"><span data-stu-id="c3530-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="c3530-108">Deaktivieren das erste oder der obersten Ebene Menüelement in einem Menü Blendet alle Menüelemente im Menü, jedoch nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c3530-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="c3530-109">Ebenso Deaktivieren eines Menüelements, das Untermenüelemente verfügt die Untermenüelemente ausgeblendet, aber nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c3530-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="c3530-110">Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, gilt die guten Programmierstil, ausgeblendet und deaktiviert das gesamte Menü, wie dies eine saubere Benutzeroberfläche dar.</span><span class="sxs-lookup"><span data-stu-id="c3530-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="c3530-111">Sie sollten ausblenden und deaktivieren das Menü und jedes Element und Untermenüelement im Menü, deaktiviert werden, weil der Zugriff auf einen Menübefehl über eine Tastenkombination zum Ausblenden von alleine nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="c3530-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="c3530-112">Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft für ein Menüelement der obersten Ebene auf `false` das gesamte Menü ausblenden.</span><span class="sxs-lookup"><span data-stu-id="c3530-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3530-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3530-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="c3530-114">Gewusst wie: Ausblenden von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="c3530-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="c3530-115">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c3530-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
