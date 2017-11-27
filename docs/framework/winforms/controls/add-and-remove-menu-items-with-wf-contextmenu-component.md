---
title: "Gewusst wie: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente von Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf0e579d5cf377169eeb4d394c4127d53fd54540
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="dc713-102">Gewusst wie: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc713-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="dc713-103">Erläutert das Hinzufügen und Entfernen von Tastenkombinations-Menüelemente in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="dc713-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="dc713-104">Windows Forms <xref:System.Windows.Forms.ContextMenu> Komponente stellt ein Kontextmenü mit häufig verwendeten Befehlen, die auf das ausgewählte Objekt relevant sind.</span><span class="sxs-lookup"><span data-stu-id="dc713-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="dc713-105">Sie können das Kontextmenü Elemente hinzufügen, durch Hinzufügen von <xref:System.Windows.Forms.MenuItem> Datenbankobjekte in der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dc713-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="dc713-106">Sie können Elemente aus einem Kontextmenü dauerhaft entfernen. Allerdings kann zur Laufzeit es besser geeignet sein ausblenden oder deaktivieren stattdessen die Elemente.</span><span class="sxs-lookup"><span data-stu-id="dc713-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dc713-107">Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzt und funktionell die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente von früheren Versionen <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> für Abwärtskompatibilität und für zukünftige Verwendung beibehalten werden, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="dc713-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="dc713-108">So entfernen Sie Elemente aus einem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="dc713-108">To remove items from a shortcut menu</span></span>  
  
1.  <span data-ttu-id="dc713-109">Verwenden der <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> oder <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, für die ein bestimmtes Element zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dc713-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
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
  
     <span data-ttu-id="dc713-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="dc713-110">-or-</span></span>  
  
2.  <span data-ttu-id="dc713-111">Verwenden der `Clear` Methode der `MenuItems` Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, bei der alle Elemente aus dem Menü zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dc713-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dc713-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc713-112">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenu>  
 [<span data-ttu-id="dc713-113">ContextMenu-Komponente</span><span class="sxs-lookup"><span data-stu-id="dc713-113">ContextMenu Component</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)  
 [<span data-ttu-id="dc713-114">Übersicht über die ContextMenu-Komponente</span><span class="sxs-lookup"><span data-stu-id="dc713-114">ContextMenu Component Overview</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
