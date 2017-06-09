---
title: "Gewusst wie: Implementieren von Validierung mit dem DataGrid-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid [WPF], Überprüfung"
  - "Validierung [WPF], DataGrid"
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Implementieren von Validierung mit dem DataGrid-Steuerelement
Das <xref:System.Windows.Controls.DataGrid>\-Steuerelement ermöglicht eine Validierung auf Zellen\- sowie auf Zeilenebene.  Bei der Validierung auf Zellenebene werden einzelne Eigenschaften eines gebundenen Datenobjekts überprüft, wenn ein Benutzer einen Wert aktualisiert.  Bei der Validierung auf Zeilenebene werden ganze Datenobjekte überprüft, wenn ein Benutzer einen Commit für Änderungen an einer Zeile ausführt.  Sie können auch angepasstes visuelles Feedback für Validierungsfehler bereitstellen oder das standardmäßige visuelle Feedback des <xref:System.Windows.Controls.DataGrid>\-Steuerelements verwenden.  
  
 In den folgenden Prozeduren wird das Anwenden von Validierungsregeln auf <xref:System.Windows.Controls.DataGrid>\-Bindungen sowie das Anpassen des visuellen Feedbacks erläutert.  
  
### So überprüfen Sie einzelne Zellenwerte  
  
-   Geben Sie für die Bindung einer Spalte mindestens eine Validierungsregel an.  Dies ist vergleichbar mit dem Überprüfen von Daten in einfachen Steuerelementen \(siehe [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)\).  
  
     Im folgenden Beispiel wird ein <xref:System.Windows.Controls.DataGrid>\-Steuerelement mit vier Spalten veranschaulicht, die an unterschiedliche Eigenschaften eines Geschäftsobjekts gebunden sind.  In drei der Spalten wird die <xref:System.Windows.Controls.ExceptionValidationRule> angegeben, indem die <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>\-Eigenschaft auf `true` festgelegt wird.  
  
     [!code-xml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Gibt ein Benutzer nun einen ungültigen Wert ein \(beispielsweise einen nicht ganzzahligen Wert in der Spalte für die Kurs\-ID\), wird die Zelle mit einem roten Rahmen versehen.  Dieses Standardvalidierungsfeedback kann wie in der folgenden Prozedur beschrieben geändert werden.  
  
### So passen Sie das Zellenvalidierungsfeedback an  
  
-   Legen Sie die <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>\-Eigenschaft der Spalte auf einen Stil fest, der für das Bearbeitungssteuerelement der Spalte geeignet ist.  Da die Bearbeitungssteuerelemente zur Laufzeit erstellt werden, kann die angefügte <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName>\-Eigenschaft nicht wie sonst bei einfachen Steuerelementen verwendet werden.  
  
     Im folgenden Beispiel wird das vorherige Beispiel aktualisiert. Hierzu wird ein gemeinsamer Fehlerstil für die drei Spalten mit Validierungsregeln hinzugefügt.  Gibt ein Benutzer nun einen ungültigen Wert ein, ändert sich die Hintergrundfarbe der Zelle, und eine QuickInfo wird hinzugefügt.  Beachten Sie, dass hier ein Trigger verwendet wird, um zu bestimmen, ob ein Validierungsfehler vorliegt.  Dies ist erforderlich, da momentan keine dedizierte Fehlervorlage für Zellen vorhanden ist.  
  
     [!code-xml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Ersetzen Sie zum Implementieren umfangreicherer Anpassungen den von der Spalte verwendeten <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>.  
  
### So überprüfen Sie mehrere Werte in einer einzelnen Zeile  
  
1.  Implementieren Sie eine <xref:System.Windows.Controls.ValidationRule>\-Unterklasse, von der mehrere Eigenschaften des gebundenen Datenobjekts überprüft werden.  Wandeln Sie in der Implementierung der <xref:System.Windows.Controls.ValidationRule.Validate%2A>\-Methode den `value`\-Parameterwert zu einer <xref:System.Windows.Data.BindingGroup>\-Instanz um.  Anschließend können Sie über die <xref:System.Windows.Data.BindingGroup.Items%2A>\-Eigenschaft auf das Datenobjekt zugreifen.  
  
     Im folgenden Beispiel wird dieser Prozess veranschaulicht, indem überprüft wird, ob der `StartDate`\-Eigenschaftswert für ein `Course`\-Objekt vor dem `EndDate`\-Eigenschaftswert des Objekts liegt.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  Fügen Sie die Validierungsregel der <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=fullName>\-Auflistung hinzu.  Die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>\-Eigenschaft bietet direkten Zugriff auf die <xref:System.Windows.Data.BindingGroup.ValidationRules%2A>\-Eigenschaft einer <xref:System.Windows.Data.BindingGroup>\-Instanz, von der alle von diesem Steuerelement verwendeten Bindungen gruppiert werden.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>\-Eigenschaft in XAML festgelegt.  Die <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>\-Eigenschaft wird auf <xref:System.Windows.Controls.ValidationStep> festgelegt, damit die Validierung nur nach der Aktualisierung des gebundenen Datenobjekts erfolgt.  
  
     [!code-xml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Wird von einem Benutzer ein Enddatum angegeben, das vor dem Startdatum liegt, wird im Zeilenkopf ein rotes Ausrufezeichen angezeigt.  Dieses Standardvalidierungsfeedback kann wie in der folgenden Prozedur beschrieben geändert werden.  
  
### So passen Sie das Zeilenvalidierungsfeedback an  
  
-   Legen Sie die <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=fullName>\-Eigenschaft fest.  Diese Eigenschaft ermöglicht das Anpassen des Zeilenvalidierungsfeedbacks für einzelne <xref:System.Windows.Controls.DataGrid>\-Steuerelemente.  Sie können auch mehrere Steuerelemente anpassen, indem Sie die <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=fullName>\-Eigenschaft mithilfe eines impliziten Zeilenstils festlegen.  
  
     Im folgenden Beispiel wird das standardmäßige Zeilenvalidierungsfeedback durch einen besser sichtbaren Indikator ersetzt.  Gibt ein Benutzer einen ungültigen Wert ein, wird im Zeilenheader ein roter Kreis mit einem weißen Ausrufezeichen angezeigt.  Dies gilt sowohl für Zeilen\- als auch für Zellenvalidierungsfehler.  Die entsprechende Fehlermeldung wird in einer QuickInfo angezeigt.  
  
     [!code-xml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## Beispiel  
 Beim folgenden Beispiel handelt es sich um eine vollständige Demonstration der Zellen\- und Zeilenvalidierung.  Von der `Course`\-Klasse wird ein Beispieldatenobjekt bereitgestellt, von dem <xref:System.ComponentModel.IEditableObject> implementiert wird, um Transaktionen zu unterstützen.  Das <xref:System.Windows.Controls.DataGrid>\-Steuerelement interagiert mit <xref:System.ComponentModel.IEditableObject>, um den Benutzern das Rückgängigmachen von Änderungen durch Drücken von ESC zu ermöglichen.  
  
> [!NOTE]
>  Ersetzen Sie bei Verwendung von Visual Basic in der ersten Zeile von "MainWindow.xaml" den Code `x:Class="DataGridValidation.MainWindow"` durch `x:Class="MainWindow"`.  
  
 Gehen Sie zum Testen der Validierung folgendermaßen vor:  
  
-   Geben Sie in der Spalte für die Kurs\-ID einen nicht ganzzahligen Wert ein.  
  
-   Geben Sie ein Enddatum ein, das vor dem Startdatum liegt.  
  
-   Löschen Sie den Wert für Kurs\-ID, Startdatum oder Enddatum.  
  
-   Platzieren Sie zum Rückgängigmachen eines ungültigen Zellenwerts den Cursor in der entsprechenden Zelle, und drücken Sie ESC.  
  
-   Drücken Sie zweimal ESC, während sich die aktuelle Zelle im Bearbeitungsmodus befindet, um die Änderungen für eine ganze Zeile rückgängig zu machen.  
  
-   Bewegen Sie bei Auftreten eines Validierungsfehlers den Mauszeiger über den Indikator im Zeilenheader, um die entsprechende Fehlermeldung anzuzeigen.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.DataGrid>   
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)   
 [Datenbindung](../../../../docs/framework/wpf/data/data-binding-wpf.md)   
 [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Implementieren von Validierungslogik für benutzerdefinierte Objekte](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)