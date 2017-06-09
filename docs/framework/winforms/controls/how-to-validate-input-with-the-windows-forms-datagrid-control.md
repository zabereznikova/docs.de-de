---
title: "Gewusst wie: &#220;berpr&#252;fen von Eingaben mit dem DataGrid-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - "DataGrid-Steuerelement [Windows Forms], Beispiele"
  - "DataGrid-Steuerelement [Windows Forms], Validieren der Eingabe"
  - "Beispiele [Windows Forms], DataGrid-Steuerelement"
  - "Benutzereingabe, Validieren"
  - "Überprüfung, Benutzereingabe"
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: &#220;berpr&#252;fen von Eingaben mit dem DataGrid-Steuerelement von Windows&#160;Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Für das <xref:System.Windows.Forms.DataGrid>\-Steuerelement in Windows Forms stehen zwei Arten der Eingabevalidierung zur Verfügung.  Wenn der Benutzer versucht, einen Wert mit einem für die Zelle unzulässigen Datentyp einzugeben \(z. B. eine Zeichenfolge anstatt einer ganzen Zahl\), wird der neue unzulässige Wert durch den alten Wert ersetzt.  Diese Art der Eingabevalidierung erfolgt automatisch und kann nicht angepasst werden.  
  
 Die andere Art der Eingabevalidierung kann verwendet werden, um unzulässige Daten zurückzuweisen \(z. B. den Wert 0 in einem Feld, dessen Wert größer oder gleich 1 sein muss, oder eine unzulässige Zeichenfolge\).  Dieser Vorgang wird im DataSet durchgeführt, indem ein Ereignishandler für das <xref:System.Data.DataTable.ColumnChanging>\-Ereignis oder das <xref:System.Data.DataTable.RowChanging>\-Ereignis geschrieben wird.  Im nachfolgenden Beispiel wird das <xref:System.Data.DataTable.ColumnChanging>\-Ereignis verwendet, da der unzulässige Wert insbesondere für die Spalte "Product" ungeeignet ist.  Das <xref:System.Data.DataTable.RowChanging>\-Ereignis kann z. B. verwendet werden, um zu überprüfen, ob der Wert einer Spalte "End Date" zeitlich gesehen nach dem Wert der Spalte "Start Date" in derselben Zeile liegt.  
  
### So überprüfen Sie Benutzereingaben  
  
1.  Schreiben Sie für die entsprechende Tabelle Code zur Behandlung des <xref:System.Data.DataTable.ColumnChanging>\-Ereignisses.  Wenn eine unzulässige Eingabe gefunden wird, rufen Sie die <xref:System.Data.DataRow.SetColumnError%2A>\-Methode des <xref:System.Data.DataRow>\-Objekts auf.  
  
    ```vb  
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _  
    ByVal e As System.Data.DataColumnChangeEventArgs)  
       ' Only check for errors in the Product column  
       If (e.Column.ColumnName.Equals("Product")) Then  
          ' Do not allow "Automobile" as a product.  
          If CType(e.ProposedValue, String) = "Automobile" Then  
             Dim badValue As Object = e.ProposedValue  
             e.ProposedValue = "Bad Data"  
             e.Row.RowError = "The Product column contians an error"  
             e.Row.SetColumnError(e.Column, "Product cannot be " & _  
             CType(badValue, String))  
          End If  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    //Handle column changing events on the Customers table  
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {  
  
       //Only check for errors in the Product column  
       if (e.Column.ColumnName.Equals("Product")) {  
  
          //Do not allow "Automobile" as a product  
          if (e.ProposedValue.Equals("Automobile")) {  
             object badValue = e.ProposedValue;  
             e.ProposedValue = "Bad Data";  
             e.Row.RowError = "The Product column contains an error";  
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);  
          }  
       }  
    }  
  
    ```  
  
2.  Verbinden Sie den Ereignishandler mit dem Ereignis.  
  
     Fügen Sie den folgenden Code entweder in das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars oder in den zugehörigen Konstruktor ein.  
  
    ```vb  
    ' Assumes the grid is bound to a dataset called customersDataSet1  
    ' with a table called Customers.  
    ' Put this code in the form's Load event or its constructor.  
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging  
  
    ```  
  
    ```csharp  
    // Assumes the grid is bound to a dataset called customersDataSet1  
    // with a table called Customers.  
    // Put this code in the form's Load event or its constructor.  
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);  
  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Data.DataTable.ColumnChanging>   
 <xref:System.Data.DataRow.SetColumnError%2A>   
 [DataGrid\-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)