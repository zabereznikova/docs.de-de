---
title: 'Gewusst wie: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente von Windows Forms'
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
ms.openlocfilehash: 7cc11eaf4a671c76933c2705b41a4df6c35c0536
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524728"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Gewusst wie: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente von Windows Forms
Erläutert das Hinzufügen und Entfernen von Tastenkombinations-Menüelemente in Windows Forms.  
  
 Windows Forms <xref:System.Windows.Forms.ContextMenu> Komponente stellt ein Kontextmenü mit häufig verwendeten Befehlen, die auf das ausgewählte Objekt relevant sind. Sie können das Kontextmenü Elemente hinzufügen, durch Hinzufügen von <xref:System.Windows.Forms.MenuItem> Datenbankobjekte in der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung.  
  
 Sie können Elemente aus einem Kontextmenü dauerhaft entfernen. Allerdings kann zur Laufzeit es besser geeignet sein ausblenden oder deaktivieren stattdessen die Elemente.  
  
> [!IMPORTANT]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzt und funktionell die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente von früheren Versionen <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> für Abwärtskompatibilität und für zukünftige Verwendung beibehalten werden, falls gewünscht.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>So entfernen Sie Elemente aus einem Kontextmenü  
  
1.  Verwenden der <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> oder <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, für die ein bestimmtes Element zu entfernen.  
  
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
  
     - oder -   
  
2.  Verwenden der `Clear` Methode der `MenuItems` Auflistung von der <xref:System.Windows.Forms.ContextMenu> Komponente, bei der alle Elemente aus dem Menü zu entfernen.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ContextMenu>  
 [ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)  
 [Übersicht über die ContextMenu-Komponente](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
