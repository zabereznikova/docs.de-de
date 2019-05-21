---
title: 'Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: fea160e62939a27521592201cd47615975b7733f
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959399"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers

Tabellendaten werden oft in einem Ledger-ähnlichen Format präsentiert, in dem Zeilen abwechselnde Hintergrundfarben haben. Dieses Format erleichtert es dem Benutzer, zu erkennen, welche Zellen sich in jeder Zeile befinden, insbesondere bei breiten Tabellen mit vielen Spalten.

Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie vollständige Stilinformationen für abwechselnde Zeilen angeben. Sie können die Stileigenschaften wie Vordergrundfarbe und Schriftart zusätzlich zur Hintergrundfarbe verwenden, um abwechselnde Zeilen zu unterscheiden. Weitere Informationen finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="define-styles-for-alternating-rows"></a>Definieren Sie Stile für abwechselnde Zeilen

1. Wählen Sie die <xref:System.Windows.Forms.DataGridView> Steuerelement im Designer.

2. In der **Eigenschaften** Fenster, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> Eigenschaft.

3. In der **CellStyle-Generator** im Dialogfeld den Stil durch Festlegen der Eigenschaften definieren und Verwenden der **Vorschau** Bereich, um Ihre Auswahl zu bestätigen. Die Stile, die Sie angeben, werden für jede weitere Zeile angezeigt, in das Steuerelement, beginnend mit dem zweiten Ausdruck verwendet.

4. Um Formate für die verbleibenden Zeilen zu definieren, wiederholen Sie Schritte 2 und 3: Verwenden der <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> Eigenschaft.

    > [!NOTE]
    > Zellen werden mit Stilen, die von mehreren Eigenschaften geerbt angezeigt. Weitere Informationen zu stilvererbung, finden Sie unter [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
