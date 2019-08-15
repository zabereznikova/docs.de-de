---
title: 'Vorgehensweise: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040446"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>Vorgehensweise: Anfügen eines Kontextmenüs an einen TreeNode mithilfe des Designers
Das Windows Forms <xref:System.Windows.Forms.TreeView> Steuerelement zeigt eine Hierarchie von Knoten an, ähnlich wie die Dateien und Ordner, die im linken Bereich des Windows Explorer-Features in Windows-Betriebssystemen angezeigt werden. Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft können Sie dem Benutzer kontextabhängige Vorgänge bereitstellen, wenn Sie mit der rechten Maustaste <xref:System.Windows.Forms.TreeView> auf das Steuerelement klicken. Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente zu <xref:System.Windows.Forms.TreeView> einzelnen <xref:System.Windows.Forms.TreeNode> Elementen können Sie den Steuerelementen eine angepasste Ebene von Kontextmenü Funktionen hinzufügen.

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>So ordnen Sie einen TreeNode zur Entwurfszeit einem Kontextmenü zu

1. Fügen Sie <xref:System.Windows.Forms.TreeView> dem <xref:System.Windows.Forms.TreeView> Formular ein-Steuerelement hinzu, und fügen Sie dann bei Bedarf Knoten hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem Windows Forms TreeView-Steuer](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)Element.

2. Fügen Sie <xref:System.Windows.Forms.ContextMenuStrip> dem Formular eine Komponente hinzu, und fügen Sie dem Kontextmenü Menü Elemente hinzu, die Vorgänge auf Knotenebene darstellen, die Sie zur Laufzeit zur Verfügung stellen möchten. Weitere Informationen finden Sie unter [Vorgehensweise: Fügen Sie einem ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md)Menü Elemente hinzu.

3. Öffnen Sie das Dialogfeld **treenobeeditor** für <xref:System.Windows.Forms.TreeView> das-Steuerelement erneut, wählen Sie den zu bearbeitenden Knoten aus, und legen Sie dessen <xref:System.Windows.Forms.ContextMenuStrip> -Eigenschaft auf das hinzugefügte Kontextmenü fest.

4. Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt, wenn Sie mit der rechten Maustaste auf den Knoten klicken.

     Außerdem sollten Sie Code schreiben, um die <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menü Elemente zu behandeln.

## <a name="see-also"></a>Siehe auch

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [ContextMenuStrip-Steuerelement](contextmenustrip-control.md)
