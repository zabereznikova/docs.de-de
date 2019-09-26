---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040078"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms mithilfe des Designers

Da das Windows Forms <xref:System.Windows.Forms.TreeView> -Steuerelement Knoten hierarchisch anzeigt, müssen Sie beim Hinzufügen eines Knotens auf den übergeordneten Knoten achten.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.TreeView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

### <a name="to-add-or-remove-nodes-in-the-designer"></a>So können Sie Knoten im Designer hinzufügen oder entfernen

1. Wählen Sie das <xref:System.Windows.Forms.TreeView>-Steuerelement.

2. Klicken Sie **im Eigenschaften** Fenster auf die Auslassungs Punkte![(die Schaltfläche mit den Auslassungs **Punkten (.** ..) in der](./media/visual-studio-ellipsis-button.png)Eigenschaftenfenster von Visual Studio. <xref:System.Windows.Forms.TreeView.Nodes%2A> ) neben der-Eigenschaft.

     Der **treumode-Editor** wird angezeigt.

3. Ein Stamm Knoten muss vorhanden sein, um Knoten hinzuzufügen. Wenn keine vorhanden ist, müssen Sie zuerst einen Stamm hinzufügen, indem Sie auf die Schaltfläche Stamm **Hinzufügen** klicken. Sie können dann untergeordnete Knoten hinzufügen, indem Sie den Stamm Knoten oder einen anderen Knoten auswählen und auf die Schaltfläche untergeordnetes Element **Hinzufügen**

4. Zum Löschen von Knoten wählen Sie den zu löschenden Knoten aus, und klicken Sie dann auf die Schaltfläche **Löschen** .

## <a name="see-also"></a>Siehe auch

- [TreeView-Steuerelement](treeview-control-windows-forms.md)
- [Übersicht über das TreeView-Steuerelement](treeview-control-overview-windows-forms.md)
- [Vorgehensweise: Festlegen von Symbolen für das Windows Forms TreeView-Steuerelement](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Iterieren aller Knoten eines Windows Forms TreeView-Steuer Elements](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Vorgehensweise: Ermitteln, auf welchen TreeView-Knoten geklickt wurde](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
