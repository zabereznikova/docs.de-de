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
ms.openlocfilehash: 2203511e91254c270c59b5d298dd87a5b3737109
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308355"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="1e9a3-102">Vorgehensweise: Verschieben von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="1e9a3-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="1e9a3-103">Zur Entwurfszeit Sie ganze Menüs der obersten Ebene und ihre Menüelemente an eine andere Stelle auf Verschieben der <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="1e9a3-104">Sie können auch einzelne Menüelemente zwischen Menüs der obersten Ebene verschieben oder Ändern der Position der Menüelemente in einem Menü.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e9a3-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1e9a3-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1e9a3-107">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1e9a3-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="1e9a3-108">Um ein Menü der obersten Ebene und den Menüelementen auf oberster Ebene verschieben</span><span class="sxs-lookup"><span data-stu-id="1e9a3-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1. <span data-ttu-id="1e9a3-109">Klicken Sie auf, und halten Sie die linke Maustaste auf das Menü, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2. <span data-ttu-id="1e9a3-110">Ziehen Sie die Einfügemarke auf das Menü der obersten Ebene, die vor der beabsichtigten neuen Position befindet, und lassen Sie die linke Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="1e9a3-111">Das ausgewählte Menü wird rechts neben der Einfügemarke verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="1e9a3-112">Ein Menü der obersten Ebene und seine Menüelemente an eine Dropdown-Speicherort zu verschieben</span><span class="sxs-lookup"><span data-stu-id="1e9a3-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1. <span data-ttu-id="1e9a3-113">Klicken Sie auf das Menü, das Sie verwenden möchten, verschieben, und drücken STRG + X, und mit der rechten Maustaste im Menüs, und wählen Sie **Ausschneiden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="1e9a3-114">Klicken Sie im Menü der obersten Ebene Ziel einen Menüpunkt oberhalb der beabsichtigten neuen Position und drücken Sie STRG + V, oder mit der rechten Maustaste in des Menüelements oberhalb der beabsichtigten neuen Position und wählen Sie **einfügen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="1e9a3-115">Das Menü, das Sie Ausschneiden wird nach dem das ausgewählte Menüelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="1e9a3-116">Verschieben Sie ein Menüelement innerhalb eines Menüs mit dem Elementauflistungs-Editor</span><span class="sxs-lookup"><span data-stu-id="1e9a3-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1. <span data-ttu-id="1e9a3-117">Mit der rechten Maustaste in des Menüs, das das Menüelement enthält, die, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2. <span data-ttu-id="1e9a3-118">Wählen Sie im Kontextmenü den Befehl **DropDownItems bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3. <span data-ttu-id="1e9a3-119">In der **-Elementauflistungs-Editor**, klicken Sie auf das Menüelement, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4. <span data-ttu-id="1e9a3-120">Klicken Sie auf die Pfeiltasten oben und nach unten, um das Menüelement im Menü zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5. <span data-ttu-id="1e9a3-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="1e9a3-122">Um ein Menüelement in einem Menü mit der Tastatur zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-122">To move a menu item within a menu using the keyboard</span></span>  
  
1. <span data-ttu-id="1e9a3-123">Drücken Sie die EINGABETASTE, und halten Sie die ALT-Taste.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-123">Press and hold down the ALT key.</span></span>  
  
2. <span data-ttu-id="1e9a3-124">Klicken Sie auf, und halten der linken Maustaste auf das Menüelement, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3. <span data-ttu-id="1e9a3-125">Ziehen Sie das Menüelement an den neuen Speicherort aus, und lassen Sie die linke Maustaste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="1e9a3-126">So verschieben ein Menüelement zu einer anderen Menüressource</span><span class="sxs-lookup"><span data-stu-id="1e9a3-126">To move a menu item to another menu</span></span>  
  
1. <span data-ttu-id="1e9a3-127">Klicken Sie auf das Menüelement, das Sie verwenden möchten, verschieben, und drücken STRG + X, oder mit der rechten Maustaste in des Menüelements, und wählen **Ausschneiden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="1e9a3-128">Klicken Sie auf das Menü, das das Menüelement enthält, das für Sie gelten.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3. <span data-ttu-id="1e9a3-129">Klicken Sie auf das Menüelement, das vor der beabsichtigten neuen Position befindet, und drücken Sie STRG + V, oder mit der rechten Maustaste in des Menüelements, das vor der beabsichtigten neuen Position, und wählen **einfügen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="1e9a3-130">Dem Menüelement, das das ausgeschnittene wird nach dem das ausgewählte Menüelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="1e9a3-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9a3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e9a3-131">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="1e9a3-132">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1e9a3-132">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
