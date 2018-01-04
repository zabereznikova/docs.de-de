---
title: "Gewusst wie: Überprüfen von Eingaben mit dem DataGrid-Steuerelement von Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88cdc7914c301af0f0f244f935b986fb78ec775e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="5ca74-102">Gewusst wie: Überprüfen von Eingaben mit dem DataGrid-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ca74-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="5ca74-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5ca74-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="5ca74-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5ca74-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="5ca74-105">Es gibt zwei Arten der Validierung von Benutzereingaben für Windows Forms verfügbar <xref:System.Windows.Forms.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5ca74-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="5ca74-106">Wenn der Benutzer versucht, einen Wert eingeben, der einen unzulässigen Datentyp für die Zelle, z. B. eine Zeichenfolge in eine ganze Zahl ist, wird der neue Wert für die ungültige mit den alten Wert ersetzt.</span><span class="sxs-lookup"><span data-stu-id="5ca74-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="5ca74-107">Diese Art von Validierung von Benutzereingaben wird automatisch ausgeführt und kann nicht angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="5ca74-107">This kind of input validation is done automatically and cannot be customized.</span></span>  
  
 <span data-ttu-id="5ca74-108">Unzulässigen Daten, z. B. einen 0-Wert in einem Feld ablehnen, die größer als oder gleich 1 oder eine Zeichenfolge, nicht geeignet sein muss, kann die andere Art von Validierung von Benutzereingaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ca74-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="5ca74-109">Dies erfolgt im Dataset durch Schreiben von einem Ereignishandler für das <xref:System.Data.DataTable.ColumnChanging> oder <xref:System.Data.DataTable.RowChanging> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5ca74-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="5ca74-110">Im folgenden Beispiel wird die <xref:System.Data.DataTable.ColumnChanging> Ereignis, da der unzulässige Wert insbesondere für die Spalte "Product" ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="5ca74-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="5ca74-111">Sie können die <xref:System.Data.DataTable.RowChanging> Ereignis für die Überprüfung, dass der Wert einer Spalte "Enddatum" höher als die Spalte "Startdatum" in der gleichen Zeile.</span><span class="sxs-lookup"><span data-stu-id="5ca74-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>  
  
### <a name="to-validate-user-input"></a><span data-ttu-id="5ca74-112">Zum Überprüfen von Benutzereingaben</span><span class="sxs-lookup"><span data-stu-id="5ca74-112">To validate user input</span></span>  
  
1.  <span data-ttu-id="5ca74-113">Schreiben Sie Code für die Behandlung der <xref:System.Data.DataTable.ColumnChanging> Ereignis für die entsprechende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5ca74-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="5ca74-114">Wenn unzulässige Eingabe erkannt wird, rufen Sie die <xref:System.Data.DataRow.SetColumnError%2A> Methode der <xref:System.Data.DataRow> Objekt.</span><span class="sxs-lookup"><span data-stu-id="5ca74-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>  
  
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
  
2.  <span data-ttu-id="5ca74-115">Verbinden Sie den Ereignishandler an das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5ca74-115">Connect the event handler to the event.</span></span>  
  
     <span data-ttu-id="5ca74-116">Fügen Sie den folgenden code innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis oder der Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="5ca74-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ca74-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ca74-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Data.DataTable.ColumnChanging>  
 <xref:System.Data.DataRow.SetColumnError%2A>  
 [<span data-ttu-id="5ca74-118">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ca74-118">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
