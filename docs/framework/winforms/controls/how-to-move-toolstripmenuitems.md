---
title: 'Vorgehensweise: Verschieben von ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039796"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="2e7db-102">Vorgehensweise: Verschieben von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="2e7db-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="2e7db-103">Zur Entwurfszeit können Sie ganze Menüs der obersten Ebene und ihre Menü Elemente an eine andere Stelle auf dem <xref:System.Windows.Forms.MenuStrip>verschieben.</span><span class="sxs-lookup"><span data-stu-id="2e7db-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="2e7db-104">Sie können auch einzelne Menü Elemente zwischen Menüs der obersten Ebene verschieben oder die Position von Menü Elementen innerhalb eines Menüs ändern.</span><span class="sxs-lookup"><span data-stu-id="2e7db-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="2e7db-105">So verschieben Sie ein Menü der obersten Ebene und die zugehörigen Menü Elemente an eine andere Position der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="2e7db-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="2e7db-106">Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="2e7db-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="2e7db-107">Ziehen Sie die Einfügemarke in das Menü der obersten Ebene, das sich vor der beabsichtigten neuen Position befindet, und lassen Sie die linke Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="2e7db-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="2e7db-108">Das ausgewählte Menü wechselt nach rechts von der Einfügemarke.</span><span class="sxs-lookup"><span data-stu-id="2e7db-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="2e7db-109">So verschieben Sie ein Menü der obersten Ebene und die zugehörigen Menü Elemente an eine Dropdown-Position</span><span class="sxs-lookup"><span data-stu-id="2e7db-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="2e7db-110">Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten, und drücken Sie STRG + X, oder klicken Sie mit der rechten Maustaste auf das Menü, und wählen Sie aus dem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="2e7db-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="2e7db-111">Klicken Sie im Menü der obersten Ebene des Ziels mit der linken Maustaste auf das Menü Element oberhalb der vorgesehenen neuen Position, und drücken Sie STRG + V, oder klicken Sie mit der rechten Maustaste auf das Menü Element oberhalb der vorgesehenen neuen Position, und wählen Sie aus dem Kontextmenü **Einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2e7db-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="2e7db-112">Das Menü, das Sie Ausschneiden, wird nach dem ausgewählten Menü Element eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2e7db-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="2e7db-113">So verschieben Sie ein Menü Element in einem Menü mithilfe des Items-Auflistungs-Editors</span><span class="sxs-lookup"><span data-stu-id="2e7db-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="2e7db-114">Klicken Sie mit der rechten Maustaste auf das Menü, das das Menü Element enthält, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="2e7db-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="2e7db-115">Wählen Sie im Kontextmenü die Option **DropDownItems bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="2e7db-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="2e7db-116">Klicken Sie im Elementauflistungs- **Editor**mit der linken Maustaste auf das Menü Element, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="2e7db-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="2e7db-117">Klicken Sie auf die Pfeiltasten nach oben und nach unten, um das Menü Element im Menü zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="2e7db-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="2e7db-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2e7db-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="2e7db-119">So verschieben Sie ein Menü Element in einem Menü mithilfe der Tastatur</span><span class="sxs-lookup"><span data-stu-id="2e7db-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="2e7db-120">Halten Sie die Alt-Taste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="2e7db-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="2e7db-121">Klicken Sie mit der linken Maustaste auf das Menü Element, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="2e7db-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="2e7db-122">Ziehen Sie das Menü Element an die neue Stelle, und lassen Sie die linke Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="2e7db-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="2e7db-123">So verschieben Sie ein Menü Element in ein anderes Menü</span><span class="sxs-lookup"><span data-stu-id="2e7db-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="2e7db-124">Klicken Sie mit der linken Maustaste auf das Menü Element, das Sie verschieben möchten, und drücken Sie STRG + X, oder klicken Sie mit der rechten Maustaste auf das Menü Element, und wählen Sie aus dem Kontextmenü aus</span><span class="sxs-lookup"><span data-stu-id="2e7db-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="2e7db-125">Klicken Sie mit der linken Maustaste auf das Menü, das das von Ihnen ausgeschnittene Menü Element enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="2e7db-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="2e7db-126">Klicken Sie mit der linken Maustaste auf das Menü Element, das sich vor der beabsichtigten neuen Position befindet, und drücken Sie STRG + V, oder klicken Sie mit der rechten Maustaste auf das Menü Element vor der vorgesehenen neuen Position, und wählen Sie aus dem Kontextmenü **Einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2e7db-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="2e7db-127">Das Menü Element, das Sie Ausschneiden, wird nach dem ausgewählten Menü Element eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2e7db-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e7db-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e7db-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="2e7db-129">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2e7db-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
