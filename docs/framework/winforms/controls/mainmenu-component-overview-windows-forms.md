---
title: Übersicht über die MainMenu-Komponente
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745118"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="da0c6-102">Übersicht über die MainMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="da0c6-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="da0c6-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> die-<xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu>-Steuerelemente früherer Versionen ersetzen und Funktionen hinzufügen, werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="da0c6-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="da0c6-104">Die Windows Forms <xref:System.Windows.Forms.MainMenu> Komponente zeigt ein Menü zur Laufzeit an.</span><span class="sxs-lookup"><span data-stu-id="da0c6-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="da0c6-105">Alle Untermenüs des Hauptmenüs und der einzelnen Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="da0c6-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="da0c6-106">Schlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="da0c6-106">Key Properties</span></span>  
 <span data-ttu-id="da0c6-107">Ein Menü Element kann als Standardelement festgelegt werden, indem die <xref:System.Windows.Forms.MenuItem.DefaultItem%2A>-Eigenschaft auf `true`festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="da0c6-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="da0c6-108">Das Standardelement wird in fettem Text angezeigt, wenn auf das Menü geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="da0c6-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="da0c6-109">Die <xref:System.Windows.Forms.MenuItem.Checked%2A>-Eigenschaft des Menü Elements ist entweder `true` oder `false`und gibt an, ob das Menü Element ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="da0c6-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="da0c6-110">Die <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>-Eigenschaft des Menü Elements passt die Darstellung des ausgewählten Elements an: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf `true`festgelegt ist, wird neben dem Element ein Optionsfeld angezeigt. Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf `false`festgelegt ist, wird neben dem Element ein Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da0c6-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da0c6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da0c6-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="da0c6-112">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="da0c6-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
