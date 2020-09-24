---
title: "\"DataRow\"-Löschung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 2092d7319a398bbdeaef764d677818f78ddf9de9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153351"
---
# <a name="datarow-deletion"></a><span data-ttu-id="f360e-102">"DataRow"-Löschung</span><span class="sxs-lookup"><span data-stu-id="f360e-102">DataRow Deletion</span></span>

<span data-ttu-id="f360e-103">Es gibt zwei Methoden zum Löschen eines- <xref:System.Data.DataRow> Objekts aus einem <xref:System.Data.DataTable> -Objekt: die **Remove** -Methode des <xref:System.Data.DataRowCollection> -Objekts und die- <xref:System.Data.DataRow.Delete%2A> Methode des **DataRow** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="f360e-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="f360e-104">Während die- <xref:System.Data.DataRowCollection.Remove%2A> Methode eine **DataRow** aus der **DataRowCollection**löscht, <xref:System.Data.DataRow.Delete%2A> markiert die Methode nur die Zeile zum Löschen.</span><span class="sxs-lookup"><span data-stu-id="f360e-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="f360e-105">Das eigentliche Entfernen tritt auf, wenn die Anwendung die Methode " **akzeptchanges** " aufruft.</span><span class="sxs-lookup"><span data-stu-id="f360e-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="f360e-106">Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen.</span><span class="sxs-lookup"><span data-stu-id="f360e-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="f360e-107">Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f360e-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="f360e-108">Beim Durchlaufen eines <xref:System.Data.DataRow.Delete%2A>-Objekts sollten weder <xref:System.Data.DataRowCollection.Remove%2A> noch <xref:System.Data.DataRowCollection> in einer foreach-Schleife aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f360e-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="f360e-109">Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="f360e-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="f360e-110">Wenn Sie eine <xref:System.Data.DataSet> -oder- **Daten** Tabelle zusammen mit **einem DataAdapter** und einer relationalen Datenquelle verwenden, verwenden Sie die **Delete** -Methode der **DataRow** , um die Zeile zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f360e-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="f360e-111">Die **Delete** -Methode markiert die Zeile als **gelöscht** im **DataSet** oder **in der Datentabelle** , entfernt Sie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="f360e-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="f360e-112">Wenn der **DataAdapter** auf eine Zeile stößt, die als **gelöscht**markiert ist, führt er stattdessen seine **DeleteCommand** -Methode aus, um die Zeile in der Datenquelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f360e-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="f360e-113">Die Zeile kann dann mithilfe der Methode " **Accept tchanges** " dauerhaft entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f360e-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="f360e-114">Wenn Sie zum Löschen der Zeile " **Entfernen** " verwenden, wird die Zeile vollständig aus der Tabelle entfernt, aber der **DataAdapter** löscht die Zeile nicht in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f360e-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="f360e-115">Die **Remove** -Methode der **DataRowCollection** übernimmt eine **DataRow** als Argument und entfernt Sie aus der Auflistung, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f360e-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="f360e-116">Im Gegensatz dazu wird im folgenden Beispiel veranschaulicht, wie die **Delete** -Methode für eine **DataRow** aufgerufen wird, um den **RowState** in " **deleted**" zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f360e-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="f360e-117">Wenn eine Zeile zum Löschen markiert ist und Sie die **Accept-Changes** -Methode des **datbare** -Objekts aufzurufen, wird die Zeile aus der **Daten**Tabelle entfernt.</span><span class="sxs-lookup"><span data-stu-id="f360e-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="f360e-118">Wenn Sie dagegen **RejectChanges**aufrufen, wird der **RowState** der Zeile auf den Wert zurückgesetzt, der vor der Markierung als **gelöscht**markiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f360e-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f360e-119">Wenn der **RowState** einer **DataRow** **hinzugefügt**wird, was bedeutet, dass Sie der Tabelle soeben hinzugefügt wurde und dann als **gelöscht**markiert ist, wird Sie aus der Tabelle entfernt.</span><span class="sxs-lookup"><span data-stu-id="f360e-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f360e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f360e-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="f360e-121">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="f360e-121">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="f360e-122">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f360e-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
