---
title: Übersicht über die ContextMenu-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 2acbcc9197a630a993471c22e572a4f3ed682c64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975142"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="6b901-102">Übersicht über die ContextMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6b901-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="6b901-103">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="6b901-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="6b901-104">Mit der Windows Forms <xref:System.Windows.Forms.ContextMenu> Komponente Sie bereitstellen, Benutzern ein leicht zugängliches Kontextmenü mit häufig verwendeten Befehlen, die dem ausgewählten Objekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6b901-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="6b901-105">Die Elemente in einem Kontextmenü sind häufig eine Teilmenge der Elemente aus den Hauptmenüs, die an anderer Stelle in der Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6b901-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="6b901-106">Ein Benutzer kann ein Kontextmenü mit der rechten Maustaste in der Maustaste in der Regel zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6b901-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="6b901-107">In Windows Forms sind die Kontextmenüs Steuerelementen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6b901-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="6b901-108">Schlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="6b901-108">Key Properties</span></span>  
 <span data-ttu-id="6b901-109">Sie können ein Kontextmenü mit einem Steuerelement zuordnen, durch Festlegen des Steuerelements <xref:System.Windows.Forms.Control.ContextMenu%2A> Eigenschaft, um die <xref:System.Windows.Forms.ContextMenu> Komponente.</span><span class="sxs-lookup"><span data-stu-id="6b901-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="6b901-110">Ein Kontextmenü für die einzelnen kann mit mehreren Steuerelementen verbunden werden, aber jedes Steuerelement kann nur ein Kontextmenü haben.</span><span class="sxs-lookup"><span data-stu-id="6b901-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="6b901-111">Die wichtigste Eigenschaft die <xref:System.Windows.Forms.ContextMenu> Komponente ist die <xref:System.Windows.Forms.Menu.MenuItems%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6b901-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="6b901-112">Sie können Menüelemente hinzufügen, indem Sie programmgesteuert erstellen <xref:System.Windows.Forms.MenuItem> Objekte und Hinzufügen der <xref:System.Windows.Forms.Menu.MenuItemCollection> des Kontextmenüs.</span><span class="sxs-lookup"><span data-stu-id="6b901-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="6b901-113">Da die Elemente in einem Kontextmenü in der Regel aus anderen Menüs gezeichnet werden, werden Sie am häufigsten Elemente in einem Kontextmenü Menüelemente hinzufügen, durch Kopieren.</span><span class="sxs-lookup"><span data-stu-id="6b901-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b901-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b901-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
