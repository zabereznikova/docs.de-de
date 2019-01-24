---
title: 'Vorgehensweise: Überprüfen von Eingaben mit dem DataGrid-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 55de6fc1ef4fdf94495ddb07f3329ef9d46b5818
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609485"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="343a0-102">Vorgehensweise: Überprüfen von Eingaben mit dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="343a0-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="343a0-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="343a0-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="343a0-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="343a0-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="343a0-105">Es stehen zwei Arten der Validierung von Benutzereingaben für die Windows-Formulare <xref:System.Windows.Forms.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="343a0-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="343a0-106">Wenn der Benutzer versucht, einen Wert eingeben, der den unzulässigen Datentyp für die Zelle, z. B. eine Zeichenfolge in eine ganze Zahl, wird der neue Wert für die ungültige mit dem alten Wert ersetzt.</span><span class="sxs-lookup"><span data-stu-id="343a0-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="343a0-107">Diese Art der Validierung von Benutzereingaben erfolgt automatisch und kann nicht angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="343a0-107">This kind of input validation is done automatically and cannot be customized.</span></span>  
  
 <span data-ttu-id="343a0-108">Die andere Art von Validierung von Benutzereingaben kann verwendet werden, um alle unzulässigen Daten, z. B. einen 0-Wert in einem Feld abzulehnen, die größer als oder gleich 1 oder eine Zeichenfolge, nicht geeignet sein muss.</span><span class="sxs-lookup"><span data-stu-id="343a0-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="343a0-109">Dies erfolgt im Dataset durch das Schreiben eines ereignishandlers für das <xref:System.Data.DataTable.ColumnChanging> oder <xref:System.Data.DataTable.RowChanging> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="343a0-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="343a0-110">Im folgenden Beispiel wird die <xref:System.Data.DataTable.ColumnChanging> Ereignis, da der unzulässige Wert insbesondere für die Spalte "Product" ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="343a0-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="343a0-111">Sie können die <xref:System.Data.DataTable.RowChanging> Ereignis, um sicherzustellen, dass der Wert einer Spalte "Enddatum" höher als die Spalte "Startdatum" in der gleichen Zeile ist.</span><span class="sxs-lookup"><span data-stu-id="343a0-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>  
  
### <a name="to-validate-user-input"></a><span data-ttu-id="343a0-112">Zum Überprüfen von Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="343a0-112">To validate user input</span></span>  
  
1.  <span data-ttu-id="343a0-113">Schreiben Sie Code zum Behandeln der <xref:System.Data.DataTable.ColumnChanging> Ereignis für die entsprechende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="343a0-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="343a0-114">Wenn unzulässige Eingabe erkannt wird, rufen Sie die <xref:System.Data.DataRow.SetColumnError%2A> Methode der <xref:System.Data.DataRow> Objekt.</span><span class="sxs-lookup"><span data-stu-id="343a0-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>  
  
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
  
2.  <span data-ttu-id="343a0-115">Verbinden Sie den Ereignishandler an das Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="343a0-115">Connect the event handler to the event.</span></span>  
  
     <span data-ttu-id="343a0-116">Fügen Sie den folgenden code innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis oder den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="343a0-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="343a0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="343a0-117">See also</span></span>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="343a0-118">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="343a0-118">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
