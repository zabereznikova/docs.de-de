---
title: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730981"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="7bab3-102">Gewusst wie: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7bab3-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="7bab3-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7bab3-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="7bab3-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7bab3-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="7bab3-105">Wenn die <xref:System.Data.DataSet> eine Reihe verknüpfter Tabellen enthält, können Sie zwei <xref:System.Windows.Forms.DataGrid>-Steuerelemente verwenden, um die Daten im Master-/Detail-Format anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7bab3-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="7bab3-106">Eine <xref:System.Windows.Forms.DataGrid> die als Haupt Raster festgelegt ist, und die zweite ist als das Detail Raster festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7bab3-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="7bab3-107">Wenn Sie in der Liste Master einen Eintrag auswählen, werden alle zugehörigen untergeordneten Einträge in der Detail Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bab3-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="7bab3-108">Wenn Ihr <xref:System.Data.DataSet> z. b. eine Customers-Tabelle und eine zugehörige Orders-Tabelle enthält, geben Sie die Customers-Tabelle als Haupt Raster und die Orders-Tabelle als Detail Raster an.</span><span class="sxs-lookup"><span data-stu-id="7bab3-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="7bab3-109">Wenn ein Kunde aus dem Haupt Raster ausgewählt wird, werden alle Bestellungen, die diesem Kunden in der Tabelle Orders zugeordnet sind, im Detail Raster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bab3-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="7bab3-110">So legen Sie eine Master/Detail-Beziehung Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="7bab3-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="7bab3-111">Erstellen Sie zwei neue <xref:System.Windows.Forms.DataGrid> Steuerelemente, und legen Sie deren Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="7bab3-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="7bab3-112">Fügen Sie dem Dataset Tabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bab3-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="7bab3-113">Deklarieren Sie eine Variable vom Typ <xref:System.Data.DataRelation>, um die Beziehung darzustellen, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7bab3-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="7bab3-114">Instanziieren Sie die Beziehung, indem Sie einen Namen für die Beziehung angeben und die Tabelle, die Spalte und das Element angeben, mit denen die beiden Tabellen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="7bab3-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="7bab3-115">Fügen Sie die Beziehung zur <xref:System.Data.DataSet.Relations%2A> Auflistung des <xref:System.Data.DataSet> Objekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bab3-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="7bab3-116">Verwenden Sie die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode des <xref:System.Windows.Forms.DataGrid>, um die einzelnen Raster an die <xref:System.Data.DataSet>zu binden.</span><span class="sxs-lookup"><span data-stu-id="7bab3-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="7bab3-117">Im folgenden Beispiel wird gezeigt, wie eine Master/Detail-Beziehung zwischen den Tabellen Customers und Orders in einem zuvor generierten <xref:System.Data.DataSet> (`ds`) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7bab3-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7bab3-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bab3-118">See also</span></span>

- [<span data-ttu-id="7bab3-119">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7bab3-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="7bab3-120">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7bab3-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="7bab3-121">Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="7bab3-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
