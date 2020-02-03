---
title: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732297"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers

Das Hinzufügen eines Elements zu einem Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement besteht hauptsächlich darin, das Element anzugeben und ihm Eigenschaften zuzuweisen. Das Hinzufügen oder Entfernen von Listenelementen ist jederzeit möglich.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.ListView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-items-using-the-designer"></a>So können Sie Elemente mithilfe des Designers hinzufügen oder entfernen

1. Wählen Sie das <xref:System.Windows.Forms.ListView>-Steuerelement.

2. Klicken Sie im **Eigenschaften** Fenster auf die Auslassungs Punkte (![die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der Eigenschaftenfenster der Visual Studio](./media/visual-studio-ellipsis-button.png))-Schaltfläche neben der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft.

     Der **ListViewItem-Auflistungs-Editor** wird angezeigt.

3. Um ein Element hinzuzufügen, klicken Sie auf die Schaltfläche **Hinzufügen** . Sie können dann die Eigenschaften des neuen Elements festlegen, z. b. die Eigenschaften <xref:System.Windows.Forms.ListView.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

4. Um ein Element zu entfernen, wählen Sie es aus und klicken auf die Schaltfläche **Entfernen** .

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
