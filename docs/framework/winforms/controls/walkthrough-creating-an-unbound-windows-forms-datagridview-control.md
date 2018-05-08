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
ms.openlocfilehash: 26c2241f4b0a3b23255de15b3d0c9f8bdd15de02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms
Möglicherweise möchten Sie häufig Tabellendaten anzeigen, die nicht aus einer Datenbank stammen. Beispielsweise empfiehlt es sich um den Inhalt des ein zweidimensionales Array von Zeichenfolgen anzuzeigen. Die <xref:System.Windows.Forms.DataGridView> -Klasse bietet eine einfache und hochgradig anpassungsfähiger Möglichkeit zum Anzeigen von Daten ohne Bindung an eine Datenquelle. In dieser exemplarischen Vorgehensweise wird gezeigt, wie zum Auffüllen einer <xref:System.Windows.Forms.DataGridView> steuern und verwalten Sie das Hinzufügen und Löschen von Zeilen im "ungebundenen" Modus. Standardmäßig kann Benutzer neue Zeilen hinzufügen. Zum Hinzufügen von Zeilen zu verhindern, legen Sie die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> Eigenschaft ist `false`.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Verwenden ein ungebundenes DataGridView-Steuerelements  
  
1.  Erstellen Sie eine Klasse, die abgeleitet <xref:System.Windows.Forms.Form> und enthält die folgenden Variablendeklarationen und `Main` Methode.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implementieren einer `SetupLayout` Methode in der Klassendefinition zum Einrichten des Formulars Layout Ihres Formulars.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Erstellen einer `SetupDataGridView` Methode zum Einrichten der <xref:System.Windows.Forms.DataGridView> Spalten und Eigenschaften.  
  
     Diese Methode fügt zunächst die <xref:System.Windows.Forms.DataGridView> Steuerelement dem Formular <xref:System.Windows.Forms.Control.Controls%2A> Auflistung. Als Nächstes wird die Anzahl der anzuzeigenden Spalten mit festgelegt die <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> Eigenschaft. Das Standardformat für die Spaltenheader wird festgelegt, durch Festlegen der <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, und <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> Eigenschaften der <xref:System.Windows.Forms.DataGridViewCellStyle> zurückgegebenes der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> Eigenschaft.  
  
     Layout und die Darstellung Eigenschaften festgelegt sind, und klicken Sie dann die Spaltennamen zugeordnet sind. Wenn diese Methode beendet wird, die <xref:System.Windows.Forms.DataGridView> Steuerelement ist bereit, aufgefüllt werden soll.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Erstellen einer `PopulateDataGridView` Methode zum Hinzufügen von Zeilen, die <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
     Jede Zeile stellt einen Titel und die dazugehörigen Informationen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Mit den Hilfsmethoden vorhanden können Sie Ereignishandler anfügen.  
  
     Behandeln Sie das **hinzufügen** und **löschen** Schaltflächen <xref:System.Windows.Forms.Control.Click> Ereignisse, die des Formulars <xref:System.Windows.Forms.Form.Load> -Ereignis und die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis.  
  
     Wenn die **hinzufügen** Schaltfläche <xref:System.Windows.Forms.Control.Click> Ereignis wird ausgelöst, eine neue, leere Zeile hinzugefügt wird die <xref:System.Windows.Forms.DataGridView>.  
  
     Wenn die **löschen** Schaltfläche <xref:System.Windows.Forms.Control.Click> Ereignis wird ausgelöst, wird die ausgewählte Zeile gelöscht, es sei denn, es ist die Zeile für neue Datensätze, wodurch der Benutzer kann neue Zeilen hinzufügen. Diese Zeile ist immer die letzte Zeile in der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
     Wenn des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis wird ausgelöst, die `SetupLayout`, `SetupDataGridView`, und `PopulateDataGridView` Utility-Methoden aufgerufen werden.  
  
     Wenn die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis wird ausgelöst, jede Zelle in der `Date` Spalte ist als ein langes Datumsformat formatiert, es sei denn, der Wert der Zelle kann nicht analysiert werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelemente aus, die Titel in aufgeführten `PopulateDataGridView`. Sie können neue Zeilen mit Hinzufügen der **Zeile hinzufügen** Schaltfläche, und Sie können ausgewählte Zeilen mit Löschen der **Zeile löschen** Schaltfläche. Die ungebundenen <xref:System.Windows.Forms.DataGridView> Steuerelement Datenspeicher, und seine Daten ist unabhängig von einer externen Quelle, z. B. eine <xref:System.Data.DataSet> oder ein Array.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung erhalten Sie einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelements auf unterschiedliche Weise:  
  
-   Ändern von Formaten für Rahmen und Header. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Rahmen- und Rasterlinienstils im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Einschränken von Benutzereingaben an das <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [wie: verhindern Hinzufügens und Löschens im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Stellen Spalten schreibgeschützter im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen von Benutzereingaben für Fehler im Zusammenhang mit Datenbank an. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, auftreten, während der Dateneingabe im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Behandeln von sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von standardmäßigen Zellenstilen für DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)  
 [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
