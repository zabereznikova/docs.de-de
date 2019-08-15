---
title: 'Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: e82fbcf63047873ebc6e5c40b8b9fbeb14a672e5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038184"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms mithilfe des Designers

Das Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement kann mehrere Spalten für jedes Listenelement anzeigen, wenn es in der **Detail** Ansicht angezeigt wird. Sie können die Spalten verwenden, um mehrere Arten von Informationen zu jedem Listenelement anzuzeigen. Beispielsweise können in einer Liste mit Dateien der Dateiname, Dateityp, die Größe und das Datum der letzten Änderung der Datei angezeigt werden. Informationen zum Auffüllen der Spalten nach ihrer Erstellung finden [Sie unter Gewusst wie: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuer](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)Element.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.ListView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.


### <a name="to-add-columns-in-the-designer"></a>So fügen Sie dem Designer Spalten hinzu

1. Legen Sie im Fenster **Eigenschaften** die-Eigenschaft des <xref:System.Windows.Forms.ListView.View%2A> -Steuer <xref:System.Windows.Forms.View.Details>Elements auf fest.

2. Klicken Sie im **Eigenschaften** Fenster auf die Schaltfläche mit den![Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (...](./media/visual-studio-ellipsis-button.png)) im Eigenschaftenfenster von <xref:System.Windows.Forms.ListView.Columns%2A> Visual Studio.) neben der-Eigenschaft.

     Der **ColumnHeader-Sammlungs-Editor** wird angezeigt.

3. Verwenden Sie die Schaltfläche **Hinzufügen** , um neue Spalten hinzuzufügen. Sie können dann die Spaltenüberschrift auswählen und Ihren Text (die Beschriftung der Spalte), die Textausrichtung und die Breite festlegen.

## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem Windows Forms ListView-Steuerelement](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von unter Elementen in Spalten mit dem Windows Forms ListView-Steuerelement](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeige Symbole für das Windows Forms ListView-Steuerelement](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
