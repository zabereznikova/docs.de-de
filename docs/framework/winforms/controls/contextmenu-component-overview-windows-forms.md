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
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962188"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="6b410-102">Übersicht über die ContextMenu-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6b410-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6b410-103">Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die-und- <xref:System.Windows.Forms.ContextMenu> Steuerelemente früherer Versionen ersetzen und Funktionen hinzu <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> , werden Sie sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="6b410-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="6b410-104">Mit der Windows Forms <xref:System.Windows.Forms.ContextMenu> -Komponente können Sie Benutzern ein leicht zugängliches Kontextmenü mit häufig verwendeten Befehlen bereitstellen, die dem ausgewählten Objekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6b410-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="6b410-105">Die Elemente in einem Kontextmenü sind häufig eine Teilmenge der Elemente aus den Hauptmenüs, die an anderer Stelle in der Anwendung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6b410-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="6b410-106">Benutzer können in der Regel auf ein Kontextmenü zugreifen, indem Sie mit der rechten Maustaste auf die Maus klicken.</span><span class="sxs-lookup"><span data-stu-id="6b410-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="6b410-107">Auf Windows Forms werden Kontextmenüs Steuerelementen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6b410-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="6b410-108">Schlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="6b410-108">Key Properties</span></span>  
 <span data-ttu-id="6b410-109">Sie können ein Kontextmenü einem-Steuerelement zuordnen, indem Sie die <xref:System.Windows.Forms.Control.ContextMenu%2A> -Eigenschaft des <xref:System.Windows.Forms.ContextMenu> -Steuer Elements auf die-Komponente festlegen.</span><span class="sxs-lookup"><span data-stu-id="6b410-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="6b410-110">Einem einzelnen Kontextmenü können mehrere Steuerelemente zugeordnet werden, aber jedes Steuerelement kann nur über ein Kontextmenü verfügen.</span><span class="sxs-lookup"><span data-stu-id="6b410-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="6b410-111">Die Schlüsseleigenschaft der <xref:System.Windows.Forms.ContextMenu> Komponente ist die <xref:System.Windows.Forms.Menu.MenuItems%2A> -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6b410-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="6b410-112">Sie können Menü Elemente hinzufügen, indem Sie <xref:System.Windows.Forms.MenuItem> Objekte Programm gesteuert erstellen und Sie <xref:System.Windows.Forms.Menu.MenuItemCollection> dem Kontextmenü hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b410-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="6b410-113">Da die Elemente in einem Kontextmenü in der Regel aus anderen Menüs gezeichnet werden, fügen Sie Elemente häufig zu einem Kontextmenü hinzu, indem Sie Sie kopieren.</span><span class="sxs-lookup"><span data-stu-id="6b410-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b410-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b410-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
