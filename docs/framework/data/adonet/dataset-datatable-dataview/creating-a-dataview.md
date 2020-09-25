---
title: Erstellen eines "DataViews"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 539e9763c8aa4affdb6f3bd219a99dbca50cee01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202342"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="d4c07-102">Erstellen eines "DataViews"</span><span class="sxs-lookup"><span data-stu-id="d4c07-102">Creating a DataView</span></span>

<span data-ttu-id="d4c07-103">Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>:</span><span class="sxs-lookup"><span data-stu-id="d4c07-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="d4c07-104">Sie können den **DataView** -Konstruktor verwenden, oder Sie können einen Verweis auf die- <xref:System.Data.DataTable.DefaultView%2A> Eigenschaft von erstellen <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="d4c07-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d4c07-105">Der **DataView** -Konstruktor kann leer sein oder entweder eine **Daten** Tabelle als einzelnes Argument oder eine **Daten** Tabelle zusammen mit Filterkriterien, Sortierkriterien und einem Zeilen Status Filter annehmen.</span><span class="sxs-lookup"><span data-stu-id="d4c07-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="d4c07-106">Weitere Informationen zu den zusätzlichen Argumenten, die für die Verwendung mit **DataView**verfügbar sind, finden Sie unter [Sortieren und Filtern von Daten](sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="d4c07-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="d4c07-107">Da der Index für eine **DataView** sowohl bei der Erstellung der **DataView** als auch bei einer Änderung der Eigenschaften **Sort**, **RowFilter**oder **RowStateFilter** erstellt wird, erzielen Sie eine optimale Leistung, indem Sie beim Erstellen der **DataView**eine beliebige anfängliche Sortierreihenfolge oder Filterkriterien als Konstruktorargumente angeben.</span><span class="sxs-lookup"><span data-stu-id="d4c07-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="d4c07-108">Wenn Sie eine **DataView** ohne Angabe von Sortier-oder Filterkriterien erstellen und dann die Eigenschaften **Sort**, **RowFilter**oder **RowStateFilter** später festlegen, wird der Index mindestens zweimal erstellt: einmal, wenn die **DataView** erstellt wird, und auch dann, wenn eine der Sortier-oder Filtereigenschaften geändert wird.</span><span class="sxs-lookup"><span data-stu-id="d4c07-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="d4c07-109">Beachten Sie Folgendes: Wenn Sie eine **DataView** mithilfe des Konstruktors erstellen, der keine Argumente akzeptiert, können Sie die **DataView** erst verwenden, wenn Sie die **Table** -Eigenschaft festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="d4c07-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="d4c07-110">Im folgenden Codebeispiel wird veranschaulicht, wie eine **DataView** mit dem **DataView** -Konstruktor erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4c07-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="d4c07-111">Ein **RowFilter**, eine **Sortier** Spalte und ein **DataViewRowState** werden zusammen mit der **Daten**Tabelle bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d4c07-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="d4c07-112">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mithilfe der **DefaultView** -Eigenschaft der Tabelle einen Verweis auf die Standard **DataView** einer **Daten** Tabelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="d4c07-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4c07-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4c07-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="d4c07-114">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="d4c07-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="d4c07-115">Sortieren und Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="d4c07-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="d4c07-116">"DataTables"</span><span class="sxs-lookup"><span data-stu-id="d4c07-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="d4c07-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4c07-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
