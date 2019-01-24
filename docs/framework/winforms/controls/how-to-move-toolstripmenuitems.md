---
title: 'Vorgehensweise: Verschieben von ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 12554ee2225dbb186392b910ddfd7c2f69695e7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660215"
---
# <a name="how-to-move-toolstripmenuitems"></a>Vorgehensweise: Verschieben von ToolStripMenuItems
Zur Entwurfszeit Sie ganze Menüs der obersten Ebene und ihre Menüelemente an eine andere Stelle auf Verschieben der <xref:System.Windows.Forms.MenuStrip>. Sie können auch einzelne Menüelemente zwischen Menüs der obersten Ebene verschieben oder Ändern der Position der Menüelemente in einem Menü.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Um ein Menü der obersten Ebene und den Menüelementen auf oberster Ebene verschieben  
  
1.  Klicken Sie auf, und halten Sie die linke Maustaste auf das Menü, das Sie verschieben möchten.  
  
2.  Ziehen Sie die Einfügemarke auf das Menü der obersten Ebene, die vor der beabsichtigten neuen Position befindet, und lassen Sie die linke Maustaste los.  
  
     Das ausgewählte Menü wird rechts neben der Einfügemarke verschoben werden.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Ein Menü der obersten Ebene und seine Menüelemente an eine Dropdown-Speicherort zu verschieben  
  
1.  Klicken Sie auf das Menü, das Sie verwenden möchten, verschieben, und drücken STRG + X, und mit der rechten Maustaste im Menüs, und wählen Sie **Ausschneiden** aus dem Kontextmenü.  
  
2.  Klicken Sie im Menü der obersten Ebene Ziel einen Menüpunkt oberhalb der beabsichtigten neuen Position und drücken Sie STRG + V, oder mit der rechten Maustaste in des Menüelements oberhalb der beabsichtigten neuen Position und wählen Sie **einfügen** aus dem Kontextmenü.  
  
     Das Menü, das Sie Ausschneiden wird nach dem das ausgewählte Menüelement eingefügt.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Verschieben Sie ein Menüelement innerhalb eines Menüs mit dem Elementauflistungs-Editor  
  
1.  Mit der rechten Maustaste in des Menüs, das das Menüelement enthält, die, das Sie verschieben möchten.  
  
2.  Wählen Sie im Kontextmenü den Befehl **DropDownItems bearbeiten**.  
  
3.  In der **-Elementauflistungs-Editor**, klicken Sie auf das Menüelement, das Sie verschieben möchten.  
  
4.  Klicken Sie auf die Pfeiltasten oben und nach unten, um das Menüelement im Menü zu verschieben.  
  
5.  Klicken Sie auf **OK**.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Um ein Menüelement in einem Menü mit der Tastatur zu verschieben.  
  
1.  Drücken Sie die EINGABETASTE, und halten Sie die ALT-Taste.  
  
2.  Klicken Sie auf, und halten der linken Maustaste auf das Menüelement, das Sie verschieben möchten.  
  
3.  Ziehen Sie das Menüelement an den neuen Speicherort aus, und lassen Sie die linke Maustaste gedrückt.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>So verschieben ein Menüelement zu einer anderen Menüressource  
  
1.  Klicken Sie auf das Menüelement, das Sie verwenden möchten, verschieben, und drücken STRG + X, oder mit der rechten Maustaste in des Menüelements, und wählen **Ausschneiden** aus dem Kontextmenü.  
  
2.  Klicken Sie auf das Menü, das das Menüelement enthält, das für Sie gelten.  
  
3.  Klicken Sie auf das Menüelement, das vor der beabsichtigten neuen Position befindet, und drücken Sie STRG + V, oder mit der rechten Maustaste in des Menüelements, das vor der beabsichtigten neuen Position, und wählen **einfügen** aus dem Kontextmenü.  
  
     Dem Menüelement, das das ausgeschnittene wird nach dem das ausgewählte Menüelement eingefügt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
