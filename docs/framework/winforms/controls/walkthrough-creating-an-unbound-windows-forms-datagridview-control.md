---
title: Erstellen eines ungebundenen DataGridView-Steuer Elements
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
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740174"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms
Möglicherweise möchten Sie häufig Tabellendaten anzeigen, die nicht aus einer Datenbank stammen. Beispielsweise möchten Sie möglicherweise den Inhalt eines zweidimensionalen Arrays von Zeichen folgen anzeigen. Die <xref:System.Windows.Forms.DataGridView>-Klasse bietet eine einfache und hochgradig anpassbare Möglichkeit zum Anzeigen von Daten ohne Bindung an eine Datenquelle. In dieser exemplarischen Vorgehensweise wird gezeigt, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement aufgefüllt und das Hinzufügen und Löschen von Zeilen im "ungebundenen" Modus verwaltet wird. Standardmäßig kann der Benutzer neue Zeilen hinzufügen. Legen Sie zum Verhindern der Zeilen Addition fest, dass die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>-Eigenschaft `false`ist.  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Erstellen eines ungebundenen Windows Forms DataGridView-Steuer](how-to-create-an-unbound-windows-forms-datagridview-control.md)Elements.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>So verwenden Sie ein ungebundenes DataGridView-Steuerelement  
  
1. Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und die folgenden Variablen Deklarationen und `Main` Methode enthält.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. Implementieren Sie eine `SetupLayout`-Methode in der Klassendefinition Ihres Formulars, um das Layout des Formulars einzurichten.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. Erstellen Sie eine `SetupDataGridView`-Methode, um die <xref:System.Windows.Forms.DataGridView> Spalten und Eigenschaften einzurichten.  
  
     Diese Methode fügt der <xref:System.Windows.Forms.Control.Controls%2A> Auflistung des Formulars zunächst das <xref:System.Windows.Forms.DataGridView>-Steuerelement hinzu. Als nächstes wird die Anzahl der anzuzeigenden Spalten mithilfe der <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>-Eigenschaft festgelegt. Der Standardstil für die Spaltenheader wird festgelegt, indem die Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>und <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> der <xref:System.Windows.Forms.DataGridViewCellStyle> festgelegt werden, die von der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>-Eigenschaft zurückgegeben werden.  
  
     Layout-und Darstellungs Eigenschaften werden festgelegt, und dann werden die Spaltennamen zugewiesen. Wenn diese Methode beendet wird, kann das <xref:System.Windows.Forms.DataGridView> Steuerelement aufgefüllt werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. Erstellen Sie eine `PopulateDataGridView`-Methode, um dem <xref:System.Windows.Forms.DataGridView> Steuerelement Zeilen hinzuzufügen.  
  
     Jede Zeile stellt einen Song und die zugehörigen Informationen dar.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. Wenn die Hilfsprogrammmethoden vorhanden sind, können Sie Ereignishandler anfügen.  
  
     Sie behandeln die <xref:System.Windows.Forms.Control.Click> Ereignisse der Schaltflächen **Hinzufügen** und **Löschen** , das <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars und das <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis des <xref:System.Windows.Forms.DataGridView>-Steuer Elements.  
  
     Wenn das <xref:System.Windows.Forms.Control.Click>-Ereignis der Schaltfläche " **Hinzufügen** " ausgelöst wird, wird der <xref:System.Windows.Forms.DataGridView>eine neue leere Zeile hinzugefügt.  
  
     Wenn das <xref:System.Windows.Forms.Control.Click> Ereignis der **Lösch** Schaltfläche ausgelöst wird, wird die ausgewählte Zeile gelöscht, es sei denn, es handelt sich um die Zeile für neue Datensätze, sodass der Benutzer neue Zeilen hinzufügen kann. Diese Zeile ist immer die letzte Zeile im <xref:System.Windows.Forms.DataGridView>-Steuerelement.  
  
     Wenn das <xref:System.Windows.Forms.Form.Load>-Ereignis des Formulars ausgelöst wird, werden die Methoden `SetupLayout`, `SetupDataGridView`und `PopulateDataGridView` Utility aufgerufen.  
  
     Wenn das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis ausgelöst wird, wird jede Zelle in der Spalte `Date` als langes Datum formatiert, es sei denn, der Wert der Zelle kann nicht analysiert werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
- Drücken Sie die Taste F5, um die Anwendung auszuführen.  
  
     Sie sehen ein <xref:System.Windows.Forms.DataGridView> Steuerelement, in dem die in `PopulateDataGridView`aufgeführten Titel angezeigt werden. Mit der Schaltfläche **Zeile hinzufügen** können Sie neue Zeilen hinzufügen, und Sie können die ausgewählten Zeilen mit der Schaltfläche **Zeile löschen** löschen. Das ungebundene <xref:System.Windows.Forms.DataGridView>-Steuerelement ist der Datenspeicher, und seine Daten sind unabhängig von einer externen Quelle, z. b. ein <xref:System.Data.DataSet> oder ein Array.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung bietet grundlegende Kenntnisse über die Funktionen des <xref:System.Windows.Forms.DataGridView>-Steuer Elements. Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView> Steuer Elements auf verschiedene Weise anpassen:  
  
- Ändern von Rahmen-und Header Stilen. Weitere Informationen finden Sie unter Gewusst [wie: Ändern der Rahmen-und Rasterlinien Stile im Windows Forms DataGridView-Steuer](change-the-border-and-gridline-styles-in-the-datagrid.md)Element.  
  
- Aktiviert oder schränkt die Benutzereingabe auf das <xref:System.Windows.Forms.DataGridView> Steuerelement ein. Weitere Informationen finden Sie unter Gewusst [wie: verhindern des Hinzufügens und Löschens von Zeilen im Windows Forms DataGridView-Steuer](prevent-row-addition-and-deletion-datagridview.md)Element und Gewusst wie: Festlegen von schreibgeschützten [Spalten im Windows Forms DataGridView-Steuer](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Element.  
  
- Überprüfen Sie die Benutzereingaben auf datenbankbezogene Fehler. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Behandeln von Fehlern, die während der Dateneingabe im Windows Forms DataGridView-Steuerelement auftreten](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
- Verarbeiten Sie sehr große Datasets im virtuellen Modus. Weitere Informationen finden Sie unter Exemplarische [Vorgehensweise: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element.  
  
- Passen Sie die Darstellung von Zellen an. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen der Darstellung von Zellen im Windows Forms DataGridView-Steuer](customize-the-appearance-of-cells-in-the-datagrid.md) Element und Gewusst [wie: Festlegen von Standardzellen Formaten für das Windows Forms DataGridView-Steuer](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)Element.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
