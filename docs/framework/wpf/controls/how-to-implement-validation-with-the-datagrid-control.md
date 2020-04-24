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
ms.openlocfilehash: 38b4c9cd7679f0d8da9b18fb5bd6bb729d33ed54
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646101"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement
Mit <xref:System.Windows.Controls.DataGrid> dem Steuerelement können Sie die Validierung sowohl auf Zellen- als auch auf Zeilenebene durchführen. Bei der Validierung auf Zellenebene überprüfen Sie einzelne Eigenschaften eines gebundenen Datenobjekts, wenn ein Benutzer einen Wert aktualisiert. Bei der Überprüfung auf Zeilenebene überprüfen Sie ganze Datenobjekte, wenn ein Benutzer Änderungen an einer Zeile festgibt. Sie können auch benutzerdefiniertes visuelles Feedback für Validierungsfehler bereitstellen oder das standardmäßige visuelle Feedback verwenden, das das <xref:System.Windows.Controls.DataGrid> Steuerelement bereitstellt.  
  
 In den folgenden Verfahren wird <xref:System.Windows.Controls.DataGrid> beschrieben, wie Validierungsregeln auf Bindungen angewendet und das visuelle Feedback angepasst werden.  
  
### <a name="to-validate-individual-cell-values"></a>So überprüfen Sie einzelne Zellwerte  
  
- Geben Sie eine oder mehrere Validierungsregeln für die Bindung an, die für eine Spalte verwendet wird. Dies ähnelt der Überprüfung von Daten in einfachen Steuerelementen, wie unter [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md)beschrieben.  
  
     Das folgende Beispiel <xref:System.Windows.Controls.DataGrid> zeigt ein Steuerelement mit vier Spalten, die an unterschiedliche Eigenschaften eines Geschäftsobjekts gebunden sind. Drei der Spalten <xref:System.Windows.Controls.ExceptionValidationRule> geben die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> an, indem die Eigenschaft auf festgelegt `true`wird.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Wenn ein Benutzer einen ungültigen Wert eingibt (z. B. eine Nicht-Ganzzahl in der Spalte Kurs-ID), wird ein roter Rahmen um die Zelle herum angezeigt. Sie können dieses Standard-Validierungsfeedback wie im folgenden Verfahren beschrieben ändern.  
  
### <a name="to-customize-cell-validation-feedback"></a>So passen Sie das Feedback zur Zellvalidierung an  
  
- Legen Sie die <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> Eigenschaft der Spalte auf einen Stil fest, der für das Bearbeitungssteuerelement der Spalte geeignet ist. Da die Bearbeitungssteuerelemente zur Laufzeit erstellt werden, können Sie die <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> angefügte Eigenschaft nicht wie bei einfachen Steuerelementen verwenden.  
  
     Im folgenden Beispiel wird das vorherige Beispiel aktualisiert, indem ein Fehlerstil hinzugefügt wird, der von den drei Spalten mit Validierungsregeln gemeinsam genutzt wird. Wenn ein Benutzer einen ungültigen Wert eingibt, ändert der Stil die Zellenhintergrundfarbe und fügt eine QuickInfo hinzu. Beachten Sie die Verwendung eines Triggers, um zu bestimmen, ob ein Validierungsfehler vorliegt. Dies ist erforderlich, da derzeit keine dedizierte Fehlervorlage für Zellen vorhanden ist.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Sie können umfangreichere Anpassungen <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> implementieren, indem Sie die von der Spalte verwendete ersetzen.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>So überprüfen Sie mehrere Werte in einer Zeile  
  
