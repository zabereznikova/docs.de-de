---
title: 'Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2ede616b311119d174534e53cb3aaf9e366c7c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms
Wenn Sie Data-Eintrag-Funktionalität für Benutzer anzeigen, müssen Sie häufig zum Überprüfen der Daten in das Formular eingegeben. Die <xref:System.Windows.Forms.DataGridView> -Klasse bietet eine einfache Möglichkeit, die Validierung ausführen, bevor Daten in den Datenspeicher übertragen werden. Überprüfen von Daten durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellValidating> Ereignis, das ausgelöst wird, indem Sie die <xref:System.Windows.Forms.DataGridView> Wenn sich die aktive Zelle ändert.  
  
 In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` -Tabelle in der Northwind-Beispieldatenbank und angezeigt werden können, die in einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn ein Benutzer eine Zelle in bearbeitet die `CompanyName` Spalte und versucht, die die Zelle verlassen der <xref:System.Windows.Forms.DataGridView.CellValidating> Ereignishandler überprüfen Sie eine neue Zeichenfolge mit dem Firmennamen, stellen Sie sicher, dass es nicht leer ist; wenn der neue Wert eine leere Zeichenfolge ist die <xref:System.Windows.Forms.DataGridView> wird verhindert, dass Cursor des Benutzers die Zelle verlässt, bis eine nicht leere Zeichenfolge eingegeben wird.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server, der die Northwind-SQL Server-Beispieldatenbank ist.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>So validieren Sie Daten in einem DataGridView eingegeben  
  
1.  Erstellen Sie eine Klasse, die abgeleitet <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement und ein <xref:System.Windows.Forms.BindingSource> Komponente.  
  
     Das folgende Codebeispiel stellt die grundlegende Initialisierung bereit und enthält eine `Main` Methode.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Implementieren Sie eine Methode, in dem Formular Klassendefinition für die Behandlung der Details zum Herstellen einer Verbindung mit der Datenbank.  
  
     Dieses Codebeispiel verwendet eine `GetData` Methode, die ein aufgefülltes zurückgibt <xref:System.Data.DataTable> Objekt. Achten Sie darauf, dass Sie legen die `connectionString` -Variable auf einen Wert, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Mithilfe der Windows-Authentifizierung, auch bekannt als integrierte Sicherheit ist eine sicherere Methode zum Steuern des Zugriffs auf eine Datenbank. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implementieren Sie einen Handler für Ihr Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> und dem Datenbindung eingerichtet.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implementieren Sie Ereignishandler für die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellValidating> und <xref:System.Windows.Forms.DataGridView.CellEndEdit> Ereignisse.  
  
     Die <xref:System.Windows.Forms.DataGridView.CellValidating> -Ereignishandler ist, in denen Sie bestimmen, ob der Wert einer Zelle in der `CompanyName` Spalte ist leer. Bei einem Überprüfungsfehler der Zellenwert Festlegen der <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> Klasse `true`. Dies bewirkt, dass die <xref:System.Windows.Forms.DataGridView> Steuerelement, um zu verhindern, dass den Cursor die Zelle verlässt. Legen Sie die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> Eigenschaft auf die Zeile, um eine erklärende Zeichenfolge. Dies zeigt ein Fehlersymbol mit einer QuickInfo, die den Fehlertext enthält. In der <xref:System.Windows.Forms.DataGridView.CellEndEdit> legen Sie Ereignishandler, d. h. die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> Eigenschaft in der Zeile auf die leere Zeichenfolge. Die <xref:System.Windows.Forms.DataGridView.CellEndEdit> Ereignis tritt auf, nur wenn die Zelle den Bearbeitungsmodus verlässt die es nicht möglich, wenn die Validierung fehlschlägt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sehen Sie eine <xref:System.Windows.Forms.DataGridView> gefüllt mit Daten aus der `Customers` Tabelle. Beim Doppelklicken auf eine Zelle in der `CompanyName` Spalte können Sie den jeweiligen Wert bearbeiten. Wenn Sie alle Zeichen löschen, und drücken Sie die TAB-Taste, um die Zelle verlassen der <xref:System.Windows.Forms.DataGridView> verhindert, dass Sie beendet. Wenn Sie eine nicht leere Zeichenfolge in die Zelle eingeben der <xref:System.Windows.Forms.DataGridView> -Steuerelement können Sie die Zelle verlassen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung erhalten Sie einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelements auf unterschiedliche Weise:  
  
-   Ändern von Formaten für Rahmen und Header. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Rahmen- und Rasterlinienstils im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Einschränken von Benutzereingaben an das <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [wie: verhindern Hinzufügens und Löschens im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Stellen Spalten schreibgeschützter im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen von Benutzereingaben für Fehler im Zusammenhang mit Datenbank an. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, auftreten, während der Dateneingabe im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Behandeln von sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Dateneingabe im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Überprüfen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)  
 [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
