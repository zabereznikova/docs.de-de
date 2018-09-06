---
title: 'Gewusst wie: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 77c4b01100aec2df16d5eb844f73f7a2bfa115aa
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864741"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Gewusst wie: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers
Die Windows-Formulare <xref:System.Windows.Forms.TreeView> Steuerelement wird eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows-Explorer-Features in Windows-Betriebssysteme angezeigt. Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie bieten kontextbezogene Vorgänge für den Benutzer sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement. Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit individuellen <xref:System.Windows.Forms.TreeNode> Elemente, Sie können eine benutzerdefinierte Ebene Verknüpfung im Menü-Funktionen zum Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Um ein Kontextmenü einen TreeNode zur Entwurfszeit zuzuordnen  
  
1.  Hinzufügen einer <xref:System.Windows.Forms.TreeView> -Steuerelement zu Ihrem Formular ein, und klicken Sie dann den Knoten zum Hinzufügen der <xref:System.Windows.Forms.TreeView> je nach Bedarf. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.ContextMenuStrip> -Komponente zum Formular, und Hinzufügen von Menüelementen klicken Sie dann auf das Kontextmenü, die auf Knotenebene Vorgänge darstellen, zur Laufzeit verfügbar gemacht werden sollen. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Menüelementen zu einem ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Öffnen Sie erneut der **TreeNode-Editor** im Dialogfeld für die <xref:System.Windows.Forms.TreeView> steuern, wählen Sie den Knoten zu bearbeiten, und legen seine <xref:System.Windows.Forms.ContextMenuStrip> Eigenschaft, um das Kontextmenü, das Sie hinzugefügt.  
  
4.  Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü per Rechtsklick auf den Knoten angezeigt werden.  
  
     Darüber hinaus sollten Sie zum Schreiben von Code zum Behandeln von der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.  
  
## <a name="see-also"></a>Siehe auch  
 [TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Übersicht über das TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [ContextMenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
