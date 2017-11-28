---
title: 'Gewusst wie: Verschieben von ToolStripMenuItems'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 342eeeb2d156488605f244da0112869a371dfa97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-toolstripmenuitems"></a>Gewusst wie: Verschieben von ToolStripMenuItems
Zur Entwurfszeit können Sie wechseln ganze Menüs der obersten Ebene und ihre Menüelemente an eine andere Stelle der <xref:System.Windows.Forms.MenuStrip>. Sie können auch einzelne Menüelemente zwischen Menüs der obersten Ebene verschieben oder Ändern der Position von Menüelementen in einem Menü.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Um ein Menü der obersten Ebene und seine Menüelemente der obersten Ebene verschieben  
  
1.  Klicken Sie auf, und halten Sie die linke Maustaste auf das Menü, das Sie verschieben möchten.  
  
2.  Ziehen Sie die Einfügemarke auf das Menü der obersten Ebene, das vor der beabsichtigten neuen Position befindet, und lassen Sie die linke Maustaste gedrückt.  
  
     Das ausgewählte Menü wird rechts neben der Einfügemarke verschoben.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>So verschieben Sie ein Menü der obersten Ebene und seine Menüelemente an einen Ablageort  
  
1.  Klicken Sie auf das Menü, das Sie verwenden möchten, verschieben und drücken STRG + X, oder das Kontextmenü und wählen Sie **Ausschneiden** aus dem Kontextmenü.  
  
2.  Klicken Sie im Menü der obersten Ebene Ziel klicken Sie auf das Menüelement oberhalb der beabsichtigten neuen Position und drücken Sie STRG + V, oder mit der rechten Maustaste des Menüelements oberhalb der beabsichtigten neuen Position und wählen Sie **einfügen** aus dem Kontextmenü.  
  
     Das Menü, das Sie Ausschneiden wird nach der ausgewählten Menüelements eingefügt.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>So verschieben Sie ein Menüelement innerhalb eines Menüs mit der Elementauflistungs-Editor  
  
1.  Mit der rechten Maustaste in des Menüs, das das Menüelement enthält, die, das Sie verschieben möchten.  
  
2.  Wählen Sie im Kontextmenü **DropDownItems bearbeiten**.  
  
3.  In der **-Elementauflistungs-Editor**, klicken Sie auf das Menüelement, das Sie verschieben möchten.  
  
4.  Klicken Sie auf die Pfeiltasten oben und nach unten, um das Menüelement im Menü zu verschieben.  
  
5.  Klicken Sie auf **OK**.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>So verschieben Sie ein Menüelement in einem Menü mithilfe der Tastatur  
  
1.  Halten Sie die ALT-Taste.  
  
2.  Klicken Sie auf, und halten Sie die linke Maustaste gedrückt, auf das Menüelement, das Sie verschieben möchten.  
  
3.  Ziehen Sie das Menüelement an den neuen Speicherort ein, und lassen Sie die linke Maustaste gedrückt.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>So verschieben Sie ein Menüelement in ein anderes Menü  
  
1.  Klicken Sie auf das Menüelement, das Sie verschieben möchten und drücken STRG + X, oder mit der rechten Maustaste des Menüelements und wählen **Ausschneiden** aus dem Kontextmenü.  
  
2.  Klicken Sie auf das Menü, das das Menüelement enthält, das Sie ausgeschnitten werden.  
  
3.  Klicken Sie auf das Menüelement, das vor der beabsichtigten neuen Position befindet, und drücken Sie STRG + V, oder mit der rechten Maustaste des Menüelements, das vor der beabsichtigten neuen Position und wählen **einfügen** aus dem Kontextmenü.  
  
     Das Menüelement, das Sie Ausschneiden wird nach dem ausgewählten Menüelements eingefügt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
