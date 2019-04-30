---
title: 'Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: 9e803b6450fb8c9ade4adde5bf98fb1c3c62c861
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971274"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten
Behandeln von Fehlern aus dem zugrunde liegenden Datenspeicher ist eine erforderliche Funktion für eine Anwendung für die Eingabe von Daten. Die Windows-Formulare <xref:System.Windows.Forms.DataGridView> Steuerelement erleichtert dies durch das Verfügbarmachen von der <xref:System.Windows.Forms.DataGridView.DataError> -Ereignis, das ausgelöst wird, wenn der Datenspeicher Verletzung einer Einschränkung oder eine Geschäftsregel erkennt.  
  
 In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` -Tabelle in der Beispieldatenbank Northwind aus, und zeigen Sie sie in einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn ein Duplikat `CustomerID` Wert wird erkannt, in einer neuen oder vorhandenen bearbeiteten Zeile der <xref:System.Windows.Forms.DataGridView.DataError> -Ereignis ausgelöst, wird durch das Anzeigen von behandelt werden eine <xref:System.Windows.Forms.MessageBox> , der die Ausnahme beschreibt.  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Behandeln von Fehlern, die auftreten, während der Dateneingabe in das Windows Forms-DataGridView-Steuerelement](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
- Zugriff auf einen Server, der die Beispieldatenbank Northwind-SQL-Server verfügt.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Behandeln von Fehlern der Dateneingabe im DataGridView-Steuerelement  
  
1. Erstellen Sie eine abgeleitete Klasse <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement und ein <xref:System.Windows.Forms.BindingSource> Komponente.  
  
     Das folgende Codebeispiel stellt die grundlegende Initialisierung bereit und umfasst eine `Main` Methode.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2. Implementieren Sie eine Methode in Ihres Formulars Klassendefinition für die Verarbeitung der Details der Verbindung zur Datenbank.  
  
     Dieses Codebeispiel verwendet einen `GetData` Methode, die ein aufgefülltes zurückgibt <xref:System.Data.DataTable> Objekt. Achten Sie darauf, dass Sie festlegen, die `connectionString` Variablen ein Wert, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3. Implementieren Sie einen Handler für Ihres Formulars <xref:System.Windows.Forms.Form.Load> -Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> und richtet die Datenbindung.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4. Behandeln der <xref:System.Windows.Forms.DataGridView.DataError> Ereignis auf der <xref:System.Windows.Forms.DataGridView>.  
  
     Wenn der Kontext für den Fehler ein Commitvorgang ist, zeigen Sie den Fehler in einem <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
- Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sie sehen eine <xref:System.Windows.Forms.DataGridView> -Steuerelement mit Daten aus der Tabelle Customers gefüllt. Wenn Sie einen doppelten Wert für eingeben `CustomerID` und committen Sie die Bearbeitung, der Wert der Zelle wird automatisch zurückgesetzt, und sehen Sie eine <xref:System.Windows.Forms.MessageBox> , die die Dateneingabefehler anzeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung verfügt über einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelement auf verschiedene Weise:  
  
- Ändern von Rahmen und Header-Formaten. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern des Rahmen- und Rasterlinienstils in der Windows Forms DataGridView-Steuerelement](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Aktivieren oder Einschränken von Benutzereingaben in die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Verhindern des Hinzufügens der Zeile, und Löschen in der Windows Forms-DataGridView-Steuerelement](prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Festlegen von Spalten schreibgeschützt in der Windows Forms-DataGridView-Steuerelement](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Überprüfen Sie Benutzereingaben an das <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Überprüfen von Daten in der Windows Forms-DataGridView-Steuerelement](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
- Behandeln Sie sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von Standardzellenformaten für das Windows-DataGridView-Steuerelement Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement von Windows Forms auftreten](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Exemplarische Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
