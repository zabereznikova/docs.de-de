---
title: 'Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement'
description: Erfahren Sie, wie das Windows Presentation Foundation DataGrid-Steuerelement die Überprüfung sowohl auf der Zelle als auch auf der Zeilenebene durchführen und Feedback zu Validierungs Fehlern liefern kann
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: a6fe3693f94c3f554e96bc167b572cf854a1a34a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167605"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Vorgehensweise: Implementieren von Validierung mit dem DataGrid-Steuerelement
Das- <xref:System.Windows.Controls.DataGrid> Steuerelement ermöglicht es Ihnen, sowohl auf der Zelle als auch auf der Zeilenebene eine Validierung auszuführen. Bei der Überprüfung auf Zellen Ebene überprüfen Sie einzelne Eigenschaften eines gebundenen Datenobjekts, wenn ein Benutzer einen Wert aktualisiert. Bei der Validierung auf Zeilenebene überprüfen Sie die gesamten Datenobjekte, wenn ein Benutzer Änderungen an einer Zeile ausführt. Sie können auch angepassten visuellen Feedback für Validierungs Fehler bereitstellen oder das standardmäßige visuelle Feedback verwenden, das das <xref:System.Windows.Controls.DataGrid> Steuerelement bereitstellt.  
  
 In den folgenden Prozeduren wird beschrieben, wie Validierungsregeln auf <xref:System.Windows.Controls.DataGrid> Bindungen angewendet und das visuelle Feedback angepasst werden.  
  
### <a name="to-validate-individual-cell-values"></a>So überprüfen Sie einzelne Zellwerte  
  
- Geben Sie eine oder mehrere Validierungsregeln für die Bindung an, die mit einer Spalte verwendet wird. Dies ähnelt dem Validieren von Daten in einfachen Steuerelementen, wie unter [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)beschrieben.  
  
     Das folgende Beispiel zeigt ein- <xref:System.Windows.Controls.DataGrid> Steuerelement mit vier Spalten, die an verschiedene Eigenschaften eines Geschäftsobjekts gebunden sind. In drei der Spalten wird der angegeben <xref:System.Windows.Controls.ExceptionValidationRule> , indem die-Eigenschaft auf festgelegt wird <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> `true` .  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Wenn ein Benutzer einen ungültigen Wert eingibt (z. b. eine nicht-ganze Zahl in der Spalte Course ID), wird ein roter Rahmen um die Zelle angezeigt. Sie können dieses standardmäßige Validierungs Feedback ändern, wie im folgenden Verfahren beschrieben.  
  
### <a name="to-customize-cell-validation-feedback"></a>So passen Sie Feedback zur Zellen Überprüfung an  
  
- Legen Sie die- <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> Eigenschaft der Spalte auf einen Stil fest, der für das Bearbeitungs Steuerelement der Spalte geeignet ist. Da die Bearbeitungs Steuerelemente zur Laufzeit erstellt werden, können Sie die <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> angefügte-Eigenschaft nicht wie bei einfachen Steuerelementen verwenden.  
  
     Im folgenden Beispiel wird das vorherige Beispiel aktualisiert, indem ein Fehler Stil hinzugefügt wird, der von den drei Spalten mit Validierungsregeln gemeinsam verwendet wird. Wenn ein Benutzer einen ungültigen Wert eingibt, wird die Hintergrundfarbe der Zelle geändert, und es wird eine QuickInfo hinzugefügt. Beachten Sie die Verwendung eines-Auslösers, um zu bestimmen, ob ein Validierungs Fehler vorliegt. Dies ist erforderlich, da derzeit keine dedizierte Fehler Vorlage für Zellen vorhanden ist.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Sie können eine umfassendere Anpassung implementieren, indem Sie die <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> von der Spalte verwendete ersetzen.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>So überprüfen Sie mehrere Werte in einer einzelnen Zeile  
  
