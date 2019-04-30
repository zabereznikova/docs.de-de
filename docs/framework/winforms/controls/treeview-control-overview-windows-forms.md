---
title: Übersicht über das TreeView-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TreeView
helpviewer_keywords:
- TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
ms.openlocfilehash: 046713745e7de18cefe5b4883af73034af2cfb31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009226"
---
# <a name="treeview-control-overview-windows-forms"></a>Übersicht über das TreeView-Steuerelement (Windows Forms)

Mit dem <xref:System.Windows.Forms.TreeView>-Steuerelement in Windows Forms können Sie Benutzern eine Hierarchie von Knoten anzeigen, die mit der Anzeige der Dateien und Ordner im linken Bereich des Windows Explorer-Features des Windows-Betriebssystems vergleichbar ist. Jeder Knoten in der Strukturansicht kann andere Knoten, so genannte enthalten *untergeordnete Knoten*. Sie können übergeordnete Knoten oder Knoten, die untergeordnete Knoten enthalten, erweitert oder reduziert anzeigen. Sie können auch eine Strukturansicht mit Kontrollkästchen neben den Knoten anzeigen, indem Sie die <xref:System.Windows.Forms.TreeView.CheckBoxes%2A>-Eigenschaft der Strukturansicht auf `true` festlegen. Anschließend können Sie Knoten programmgesteuert auswählen oder löschen, indem Sie die <xref:System.Windows.Forms.TreeNode.Checked%2A>-Eigenschaft des Knotens auf `true` oder `false` festlegen.

## <a name="key-properties"></a>Schlüsseleigenschaften

Die wichtigsten Eigenschaften des <xref:System.Windows.Forms.TreeView>-Steuerelements sind <xref:System.Windows.Forms.TreeView.Nodes%2A> und <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. Die <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft enthält die Liste der Knoten der obersten Ebene in der Strukturansicht. Die <xref:System.Windows.Forms.TreeView.SelectedNode%2A>-Eigenschaft legt den aktuell ausgewählten Knoten fest. Sie können neben den Knoten Symbole anzeigen. Das Steuerelement verwendet Bilder aus der <xref:System.Windows.Forms.ImageList>, die in der <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft der Strukturansicht genannt ist. Die <xref:System.Windows.Forms.TreeView.ImageIndex%2A>-Eigenschaft legt das Standardbild für Knoten in der Strukturansicht fest. Weitere Informationen zum Anzeigen von Bildern finden Sie unter [Vorgehensweise: Festlegen von Symbolen für das Windows-TreeView-Steuerelement Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md). Wenn Sie Visual Studio 2005 verwenden, haben Sie Zugriff auf eine umfangreiche Bibliothek von Standardbildern, mit denen Sie mit der <xref:System.Windows.Forms.TreeView> Steuerelement.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TreeView>
- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Vorgehensweise: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Durchlaufen Sie aller Knoten eines Windows Forms TreeView-Steuerelements](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Vorgehensweise: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)