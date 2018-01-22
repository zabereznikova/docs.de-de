---
title: 'Gewusst wie: Verschieben von ToolStripMenuItems'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ffef860118ba20508bba037910d85866055c898
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="0d5d8-102">Gewusst wie: Verschieben von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="0d5d8-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="0d5d8-103">Zur Entwurfszeit können Sie wechseln ganze Menüs der obersten Ebene und ihre Menüelemente an eine andere Stelle der <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="0d5d8-104">Sie können auch einzelne Menüelemente zwischen Menüs der obersten Ebene verschieben oder Ändern der Position von Menüelementen in einem Menü.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d5d8-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0d5d8-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0d5d8-107">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0d5d8-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="0d5d8-108">Um ein Menü der obersten Ebene und seine Menüelemente der obersten Ebene verschieben</span><span class="sxs-lookup"><span data-stu-id="0d5d8-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="0d5d8-109">Klicken Sie auf, und halten Sie die linke Maustaste auf das Menü, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2.  <span data-ttu-id="0d5d8-110">Ziehen Sie die Einfügemarke auf das Menü der obersten Ebene, das vor der beabsichtigten neuen Position befindet, und lassen Sie die linke Maustaste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="0d5d8-111">Das ausgewählte Menü wird rechts neben der Einfügemarke verschoben.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="0d5d8-112">So verschieben Sie ein Menü der obersten Ebene und seine Menüelemente an einen Ablageort</span><span class="sxs-lookup"><span data-stu-id="0d5d8-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="0d5d8-113">Klicken Sie auf das Menü, das Sie verwenden möchten, verschieben und drücken STRG + X, oder das Kontextmenü und wählen Sie **Ausschneiden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="0d5d8-114">Klicken Sie im Menü der obersten Ebene Ziel klicken Sie auf das Menüelement oberhalb der beabsichtigten neuen Position und drücken Sie STRG + V, oder mit der rechten Maustaste des Menüelements oberhalb der beabsichtigten neuen Position und wählen Sie **einfügen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="0d5d8-115">Das Menü, das Sie Ausschneiden wird nach der ausgewählten Menüelements eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="0d5d8-116">So verschieben Sie ein Menüelement innerhalb eines Menüs mit der Elementauflistungs-Editor</span><span class="sxs-lookup"><span data-stu-id="0d5d8-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1.  <span data-ttu-id="0d5d8-117">Mit der rechten Maustaste in des Menüs, das das Menüelement enthält, die, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2.  <span data-ttu-id="0d5d8-118">Wählen Sie im Kontextmenü **DropDownItems bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3.  <span data-ttu-id="0d5d8-119">In der **-Elementauflistungs-Editor**, klicken Sie auf das Menüelement, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4.  <span data-ttu-id="0d5d8-120">Klicken Sie auf die Pfeiltasten oben und nach unten, um das Menüelement im Menü zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5.  <span data-ttu-id="0d5d8-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="0d5d8-122">So verschieben Sie ein Menüelement in einem Menü mithilfe der Tastatur</span><span class="sxs-lookup"><span data-stu-id="0d5d8-122">To move a menu item within a menu using the keyboard</span></span>  
  
1.  <span data-ttu-id="0d5d8-123">Halten Sie die ALT-Taste.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-123">Press and hold down the ALT key.</span></span>  
  
2.  <span data-ttu-id="0d5d8-124">Klicken Sie auf, und halten Sie die linke Maustaste gedrückt, auf das Menüelement, das Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3.  <span data-ttu-id="0d5d8-125">Ziehen Sie das Menüelement an den neuen Speicherort ein, und lassen Sie die linke Maustaste gedrückt.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="0d5d8-126">So verschieben Sie ein Menüelement in ein anderes Menü</span><span class="sxs-lookup"><span data-stu-id="0d5d8-126">To move a menu item to another menu</span></span>  
  
1.  <span data-ttu-id="0d5d8-127">Klicken Sie auf das Menüelement, das Sie verschieben möchten und drücken STRG + X, oder mit der rechten Maustaste des Menüelements und wählen **Ausschneiden** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="0d5d8-128">Klicken Sie auf das Menü, das das Menüelement enthält, das Sie ausgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3.  <span data-ttu-id="0d5d8-129">Klicken Sie auf das Menüelement, das vor der beabsichtigten neuen Position befindet, und drücken Sie STRG + V, oder mit der rechten Maustaste des Menüelements, das vor der beabsichtigten neuen Position und wählen **einfügen** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="0d5d8-130">Das Menüelement, das Sie Ausschneiden wird nach dem ausgewählten Menüelements eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0d5d8-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5d8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d5d8-131">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="0d5d8-132">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0d5d8-132">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
