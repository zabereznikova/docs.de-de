---
title: "\"DataRow\"-Löschung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 128c41e1906b17e7f42458e8a5f1b3d3ec9cc449
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="datarow-deletion"></a><span data-ttu-id="12bd1-102">"DataRow"-Löschung</span><span class="sxs-lookup"><span data-stu-id="12bd1-102">DataRow Deletion</span></span>
<span data-ttu-id="12bd1-103">Stehen zwei Methoden, die Sie löschen können eine <xref:System.Data.DataRow> -Objekt aus einer <xref:System.Data.DataTable> Objekt: der **entfernen** Methode der <xref:System.Data.DataRowCollection> -Objekt, und die <xref:System.Data.DataRow.Delete%2A> Methode der **DataRow**Objekt.</span><span class="sxs-lookup"><span data-stu-id="12bd1-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="12bd1-104">Während der <xref:System.Data.DataRowCollection.Remove%2A> -Methode löscht eine **DataRow** aus der **DataRowCollection**, die <xref:System.Data.DataRow.Delete%2A> Methode nur die Zeile zum Löschen markiert.</span><span class="sxs-lookup"><span data-stu-id="12bd1-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="12bd1-105">Das eigentliche löschen erfolgt, wenn die Anwendung aufruft, die **AcceptChanges** Methode.</span><span class="sxs-lookup"><span data-stu-id="12bd1-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="12bd1-106">Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen.</span><span class="sxs-lookup"><span data-stu-id="12bd1-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="12bd1-107">Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12bd1-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="12bd1-108">Beim Durchlaufen eines <xref:System.Data.DataRow.Delete%2A>-Objekts sollten weder <xref:System.Data.DataRowCollection.Remove%2A> noch <xref:System.Data.DataRowCollection> in einer foreach-Schleife aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="12bd1-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="12bd1-109">Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="12bd1-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="12bd1-110">Bei Verwendung einer <xref:System.Data.DataSet> oder **DataTable** in Verbindung mit einer **"DataAdapter"** und einer relationalen Datenquelle verwenden die **löschen** Methode der  **DataRow** zum Entfernen der Zeile.</span><span class="sxs-lookup"><span data-stu-id="12bd1-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="12bd1-111">Die **löschen** Methode markiert die Zeile als **gelöschte** in der **DataSet** oder **DataTable** jedoch nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="12bd1-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="12bd1-112">Stattdessen, wenn die **"DataAdapter"** als markierte Zeile stößt **gelöschte**, führt er seine **DeleteCommand** Methode, um die Zeile in der Datenquelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="12bd1-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="12bd1-113">Die Zeile kann dann dauerhaft entfernt mithilfe der **AcceptChanges** Methode.</span><span class="sxs-lookup"><span data-stu-id="12bd1-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="12bd1-114">Bei Verwendung von **entfernen** um die Zeile zu löschen, wird die Zeile entfernt, vollständig aus der Tabelle, aber die **"DataAdapter"** löscht die Zeile in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="12bd1-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="12bd1-115">Die **entfernen** Methode der **DataRowCollection** nimmt eine **DataRow** als Argument und entfernt es aus der Auflistung, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="12bd1-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="12bd1-116">Im Gegensatz dazu das folgende Beispiel veranschaulicht das Aufrufen der **löschen** Methode auf eine **DataRow** so ändern Sie die **RowState** auf **gelöschte** .</span><span class="sxs-lookup"><span data-stu-id="12bd1-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="12bd1-117">Wenn eine Zeile zum Löschen markiert ist, und Sie rufen die **AcceptChanges** Methode der **DataTable** -Objekt, aus der Zeile entfernt die **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="12bd1-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="12bd1-118">Im Gegensatz dazu sind beim Aufrufen **RejectChanges**, **RowState** der Zeile wird zurückgesetzt, bevor als markiert war **gelöschte**.</span><span class="sxs-lookup"><span data-stu-id="12bd1-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12bd1-119">Wenn die **RowState** von einer **DataRow** ist **Added**, d. h. sie hat gerade der Tabelle hinzugefügt wurde, und wird dann als markiert **gelöschte**, ist aus der Tabelle entfernt.</span><span class="sxs-lookup"><span data-stu-id="12bd1-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bd1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12bd1-120">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="12bd1-121">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="12bd1-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="12bd1-122">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="12bd1-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
