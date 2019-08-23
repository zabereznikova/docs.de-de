---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente von Windows Forms'
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
ms.openlocfilehash: 5d1862b1fc1398f0f8c2217b51c4efb93db639af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957018"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Vorgehensweise: Hinzufügen und Entfernen von Menüelementen mit der ContextMenu-Komponente von Windows Forms
Erläutert das Hinzufügen und Entfernen von Kontextmenü Elementen in Windows Forms.  
  
 Die Windows Forms <xref:System.Windows.Forms.ContextMenu> Komponente enthält ein Menü mit häufig verwendeten Befehlen, die für das ausgewählte Objekt relevant sind. Sie können dem Kontextmenü Elemente hinzufügen, indem <xref:System.Windows.Forms.MenuItem> Sie der <xref:System.Windows.Forms.Menu.MenuItems%2A> Auflistung Objekte hinzufügen.  
  
 Elemente aus einem Kontextmenü können dauerhaft entfernt werden. zur Laufzeit ist es jedoch möglicherweise besser, die Elemente auszublenden oder zu deaktivieren.  
  
> [!IMPORTANT]
> Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die-und- <xref:System.Windows.Forms.ContextMenu> Steuerelemente früherer Versionen ersetzen und Funktionen hinzu <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> , werden Sie sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>So entfernen Sie Elemente aus einem Kontextmenü  
  
1. Verwenden Sie <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> die <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> -Methode oder <xref:System.Windows.Forms.Menu.MenuItems%2A> die-Methode <xref:System.Windows.Forms.ContextMenu> der-Auflistung der-Komponente, um ein bestimmtes Menü Element zu entfernen.  
  
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
  
     -oder-  
  
2. Verwenden Sie `Clear` die-Methode `MenuItems` der <xref:System.Windows.Forms.ContextMenu> -Auflistung der-Komponente, um alle Elemente aus dem Menü zu entfernen.  
  
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

- <xref:System.Windows.Forms.ContextMenu>
- [ContextMenu-Komponente](contextmenu-component-windows-forms.md)
- [Übersicht über die ContextMenu-Komponente](contextmenu-component-overview-windows-forms.md)
