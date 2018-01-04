---
title: "Gewusst wie: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3acc1a731fa584a17c8a96f8a02986a504cd302d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Gewusst wie: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers
Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement zeigt eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows Explorer-Features in Windows-Betriebssysteme angezeigt. Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie können kontextbezogene Vorgänge für den Benutzer bereitstellen, wenn sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement. Durch das Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit einzelnen <xref:System.Windows.Forms.TreeNode> Elemente, können Sie eine benutzerdefinierte Ebene Verknüpfung im Menü Funktionen zur Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>Zuordnen ein Kontextmenüs zu einem TreeNode zur Entwurfszeit  
  
1.  Hinzufügen einer <xref:System.Windows.Forms.TreeView> in Ihr Formular zu steuern, und fügen Sie dann den Knoten, um die <xref:System.Windows.Forms.TreeView> nach Bedarf. Weitere Informationen finden Sie unter [wie: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Hinzufügen einer <xref:System.Windows.Forms.ContextMenuStrip> -Komponente in Ihr Formular, und klicken Sie dann im Kontextmenü an, die auf Knotenebene Vorgänge darstellen, zur Laufzeit verfügbar machen möchten, Menüelemente hinzuzufügen. Weitere Informationen finden Sie unter [wie: Hinzufügen von Menüelementen zu einem ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Öffnen Sie erneut der **TreeNode-Editor** im Dialogfeld für die <xref:System.Windows.Forms.TreeView> steuern, wählen Sie den Knoten bearbeiten, und legen seine <xref:System.Windows.Forms.ContextMenuStrip> Eigenschaft, um das Kontextmenü, das Sie hinzugefügt.  
  
4.  Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt werden, wenn Sie den Knoten mit der rechten Maustaste.  
  
     Darüber hinaus sollten so schreiben Sie Code zum Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.  
  
## <a name="see-also"></a>Siehe auch  
 [TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Übersicht über das TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [ContextMenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
