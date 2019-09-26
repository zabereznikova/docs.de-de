---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 62665746ea9fcd1553717b02b1f1349dc6415ab2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040087"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers

Das Hinzufügen eines Elements zu einem Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement besteht hauptsächlich darin, das Element anzugeben und ihm Eigenschaften zuzuweisen. Das Hinzufügen oder Entfernen von Listenelementen ist jederzeit möglich.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.ListView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

### <a name="to-add-or-remove-items-using-the-designer"></a>So können Sie Elemente mithilfe des Designers hinzufügen oder entfernen

1. Wählen Sie das <xref:System.Windows.Forms.ListView>-Steuerelement.

2. Klicken Sie **im Eigenschaften** Fenster auf die Auslassungs Punkte![(die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der](./media/visual-studio-ellipsis-button.png)Eigenschaftenfenster von Visual Studio. <xref:System.Windows.Forms.ListView.Items%2A> ) neben der-Eigenschaft.

     Der **ListViewItem-Auflistungs-Editor** wird angezeigt.

3. Um ein Element hinzuzufügen, klicken Sie auf die Schaltfläche **Hinzufügen** . Sie können dann die Eigenschaften des neuen Elements festlegen, z. b <xref:System.Windows.Forms.ListView.Text%2A> . <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> die-Eigenschaft und die-Eigenschaft.

4. Um ein Element zu entfernen, wählen Sie es aus und klicken auf die Schaltfläche **Entfernen** .

## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen von Spalten zum Windows Forms ListView-Steuerelement](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuerelement](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeige Symbole für das Windows Forms ListView-Steuerelement](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Vorgehensweise: Gruppieren von Elementen in einem Windows Forms ListView-Steuerelement](how-to-group-items-in-a-windows-forms-listview-control.md)