1. Implementieren <xref:System.Windows.Controls.ValidationRule> Sie eine Unterklasse, die mehrere Eigenschaften des gebundenen Datenobjekts überprüft. Geben <xref:System.Windows.Controls.ValidationRule.Validate%2A> Sie in der `value` Methodenimplementierung <xref:System.Windows.Data.BindingGroup> den Parameterwert in eine Instanz um. Sie können dann über die <xref:System.Windows.Data.BindingGroup.Items%2A> Eigenschaft auf das Datenobjekt zugreifen.  
  
     Im folgenden Beispiel wird dieser `StartDate` Prozess veranschaulicht, `Course` um zu `EndDate` überprüfen, ob der Eigenschaftswert für ein Objekt älter als sein Eigenschaftswert ist.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Fügen Sie der <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> Auflistung die Validierungsregel hinzu. Die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Eigenschaft bietet direkten <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> Zugriff <xref:System.Windows.Data.BindingGroup> auf die Eigenschaft einer Instanz, die alle vom Steuerelement verwendeten Bindungen gruppiert.  
  
     Im folgenden Beispiel <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> wird die Eigenschaft in XAML festgelegt. Die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> Eigenschaft ist <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so festgelegt, dass die Überprüfung erst erfolgt, nachdem das gebundene Datenobjekt aktualisiert wurde.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Wenn ein Benutzer ein Enddatum angibt, das vor dem Startdatum liegt, wird im Zeilenkopf ein rotes Ausrufezeichen (!) angezeigt. Sie können dieses Standard-Validierungsfeedback wie im folgenden Verfahren beschrieben ändern.  
  
### <a name="to-customize-row-validation-feedback"></a>So passen Sie das Feedback zur Zeilenvalidierung an  
  
- Legen Sie die <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>-Eigenschaft fest. Mit dieser Eigenschaft können Sie das <xref:System.Windows.Controls.DataGrid> Feedback zur Zeilenüberprüfung für einzelne Steuerelemente anpassen. Sie können auch mehrere Steuerelemente beeinflussen, indem <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> Sie einen impliziten Zeilenstil verwenden, um die Eigenschaft festzulegen.  
  
     Im folgenden Beispiel wird das standardmäßige Zeilenvalidierungsfeedback durch einen sichtbareren Indikator ersetzt. Wenn ein Benutzer einen ungültigen Wert eingibt, wird ein roter Kreis mit einem weißen Ausrufezeichen in der Zeilenüberschrift angezeigt. Dies tritt sowohl für Zeilen- als auch für Zellenvalidierungsfehler auf. Die zugehörige Fehlermeldung wird in einer QuickInfo angezeigt.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel bietet eine vollständige Demonstration für die Zellen- und Zeilenüberprüfung. Die `Course` Klasse stellt ein Beispieldatenobjekt bereit, das <xref:System.ComponentModel.IEditableObject> zur Unterstützung von Transaktionen implementiert wird. Das <xref:System.Windows.Controls.DataGrid> Steuerelement interagiert mit, <xref:System.ComponentModel.IEditableObject> damit Benutzer Änderungen durch Drücken von ESC rückgängig machen können.  
  
> [!NOTE]
> Wenn Sie Visual Basic verwenden, ersetzen Sie in der ersten `x:Class="DataGridValidation.MainWindow"` `x:Class="MainWindow"`Zeile von MainWindow.xaml durch .  
  
 Um die Validierung zu testen, versuchen Sie Folgendes:  
  
- Geben Sie in der Spalte Kurs-ID einen Nicht-Ganzzahlwert ein.  
  
- Geben Sie in der Spalte Enddatum ein Datum ein, das vor dem Startdatum liegt.  
  
- Löschen Sie den Wert in Kurs-ID, Startdatum oder Enddatum.  
  
- Um einen ungültigen Zellenwert rückgängig zu machen, setzen Sie den Cursor wieder in die Zelle, und drücken Sie die ESC-Taste.  
  
- Um Änderungen für eine ganze Zeile rückgängig zu machen, wenn sich die aktuelle Zelle im Bearbeitungsmodus befindet, drücken Sie zweimal die ESC-Taste.  
  
- Wenn ein Validierungsfehler auftritt, bewegen Sie den Mauszeiger über den Indikator im Zeilenkopf, um die zugehörige Fehlermeldung anzuzeigen.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Implementieren der Bindungsvalidierung](../data/how-to-implement-binding-validation.md)
- [Implementieren der Validierungslogik für benutzerdefinierte Objekte](../data/how-to-implement-validation-logic-on-custom-objects.md)
