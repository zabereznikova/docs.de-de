---
title: 'Vorgehensweise: Erstellen von Master-/Detaillisten mit dem Windows Forms DataGrid-Steuerelement'
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
ms.openlocfilehash: f0fd95cf0cd66e9a5105c0b8ff77d8c536a5822d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914761"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="97e34-102">Vorgehensweise: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97e34-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="97e34-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="97e34-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="97e34-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="97e34-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="97e34-105">Wenn Ihr <xref:System.Data.DataSet> eine Reihe verwandter Tabellen enthält, können Sie zwei <xref:System.Windows.Forms.DataGrid> -Steuerelemente verwenden, um die Daten im Master-/Detail-Format anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="97e34-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="97e34-106">Eine <xref:System.Windows.Forms.DataGrid> ist als Haupt Raster festgelegt, und die zweite ist als das Detail Raster festgelegt.</span><span class="sxs-lookup"><span data-stu-id="97e34-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="97e34-107">Wenn Sie in der Liste Master einen Eintrag auswählen, werden alle zugehörigen untergeordneten Einträge in der Detail Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97e34-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="97e34-108">Wenn Ihr <xref:System.Data.DataSet> z. b. eine Customers-Tabelle und eine zugehörige Orders-Tabelle enthält, geben Sie die Customers-Tabelle als Haupt Raster und die Orders-Tabelle als Detail Raster an.</span><span class="sxs-lookup"><span data-stu-id="97e34-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="97e34-109">Wenn ein Kunde aus dem Haupt Raster ausgewählt wird, werden alle Bestellungen, die diesem Kunden in der Tabelle Orders zugeordnet sind, im Detail Raster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="97e34-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="97e34-110">So legen Sie eine Master/Detail-Beziehung Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="97e34-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="97e34-111">Erstellen Sie zwei <xref:System.Windows.Forms.DataGrid> neue Steuerelemente, und legen Sie deren Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="97e34-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="97e34-112">Fügen Sie dem Dataset Tabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="97e34-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="97e34-113">Deklarieren Sie eine Variable <xref:System.Data.DataRelation> vom Typ zur Darstellung der Beziehung, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="97e34-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="97e34-114">Instanziieren Sie die Beziehung, indem Sie einen Namen für die Beziehung angeben und die Tabelle, die Spalte und das Element angeben, mit denen die beiden Tabellen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="97e34-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="97e34-115">Fügen Sie die Beziehung der <xref:System.Data.DataSet> -Auflistung <xref:System.Data.DataSet.Relations%2A> des-Objekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="97e34-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="97e34-116">Verwenden <xref:System.Windows.Forms.DataGrid> Sie <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> die-Methode des, um die einzelnen Raster an die <xref:System.Data.DataSet>zu binden.</span><span class="sxs-lookup"><span data-stu-id="97e34-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="97e34-117">Im folgenden Beispiel wird gezeigt, wie eine Master/Detail-Beziehung zwischen den Tabellen Customers und Orders in einem zuvor <xref:System.Data.DataSet> generierten`ds`() festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="97e34-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97e34-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97e34-118">See also</span></span>

- [<span data-ttu-id="97e34-119">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="97e34-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="97e34-120">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="97e34-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="97e34-121">Vorgehensweise: Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="97e34-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
