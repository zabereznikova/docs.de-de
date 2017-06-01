---
title: "Gewusst wie: Reagieren auf das Klicken in das DataGrid-Steuerelement in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zellen, Position im DataGrid"
  - "Click-Ereignis, Überwachen in DataGrid-Steuerelementen"
  - "DataGrid-Steuerelement [Windows Forms], Click-Ereignisse"
  - "DataGrid-Steuerelement [Windows Forms], Beispiele"
  - "DataGrid-Steuerelement [Windows Forms], Zurückgeben eines angeklickten Zellwertes"
  - "Beispiele [Windows Forms], DataGrid-Steuerelement"
ms.assetid: a0aa204b-8351-4d82-9933-ee21a5c9e409
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Reagieren auf das Klicken in das DataGrid-Steuerelement in Windows&#160;Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Nachdem das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in Windows Forms mit einer Datenbank verbunden wurde, können Sie überwachen, auf welche Zellen die Benutzer klicken.  
  
### So erkennen Sie, wenn Benutzer des datengebundenen Steuerelements \(DataGrid\) eine andere Zelle auswählen  
  
-   Schreiben Sie für eine zweckmäßige Antwort Code in den <xref:System.Windows.Forms.DataGrid.CurrentCellChanged>\-Ereignishandler.  
  
    ```vb  
    Private Sub myDataGrid_CurrentCellChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles myDataGrid.CurrentCellChanged  
       MessageBox.Show("Col is " & myDataGrid.CurrentCell.ColumnNumber _  
          & ", Row is " & myDataGrid.CurrentCell.RowNumber _  
          & ", Value is " & myDataGrid.Item(myDataGrid.CurrentCell))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void myDataGrid_CurrentCellChanged(object sender,   
    System.EventArgs e)  
    {  
       MessageBox.Show ("Col is " + myDataGrid.CurrentCell.ColumnNumber  
          + ", Row is " + myDataGrid.CurrentCell.RowNumber   
          + ", Value is " + myDataGrid[myDataGrid.CurrentCell] );  
    }  
    ```  
  
     \(Visual C\#\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.myDataGrid.CurrentCellChanged += new  
       System.EventHandler(this.myDataGrid_CurrentCellChanged);  
    ```  
  
### So stellen Sie fest, auf welchen Teil des datengebundenen Steuerelements \(DataGrid\) die Benutzer klicken  
  
-   Rufen Sie in einem entsprechenden Ereignishandler die <xref:System.Windows.Forms.DataGrid.HitTest%2A>\-Methode auf, beispielsweise für das Ereignis <xref:System.Windows.Forms.Control.MouseDown> oder <xref:System.Windows.Forms.Control.Click>.  
  
     Die <xref:System.Windows.Forms.DataGrid.HitTest%2A>\-Methode gibt ein <xref:System.Windows.Forms.DataGrid.HitTestInfo>\-Objekt zurück, das die Zeile und Spalte eines Bereichs enthält, auf den geklickt wurde.  
  
    ```vb  
    Private Sub myDataGrid_MouseDown(ByVal sender As Object, _  
    ByVal e As MouseEventArgs) Handles myDataGrid.MouseDown  
       Dim myGrid As DataGrid = CType(sender, DataGrid)  
       Dim hti As System.Windows.Forms.DataGrid.HitTestInfo  
       hti = myGrid.HitTest(e.X, e.Y)  
       Dim message As String = "You clicked "  
  
       Select Case hti.Type  
          Case System.Windows.Forms.DataGrid.HitTestType.None  
             message &= "the background."  
          Case System.Windows.Forms.DataGrid.HitTestType.Cell  
             message &= "cell at row " & hti.Row & ", col " & hti.Column  
          Case System.Windows.Forms.DataGrid.HitTestType.ColumnHeader  
             message &= "the column header for column " & hti.Column  
          Case System.Windows.Forms.DataGrid.HitTestType.RowHeader  
             message &= "the row header for row " & hti.Row  
          Case System.Windows.Forms.DataGrid.HitTestType.ColumnResize  
             message &= "the column resizer for column " & hti.Column  
          Case System.Windows.Forms.DataGrid.HitTestType.RowResize  
             message &= "the row resizer for row " & hti.Row  
          Case System.Windows.Forms.DataGrid.HitTestType.Caption  
             message &= "the caption"  
          Case System.Windows.Forms.DataGrid.HitTestType.ParentRows  
             message &= "the parent row"  
       End Select  
  
       Console.WriteLine(message)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void myDataGrid_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       DataGrid myGrid = (DataGrid) sender;  
       System.Windows.Forms.DataGrid.HitTestInfo hti;  
       hti = myGrid.HitTest(e.X, e.Y);  
       string message = "You clicked ";  
  
       switch (hti.Type)   
       {  
          case System.Windows.Forms.DataGrid.HitTestType.None :  
             message += "the background.";  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.Cell :  
             message += "cell at row " + hti.Row + ", col " + hti.Column;  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.ColumnHeader :  
             message += "the column header for column " + hti.Column;  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.RowHeader :  
             message += "the row header for row " + hti.Row;  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.ColumnResize :  
             message += "the column resizer for column " + hti.Column;  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.RowResize :  
             message += "the row resizer for row " + hti.Row;  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.Caption :  
             message += "the caption";  
             break;  
          case System.Windows.Forms.DataGrid.HitTestType.ParentRows :  
             message += "the parent row";  
             break;  
          }  
  
          Console.WriteLine(message);  
    }  
    ```  
  
     \(Visual C\#\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.myDataGrid.MouseDown += new  
       System.Windows.Forms.MouseEventHandler  
       (this.myDataGrid_MouseDown);  
    ```  
  
## Siehe auch  
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Gewusst wie: Ändern der angezeigten Daten im DataGrid\-Steuerelement in Windows Forms zur Laufzeit](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)