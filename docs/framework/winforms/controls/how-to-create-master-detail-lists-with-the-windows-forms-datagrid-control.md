---
title: 'Vorgehensweise: Erstellen von Master / Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 92b4a7d9513ce0ec9b7c02f57c23fa4267fb26ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302400"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="4db80-102">Vorgehensweise: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4db80-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="4db80-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="4db80-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="4db80-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="4db80-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="4db80-105">Wenn Ihre <xref:System.Data.DataSet> enthält eine Reihe verknüpfter Tabellen, können Sie mithilfe von zwei <xref:System.Windows.Forms.DataGrid> Steuerelemente zum Anzeigen der Daten in einem Master/Detail-Format.</span><span class="sxs-lookup"><span data-stu-id="4db80-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="4db80-106">Eine <xref:System.Windows.Forms.DataGrid> als master-Raster, festgelegt und die Sekunde als das Raster festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4db80-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="4db80-107">Wenn Sie einen Eintrag in der master-Liste auswählen, werden alle zugehörigen untergeordneten Einträge in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4db80-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="4db80-108">Beispielsweise wenn Ihre <xref:System.Data.DataSet> enthält eine Kundentabelle und einer verknüpften Tabelle Orders würden Sie angeben, der Customers-Tabelle der master-Raster sein und die Tabelle Orders, das Detailraster sein.</span><span class="sxs-lookup"><span data-stu-id="4db80-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="4db80-109">Wenn ein Kunde aus der master-Raster ausgewählt ist, würden alle Bestellungen dieses Kunden in der Orders-Tabelle zugeordnet im Raster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4db80-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="4db80-110">So legen Sie eine Master-/detailbeziehung programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="4db80-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="4db80-111">Erstellen Sie zwei neue <xref:System.Windows.Forms.DataGrid> steuert und deren Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="4db80-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="4db80-112">Hinzufügen von Tabellen für das Dataset.</span><span class="sxs-lookup"><span data-stu-id="4db80-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="4db80-113">Deklarieren Sie eine Variable vom Typ <xref:System.Data.DataRelation> Beziehung darstellen, erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4db80-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="4db80-114">Instanziieren Sie die Beziehung, indem Sie einen Namen für die Beziehung und Angeben der Tabellen-, Spalten- und Element, das die zwei Tabellen verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="4db80-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="4db80-115">Fügen Sie die Beziehung zu den <xref:System.Data.DataSet> des Objekts <xref:System.Data.DataSet.Relations%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="4db80-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="4db80-116">Verwenden der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode der <xref:System.Windows.Forms.DataGrid> jedes der Raster zum Binden der <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="4db80-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="4db80-117">Das folgende Beispiel zeigt, wie Sie eine Master/Detail-Beziehung zwischen den Tabellen Customers und Orders in einer zuvor generierten festlegen <xref:System.Data.DataSet> (`ds`).</span><span class="sxs-lookup"><span data-stu-id="4db80-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4db80-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4db80-118">See also</span></span>

- [<span data-ttu-id="4db80-119">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4db80-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="4db80-120">Übersicht über das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4db80-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="4db80-121">Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="4db80-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
