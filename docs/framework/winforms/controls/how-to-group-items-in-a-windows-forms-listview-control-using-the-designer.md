---
title: 'Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 03958109d4daa3fc369660de66973bb659e29c60
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960177"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms mithilfe des Designers

Mit der Gruppierungs Funktion des <xref:System.Windows.Forms.ListView>-Steuer Elements können Sie Verwandte Gruppen von Elementen in Gruppen anzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppen Kopfzeilen getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen verwenden, um die Navigation durch große Listen zu vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach einer anderen logischen Gruppierung gruppieren. Die folgende Abbildung zeigt einige gruppierte Elemente:

![Zahlen, die in ungerade und gerade Gruppen aufgeteilt sind.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.ListView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

Um die Gruppierung zu aktivieren, müssen Sie zunächst ein oder mehrere <xref:System.Windows.Forms.ListViewGroup> Objekte entweder im Designer oder Programm gesteuert erstellen. Nachdem eine Gruppe definiert wurde, können Sie Ihr Elemente zuweisen.

## <a name="to-add-or-remove-groups-in-the-designer"></a>So können Sie Gruppen im Designer hinzufügen oder entfernen

1. Klicken Sie im **Eigenschaften** Fenster auf die Auslassungs Punkte (![die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der Eigenschaftenfenster der Visual Studio](./media/visual-studio-ellipsis-button.png))-Schaltfläche neben der <xref:System.Windows.Forms.ListView.Groups%2A>-Eigenschaft.

     Der **ListViewGroup-Sammlungs-Editor** wird angezeigt.

2. Um eine Gruppe hinzuzufügen, klicken Sie auf die Schaltfläche **Hinzufügen** . Sie können dann Eigenschaften der neuen Gruppe festlegen, z. b. die Eigenschaften <xref:System.Windows.Forms.ListViewGroup.Header%2A> und <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>. Um eine Gruppe zu entfernen, wählen Sie Sie aus und klicken auf die Schaltfläche **Entfernen** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>So weisen Sie Gruppen im Designer Elemente zu

1. Klicken Sie im **Eigenschaften** Fenster auf die Auslassungs Punkte (![die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der Eigenschaftenfenster der Visual Studio](./media/visual-studio-ellipsis-button.png))-Schaltfläche neben der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft.

     Der **ListViewItem-Auflistungs-Editor** wird angezeigt.

2. Um ein neues Element hinzuzufügen, klicken Sie auf die Schaltfläche **Hinzufügen** . Sie können dann die Eigenschaften des neuen Elements festlegen, z. b. die Eigenschaften <xref:System.Windows.Forms.ListViewItem.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

3. Wählen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A>-Eigenschaft aus, und wählen Sie eine Gruppe aus der Dropdown Liste aus.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
