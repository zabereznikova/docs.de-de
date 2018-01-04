---
title: 'Gewusst wie: Implementieren von Validierung mit dem DataGrid-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78846e2b6a1d73e011441b0ccb46b8aad365d5dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Gewusst wie: Implementieren von Validierung mit dem DataGrid-Steuerelement
Die <xref:System.Windows.Controls.DataGrid> -Steuerelement ermöglicht Ihnen die Durchführung der Validierung auf die Zelle und die Zeile. Überprüfen Sie mit Überprüfung auf Zellenebene einzelne Eigenschaften eines gebundenen Objekts aus, wenn ein Benutzer einen Wert aktualisiert. Mit Überprüfung auf Zeilenebene wird der gesamte Dataset Objekte überprüfen, wenn ein Benutzer Änderungen an einer Zeile ein Commit ausgeführt wird. Sie können auch angepasste visuelles Feedback für Validierungsfehler oder verwenden Sie die standardmäßige visuelles Feedback, die die <xref:System.Windows.Controls.DataGrid> gesteuert.  
  
 Die folgenden Verfahren wird beschrieben, wie zum Anwenden von Validierungsregeln zum <xref:System.Windows.Controls.DataGrid> Bindungen und Anpassen der visuelle Feedback.  
  
### <a name="to-validate-individual-cell-values"></a>So überprüfen Sie die Werte der einzelnen Zellen  
  
