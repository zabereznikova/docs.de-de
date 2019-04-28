---
title: 'Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: 99561490786f3f3569f272138001ea5ad8937410
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792261"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms
Möglicherweise möchten Sie häufig Tabellendaten anzeigen, die nicht aus einer Datenbank stammen. Beispielsweise empfiehlt es sich um den Inhalt eines zweidimensionalen Arrays von Zeichenfolgen anzuzeigen. Die <xref:System.Windows.Forms.DataGridView> -Klasse bietet eine einfache und äußerst anpassbare Möglichkeit zum Anzeigen von Daten ohne Bindung an eine Datenquelle. Diese exemplarische Vorgehensweise zeigt das Auffüllen einer <xref:System.Windows.Forms.DataGridView> steuern und verwalten Sie das Hinzufügen und Löschen von Zeilen in "ungebunden"-Modus. Standardmäßig kann Benutzer neue Zeilen hinzufügen. Um Zeilen zu verhindern, legen die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> Eigenschaft `false`.  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Erstellen eines ungebundenen Windows Forms-DataGridView-Steuerelements](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Verwendung ein ungebundenes DataGridView-Steuerelements  
  
1. Erstellen Sie eine abgeleitete Klasse <xref:System.Windows.Forms.Form> und enthält die folgenden Variablendeklarationen und `Main` Methode.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. Implementieren einer `SetupLayout` -Methode in der Klassendefinition Ihres Formulars, das Layout des Formulars einrichten.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. Erstellen Sie eine `SetupDataGridView` Methode zum Einrichten der <xref:System.Windows.Forms.DataGridView> Spalten und Eigenschaften.  
  
     Diese Methode fügt zunächst die <xref:System.Windows.Forms.DataGridView> -Steuerelement des Formulars <xref:System.Windows.Forms.Control.Controls%2A> Auflistung. Als Nächstes wird die Anzahl der anzuzeigenden Spalten mit festgelegt die <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> Eigenschaft. Das Standardformat für die Spaltenüberschriften festgelegt ist, durch Festlegen der <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, und <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> Eigenschaften der <xref:System.Windows.Forms.DataGridViewCellStyle> zurückgegebenes der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> Eigenschaft.  
  
     Layout und die Darstellung Eigenschaften festgelegt werden, und klicken Sie dann die Namen der Spalten zugewiesen werden. Wenn diese Methode beendet wird, die <xref:System.Windows.Forms.DataGridView> Steuerelement ist gefüllt werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. Erstellen Sie eine `PopulateDataGridView` Methode zum Hinzufügen von Zeilen, die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
     Jede Zeile stellt einen Titel und die dazugehörigen Informationen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. Mit dem Hilfsprogrammmethoden können Sie Ereignishandler anfügen.  
  
     Behandeln Sie die **hinzufügen** und **löschen** Schaltflächen <xref:System.Windows.Forms.Control.Click> Ereignisse, des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis und die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis.  
  
     Wenn die **hinzufügen** Schaltfläche <xref:System.Windows.Forms.Control.Click> -Ereignis ausgelöst wird, eine neue, leere Zeile hinzugefügt wird die <xref:System.Windows.Forms.DataGridView>.  
  
     Wenn die **löschen** Schaltfläche <xref:System.Windows.Forms.Control.Click> -Ereignis ausgelöst wird, wird die ausgewählte Zeile gelöscht, es sei denn, es ist die Zeile für neue Datensätze, die der Benutzer kann neue Zeilen hinzufügen. Diese Zeile ist immer die letzte Zeile in der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
     Wenn des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis wird ausgelöst, die `SetupLayout`, `SetupDataGridView`, und `PopulateDataGridView` Utility-Methoden aufgerufen werden.  
  
     Wenn die <xref:System.Windows.Forms.DataGridView.CellFormatting> -Ereignis ausgelöst wird, jede Zelle in der `Date` Spalte ist als ein langes Datumsformat formatiert, es sei denn, der den Wert der Zelle kann nicht analysiert werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
- Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sie sehen eine <xref:System.Windows.Forms.DataGridView> -Steuerelement, das den in aufgeführten Lieder angezeigt `PopulateDataGridView`. Sie können neue Zeilen mit Hinzufügen der **Zeile hinzufügen** Schaltfläche, und Sie können ausgewählte Zeilen mit Löschen der **Zeile löschen** Schaltfläche. Die ungebundenen <xref:System.Windows.Forms.DataGridView> Steuerelement Datenspeicher, und die Daten ist unabhängig von einer externen Quelle, z. B. eine <xref:System.Data.DataSet> oder ein Array.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung verfügt über einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelement auf verschiedene Weise:  
  
- Ändern von Rahmen und Header-Formaten. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern des Rahmen- und Rasterlinienstils in der Windows Forms DataGridView-Steuerelement](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Aktivieren oder Einschränken von Benutzereingaben in die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Verhindern des Hinzufügens der Zeile, und Löschen in der Windows Forms-DataGridView-Steuerelement](prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Festlegen von Spalten schreibgeschützt in der Windows Forms-DataGridView-Steuerelement](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Überprüfen Sie Benutzereingaben für Fehler im Zusammenhang mit Datenbank. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, die auftreten, während der Dateneingabe in das Windows Forms-DataGridView-Steuerelement](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
- Behandeln Sie sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von Standardzellenformaten für das Windows-DataGridView-Steuerelement Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Erstellen eines ungebundenen Windows Forms-DataGridView-Steuerelements](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
