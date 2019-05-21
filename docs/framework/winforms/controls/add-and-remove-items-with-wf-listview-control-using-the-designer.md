---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 37bbd157e0c23886d026b4523ff4a7e74bb7828d
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959669"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms mithilfe des Designers

Beim Hinzufügen eines Elements zu einer Windows Forms <xref:System.Windows.Forms.ListView> -Steuerelement besteht aus in erster Linie das Element angeben, und Eigenschaften zuweisen. Hinzufügen oder Entfernen von Elementen kann jederzeit erfolgen.

Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-add-or-remove-items-using-the-designer"></a>Hinzufügen oder Entfernen von Elementen, die mithilfe des Designers

1. Wählen Sie das <xref:System.Windows.Forms.ListView>-Steuerelement.

2. In der **Eigenschaften** Fenster, klicken Sie auf die **mit den Auslassungspunkten** (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft .

     Die **ListViewItem Auflistungs-Editor** angezeigt wird.

3. Um ein Element hinzuzufügen, klicken Sie auf die **hinzufügen** Schaltfläche. Sie können dann Eigenschaften des neuen Elements, z. B. Festlegen der <xref:System.Windows.Forms.ListView.Text%2A> und <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> Eigenschaften.

4. Um ein Element zu entfernen, wählen Sie ihn, und klicken Sie auf die **entfernen** Schaltfläche.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Vorgehensweise: Gruppieren von Elementen in ein ListView-Steuerelement in Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
