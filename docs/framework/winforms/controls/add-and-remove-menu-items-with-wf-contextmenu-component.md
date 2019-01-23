---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: ac554f080cdabc7034ca839c3a9086e927429f7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520034"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="a601e-102">Vorgehensweise: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a601e-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="a601e-103">Erläutert das Hinzufügen und Entfernen von Tastenkombinations-Menüelemente in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a601e-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="a601e-104">Die Windows-Formulare <xref:System.Windows.Forms.ContextMenu> Komponente stellt ein Menü der häufig verwendete Befehle, die auf das ausgewählte Objekt relevant sind.</span><span class="sxs-lookup"><span data-stu-id="a601e-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="a601e-105">Sie können Elemente zum Kontextmenü hinzufügen, durch das Hinzufügen <xref:System.Windows.Forms.MenuItem> Objekte die <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a601e-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="a601e-106">Sie können Elemente aus einem Kontextmenü dauerhaft entfernen. Allerdings zur Laufzeit es möglicherweise besser geeignet ist, ausblenden oder deaktivieren stattdessen die Elemente.</span><span class="sxs-lookup"><span data-stu-id="a601e-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a601e-107">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="a601e-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="a601e-108">So entfernen Sie Elemente aus einem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="a601e-108">To remove items from a shortcut menu</span></span>  
  
1.  <span data-ttu-id="a601e-109">Verwenden der <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> oder <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, um ein bestimmtes Element zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a601e-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="a601e-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="a601e-110">-or-</span></span>  
  
2.  <span data-ttu-id="a601e-111">Verwenden der `Clear` Methode der `MenuItems` Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, um alle Elemente aus dem Menü zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a601e-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a601e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a601e-112">See also</span></span>
- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="a601e-113">ContextMenu-Komponente</span><span class="sxs-lookup"><span data-stu-id="a601e-113">ContextMenu Component</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)
- [<span data-ttu-id="a601e-114">Übersicht über die ContextMenu-Komponente</span><span class="sxs-lookup"><span data-stu-id="a601e-114">ContextMenu Component Overview</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
