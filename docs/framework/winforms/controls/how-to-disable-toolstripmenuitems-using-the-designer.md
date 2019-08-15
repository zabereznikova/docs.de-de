---
title: 'Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: fd80a6543c83ae957cd9c51b068d0702559f0925
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040267"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="f5481-102">Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f5481-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="f5481-103">Sie können die Befehle, die ein Benutzer durchführen kann, einschränken oder erweitern, indem Sie Menü Elemente als Reaktion auf Benutzeraktivitäten aktivieren und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5481-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="f5481-104">Menü Elemente werden standardmäßig aktiviert, wenn Sie erstellt werden, aber dies kann über die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> -Eigenschaft angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="f5481-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="f5481-105">Sie können diese Eigenschaft zur Entwurfszeit im **Eigenschaften** Fenster oder Programm gesteuert bearbeiten, indem Sie Sie im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="f5481-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="f5481-106">Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren Sie ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="f5481-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="f5481-107">So deaktivieren Sie ein Menü Element zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="f5481-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="f5481-108">Wenn das Menü Element im Formular ausgewählt ist, legen Sie <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> die- `false`Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="f5481-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    >  <span data-ttu-id="f5481-109">Wenn Sie das erste Menü Element der obersten Ebene in einem Menü deaktivieren, werden alle im Menü enthaltenen Menü Elemente deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5481-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="f5481-110">Ebenso werden die unter Menü Elemente deaktiviert, wenn ein Menü Element mit unter Menü Elementen deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="f5481-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="f5481-111">Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, wird als bewährte Programmier Übung empfohlen, das gesamte Menü auszublenden und zu deaktivieren, da dadurch eine saubere Benutzeroberfläche dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5481-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="f5481-112">Sie sollten das Menü ausblenden und deaktivieren, da durch das Ausblenden allein der Zugriff auf einen Menübefehl über eine Tastenkombination nicht verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="f5481-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="f5481-113">Legen Sie <xref:System.Windows.Forms.ToolStripItem.Visible%2A> die-Eigenschaft eines Menü Elements der obersten Ebene `false` auf fest, um das gesamte Menü auszublenden.</span><span class="sxs-lookup"><span data-stu-id="f5481-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5481-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5481-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="f5481-115">Vorgehensweise: ToolStripMenuItems ausblenden</span><span class="sxs-lookup"><span data-stu-id="f5481-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="f5481-116">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f5481-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
