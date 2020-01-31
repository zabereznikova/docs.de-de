---
title: Hinzufügen von Spalten zum ListView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744608"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms mithilfe des Designers

Das Windows Forms <xref:System.Windows.Forms.ListView>-Steuerelement kann mehrere Spalten für jedes Listenelement anzeigen, wenn es in der **Detail** Ansicht angezeigt wird. Sie können die Spalten verwenden, um mehrere Arten von Informationen zu jedem Listenelement anzuzeigen. Beispielsweise können in einer Liste mit Dateien der Dateiname, Dateityp, die Größe und das Datum der letzten Änderung der Datei angezeigt werden. Informationen zum Auffüllen der Spalten nach ihrer Erstellung finden Sie unter Gewusst [wie: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuer](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)Element.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.ListView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-columns-in-the-designer"></a>So fügen Sie dem Designer Spalten hinzu

1. Legen Sie im Fenster **Eigenschaften** die <xref:System.Windows.Forms.ListView.View%2A>-Eigenschaft des Steuer Elements auf <xref:System.Windows.Forms.View.Details>fest.

2. Klicken Sie im **Eigenschaften** Fenster **auf die Schaltfläche mit den** Auslassungs Punkten (![die Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ListView.Columns%2A>-Eigenschaft.

     Der **ColumnHeader-Sammlungs-Editor** wird angezeigt.

3. Verwenden Sie die Schaltfläche **Hinzufügen** , um neue Spalten hinzuzufügen. Sie können dann die Spaltenüberschrift auswählen und Ihren Text (die Beschriftung der Spalte), die Textausrichtung und die Breite festlegen.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
