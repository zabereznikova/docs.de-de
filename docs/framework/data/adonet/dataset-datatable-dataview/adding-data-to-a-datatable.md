---
title: Hinzufügen von Daten zu einer "DataTable"
description: Weitere Informationen zum Hinzufügen neuer Daten Zeilen zu einer Tabelle in ADO.net finden Sie in diesem Beispielcode, nachdem Sie eine Datentabelle erstellt und ihre Struktur mithilfe von Spalten und Einschränkungen definiert haben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: aac2d90cc57a4af823c42f8c7eb2adcd43c63caf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164817"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="1f968-103">Hinzufügen von Daten zu einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="1f968-103">Adding Data to a DataTable</span></span>

<span data-ttu-id="1f968-104">Nachdem Sie eine <xref:System.Data.DataTable> erstellt und deren Struktur mithilfe von Spalten und Einschränkungen definiert haben, können Sie der Tabelle neue Datenzeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1f968-104">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="1f968-105">Dazu deklarieren Sie eine neue Variable als <xref:System.Data.DataRow>-Typ.</span><span class="sxs-lookup"><span data-stu-id="1f968-105">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="1f968-106">Ein neues **DataRow** -Objekt wird zurückgegeben, wenn Sie die- <xref:System.Data.DataTable.NewRow%2A> Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1f968-106">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="1f968-107">Die **Daten** Tabelle erstellt dann das **DataRow** -Objekt basierend auf der Struktur der Tabelle, wie im definiert <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="1f968-107">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="1f968-108">Im folgenden Beispiel wird veranschaulicht, wie eine neue Zeile durch Aufrufen der **NewRow** -Methode erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1f968-108">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="1f968-109">Anschließend können Sie die neu hinzugefügte Zeile mithilfe eines Indexes oder des Spaltennamens bearbeiten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f968-109">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="1f968-110">Nachdem die Daten in die neue Zeile eingefügt wurden, wird die-Methode mithilfe der **Add** -Methode der hinzugefügt <xref:System.Data.DataRowCollection> , wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f968-110">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="1f968-111">Sie können auch die **Add** -Methode zum Hinzufügen einer neuen Zeile hinzufügen, indem Sie ein Array von Werten übergeben, die als typisiert sind <xref:System.Object> , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f968-111">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="1f968-112">Wenn Sie ein Array von Werten, die als **Object**eingegeben werden, an die **Add** -Methode übergeben, wird eine neue Zeile in der Tabelle erstellt, und die Spaltenwerte werden auf die Werte im Objekt Array festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f968-112">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="1f968-113">Beachten Sie, dass Werte in dem Array nacheinander den Spalten zugeordnet werden, und zwar in der Reihenfolge, in der sie in der Tabelle vorkommen.</span><span class="sxs-lookup"><span data-stu-id="1f968-113">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="1f968-114">Im folgenden Beispiel werden der neu erstellten **Customers** -Tabelle 10 Zeilen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f968-114">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f968-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f968-115">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="1f968-116">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="1f968-116">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="1f968-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1f968-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
