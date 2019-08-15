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
ms.openlocfilehash: 1be746d4cce36344e034692a0e2e8e6a9e9320d5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040439"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers

Tabellendaten werden häufig in einem Ledger-Format dargestellt, in dem abwechselnde Zeilen andere Hintergrundfarben aufweisen. Dieses Format erleichtert es dem Benutzer, zu erkennen, welche Zellen sich in jeder Zeile befinden, insbesondere bei breiten Tabellen mit vielen Spalten.

Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie vollständige Stilinformationen für abwechselnde Zeilen angeben. Sie können Stilmerkmale wie Vordergrundfarbe und-Schriftart zusätzlich zur Hintergrundfarbe verwenden, um abwechselnde Zeilen zu unterscheiden. Weitere Informationen finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGridView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.


### <a name="define-styles-for-alternating-rows"></a>Definieren von Stilen für abwechselnde Zeilen

1. Wählen Sie <xref:System.Windows.Forms.DataGridView> das Steuerelement im Designer aus.

2. Klicken Sie **im Eigenschaften** Fenster auf die Schaltfläche mit den![Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten (...](./media/visual-studio-ellipsis-button.png)) im Eigenschaftenfenster von <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> Visual Studio.) neben der-Eigenschaft.

3. Definieren Sie im Dialogfeld **CellStyle Builder** den Stil durch Festlegen der Eigenschaften, und überprüfen Sie die Optionen im **Vorschau** Bereich. Die Formate, die Sie angeben, werden für jede andere Zeile verwendet, die im Steuerelement angezeigt wird, beginnend mit dem zweiten.

4. Um Stile für die verbleibenden Zeilen zu definieren, wiederholen Sie die Schritte <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 2 und 3 mithilfe der-Eigenschaft.

    > [!NOTE]
    > Zellen werden mithilfe von Stilen angezeigt, die von mehreren Eigenschaften geerbt wurden. Weitere Informationen zur Stil Vererbung finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
