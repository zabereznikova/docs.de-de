---
title: 'Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten'
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
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294172"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten
Die Windows-Formulare <xref:System.Windows.Forms.TreeView> Steuerelement wird eine Hierarchie von Knoten, ähnlich wie die Dateien und Ordner im linken Bereich des Windows-Explorer angezeigt. Durch Festlegen der <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> -Eigenschaft, Sie bieten kontextbezogene Vorgänge für den Benutzer sie mit der rechten Maustaste die <xref:System.Windows.Forms.TreeView> Steuerelement. Durch Zuordnen einer <xref:System.Windows.Forms.ContextMenuStrip> Komponente mit individuellen <xref:System.Windows.Forms.TreeNode> Elemente, Sie können eine benutzerdefinierte Ebene Verknüpfung im Menü-Funktionen zum Hinzufügen Ihrer <xref:System.Windows.Forms.TreeView> Steuerelemente.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Ein Kontextmenü einen TreeNode programmgesteuert zugeordnet werden soll  
  
1. Instanziieren einer <xref:System.Windows.Forms.TreeView> steuern Sie mit den entsprechenden eigenschafteneinstellungen, erstellen Sie ein Stamm <xref:System.Windows.Forms.TreeNode>, und fügen Sie dann die untergeordneten Knoten.  
  
2. Instanziieren einer <xref:System.Windows.Forms.ContextMenuStrip> -Komponente, und fügen Sie dann eine <xref:System.Windows.Forms.ToolStripMenuItem> für jeden Vorgang, der zur Laufzeit verfügbar gemacht werden sollen.  
  
3. Legen Sie die <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> Eigenschaft des entsprechenden <xref:System.Windows.Forms.TreeNode> auf das Kontextmenü, das Sie erstellen.  
  
4. Wenn diese Eigenschaft festgelegt ist, wird das Kontextmenü per Rechtsklick auf den Knoten angezeigt werden.  
  
 Das folgende Codebeispiel erstellt eine grundlegende <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ContextMenuStrip> zugeordnet <xref:System.Windows.Forms.TreeNode> von der <xref:System.Windows.Forms.TreeView>. Sie müssen an die Menüoptionen auf die Anpassen der <xref:System.Windows.Forms.TreeView> Sie entwickeln. Darüber hinaus sollten Sie zum Schreiben von Code zum Behandeln von der <xref:System.Windows.Forms.ToolStripItem.Click> Ereignisse für diese Menüelemente.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ContextMenuStrip>
- [TreeView-Steuerelement](treeview-control-windows-forms.md)
