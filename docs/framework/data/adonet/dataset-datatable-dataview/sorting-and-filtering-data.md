---
title: Sortieren und Filtern von Daten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 89e2fdf656fb06ee545ba936f033646ad86182d4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183376"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="77f4d-102">Sortieren und Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="77f4d-102">Sorting and Filtering Data</span></span>

<span data-ttu-id="77f4d-103">Die <xref:System.Data.DataView> stellt mehrere Methoden zum Sortieren und Filtern von Daten in einer <xref:System.Data.DataTable> bereit:</span><span class="sxs-lookup"><span data-stu-id="77f4d-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="77f4d-104">Mit der <xref:System.Data.DataView.Sort%2A>-Eigenschaft können Sie einzelne oder mehrere Sortierreihenfolgen für Spalten angeben und die Parameter ASC (ascending = aufsteigend) und DESC (descending = absteigend) einfügen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="77f4d-105">Sie können mithilfe der <xref:System.Data.DataView.ApplyDefaultSort%2A>-Eigenschaft automatisch eine Sortierreihenfolge in aufsteigender Reihenfolge auf Grundlage der Primärschlüsselspalte bzw. -spalten der Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="77f4d-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> gilt nur, wenn die **Sort** -Eigenschaft ein NULL-Verweis oder eine leere Zeichenfolge ist und wenn für die Tabelle ein Primärschlüssel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="77f4d-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="77f4d-107">	Mit der <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft können Sie Teilmengen von Zeilen angeben, die auf den Spaltenwerten basieren.</span><span class="sxs-lookup"><span data-stu-id="77f4d-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="77f4d-108">Ausführliche Informationen zu gültigen Ausdrücken für die **RowFilter** -Eigenschaft finden Sie in den Referenzinformationen für die- <xref:System.Data.DataColumn.Expression%2A> Eigenschaft der- <xref:System.Data.DataColumn> Klasse.</span><span class="sxs-lookup"><span data-stu-id="77f4d-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="77f4d-109">Wenn Sie die Ergebnisse einer bestimmten Abfrage für die Daten zurückgeben möchten, anstatt eine dynamische Ansicht einer Teilmenge der Daten bereitzustellen, verwenden Sie die- <xref:System.Data.DataView.Find%2A> Methode oder die- <xref:System.Data.DataView.FindRows%2A> Methode der **DataView** , um eine optimale Leistung zu erzielen, anstatt die **RowFilter** -Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="77f4d-110">Wenn Sie die **RowFilter** -Eigenschaft festlegen, wird der Index für die Daten neu erstellt, und die Leistung wird erhöht, und die Leistung wird verringert.</span><span class="sxs-lookup"><span data-stu-id="77f4d-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="77f4d-111">Die **RowFilter** -Eigenschaft wird am besten in einer Daten gebundenen Anwendung verwendet, in der ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="77f4d-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="77f4d-112">Die **Find** -Methode und die **FindRows** -Methode nutzen den aktuellen Index, ohne dass der Index neu erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="77f4d-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="77f4d-113">Weitere Informationen zu den Methoden **Find** und **FindRows** finden Sie untersuchen von [Zeilen](finding-rows.md).</span><span class="sxs-lookup"><span data-stu-id="77f4d-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="77f4d-114">Mit der <xref:System.Data.DataView.RowStateFilter%2A>-Eigenschaft können Sie festlegen, welche Zeilenversionen Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="77f4d-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="77f4d-115">Die **DataView** verwaltet implizit, welche Zeilen Version in Abhängigkeit vom **RowState** der zugrunde liegenden Zeile verfügbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="77f4d-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="77f4d-116">Wenn z. b. **RowStateFilter** auf **DataViewRowState. Deleted**festgelegt ist, macht die **DataView** die **Original** Zeilen Version aller **gelöschten** Zeilen verfügbar, da keine **aktuelle** Zeilen Version vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="77f4d-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="77f4d-117">Mithilfe der **rowversion** -Eigenschaft der **DataRowView**können Sie ermitteln, welche Zeilen Version einer Zeile verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="77f4d-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="77f4d-118">In der folgenden Tabelle sind die Optionen für **DataViewRowState**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="77f4d-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="77f4d-119">"DataViewRowState"-Optionen</span><span class="sxs-lookup"><span data-stu-id="77f4d-119">DataViewRowState options</span></span>|<span data-ttu-id="77f4d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77f4d-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="77f4d-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="77f4d-121">**CurrentRows**</span></span>|<span data-ttu-id="77f4d-122">Die **aktuelle** Zeilen Version aller **unverändert**, **hinzugefügten**und **geänderten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="77f4d-123">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="77f4d-123">This is the default.</span></span>|  
    |<span data-ttu-id="77f4d-124">**Hinzugefügt**</span><span class="sxs-lookup"><span data-stu-id="77f4d-124">**Added**</span></span>|<span data-ttu-id="77f4d-125">Die **aktuelle** Zeilen Version aller **hinzugefügten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="77f4d-126">**Gelöscht**</span><span class="sxs-lookup"><span data-stu-id="77f4d-126">**Deleted**</span></span>|<span data-ttu-id="77f4d-127">Die **Original** Zeilen Version aller **gelöschten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="77f4d-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="77f4d-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="77f4d-129">Die **aktuelle** Zeilen Version aller **geänderten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="77f4d-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="77f4d-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="77f4d-131">Die **Original** Zeilen Version aller **geänderten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="77f4d-132">**None**</span><span class="sxs-lookup"><span data-stu-id="77f4d-132">**None**</span></span>|<span data-ttu-id="77f4d-133">Keine Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-133">No rows.</span></span>|  
    |<span data-ttu-id="77f4d-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="77f4d-134">**OriginalRows**</span></span>|<span data-ttu-id="77f4d-135">Die **Original** Zeilen Version aller **unverändert**, **geänderten**und **gelöschten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="77f4d-136">**Unverändert**</span><span class="sxs-lookup"><span data-stu-id="77f4d-136">**Unchanged**</span></span>|<span data-ttu-id="77f4d-137">Die **aktuelle** Zeilen Version aller **unveränderten** Zeilen.</span><span class="sxs-lookup"><span data-stu-id="77f4d-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="77f4d-138">Weitere Informationen zu Zeilen Zuständen und Zeilen Versionen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="77f4d-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="77f4d-139">Im folgenden Codebeispiel wird eine Ansicht erstellt, die alle Produkte anzeigt, bei denen die Anzahl der Einheiten im Lager kleiner als oder gleich der Neusortierungsebene ist, wobei zuerst nach der Lieferanten-ID und dann nach dem Produktnamen sortiert wird.</span><span class="sxs-lookup"><span data-stu-id="77f4d-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="77f4d-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77f4d-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="77f4d-141">"DataViews"</span><span class="sxs-lookup"><span data-stu-id="77f4d-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="77f4d-142">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="77f4d-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
