---
title: 'Exemplarische Vorgehensweise: Überprüfen von Daten in DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 45753fb206ad58616c9a727bd81bd2458db6053e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740102"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms

Wenn Sie Benutzern Dateneingabe Funktionen anzeigen, müssen Sie häufig die Daten überprüfen, die in das Formular eingegeben wurden. Die <xref:System.Windows.Forms.DataGridView>-Klasse bietet eine bequeme Möglichkeit, die Validierung auszuführen, bevor Daten in den Datenspeicher übertragen werden. Sie können Daten überprüfen, indem Sie das <xref:System.Windows.Forms.DataGridView.CellValidating>-Ereignis behandeln, das von der <xref:System.Windows.Forms.DataGridView> ausgelöst wird, wenn sich die aktuelle Zelle ändert.

In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` Tabelle in der Northwind-Beispieldatenbank ab und zeigen Sie in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement an. Wenn ein Benutzer eine Zelle in der `CompanyName` Spalte bearbeitet und versucht, die Zelle zu verlassen, prüft der <xref:System.Windows.Forms.DataGridView.CellValidating>-Ereignishandler die neue Firmenname-Zeichenfolge, um sicherzustellen, dass Sie nicht leer ist. Wenn der neue Wert eine leere Zeichenfolge ist, verhindert die <xref:System.Windows.Forms.DataGridView>, dass der Cursor des Benutzers die Zelle verlässt, bis eine nicht leere Zeichenfolge eingegeben wird.

Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst wie: Überprüfen von [Daten im Windows Forms DataGridView-Steuer](how-to-validate-data-in-the-windows-forms-datagridview-control.md)Element.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:

- Zugriff auf einen Server mit der Beispieldatenbank Northwind SQL Server.

## <a name="creating-the-form"></a>Erstellen des Formulars

#### <a name="to-validate-data-entered-in-a-datagridview"></a>So überprüfen Sie Daten, die in einer DataGridView eingegeben wurden

1. Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und ein <xref:System.Windows.Forms.DataGridView> Steuerelement und eine <xref:System.Windows.Forms.BindingSource> Komponente enthält.

    Das folgende Codebeispiel stellt eine grundlegende Initialisierung bereit und enthält eine `Main`-Methode.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Implementieren Sie eine Methode in der Klassendefinition Ihres Formulars, um die Details der Verbindungs Herstellung mit der Datenbank zu verarbeiten.

    Dieses Codebeispiel verwendet eine `GetData`-Methode, die ein aufgefülltes <xref:System.Data.DataTable> Objekt zurückgibt. Stellen Sie sicher, dass Sie die `connectionString` Variable auf einen Wert festlegen, der für Ihre Datenbank geeignet ist.

    > [!IMPORTANT]
    > Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Die Verwendung der Windows-Authentifizierung (auch als integrierte Sicherheit bezeichnet) ist eine sicherere Methode zum Steuern des Zugriffs auf eine Datenbank. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das die <xref:System.Windows.Forms.DataGridView> initialisiert und <xref:System.Windows.Forms.BindingSource> und die Datenbindung einrichtet.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Implementieren von Handlern für die <xref:System.Windows.Forms.DataGridView.CellValidating>-und <xref:System.Windows.Forms.DataGridView.CellEndEdit>-Ereignisse des <xref:System.Windows.Forms.DataGridView>-Steuer Elements.

    Der <xref:System.Windows.Forms.DataGridView.CellValidating>-Ereignishandler bestimmt, ob der Wert einer Zelle in der Spalte `CompanyName` leer ist. Wenn der Zellwert die Überprüfung nicht besteht, legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType>-Klasse auf `true`fest. Dies bewirkt, dass das <xref:System.Windows.Forms.DataGridView> Steuerelement verhindert, dass der Cursor die Zelle verlässt. Legen Sie die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>-Eigenschaft in der Zeile auf eine erklärende Zeichenfolge fest. Dadurch wird ein Fehler Symbol mit einer QuickInfo angezeigt, die den Fehlertext enthält. Legen Sie im Ereignishandler <xref:System.Windows.Forms.DataGridView.CellEndEdit> die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>-Eigenschaft der Zeile auf die leere Zeichenfolge fest. Das <xref:System.Windows.Forms.DataGridView.CellEndEdit>-Ereignis tritt nur auf, wenn die Zelle den Bearbeitungsmodus verlässt, was nicht möglich ist, wenn die Überprüfung fehlschlägt.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Testen der Anwendung

Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.

#### <a name="to-test-the-form"></a>So testen Sie das Formular

- Kompilieren Sie die Anwendung, und führen Sie sie aus.

  Eine <xref:System.Windows.Forms.DataGridView> mit Daten aus der `Customers` Tabelle wird angezeigt. Wenn Sie in der Spalte `CompanyName` auf eine Zelle doppelklicken, können Sie den Wert bearbeiten. Wenn Sie alle Zeichen löschen und die Tab-Taste drücken, um die Zelle zu beenden, verhindert die <xref:System.Windows.Forms.DataGridView>, dass Sie beendet werden. Wenn Sie eine nicht leere Zeichenfolge in die Zelle eingeben, können Sie mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement die Zelle beenden.

## <a name="next-steps"></a>Nächste Schritte

Diese Anwendung bietet grundlegende Kenntnisse über die Funktionen des <xref:System.Windows.Forms.DataGridView>-Steuer Elements. Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView> Steuer Elements auf verschiedene Weise anpassen:

- Ändern von Rahmen-und Header Stilen. Weitere Informationen finden Sie unter Gewusst [wie: Ändern der Rahmen-und Rasterlinien Stile im Windows Forms DataGridView-Steuer](change-the-border-and-gridline-styles-in-the-datagrid.md)Element.

- Aktiviert oder schränkt die Benutzereingabe auf das <xref:System.Windows.Forms.DataGridView> Steuerelement ein. Weitere Informationen finden Sie unter Gewusst [wie: verhindern des Hinzufügens und Löschens von Zeilen im Windows Forms DataGridView-Steuer](prevent-row-addition-and-deletion-datagridview.md)Element und Gewusst wie: Festlegen von schreibgeschützten [Spalten im Windows Forms DataGridView-Steuer](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Element.

- Überprüfen Sie die Benutzereingaben auf datenbankbezogene Fehler. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView-Steuerelement auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).

- Verarbeiten Sie sehr große Datasets im virtuellen Modus. Weitere Informationen finden Sie unter Exemplarische [Vorgehensweise: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element.

- Passen Sie die Darstellung von Zellen an. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen der Darstellung von Zellen im Windows Forms DataGridView-Steuer](customize-the-appearance-of-cells-in-the-datagrid.md) Element und Gewusst [wie: Festlegen von Schriftart-und Farb Stilen im Windows Forms DataGridView-Steuer](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)Element.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Überprüfen von Daten im DataGridView-Steuerelement in Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