-   Geben Sie eine oder mehrere Validierungsregeln für die Bindung mit einer Spalte verwendet. Dieser Vorgang ähnelt, Überprüfen von Daten in einfache Steuerelemente, wie in beschrieben [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.DataGrid> -Steuerelement mit vier Spalten, die an unterschiedliche Eigenschaften eines Geschäftsobjekts gebunden. Drei Spalten geben die <xref:System.Windows.Controls.ExceptionValidationRule> durch Festlegen der <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> Eigenschaft `true`.  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Wenn ein Benutzer einen ungültigen Wert (z. B. eine nicht ganzzahlige in der Spalte für die Kurs-ID) eingibt, wird ein roter Rahmen um die Zelle angezeigt. Sie können diese standardmäßige Überprüfung Feedback wie im folgenden Verfahren beschrieben ändern.  
  
### <a name="to-customize-cell-validation-feedback"></a>Die Überprüfung Zellenvalidierungsfeedback anpassen  
  
-   Legen Sie die Spalte <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> Eigenschaft, um einen Stil geeignet, für das Bearbeitungssteuerelement der Spalte. Da die Bearbeitung von Steuerelementen zur Laufzeit erstellt werden, können Sie keine der <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> angefügte Eigenschaft wie bei einfachen Steuerelementen verwenden.  
  
     Das folgende Beispiel aktualisiert die im vorherige Beispiel durch einen von drei Spalten mit Validierungsregeln gemeinsam Stil hinzufügen. Wenn ein Benutzer einen ungültigen Wert eingibt, wird das Format wird die Hintergrundfarbe der Zelle und fügt eine QuickInfo hinzu. Beachten Sie die Verwendung eines Triggers, um festzustellen, ob ein Validierungsfehler vorliegt. Dies ist erforderlich, weil es zurzeit keine dedizierte Fehlervorlage für Zellen.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Sie können eine erweiterte Anpassung implementieren, indem Sie ersetzen die <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> nach der Spalte verwendet.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>So überprüfen Sie mehrere Werte in einer einzelnen Zeile  
  
1.  Implementieren einer <xref:System.Windows.Controls.ValidationRule> Unterklasse, die mehrere Eigenschaften des gebundenen Objekts überprüft. In Ihrer <xref:System.Windows.Controls.ValidationRule.Validate%2A> methodenimplementierung, wandeln die `value` Parameterwert eine <xref:System.Windows.Data.BindingGroup> Instanz. Anschließend können Sie zugreifen, das Datenobjekt mithilfe der <xref:System.Windows.Data.BindingGroup.Items%2A> Eigenschaft.  
  
     Das folgende Beispiel veranschaulicht diesen Prozess um zu überprüfen, ob die `StartDate` Eigenschaftswert für ein `Course` -Objekt liegt vor seiner `EndDate` Eigenschaftswert.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  Fügen Sie die Validierungsregel der <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> Auflistung. Die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Eigenschaft bietet direkten Zugriff auf die <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> Eigenschaft eine <xref:System.Windows.Data.BindingGroup> -Instanz, die alle vom Steuerelement verwendeten Bindungen gruppiert.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> Eigenschaft in XAML. Die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.ValidationStep.UpdatedValue> , damit die Überprüfung wird nur verwendet werden, nachdem das gebundene Datenobjekt aktualisiert wird.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Wenn ein Benutzer ein Enddatum, die vor dem Startdatum liegt angibt, wird ein rotes Ausrufezeichen (!) in die Zeilenüberschrift angezeigt. Sie können diese standardmäßige Überprüfung Feedback wie im folgenden Verfahren beschrieben ändern.  
  
### <a name="to-customize-row-validation-feedback"></a>Zeile Überprüfung Feedback anpassen  
  
-   Legen Sie die <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>-Eigenschaft fest. Dieser Eigenschaft können Sie zum Anpassen der Zeile Überprüfung Feedback für einzelne <xref:System.Windows.Controls.DataGrid> Steuerelemente. Sie können auch mehrere Steuerelemente, die beeinflussen, indem eine implizite Zeilenformat zum Festlegen der <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> Eigenschaft.  
  
     Im folgende Beispiel ersetzt die standardmäßige Zeile Überprüfung Feedback mit einem Indikator besser zu sehen. Wenn ein Benutzer einen ungültigen Wert eingibt, wird ein roter Kreis mit einem weißen Ausrufezeichen in der Zeile mit einer Überschrift angezeigt. Dieser Fehler tritt für Zeilen- und Zellenebene Validierungsfehler. Die entsprechende Fehlermeldung wird in einer QuickInfo angezeigt.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel stellt eine umfassende Demonstration für Zellen- und Validierung bereit. Die `Course` -Klasse stellt eine Beispiel-Datenobjekt, das implementiert <xref:System.ComponentModel.IEditableObject> zur Unterstützung von Transaktionen. Die <xref:System.Windows.Controls.DataGrid> Steuerelement interagiert mit <xref:System.ComponentModel.IEditableObject> Benutzern Änderungen rückgängig zu machen, durch Drücken von ESC aktiviert.  
  
> [!NOTE]
>  Ersetzen Sie bei Verwendung von Visual Basic, in der ersten Zeile von "MainWindow.xaml" `x:Class="DataGridValidation.MainWindow"` mit `x:Class="MainWindow"`.  
  
 Versuchen Sie Folgendes, um die Überprüfung zu testen:  
  
-   Geben Sie einen Ganzzahlwert, in der Kurs-ID-Spalte.  
  
-   Geben Sie in der Spalte mit Enddatum ein, die vor dem Startdatum liegt.  
  
-   Löschen Sie den Wert im Kurs-ID, Startdatum und Enddatum ein.  
  
-   Um einen ungültigen Zellenwert rückgängig zu machen, platzieren Sie den Cursor in der Zelle zurück, und drücken Sie die ESC-Taste.  
  
-   Um die Änderungen für eine ganze Zeile rückgängig, wenn die aktuelle Zelle im Bearbeitungsmodus befindet, drücken Sie die ESC-Taste zweimal.  
  
-   Wenn ein Validierungsfehler auftritt, verschieben Sie den Mauszeiger über dem Indikator im Zeilenheader der zugehörigen Fehlermeldung angezeigt.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.DataGrid>  
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)  
 [Datenbindung](../../../../docs/framework/wpf/data/data-binding-wpf.md)  
 [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Implementieren von Validierungslogik für benutzerdefinierte Objekte](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
