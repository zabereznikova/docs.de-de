---
title: 'Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 252ed6a599ba3601344c6423385946c3dadfafaa
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960174"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms mithilfe des Designers

Die Windows-Formulare <xref:System.Windows.Forms.ListView> Steuerelement kann mehrere Spalten für jede Liste anzeigen in Element der **Details** anzeigen. Sie können die Spalten verwenden, um verschiedene Arten von Informationen zu jedem Listenelement anzuzeigen. Beispielsweise kann eine Liste der Dateien angezeigt, der Dateiname, Typ, Größe und Datum, an der letzten der Datei Änderung. Informationen zum Auffüllen der Spalten aus, nachdem sie erstellt wurden, finden Sie unter [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem Windows Forms-ListView-Steuerelement](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).

Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.ListView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-add-columns-in-the-designer"></a>Hinzufügen von Spalten im designer

1. In der **Eigenschaften** legen des Steuerelements <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft <xref:System.Windows.Forms.View.Details>.

2. In der **Eigenschaften** Fenster, klicken Sie auf die **mit den Auslassungspunkten** Schaltfläche (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft .

     Die **ColumnHeader-Auflistungs-Editor** angezeigt wird.

3. Verwenden der **hinzufügen** , um neue Spalten hinzuzufügen. Sie können anschließend wählen Sie die Kopfzeile der Spalte und der Text (die Beschriftung der Spalte), Ausrichtung und die Breite.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
