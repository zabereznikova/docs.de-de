---
title: 'Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966615"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="8e97b-102">Vorgehensweise: Ausblenden von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="8e97b-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="8e97b-103">Das Ausblenden von Menü Elementen ist eine Möglichkeit, die Benutzeroberfläche (UI) Ihrer Anwendung zu steuern und Benutzer Befehle einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="8e97b-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="8e97b-104">Häufig ist es ratsam, ein gesamtes Menü auszublenden, wenn alle Menü Elemente darin nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8e97b-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="8e97b-105">Dies stellt weniger Ablenkungen für den Benutzer dar.</span><span class="sxs-lookup"><span data-stu-id="8e97b-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="8e97b-106">Außerdem empfiehlt es sich, das Menü oder das Menü Element auszublenden und zu deaktivieren, da durch das Ausblenden allein nicht verhindert wird, dass der Benutzer über eine Tastenkombination auf einen Menübefehl zugreift.</span><span class="sxs-lookup"><span data-stu-id="8e97b-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="8e97b-107">Weitere Informationen zum Deaktivieren von Menü Elementen finden [Sie unter Gewusst wie: Deaktivieren Sie ToolStripMenuItems mithilfe des](how-to-disable-toolstripmenuitems-using-the-designer.md)Designers.</span><span class="sxs-lookup"><span data-stu-id="8e97b-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="8e97b-108">So blenden Sie ein Menü der obersten Ebene und seine unter Menü Elemente aus</span><span class="sxs-lookup"><span data-stu-id="8e97b-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="8e97b-109">Wählen Sie das Menü Element der obersten Ebene aus, <xref:System.Windows.Forms.ToolStripItem.Visible%2A> und <xref:System.Windows.Forms.ToolStripItem.Available%2A> legen Sie `false`die-oder-Eigenschaft auf fest</span><span class="sxs-lookup"><span data-stu-id="8e97b-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="8e97b-110">Wenn Sie das Menü Element der obersten Ebene ausblenden, werden alle Menü Elemente in diesem Menü ebenfalls ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="8e97b-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="8e97b-111">Wenn Sie auf eine andere Stelle als auf <xref:System.Windows.Forms.MenuStrip> der nach <xref:System.Windows.Forms.ToolStripItem.Visible%2A> - `false`Einstellung auf klicken, werden das gesamte Menü Element der obersten Ebene und seine unter Menü Elemente aus dem Formular entfernt, sodass Sie die Lauf Zeit Wirkung ihrer Aktion angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8e97b-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="8e97b-112">Um das ausgeblendete Menü Element der obersten Ebene zur Entwurfszeit anzuzeigen, <xref:System.Windows.Forms.MenuStrip> klicken Sie in der **Komponenten Leiste**, in der **Dokument**Gliederung oder am oberen Rand des Eigenschaften Rasters auf das.</span><span class="sxs-lookup"><span data-stu-id="8e97b-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
> <span data-ttu-id="8e97b-113">Sie werden in einem Zusammenführungs Szenario selten ein gesamtes Menü mit Ausnahme von untergeordneten MDI-Menüs (Multiple Document Interface) ausblenden.</span><span class="sxs-lookup"><span data-stu-id="8e97b-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="8e97b-114">So blenden Sie ein unter Menü Element aus</span><span class="sxs-lookup"><span data-stu-id="8e97b-114">To hide a submenu item</span></span>

1. <span data-ttu-id="8e97b-115">Wählen Sie das unter Menü Element, und <xref:System.Windows.Forms.ToolStripItem.Visible%2A> legen Sie `false`dessen-Eigenschaft auf fest.</span><span class="sxs-lookup"><span data-stu-id="8e97b-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="8e97b-116">Wenn Sie ein unter Menü Element ausblenden, bleibt es zur Entwurfszeit auf dem Formular sichtbar, sodass Sie es für weitere Aufgaben problemlos auswählen können.</span><span class="sxs-lookup"><span data-stu-id="8e97b-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="8e97b-117">Sie wird zur Laufzeit ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="8e97b-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e97b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e97b-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="8e97b-119">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8e97b-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="8e97b-120">Vorgehensweise: Deaktivieren von ToolStripMenuItems mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="8e97b-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
