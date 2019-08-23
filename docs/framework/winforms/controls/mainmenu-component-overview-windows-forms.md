---
title: Übersicht über die MainMenu-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952131"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="d781e-102">Übersicht über die MainMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d781e-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="d781e-103">Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die-und- <xref:System.Windows.Forms.ContextMenu> Steuerelemente früherer Versionen ersetzen und Funktionen hinzu <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> , werden Sie sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="d781e-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="d781e-104">Die Windows Forms <xref:System.Windows.Forms.MainMenu> Komponente zeigt ein Menü zur Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="d781e-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="d781e-105">Alle Untermenüs des Hauptmenüs und der einzelnen Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="d781e-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="d781e-106">Schlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="d781e-106">Key Properties</span></span>  
 <span data-ttu-id="d781e-107">Ein Menü Element kann als Standardelement festgelegt werden, indem die <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> -Eigenschaft `true`auf festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d781e-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="d781e-108">Das Standardelement wird in fettem Text angezeigt, wenn auf das Menü geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="d781e-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="d781e-109">Die- <xref:System.Windows.Forms.MenuItem.Checked%2A> Eigenschaft des Menü Elements ist `true` entweder `false`oder und gibt an, ob das Menü Element ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d781e-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="d781e-110"><xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Die-Eigenschaft des Menü Elements passt die Darstellung des ausgewählten Elements an: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf `true`festgelegt ist, wird neben dem Element ein Optionsfeld angezeigt. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> wenn auf `false`festgelegt ist, wird neben dem Element ein Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d781e-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d781e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d781e-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="d781e-112">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d781e-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
