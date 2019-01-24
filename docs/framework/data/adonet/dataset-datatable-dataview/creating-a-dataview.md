---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 0625d1005e6519b395ffd7ff0fb0c35583117875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623052"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="9185c-102">Erstellen eines "DataViews"</span><span class="sxs-lookup"><span data-stu-id="9185c-102">Creating a DataView</span></span>
<span data-ttu-id="9185c-103">Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>:</span><span class="sxs-lookup"><span data-stu-id="9185c-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="9185c-104">Können Sie die **DataView** -Konstruktor verwenden, oder Sie erstellen einen Verweis auf die <xref:System.Data.DataTable.DefaultView%2A> Eigenschaft der <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="9185c-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9185c-105">Die **DataView** Konstruktor kann leer sein oder akzeptiert entweder eine **DataTable** als einzelnes Argument, oder ein **DataTable** zusammen mit Filterkriterien, Sortierkriterien und eine Zeile State-Filter.</span><span class="sxs-lookup"><span data-stu-id="9185c-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="9185c-106">Weitere Informationen zu zusätzlichen Argumenten, die für die Verwendung mit der **DataView**, finden Sie unter [sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="9185c-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="9185c-107">Da der Index für eine **DataView** basiert sowohl bei der **DataView** erstellt wird, und wenn eine der **sortieren**, **RowFilter**, oder  **RowStateFilter** Eigenschaften geändert werden, erreichen Sie die optimale Leistung durch Angabe von alle anfänglichen Sortierreihenfolge- oder Filterkriterien als Konstruktorargumente, bei der Erstellung der **DataView**.</span><span class="sxs-lookup"><span data-stu-id="9185c-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="9185c-108">Erstellen einer **DataView** ohne Angabe von Sortier- oder Filterkriterien festlegen und anschließend die **Sortierreihenfolge**, **RowFilter**, oder **RowStateFilter** Eigenschaften höher führt dazu, dass den Index mindestens zweimal erstellt werden sollen: nach der bei der **DataView** erstellt wird, und erneut bei Eigenschaften Sortier- oder Filtereigenschaften geändert.</span><span class="sxs-lookup"><span data-stu-id="9185c-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="9185c-109">Beachten Sie, dass bei der Erstellung einer **DataView** verwenden den Konstruktor, der keine Argumente akzeptiert, Sie ist nicht möglich, verwenden Sie die **DataView** bis Sie festgelegt haben die **Tabelle** Eigenschaft .</span><span class="sxs-lookup"><span data-stu-id="9185c-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="9185c-110">Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer **DataView** mithilfe der **DataView** Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9185c-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="9185c-111">Ein **RowFilter**, **Sortierreihenfolge** Spalte und **DataViewRowState** bereitgestellt werden, zusammen mit den **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="9185c-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="9185c-112">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Verweis auf den Standardwert zu erhalten **DataView** von einer **DataTable** mithilfe der **DefaultView** Eigenschaft der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="9185c-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="9185c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9185c-113">See also</span></span>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="9185c-114">DataViews</span><span class="sxs-lookup"><span data-stu-id="9185c-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="9185c-115">Sortieren und Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="9185c-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [<span data-ttu-id="9185c-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="9185c-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="9185c-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9185c-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
