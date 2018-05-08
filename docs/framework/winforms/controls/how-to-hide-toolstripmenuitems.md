---
title: 'Gewusst wie: Ausblenden von ToolStripMenuItems'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 73f67bbe6b2d51a59b6f72ab5faf21db9d6db12d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-toolstripmenuitems"></a>Gewusst wie: Ausblenden von ToolStripMenuItems
Ausblenden von Menüelementen lässt sich die Benutzeroberfläche der Anwendung steuern und Benutzerbefehle einschränken. Häufig, sollten Sie ein ganzes Menü auszublenden, wenn alle Menüelemente im auf ihm nicht verfügbar sind. Dies ist weniger verwirrend für den Benutzer. Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren das Menü oder Menüelement, wie durch das bloße Ausblenden nicht den Benutzer verhindert den Zugriff auf einen Menübefehl über eine Tastenkombination.  
  
### <a name="to-hide-any-menu-item-programmatically"></a>So blenden Sie alle Menüelement programmgesteuert aus  
  
-   Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [Gewusst wie: Deaktivieren von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
