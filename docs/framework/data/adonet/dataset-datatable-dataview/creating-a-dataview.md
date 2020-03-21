---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151337"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="838a9-102">Erstellen eines "DataViews"</span><span class="sxs-lookup"><span data-stu-id="838a9-102">Creating a DataView</span></span>
<span data-ttu-id="838a9-103">Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>:</span><span class="sxs-lookup"><span data-stu-id="838a9-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="838a9-104">Sie können den **DataView-Konstruktor** verwenden oder einen <xref:System.Data.DataTable.DefaultView%2A> Verweis <xref:System.Data.DataTable>auf die Eigenschaft der erstellen.</span><span class="sxs-lookup"><span data-stu-id="838a9-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="838a9-105">Der **DataView-Konstruktor** kann leer sein, oder er kann entweder eine **DataTable** als einzelnes Argument oder eine **DataTable** zusammen mit Filterkriterien, Sortierkriterien und einem Zeilenstatusfilter verwenden.</span><span class="sxs-lookup"><span data-stu-id="838a9-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="838a9-106">Weitere Informationen zu den zusätzlichen Argumenten, die für die Verwendung mit **DataView**verfügbar sind, finden Sie unter [Sortieren und Filtern von Daten](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="838a9-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="838a9-107">Da der Index für eine **DataView** sowohl beim Erstellen der **DataView** als auch beim Ändern der **Eigenschaften Sort**, **RowFilter**oder **RowStateFilter** erstellt wird, erzielen Sie die beste Leistung, indem Sie beim Erstellen der **DataView**alle anfänglichen Sortierreihenfolge- oder Filterkriterien als Konstruktorargumente angeben.</span><span class="sxs-lookup"><span data-stu-id="838a9-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="838a9-108">Das Erstellen einer **DataView** ohne Angabe von Sortier- oder Filterkriterien und anschließendes Festlegen der **Eigenschaften Sortieren**, **RowFilter**oder **RowStateFilter** bewirkt, dass der Index mindestens zweimal erstellt wird: einmal, wenn die **DataView** erstellt wird, und erneut, wenn die Sortier- oder Filtereigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="838a9-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="838a9-109">Beachten Sie, dass Sie, wenn Sie eine **DataView** mit dem Konstruktor erstellen, der keine Argumente verwendet, die **DataView** erst verwenden können, wenn Sie die **Table-Eigenschaft** festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="838a9-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="838a9-110">Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine **DataView** mit dem **DataView-Konstruktor** erstellen.</span><span class="sxs-lookup"><span data-stu-id="838a9-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="838a9-111">Eine **RowFilter**-, **Sortierspalte** und **DataViewRowState** werden zusammen mit der **DataTable**bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="838a9-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="838a9-112">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe der **DefaultView-Eigenschaft** der Tabelle einen Verweis auf die **Standarddatenansicht** einer **DataTable** abrufen.</span><span class="sxs-lookup"><span data-stu-id="838a9-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="838a9-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="838a9-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="838a9-114">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="838a9-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="838a9-115">Sortieren und Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="838a9-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="838a9-116">"DataTables"</span><span class="sxs-lookup"><span data-stu-id="838a9-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="838a9-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="838a9-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
