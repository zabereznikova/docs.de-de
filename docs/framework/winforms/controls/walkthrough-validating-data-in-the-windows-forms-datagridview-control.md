---
title: 'Exemplarische Vorgehensweise: Überprüfen von Daten im DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 89569feb0cb741f56d09f4e58154b4eecb5a89d4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046377"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Überprüfen von Daten im DataGridView-Steuerelement in Windows Forms

Wenn Sie Benutzern Dateneingabe Funktionen anzeigen, müssen Sie häufig die Daten überprüfen, die in das Formular eingegeben wurden. Die <xref:System.Windows.Forms.DataGridView> -Klasse stellt eine bequeme Möglichkeit dar, eine Validierung durchzuführen, bevor Daten in den Datenspeicher übertragen werden. Sie können Daten überprüfen, indem <xref:System.Windows.Forms.DataGridView.CellValidating> Sie das-Ereignis behandeln, das <xref:System.Windows.Forms.DataGridView> von ausgelöst wird, wenn sich die aktuelle Zelle ändert.

In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` -Tabelle in der Northwind-Beispieldatenbank ab und zeigen <xref:System.Windows.Forms.DataGridView> Sie in einem-Steuerelement an. Wenn ein Benutzer eine Zelle in der `CompanyName` Spalte bearbeitet und versucht, die Zelle zu verlassen, untersucht der <xref:System.Windows.Forms.DataGridView.CellValidating> Ereignishandler die neue Firmenname-Zeichenfolge, um sicherzustellen, dass er nicht leer ist. wenn der neue Wert <xref:System.Windows.Forms.DataGridView> eine leere Zeichenfolge ist, wird der Cursor des Benutzers von verhindert. Das belassen der Zelle, bis eine nicht leere Zeichenfolge eingegeben wird.

Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Überprüfen Sie die Daten im Windows Forms DataGridView-Steuer](how-to-validate-data-in-the-windows-forms-datagridview-control.md)Element.

## <a name="prerequisites"></a>Erforderliche Komponenten

Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:

- Zugriff auf einen Server mit der Beispieldatenbank Northwind SQL Server.

## <a name="creating-the-form"></a>Erstellen des Formulars

#### <a name="to-validate-data-entered-in-a-datagridview"></a>So überprüfen Sie Daten, die in einer DataGridView eingegeben wurden

1. Erstellen Sie eine Klasse, die <xref:System.Windows.Forms.Form> von abgeleitet ist <xref:System.Windows.Forms.DataGridView> und ein- <xref:System.Windows.Forms.BindingSource> Steuerelement und eine-Komponente enthält.

    Im folgenden Codebeispiel wird die grundlegende Initialisierung und `Main` eine-Methode bereitstellt.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Implementieren Sie eine Methode in der Klassendefinition Ihres Formulars, um die Details der Verbindungs Herstellung mit der Datenbank zu verarbeiten.

    Dieses Codebeispiel verwendet eine `GetData` -Methode, die <xref:System.Data.DataTable> ein aufgefülltes Objekt zurückgibt. Stellen Sie sicher, dass Sie `connectionString` die Variable auf einen Wert festlegen, der für Ihre Datenbank geeignet ist.

    > [!IMPORTANT]
    > Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Die Verwendung der Windows-Authentifizierung (auch als integrierte Sicherheit bezeichnet) ist eine sicherere Methode zum Steuern des Zugriffs auf eine Datenbank. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Implementieren Sie einen Handler für das- <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> initialisiert, und richtet die Datenbindung ein.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Implementieren Sie Handler für das <xref:System.Windows.Forms.DataGridView> -Ereignis <xref:System.Windows.Forms.DataGridView.CellValidating> und <xref:System.Windows.Forms.DataGridView.CellEndEdit> das-Ereignis des Steuer Elements.

    Der <xref:System.Windows.Forms.DataGridView.CellValidating> Ereignishandler bestimmt, ob der Wert einer Zelle in der `CompanyName` Spalte leer ist. Wenn für den Zellwert die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> Überprüfung fehlschlägt, legen Sie die `true`-Eigenschaft der-Klasse auf fest. Dies bewirkt <xref:System.Windows.Forms.DataGridView> , dass das-Steuerelement verhindert, dass der Cursor die Zelle verlässt. Legen Sie <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> die-Eigenschaft in der Zeile auf eine erklärende Zeichenfolge fest. Dadurch wird ein Fehler Symbol mit einer QuickInfo angezeigt, die den Fehlertext enthält. Legen Sie im- <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> Ereignishandlerdie-EigenschaftderZeileaufdieleereZeichenfolgefest.<xref:System.Windows.Forms.DataGridView.CellEndEdit> Das <xref:System.Windows.Forms.DataGridView.CellEndEdit> Ereignis tritt nur auf, wenn die Zelle den Bearbeitungsmodus verlässt, was nicht möglich ist, wenn die Überprüfung fehlschlägt.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Testen der Anwendung

Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.

#### <a name="to-test-the-form"></a>So testen Sie das Formular

- Kompilieren Sie die Anwendung, und führen Sie sie aus.

  Es wird eine <xref:System.Windows.Forms.DataGridView> mit Daten aus der `Customers` Tabelle angezeigt. Wenn Sie auf eine Zelle in der `CompanyName` Spalte doppelklicken, können Sie den Wert bearbeiten. Wenn Sie alle Zeichen löschen und die Tab-Taste drücken, um die Zelle zu beenden <xref:System.Windows.Forms.DataGridView> , verhindert, dass Sie beendet werden. Wenn Sie eine nicht leere Zeichenfolge in die Zelle eingeben, können <xref:System.Windows.Forms.DataGridView> Sie mit dem-Steuerelement die Zelle beenden.

## <a name="next-steps"></a>Nächste Schritte

Diese Anwendung enthält grundlegende Kenntnisse über die <xref:System.Windows.Forms.DataGridView> Funktionen des-Steuer Elements. Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView> Steuer Elements auf verschiedene Weise anpassen:

- Ändern von Rahmen-und Header Stilen. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern Sie die Rahmen-und Rasterlinien Stile im Windows Forms DataGridView](change-the-border-and-gridline-styles-in-the-datagrid.md)-Steuerelement.

- Aktivieren oder Einschränken der Benutzereingaben für <xref:System.Windows.Forms.DataGridView> das Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Verhindern Sie das Hinzufügen und Löschen von Zeilen im Windows Forms DataGridView [-Steuer](prevent-row-addition-and-deletion-datagridview.md)Element, und Gewusst wie: Legen Sie die Spalten im Windows Forms DataGridView-Steuer](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Element als schreibgeschützt fest.

- Überprüfen Sie die Benutzereingaben auf datenbankbezogene Fehler. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)-Steuerelement auftreten.

- Verarbeiten Sie sehr große Datasets im virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element Windows Forms.

- Passen Sie die Darstellung von Zellen an. Weitere Informationen finden Sie unter [Vorgehensweise: Passen Sie die Darstellung von Zellen im Windows Forms DataGridView-](customize-the-appearance-of-cells-in-the-datagrid.md) Steuer [Element an, und Gewusst wie: Legen Sie Schriftart und Farbstile im Windows Forms DataGridView-](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)Steuerelement fest.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Validieren von Daten im Windows Forms DataGridView-Steuerelement](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView-Steuerelement auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
