---
title: 'Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 00d09c62aae67e3438816409c95ccf96050b3206
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770876"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement
Die <xref:System.Windows.Controls.DataGrid> -Steuerelement können Sie eine Überprüfung auf die Zelle und die Zeile Ebene durchführen. Überprüfen Sie mit Überprüfung auf Zellenebene einzelne Eigenschaften eines Objekts an Sie gebundenen Daten aus, wenn ein Benutzer einen Wert aktualisiert. Überprüfen Sie mit Überprüfung auf Zeilenebene gesamte Datenobjekte aus, wenn ein Benutzer auf eine Zeile Änderungen ein Commit ausgeführt. Sie können auch benutzerdefinierte visuelles Feedback für Validierungsfehler oder verwenden Sie das standardmäßige visuelle Feedback, das die <xref:System.Windows.Controls.DataGrid> gesteuert.  
  
 Die folgenden Verfahren wird beschrieben, wie Anwenden von Validierungsregeln zum <xref:System.Windows.Controls.DataGrid> Bindungen und Anpassen des visuellen Feedbacks.  
  
### <a name="to-validate-individual-cell-values"></a>Zum Überprüfen der Werte der einzelnen Zellen  
  
- Geben Sie einen oder mehrere Validierungsregeln für die Bindung mit einer Spalte verwendet. Dies ist vergleichbar mit Validieren von Daten in einfachen Steuerelementen, wie in beschrieben [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
     Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.DataGrid> -Steuerelement mit vier Spalten, die auf verschiedene Eigenschaften eines Geschäftsobjekts gebunden. Drei Spalten geben die <xref:System.Windows.Controls.ExceptionValidationRule> durch Festlegen der <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> Eigenschaft `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Wenn ein Benutzer einen ungültigen Wert (z. B. eine nicht ganzzahlige in der Kurs-ID-Spalte) eingibt, wird ein roter Rahmen um die Zelle angezeigt. Sie können dieses Feedback der Standard-Überprüfung wie im folgenden Verfahren beschrieben ändern.  
  
### <a name="to-customize-cell-validation-feedback"></a>Die Überprüfung Zellenvalidierungsfeedback anpassen.  
  
- Legen Sie die <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> Eigenschaft, um einen Stil geeignet, für die Spalte Bearbeitungssteuerelement der. Da die Bearbeitung von Steuerelementen zur Laufzeit erstellt werden, können keine der <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> angefügte Eigenschaft wie bei einfachen Steuerelementen.  
  
     Das folgende Beispiel aktualisiert die im vorherige Beispiel durch das Hinzufügen eines Fehler-Stils, die von den drei Spalten mit Validierungsregeln gemeinsam verwendet werden. Wenn ein Benutzer einen ungültigen Wert eingibt, wird das Format ändert die Hintergrundfarbe der Zelle, und fügt eine QuickInfo. Beachten Sie die Verwendung eines Triggers, um festzustellen, ob ein Überprüfungsfehler vorliegt. Dies ist erforderlich, da es derzeit keine dedizierten Fehlervorlage für Zellen.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Sie können umfangreichere Anpassung implementieren, indem Sie ersetzt die <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> von der Spalte verwendet wird.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Um mehrere Werte in einer einzelnen Zeile zu überprüfen.  
  
1. Implementieren einer <xref:System.Windows.Controls.ValidationRule> Unterklasse, die mehrere Eigenschaften des gebundenen Objekts überprüft. In Ihrer <xref:System.Windows.Controls.ValidationRule.Validate%2A> methodenimplementierung, wandeln die `value` Parameterwert, der eine <xref:System.Windows.Data.BindingGroup> Instanz. Sie können dann zugreifen, das Datenobjekt mithilfe der <xref:System.Windows.Data.BindingGroup.Items%2A> Eigenschaft.  
  
     Das folgende Beispiel zeigt diesen Vorgang aus, um zu überprüfen, ob die `StartDate` Eigenschaftswert für eine `Course` -Objekt liegt vor dessen `EndDate` -Eigenschaftswert.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Fügen Sie die Validierungsregel dem <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> Auflistung. Die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Eigenschaft bietet direkten Zugriff auf die <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> Eigenschaft eine <xref:System.Windows.Data.BindingGroup> -Instanz, die alle vom Steuerelement verwendeten Bindungen gruppiert.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> -Eigenschaft in XAML. Die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , damit die Überprüfung wird nur verwendet werden, nachdem das gebundene Datenobjekt, das aktualisiert wurde.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Wenn ein Benutzer ein Enddatum angegeben ist, die vor dem Startdatum liegt, wird ein rotes Ausrufezeichen (!) in der Zeilenheader angezeigt. Sie können dieses Feedback der Standard-Überprüfung wie im folgenden Verfahren beschrieben ändern.  
  
### <a name="to-customize-row-validation-feedback"></a>Anpassen von Zeile Überprüfung feedback  
  
- Legen Sie die <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>-Eigenschaft fest. Mit dieser Eigenschaft können Sie anpassen, Zeile Überprüfung Feedback für einzelne <xref:System.Windows.Controls.DataGrid> Steuerelemente. Sie können auch mehrere Steuerelemente beeinflussen, mithilfe eines impliziten Zeilen-Stils zum Festlegen der <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> Eigenschaft.  
  
     Im folgende Beispiel ersetzt das standardmäßige Zeile Überprüfung Feedback mit einem Indikator, der besser sichtbar. Wenn ein Benutzer einen ungültigen Wert eingibt, wird ein roter Kreis mit einem weißen Ausrufezeichen in der Zeilenheader angezeigt. Dies tritt auf, für sowohl Zeilen- und Zellenebene Validierungsfehler. Die entsprechende Fehlermeldung wird in einer QuickInfo angezeigt.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel stellt eine vollständige Demo für die Überprüfung von Zellen- und Zeilenoperationen bereit. Die `Course` -Klasse stellt ein Beispiel-Datenobjekt, das implementiert <xref:System.ComponentModel.IEditableObject> zur Unterstützung von Transaktionen. Die <xref:System.Windows.Controls.DataGrid> Steuerelement interagiert mit <xref:System.ComponentModel.IEditableObject> Benutzer Änderungen durch Drücken der ESC-TASTE rückgängig machen können.  
  
> [!NOTE]
>  Ersetzen Sie bei Verwendung von Visual Basic in der ersten Zeile der Datei "MainWindow.xaml" `x:Class="DataGridValidation.MainWindow"` mit `x:Class="MainWindow"`.  
  
 Um die Überprüfung zu testen, gehen Sie folgendermaßen vor:  
  
- Geben Sie in der Kurs-ID-Spalte einen nicht ganzzahligen Wert ein.  
  
- Geben Sie in der Spalte mit Enddatum und ein Datum, das vor dem Startdatum liegt.  
  
- Löschen Sie den Wert im Kurs-ID, Start- oder Enddatum an.  
  
- Um einen ungültigen Zellenwert rückgängig zu machen, platzieren Sie den Cursor in die Zelle, und drücken Sie die ESC-Taste.  
  
- Drücken Sie die ESC-Taste zweimal, zum Rückgängigmachen von Änderungen für eine gesamte Zeile, wenn die aktuelle Zelle im Bearbeitungsmodus befindet.  
  
- Tritt ein Validierungsfehler auf, verschieben Sie den Mauszeiger über dem Indikator in der zugehörigen Fehlermeldung finden Sie unter den Zeilenkopf ein.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Datenbindung](../data/data-binding-wpf.md)
- [Implementieren der Bindungsvalidierung](../data/how-to-implement-binding-validation.md)
- [Implementieren von Validierungslogik für benutzerdefinierte Objekte](../data/how-to-implement-validation-logic-on-custom-objects.md)
