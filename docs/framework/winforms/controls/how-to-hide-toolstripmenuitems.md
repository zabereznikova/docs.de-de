---
title: 'Vorgehensweise: Ausblenden von ToolStripMenuItems'
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
ms.openlocfilehash: dc9daa945f2a546548f2cc6ea033378bd9ceff93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941220"
---
# <a name="how-to-hide-toolstripmenuitems"></a>Vorgehensweise: Ausblenden von ToolStripMenuItems
Ausblenden von Menüelementen ist eine Möglichkeit zum Steuern der Benutzeroberfläche Ihrer Anwendung und User-Befehle zu beschränken. Häufig möchten ein ganzes Menü ausblenden, wenn alle Menüelemente im auf nicht verfügbar sind. Dies führt zu weniger ablenkungen für den Benutzer. Darüber hinaus empfiehlt sowohl ausblenden und deaktivieren Sie das Menü oder Menüelement, da allein durch das Ausblenden den Benutzer den Zugriff auf einen Menübefehl mit einer Tastenkombination nicht verhindert wird.  
  
### <a name="to-hide-any-menu-item-programmatically"></a>So blenden Sie eine beliebige Menüoption programmgesteuert aus  
  
- Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft `false`.  
  
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

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
- [Vorgehensweise: Deaktivieren von ToolStripMenuItems](how-to-disable-toolstripmenuitems.md)
