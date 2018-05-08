---
title: 'Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: 737e74184b0763ed84b4e585f2508d69944d0e77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten
Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement zeigt eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows-Explorer angezeigt. Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie können kontextbezogene Vorgänge für den Benutzer bereitstellen, wenn sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement. Durch das Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit einzelnen <xref:System.Windows.Forms.TreeNode> Elemente, können Sie eine benutzerdefinierte Ebene Verknüpfung im Menü Funktionen zur Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Um ein Kontextmenü mit einem TreeNode programmgesteuert zu verknüpfen  
  
1.  Instanziieren einer <xref:System.Windows.Forms.TreeView> mit den entsprechenden eigenschafteneinstellungen gesteuert, erstellen Sie ein Stamm <xref:System.Windows.Forms.TreeNode>, und fügen Sie dann die untergeordneten Knoten hinzu.  
  
2.  Instanziieren einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente, und fügen Sie dann eine <xref:System.Windows.Forms.ToolStripMenuItem> für jeden Vorgang, der zur Laufzeit verfügbar machen möchten.  
  
3.  Legen Sie die <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> der entsprechenden Eigenschaft <xref:System.Windows.Forms.TreeNode> auf das Kontextmenü, das Sie erstellen.  
  
4.  Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü angezeigt werden, wenn Sie den Knoten mit der rechten Maustaste.  
  
 Das folgende Codebeispiel erstellt einen grundlegenden <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ContextMenuStrip> verknüpft sind, mit dem Stamm <xref:System.Windows.Forms.TreeNode> von der <xref:System.Windows.Forms.TreeView>. Sie müssen an die Menüoptionen auf solche Anpassen der <xref:System.Windows.Forms.TreeView> Sie entwickeln. Darüber hinaus sollten so schreiben Sie Code zum Behandeln der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [TreeView-Steuerelement](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
