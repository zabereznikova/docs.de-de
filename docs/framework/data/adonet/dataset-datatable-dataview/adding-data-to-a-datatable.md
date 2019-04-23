---
title: Hinzufügen von Daten zu einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: ec4ad84a39afe21ef77507732e5e0e417d45f3e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104285"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="e9fce-102">Hinzufügen von Daten zu einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="e9fce-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="e9fce-103">Nachdem Sie eine <xref:System.Data.DataTable> erstellt und deren Struktur mithilfe von Spalten und Einschränkungen definiert haben, können Sie der Tabelle neue Datenzeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e9fce-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="e9fce-104">Dazu deklarieren Sie eine neue Variable als <xref:System.Data.DataRow>-Typ.</span><span class="sxs-lookup"><span data-stu-id="e9fce-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="e9fce-105">Ein neues **DataRow** Objekt wird zurückgegeben, beim Aufrufen der <xref:System.Data.DataTable.NewRow%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="e9fce-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="e9fce-106">Die **DataTable** erstellt dann die **DataRow** Objekt entsprechend der Struktur der Tabelle gemäß den <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="e9fce-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="e9fce-107">Im folgende Beispiel wird veranschaulicht, wie zum Erstellen einer neuen Zeile durch Aufrufen der **NewRow** Methode.</span><span class="sxs-lookup"><span data-stu-id="e9fce-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="e9fce-108">Anschließend können Sie die neu hinzugefügte Zeile mithilfe eines Indexes oder des Spaltennamens bearbeiten, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9fce-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="e9fce-109">Nachdem die Daten in der neuen Zeile eingefügt werden die **hinzufügen** Methode dient zum Hinzufügen der Zeile, die <xref:System.Data.DataRowCollection>, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9fce-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="e9fce-110">Sie können auch aufrufen, die **hinzufügen** Methode, um eine neue Zeile hinzuzufügen, durch die Übergabe in einem Array von Werten, die als typisierte <xref:System.Object>, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e9fce-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="e9fce-111">Übergibt ein Array von Werten als **Objekt**, zu der **hinzufügen** Methode erstellt eine neue Zeile in der Tabelle und als Spaltenwerte werden auf die Werte im Objektarray.</span><span class="sxs-lookup"><span data-stu-id="e9fce-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="e9fce-112">Beachten Sie, dass Werte in dem Array nacheinander den Spalten zugeordnet werden, und zwar in der Reihenfolge, in der sie in der Tabelle vorkommen.</span><span class="sxs-lookup"><span data-stu-id="e9fce-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="e9fce-113">Im folgenden Beispiel wird 10 Zeilen, auf das neu erstellte **Kunden** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e9fce-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9fce-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9fce-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="e9fce-115">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="e9fce-115">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="e9fce-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e9fce-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
