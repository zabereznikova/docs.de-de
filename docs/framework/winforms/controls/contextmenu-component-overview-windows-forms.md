---
title: "Übersicht über die ContextMenu-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6c2542ca7ee27bec96bb5010bcdb2fcd7416f72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="d7024-102">Übersicht über die ContextMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d7024-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="d7024-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzt und funktionell die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente von früheren Versionen <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> für Abwärtskompatibilität und für zukünftige Verwendung beibehalten werden, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="d7024-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="d7024-104">Mit dem Windows Forms <xref:System.Windows.Forms.ContextMenu> Komponente, können Sie Benutzer bereitstellen, ein leicht zugänglichen Kontextmenü mit häufig verwendeten Befehlen, die dem ausgewählten Objekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d7024-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="d7024-105">Die Elemente in einem Kontextmenü sind häufig eine Teilmenge der Elemente aus den Hauptmenüs, die an anderer Stelle in der Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d7024-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="d7024-106">Benutzer kann ein Kontextmenü mit der rechten Maustaste des Mauszeiger in der Regel zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d7024-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="d7024-107">In Windows Forms sind Kontextmenüs Steuerelementen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d7024-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="d7024-108">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d7024-108">Key Properties</span></span>  
 <span data-ttu-id="d7024-109">Sie können ein Kontextmenü mit einem Steuerelement zuordnen, indem Sie des Steuerelements <xref:System.Windows.Forms.Control.ContextMenu%2A> Eigenschaft, um die <xref:System.Windows.Forms.ContextMenu> Komponente.</span><span class="sxs-lookup"><span data-stu-id="d7024-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="d7024-110">Ein einzelnes Kontextmenü kann mehreren Steuerelementen zugeordnet werden, aber jedes Steuerelement nur ein Kontextmenü haben kann.</span><span class="sxs-lookup"><span data-stu-id="d7024-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="d7024-111">Die wichtigste Eigenschaft die <xref:System.Windows.Forms.ContextMenu> Komponente ist die <xref:System.Windows.Forms.Menu.MenuItems%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d7024-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="d7024-112">Sie können Menüelemente hinzufügen, indem Sie programmgesteuert erstellen <xref:System.Windows.Forms.MenuItem> -Objekte und durch Hinzufügen, damit die <xref:System.Windows.Forms.Menu.MenuItemCollection> des Kontextmenüs.</span><span class="sxs-lookup"><span data-stu-id="d7024-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="d7024-113">Da die Elemente in einem Kontextmenü in der Regel aus anderen Menüs gezeichnet werden, werden Sie am häufigsten Elemente ein Kontextmenü hinzugefügt durch Kopieren.</span><span class="sxs-lookup"><span data-stu-id="d7024-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7024-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7024-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
