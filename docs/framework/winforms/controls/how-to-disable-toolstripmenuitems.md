---
title: 'Gewusst wie: Deaktivieren von ToolStripMenuItems'
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
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3307da3e0810ea775c799a4b065e1f7484b5779
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a>Gewusst wie: Deaktivieren von ToolStripMenuItems
Sie können begrenzen oder erweitern die Befehle, die ein Benutzer durch das Aktivieren und Deaktivieren von Menüelementen in Reaktion auf Benutzeraktivitäten treffen. Menüelemente sind standardmäßig aktiviert, wenn sie erstellt werden, aber dies die angepasst werden kann, durch die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft. Sie können diese Eigenschaft zur Entwurfszeit im Bearbeiten der **Eigenschaften** Fenster oder programmgesteuert im Code festlegen.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>So deaktivieren Sie ein Menüelement programmgesteuert  
  
-   Fügen Sie innerhalb der Methode, in dem Sie die Eigenschaften des Menüelements festlegen, Code aus, um die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft `false`.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  Deaktivieren das erste oder der obersten Ebene Menüelement in einem Menü Blendet alle Menüelemente im Menü, jedoch nicht deaktivieren. Ebenso Deaktivieren eines Menüelements, das Untermenüelemente verfügt die Untermenüelemente ausgeblendet, aber nicht deaktivieren. Wenn alle Befehle in einem bestimmten Menü für den Benutzer nicht verfügbar sind, gilt die guten Programmierstil, ausgeblendet und deaktiviert das gesamte Menü, wie dies eine saubere Benutzeroberfläche dar. Sie sollten ausblenden und deaktivieren das Menü und jedes Element und Untermenüelement im Menü, deaktiviert werden, weil der Zugriff auf einen Menübefehl über eine Tastenkombination zum Ausblenden von alleine nicht verhindert wird. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Visible%2A> Eigenschaft für ein Menüelement der obersten Ebene auf `false` das gesamte Menü ausblenden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Gewusst wie: Ausblenden von ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
