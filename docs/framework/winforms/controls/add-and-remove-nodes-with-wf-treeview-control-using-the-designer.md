---
title: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732253"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Gewusst wie: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers

Da das Windows Forms <xref:System.Windows.Forms.TreeView>-Steuerelement Knoten hierarchisch anzeigt, müssen Sie beim Hinzufügen eines Knotens auf den übergeordneten Knoten achten.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.TreeView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-nodes-in-the-designer"></a>So können Sie Knoten im Designer hinzufügen oder entfernen

1. Wählen Sie das <xref:System.Windows.Forms.TreeView>-Steuerelement.

2. Klicken Sie im **Eigenschaften** Fenster auf die Auslassungs Punkte (![die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der Eigenschaftenfenster der Visual Studio](./media/visual-studio-ellipsis-button.png))-Schaltfläche neben der <xref:System.Windows.Forms.TreeView.Nodes%2A>-Eigenschaft.

     Der **treumode-Editor** wird angezeigt.

3. Ein Stamm Knoten muss vorhanden sein, um Knoten hinzuzufügen. Wenn keine vorhanden ist, müssen Sie zuerst einen Stamm hinzufügen, indem Sie auf die Schaltfläche Stamm **Hinzufügen** klicken. Sie können dann untergeordnete Knoten hinzufügen, indem Sie den Stamm Knoten oder einen anderen Knoten auswählen und auf die Schaltfläche untergeordnetes Element **Hinzufügen**

4. Zum Löschen von Knoten wählen Sie den zu löschenden Knoten aus, und klicken Sie dann auf die Schaltfläche **Löschen** .

## <a name="see-also"></a>Siehe auch

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [Gewusst wie: Festlegen von Symbolen für das TreeView-Steuerelement in Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Gewusst wie: Durchlaufen aller Knoten eines TreeView-Steuerelements in Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Gewusst wie: Ermitteln des per Mausklick ausgewählten TreeView-Knotens](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