1. Implementieren Sie eine <xref:System.Windows.Controls.ValidationRule> Unterklasse, die mehrere Eigenschaften des gebundenen Datenobjekts überprüft. Wandeln Sie in <xref:System.Windows.Controls.ValidationRule.Validate%2A> der Methoden Implementierung den `value` Parameterwert in eine- <xref:System.Windows.Data.BindingGroup> Instanz um. Anschließend können Sie über die-Eigenschaft auf das Datenobjekt zugreifen <xref:System.Windows.Data.BindingGroup.Items%2A> .  
  
     Im folgenden Beispiel wird dieser Prozess veranschaulicht, um zu überprüfen, ob der `StartDate` Eigenschafts Wert für ein- `Course` Objekt älter ist als der- `EndDate` Eigenschafts Wert  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Fügen Sie die Validierungs Regel der Auflistung hinzu <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> . Die- <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Eigenschaft bietet direkten Zugriff auf die- <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> Eigenschaft einer- <xref:System.Windows.Data.BindingGroup> Instanz, die alle vom-Steuerelement verwendeten Bindungen gruppiert.  
  
     Im folgenden Beispiel wird die- <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Eigenschaft in XAML festgelegt. Die- <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> Eigenschaft ist auf festgelegt <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , sodass die Überprüfung erst erfolgt, nachdem das gebundene Datenobjekt aktualisiert wurde.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Wenn ein Benutzer ein Enddatum angibt, das vor dem Startdatum liegt, wird ein rotes Ausrufezeichen (!) im Zeilen Header angezeigt. Sie können dieses standardmäßige Validierungs Feedback ändern, wie im folgenden Verfahren beschrieben.  
  
### <a name="to-customize-row-validation-feedback"></a>So passen Sie Feedback zur Zeilen Überprüfung an  
  
- Legen Sie die <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>-Eigenschaft fest. Diese Eigenschaft ermöglicht es Ihnen, das Feedback der Zeilen Validierung für einzelne Steuer <xref:System.Windows.Controls.DataGrid> Elemente anzupassen. Sie können sich auch auf mehrere Steuerelemente auswirken, indem Sie einen impliziten Zeilen Stil zum Festlegen der- <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> Eigenschaft verwenden.  
  
     Im folgenden Beispiel wird das standardmäßige Zeilen Validierungs Feedback durch einen besser sichtbaren Indikator ersetzt. Wenn ein Benutzer einen ungültigen Wert eingibt, wird ein roter Kreis mit einem weißen Ausrufezeichen im Zeilen Header angezeigt. Dies tritt sowohl bei Zeilen-als auch bei Zellen Validierungs Fehlern auf. Die zugehörige Fehlermeldung wird in einer QuickInfo angezeigt.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine umfassende Demonstration der Zellen-und Zeilen Validierung. Die- `Course` Klasse stellt ein Beispiel Datenobjekt bereit, das <xref:System.ComponentModel.IEditableObject> zur Unterstützung von Transaktionen implementiert. Das- <xref:System.Windows.Controls.DataGrid> Steuerelement interagiert mit <xref:System.ComponentModel.IEditableObject> , um Benutzern das Zurücksetzen von Änderungen durch Drücken von ESC zu ermöglichen.  
  
> [!NOTE]
> Wenn Sie Visual Basic verwenden, ersetzen Sie in der ersten Zeile der Datei "MainWindow. XAML" `x:Class="DataGridValidation.MainWindow"` durch `x:Class="MainWindow"` .  
  
 Versuchen Sie Folgendes, um die Überprüfung zu testen:  
  
- Geben Sie in der Spalte Course ID einen nicht ganzzahligen Wert ein.  
  
- Geben Sie in der Spalte Enddatum ein Datum ein, das vor dem Start Datum liegt.  
  
- Löschen Sie den Wert in Kurs-ID, Start Datum oder Enddatum.  
  
- Um einen ungültigen Zellwert rückgängig zu machen, setzen Sie den Cursor wieder in die Zelle, und drücken Sie die ESC-Taste.  
  
- Um Änderungen für eine ganze Zeile rückgängig zu machen, wenn sich die aktive Zelle im Bearbeitungsmodus befindet, drücken Sie zweimal die ESC-Taste.  
  
- Wenn ein Validierungs Fehler auftritt, bewegen Sie den Mauszeiger über den Indikator im Zeilen Header, um die zugehörige Fehlermeldung anzuzeigen.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Implementieren der Bindungs Validierung](../data/how-to-implement-binding-validation.md)
- [Implementieren von Validierungs Logik für benutzerdefinierte Objekte](../data/how-to-implement-validation-logic-on-custom-objects.md)
