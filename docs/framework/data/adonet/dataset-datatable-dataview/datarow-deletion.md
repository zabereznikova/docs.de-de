---
title: "\"DataRow\"-Löschung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: e7e687dfa6af47161be9d26054eb58f319a5099d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425595"
---
# <a name="datarow-deletion"></a><span data-ttu-id="f4bdc-102">"DataRow"-Löschung</span><span class="sxs-lookup"><span data-stu-id="f4bdc-102">DataRow Deletion</span></span>
<span data-ttu-id="f4bdc-103">Stehen zwei Methoden Sie löschen können eine <xref:System.Data.DataRow> -Objekt aus einer <xref:System.Data.DataTable> Objekt: die **entfernen** -Methode der der <xref:System.Data.DataRowCollection> -Objekt, und die <xref:System.Data.DataRow.Delete%2A> -Methode der der **DataRow**Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="f4bdc-104">Während der <xref:System.Data.DataRowCollection.Remove%2A> Methode löscht eine **DataRow** aus der **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> Methode wird nur die Zeile zum Löschen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="f4bdc-105">Die tatsächlich entfernt, wenn die Anwendung ruft die **AcceptChanges** Methode.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="f4bdc-106">Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="f4bdc-107">Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="f4bdc-108">Beim Durchlaufen eines <xref:System.Data.DataRow.Delete%2A>-Objekts sollten weder <xref:System.Data.DataRowCollection.Remove%2A> noch <xref:System.Data.DataRowCollection> in einer foreach-Schleife aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="f4bdc-109">Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="f4bdc-110">Bei Verwendung einer <xref:System.Data.DataSet> oder **DataTable** in Verbindung mit einer **DataAdapter** und einer relationalen Datenquelle, verwenden Sie die **löschen** -Methode der der  **DataRow** auf die Zeile zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="f4bdc-111">Die **löschen** Methode kennzeichnet die Zeile als **gelöschte** in die **DataSet** oder **DataTable** jedoch nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="f4bdc-112">Stattdessen, wenn die **DataAdapter** findet eine Zeile, die als **gelöschte**, Ausführen der **DeleteCommand** Methode, um die Zeile in der Datenquelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="f4bdc-113">Die Zeile kann dann dauerhaft entfernt werden mithilfe der **AcceptChanges** Methode.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="f4bdc-114">Bei Verwendung von **entfernen** zum Löschen der zeilenupdates die Zeile wird vollständig aus der Tabelle entfernt jedoch **DataAdapter** die Zeile in der Datenquelle werden nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="f4bdc-115">Die **entfernen** Methode der **DataRowCollection** akzeptiert eine **DataRow** als Argument und entfernt sie aus der Auflistung, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="f4bdc-116">Im Gegensatz dazu wird im folgenden Beispiel wird veranschaulicht, wie zum Aufrufen der **löschen** Methode für eine **DataRow** so ändern Sie seine **RowState** zu **gelöschte** .</span><span class="sxs-lookup"><span data-stu-id="f4bdc-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="f4bdc-117">Wenn eine Zeile zum Löschen markiert ist, und Sie rufen die **AcceptChanges** Methode der **DataTable** Objekt ist, wird die Zeile wurde aus entfernt die **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="f4bdc-118">Im Gegensatz dazu sind Aufrufen **RejectChanges**, **RowState** wiederhergestellt, bevor Sie als markiert wird, was sie die Zeile **gelöschte**.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4bdc-119">Wenn die **RowState** von eine **DataRow** ist **Added**, d. h. sie gerade hinzugefügt wurde, in der Tabelle und wird dann als markiert **gelöschte**, ist aus der Tabelle entfernt.</span><span class="sxs-lookup"><span data-stu-id="f4bdc-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4bdc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4bdc-120">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="f4bdc-121">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="f4bdc-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="f4bdc-122">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f4bdc-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
