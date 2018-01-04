---
title: "Übersicht über die MainMenu-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8681635f2f97e74893704513f57313106168e52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="bab04-102">Übersicht über die MainMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bab04-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="bab04-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzt und funktionell die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente von früheren Versionen <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> für Abwärtskompatibilität und für zukünftige Verwendung beibehalten werden, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="bab04-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="bab04-104">Windows Forms <xref:System.Windows.Forms.MainMenu> Komponente wird ein Menü angezeigt, zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="bab04-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="bab04-105">Alle Untermenüs des Hauptmenüs und einzelne Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="bab04-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="bab04-106">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bab04-106">Key Properties</span></span>  
 <span data-ttu-id="bab04-107">Ein Menüelement kann als das Standardelement gekennzeichnet werden, durch Festlegen der <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="bab04-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="bab04-108">Das Standardelement wird in Fettschrift angezeigt, wenn das Menü geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="bab04-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="bab04-109">Des Menüelements <xref:System.Windows.Forms.MenuItem.Checked%2A> Eigenschaft `true` oder `false`, und gibt an, ob das Menüelement aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bab04-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="bab04-110">Des Menüelements <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Eigenschaft passt die Anzeige des ausgewählten Elements: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> festgelegt ist, um `true`, ein Optionsfeld wird neben dem Element angezeigt, wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf festgelegt ist `false`, ein Häkchen neben dem Element angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bab04-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab04-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bab04-111">See Also</span></span>  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="bab04-112">Übersicht über das MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="bab04-112">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
