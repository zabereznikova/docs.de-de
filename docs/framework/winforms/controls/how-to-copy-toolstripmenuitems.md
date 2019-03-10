---
title: 'Vorgehensweise: Kopieren von ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
ms.openlocfilehash: 18077f542b1b49f8e81e68fc1e7a5d3e1e417a21
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713877"
---
# <a name="how-to-copy-toolstripmenuitems"></a><span data-ttu-id="608cb-102">Vorgehensweise: Kopieren von ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="608cb-102">How to: Copy ToolStripMenuItems</span></span>
<span data-ttu-id="608cb-103">Zur Entwurfszeit können Sie ganze Menüs der obersten Ebene und ihre Untermenüelemente an eine andere Stelle auf dem <xref:System.Windows.Forms.MenuStrip>kopieren.</span><span class="sxs-lookup"><span data-stu-id="608cb-103">At design time, you can copy entire top-level menus and their submenu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="608cb-104">Die können auch einzelne Menüelemente zwischen Menüs der obersten Ebene kopieren oder die Position von Menüelementen innerhalb eines Menüs ändern.</span><span class="sxs-lookup"><span data-stu-id="608cb-104">You can also copy individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a><span data-ttu-id="608cb-105">So kopieren Sie ein Menü der obersten Ebene und seine Untermenüelemente an eine andere Position der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="608cb-105">To copy a top-level menu and its submenu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="608cb-106">Klicken Sie mit der linken Maustaste auf das Menü, das Sie kopieren möchten, und drücken Sie STRG+C, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Kopieren** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="608cb-106">Left-click the menu that you want to copy and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="608cb-107">Klicken Sie mit der linken Maustaste auf das Menü der obersten Ebene, das sich hinter der beabsichtigten neuen Position befindet, und drücken Sie STRG+V, oder klicken Sie mit der rechten Maustaste auf das Menüelement der obersten Ebene, das sich vor der beabsichtigten neuen Position befindet, und wählen Sie **Einfügen** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="608cb-107">Left-click the top-level menu that is after the intended new location and press CTRL+V, or right-click the top-level menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="608cb-108">Das kopierte Menü wird vor dem ausgewählten Menü der obersten Ebene eingefügt.</span><span class="sxs-lookup"><span data-stu-id="608cb-108">The menu that you copied is inserted before the selected top-level menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a><span data-ttu-id="608cb-109">So kopieren Sie ein Menü der obersten Ebene und seine Untermenüelemente an einen Ablageort</span><span class="sxs-lookup"><span data-stu-id="608cb-109">To copy a top-level menu and its submenu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="608cb-110">Klicken Sie mit der linken Maustaste auf das Menü, das Sie verschieben möchten, und drücken Sie STRG+C, oder klicken Sie mit der rechten Maustaste, und wählen Sie **Kopieren** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="608cb-110">Left-click the menu that you want to move and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="608cb-111">Klicken Sie im Zielmenü der obersten Ebene mit der linken Maustaste auf das Untermenüelement, das sich oberhalb der beabsichtigten neuen Position befindet, und drücken Sie STRG+V, oder klicken Sie mit der rechten Maustaste auf das Untermenüelement, das sich oberhalb der beabsichtigten neuen Position befindet,und wählen Sie aus dem Kontextmenü **Einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="608cb-111">In the destination top-level menu, left-click the submenu item that is above the intended new location and press CTRL+V, or right-click the submenu item that is above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="608cb-112">Das kopierte Menü wird vor dem ausgewählten Untermenüelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="608cb-112">The menu that you copied is inserted before the selected submenu item.</span></span>  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a><span data-ttu-id="608cb-113">So kopieren Sie ein Untermenüelement in ein anderes Menü</span><span class="sxs-lookup"><span data-stu-id="608cb-113">To copy a submenu item to another menu</span></span>  
  
1.  <span data-ttu-id="608cb-114">Klicken Sie mit der linken Maustaste auf das Untermenüelement, das Sie kopieren möchten, und drücken Sie STRG+C, oder klicken Sie mit der rechten Maustaste auf das Untermenüelement, und wählen Sie **Kopieren** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="608cb-114">Left-click the submenu item that you want to copy and press CTRL+C, or right-click the submenu item and choose **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="608cb-115">Klicken Sie mit der linken Maustaste auf das Menü, das das ausgeschnittene Untermenüelement aufnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="608cb-115">Left-click the menu that will contain the submenu item that you cut.</span></span>  
  
3.  <span data-ttu-id="608cb-116">Klicken Sie mit der linken Maustaste auf das Untermenüelement, das sich vor der beabsichtigten neuen Position befindet, und drücken Sie STRG+V, oder klicken Sie mit der rechten Maustaste auf das Untermenüelement, das sich vor der beabsichtigten neuen Position befindet, und wählen Sie **Einfügen** aus dem Kontextmenü aus.</span><span class="sxs-lookup"><span data-stu-id="608cb-116">Left-click the submenu item that is before the intended new location and press CTRL+V, or right-click the submenu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="608cb-117">Das kopierte Untermenüelement wird vor dem ausgewählten Untermenüelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="608cb-117">The submenu item that you copied is inserted before the selected submenu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608cb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="608cb-118">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="608cb-119">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="608cb-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
