---
title: Validieren von Eingaben mit dem DataGrid-Steuerelement
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
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728297"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Gewusst wie: Überprüfen von Eingaben mit dem DataGrid-Steuerelement von Windows Forms

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Für das Windows Forms <xref:System.Windows.Forms.DataGrid>-Steuerelement sind zwei Arten der Eingabe Überprüfung verfügbar. Wenn der Benutzer versucht, einen Wert einzugeben, der einen ungültigen Datentyp für die Zelle hat, z. b. eine Zeichenfolge in eine ganze Zahl, wird der neue ungültige Wert durch den alten Wert ersetzt. Diese Art der Eingabevalidierung erfolgt automatisch und kann nicht angepasst werden.

Der andere Typ der Eingabevalidierung kann verwendet werden, um unzulässige Daten abzulehnen, z. b. einen 0-Wert in einem Feld, das größer oder gleich 1 sein muss, oder eine ungeeignete Zeichenfolge. Dies erfolgt im Dataset durch Schreiben eines Ereignis Handlers für die <xref:System.Data.DataTable.ColumnChanging> oder <xref:System.Data.DataTable.RowChanging> Ereignisses. Im folgenden Beispiel wird das <xref:System.Data.DataTable.ColumnChanging>-Ereignis verwendet, da der unzulässige Wert für die Spalte "Product" besonders nicht zulässig ist. Sie können das <xref:System.Data.DataTable.RowChanging>-Ereignis verwenden, um zu überprüfen, ob der Wert einer Spalte "Enddatum" nach der Spalte "Start Datum" in derselben Zeile liegt.

## <a name="to-validate-user-input"></a>So überprüfen Sie Benutzereingaben

1. Schreiben Sie Code, um das <xref:System.Data.DataTable.ColumnChanging>-Ereignis für die entsprechende Tabelle zu verarbeiten. Wenn ungeeignete Eingaben erkannt werden, müssen Sie die <xref:System.Data.DataRow.SetColumnError%2A>-Methode des <xref:System.Data.DataRow>-Objekts aufzurufen.

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
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

2. Verbinden Sie den Ereignishandler mit dem-Ereignis.

    Fügen Sie den folgenden Code in das <xref:System.Windows.Forms.Form.Load>-Ereignis des Formulars oder seinen Konstruktor ein.

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
