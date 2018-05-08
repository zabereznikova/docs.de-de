---
title: 'Gewusst wie: Überprüfen von Eingaben mit dem DataGrid-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: a01cb90b7cba596dafa56963dcf9c489deb3e21a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Gewusst wie: Überprüfen von Eingaben mit dem DataGrid-Steuerelement von Windows Forms
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Es gibt zwei Arten der Validierung von Benutzereingaben für Windows Forms verfügbar <xref:System.Windows.Forms.DataGrid> Steuerelement. Wenn der Benutzer versucht, einen Wert eingeben, der einen unzulässigen Datentyp für die Zelle, z. B. eine Zeichenfolge in eine ganze Zahl ist, wird der neue Wert für die ungültige mit den alten Wert ersetzt. Diese Art von Validierung von Benutzereingaben wird automatisch ausgeführt und kann nicht angepasst werden.  
  
 Unzulässigen Daten, z. B. einen 0-Wert in einem Feld ablehnen, die größer als oder gleich 1 oder eine Zeichenfolge, nicht geeignet sein muss, kann die andere Art von Validierung von Benutzereingaben verwendet werden. Dies erfolgt im Dataset durch Schreiben von einem Ereignishandler für das <xref:System.Data.DataTable.ColumnChanging> oder <xref:System.Data.DataTable.RowChanging> Ereignis. Im folgenden Beispiel wird die <xref:System.Data.DataTable.ColumnChanging> Ereignis, da der unzulässige Wert insbesondere für die Spalte "Product" ungeeignet ist. Sie können die <xref:System.Data.DataTable.RowChanging> Ereignis für die Überprüfung, dass der Wert einer Spalte "Enddatum" höher als die Spalte "Startdatum" in der gleichen Zeile.  
  
### <a name="to-validate-user-input"></a>Zum Überprüfen von Benutzereingaben  
  
1.  Schreiben Sie Code für die Behandlung der <xref:System.Data.DataTable.ColumnChanging> Ereignis für die entsprechende Tabelle. Wenn unzulässige Eingabe erkannt wird, rufen Sie die <xref:System.Data.DataRow.SetColumnError%2A> Methode der <xref:System.Data.DataRow> Objekt.  
  
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
  
2.  Verbinden Sie den Ereignishandler an das Ereignis.  
  
     Fügen Sie den folgenden code innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis oder der Konstruktor.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Data.DataTable.ColumnChanging>  
 <xref:System.Data.DataRow.SetColumnError%2A>  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
