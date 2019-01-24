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
ms.openlocfilehash: 529b57ed443791b87331358a7e6c420dd63933a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700623"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="c9cb2-102">Übersicht über die MainMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c9cb2-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="c9cb2-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="c9cb2-104">Die Windows-Formulare <xref:System.Windows.Forms.MainMenu> Komponente wird ein Menü zur Laufzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="c9cb2-105">Alle Untermenüs des Hauptmenüs und einzelne Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="c9cb2-106">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c9cb2-106">Key Properties</span></span>  
 <span data-ttu-id="c9cb2-107">Ein Menüelement kann als das Standardelement gekennzeichnet werden, durch Festlegen der <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="c9cb2-108">Das Standardelement in Fettdruck angezeigt wird, wenn Sie im Menü geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="c9cb2-109">Des Menüelements <xref:System.Windows.Forms.MenuItem.Checked%2A> Eigenschaft `true` oder `false`, und gibt an, ob das Menüelement ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="c9cb2-110">Des Menüelements <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Eigenschaft passt die Anzeige des ausgewählten Elements: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> nastaven NA hodnotu `true`, ein Optionsfeld wird neben dem Element; angezeigt, wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> nastaven NA hodnotu `false`, ein Häkchen neben dem Element angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c9cb2-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9cb2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9cb2-111">See also</span></span>
- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="c9cb2-112">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c9cb2-112">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
