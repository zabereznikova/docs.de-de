---
title: 'Exemplarische Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: f9bea4ef90a455f228fd095ad6a5c022b95493d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681832"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms
Wenn Sie Data-Eintrag-Funktionalität für Benutzer angezeigt wird, müssen Sie häufig in Ihr Formular eingegebenen Daten zu überprüfen. Die <xref:System.Windows.Forms.DataGridView> -Klasse bietet eine bequeme Möglichkeit, die Validierung ausführen, bevor Daten an den Datenspeicher übertragen werden. Sie können Daten validieren, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellValidating> -Ereignis, das ausgelöst wird, indem die <xref:System.Windows.Forms.DataGridView> Wenn die aktuelle Zelle geändert wird.  
  
 In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` -Tabelle in der Beispieldatenbank Northwind aus, und zeigen Sie sie in einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn ein Benutzer eine Zelle in bearbeitet die `CompanyName` Spalten- und versucht, die die Zelle, lassen die <xref:System.Windows.Forms.DataGridView.CellValidating> -Ereignishandler überprüft neue Zeichenfolge mit dem Firmennamen, stellen Sie sicher, dass es nicht leer ist; wenn der neue Wert eine leere Zeichenfolge ist die <xref:System.Windows.Forms.DataGridView> wird verhindert, dass den Cursor des Benutzers die Zelle verlässt, bis eine nicht leere Zeichenfolge eingegeben wird.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren möchten, finden Sie unter [Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server, der die Beispieldatenbank Northwind-SQL-Server verfügt.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>So überprüfen Sie Daten in einem DataGridView eingegeben  
  
1.  Erstellen Sie eine abgeleitete Klasse <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement und ein <xref:System.Windows.Forms.BindingSource> Komponente.  
  
     Das folgende Codebeispiel stellt die grundlegende Initialisierung bereit und umfasst eine `Main` Methode.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Implementieren Sie eine Methode in Ihres Formulars Klassendefinition für die Verarbeitung der Details der Verbindung zur Datenbank.  
  
     Dieses Codebeispiel verwendet einen `GetData` Methode, die ein aufgefülltes zurückgibt <xref:System.Data.DataTable> Objekt. Achten Sie darauf, dass Sie festlegen, die `connectionString` Variablen ein Wert, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Mithilfe der Windows-Authentifizierung, auch bekannt als integrierte Sicherheit ist eine sicherere Methode zum Steuern des Zugriffs auf eine Datenbank. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implementieren Sie einen Handler für Ihres Formulars <xref:System.Windows.Forms.Form.Load> -Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> und richtet die Datenbindung.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implementieren Sie Ereignishandler für die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellValidating> und <xref:System.Windows.Forms.DataGridView.CellEndEdit> Ereignisse.  
  
     Die <xref:System.Windows.Forms.DataGridView.CellValidating> -Ereignishandler ist, in denen Sie bestimmen, ob der Wert einer Zelle in der `CompanyName` Spalte ist leer. Wenn der Wert der Zelle die Validierung fehlschlägt, legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> -Klasse `true`. Dies bewirkt, dass die <xref:System.Windows.Forms.DataGridView> Steuerelement, um zu verhindern, dass den Cursor die Zelle verlässt. Legen Sie die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> Eigenschaft auf die Zeile, um eine aufschlussreiche Zeichenfolge. Dies zeigt ein Fehlersymbol mit einer QuickInfo, die den Fehlertext enthält. In der <xref:System.Windows.Forms.DataGridView.CellEndEdit> ereignishandlers, der <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> Eigenschaft in der Zeile auf eine leere Zeichenfolge. Die <xref:System.Windows.Forms.DataGridView.CellEndEdit> Ereignis tritt auf, nur wenn die Zelle den Bearbeitungsmodus verlässt die es nicht möglich, wenn die Validierung fehlschlägt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sie sehen eine <xref:System.Windows.Forms.DataGridView> gefüllt mit Daten aus der `Customers` Tabelle. Beim Doppelklicken auf eine Zelle in der `CompanyName` Spalte können Sie den Wert bearbeiten. Wenn Sie alle Zeichen löschen, und drücken die TAB-Taste, um die Zelle, beenden die <xref:System.Windows.Forms.DataGridView> verhindert, dass Sie beendet wird. Wenn Sie eine nicht leere Zeichenfolge in die Zelle, geben Sie die <xref:System.Windows.Forms.DataGridView> -Steuerelement können Sie die Zelle verlassen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung verfügt über einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelement auf verschiedene Weise:  
  
-   Ändern von Rahmen und Header-Formaten. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern des Rahmen- und Rasterlinienstils in der Windows Forms DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Einschränken von Benutzereingaben in die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Verhindern des Hinzufügens der Zeile, und Löschen in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Festlegen von Spalten schreibgeschützt in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen Sie Benutzereingaben für Fehler im Zusammenhang mit Datenbank. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, die auftreten, während der Dateneingabe in das Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Behandeln Sie sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement von Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
