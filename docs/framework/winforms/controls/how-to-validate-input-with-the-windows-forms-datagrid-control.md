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
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="2d8b8-102">Gewusst wie: Überprüfen von Eingaben mit dem DataGrid-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d8b8-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="2d8b8-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="2d8b8-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2d8b8-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="2d8b8-105">Für das Windows Forms <xref:System.Windows.Forms.DataGrid>-Steuerelement sind zwei Arten der Eingabe Überprüfung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="2d8b8-106">Wenn der Benutzer versucht, einen Wert einzugeben, der einen ungültigen Datentyp für die Zelle hat, z. b. eine Zeichenfolge in eine ganze Zahl, wird der neue ungültige Wert durch den alten Wert ersetzt.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="2d8b8-107">Diese Art der Eingabevalidierung erfolgt automatisch und kann nicht angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="2d8b8-108">Der andere Typ der Eingabevalidierung kann verwendet werden, um unzulässige Daten abzulehnen, z. b. einen 0-Wert in einem Feld, das größer oder gleich 1 sein muss, oder eine ungeeignete Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="2d8b8-109">Dies erfolgt im Dataset durch Schreiben eines Ereignis Handlers für die <xref:System.Data.DataTable.ColumnChanging> oder <xref:System.Data.DataTable.RowChanging> Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="2d8b8-110">Im folgenden Beispiel wird das <xref:System.Data.DataTable.ColumnChanging>-Ereignis verwendet, da der unzulässige Wert für die Spalte "Product" besonders nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="2d8b8-111">Sie können das <xref:System.Data.DataTable.RowChanging>-Ereignis verwenden, um zu überprüfen, ob der Wert einer Spalte "Enddatum" nach der Spalte "Start Datum" in derselben Zeile liegt.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="2d8b8-112">So überprüfen Sie Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="2d8b8-112">To validate user input</span></span>

1. <span data-ttu-id="2d8b8-113">Schreiben Sie Code, um das <xref:System.Data.DataTable.ColumnChanging>-Ereignis für die entsprechende Tabelle zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="2d8b8-114">Wenn ungeeignete Eingaben erkannt werden, müssen Sie die <xref:System.Data.DataRow.SetColumnError%2A>-Methode des <xref:System.Data.DataRow>-Objekts aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

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

2. <span data-ttu-id="2d8b8-115">Verbinden Sie den Ereignishandler mit dem-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="2d8b8-116">Fügen Sie den folgenden Code in das <xref:System.Windows.Forms.Form.Load>-Ereignis des Formulars oder seinen Konstruktor ein.</span><span class="sxs-lookup"><span data-stu-id="2d8b8-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2d8b8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d8b8-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="2d8b8-118">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2d8b8-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
