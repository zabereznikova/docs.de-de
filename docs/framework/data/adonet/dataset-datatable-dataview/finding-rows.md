---
title: Suchen von Zeilen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: daa8097bc5dfee203f988915b1e4a8bdcd2c50e0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515411"
---
# <a name="finding-rows"></a><span data-ttu-id="e6a0f-102">Suchen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="e6a0f-102">Finding Rows</span></span>
<span data-ttu-id="e6a0f-103">Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="e6a0f-104">Die Groß-/Kleinschreibung der Suche Werte in der **finden** und **FindRows** Methoden richtet sich nach der **CaseSensitive** Eigenschaft des zugrunde liegenden <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="e6a0f-105">Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="e6a0f-106">Die **finden** Methode gibt eine ganze Zahl, durch den Index des dem <xref:System.Data.DataRowView> , die den Suchkriterien entspricht.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="e6a0f-107">Wenn mehr als eine Zeile mit die Suchkriterien entsprechen, nur der Index der ersten übereinstimmenden entspricht **DataRowView** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="e6a0f-108">Wenn keine Übereinstimmungen gefunden werden, **finden** gibt-1 zurück.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="e6a0f-109">Verwenden, um Ergebnisse zurückzugeben, die mehrere Zeilen entsprechen den **FindRows** Methode.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="e6a0f-110">**FindRows** funktioniert wie die **finden** -Methode, mit dem Unterschied, dass die It gibt eine **DataRowView** Array, das alle übereinstimmenden Zeilen in verweist auf die **DataView**.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="e6a0f-111">Wenn keine Übereinstimmungen gefunden werden, die **DataRowView** Array leer sein wird.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="e6a0f-112">Verwenden der **finden** oder **FindRows** Methoden müssen Sie eine Sortierung angeben bestellen, entweder durch Festlegen **ApplyDefaultSort** zu **"true"** oder mithilfe der **Sortierreihenfolge** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="e6a0f-113">Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="e6a0f-114">Die **finden** und **FindRows** Methoden akzeptieren ein Array von Werten als Eingabe, dessen Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="e6a0f-115">Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="e6a0f-116">Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="e6a0f-117">Beachten Sie, dass für eine Sortierung für mehrere Spalten die Werte im Objektarray die Reihenfolge der im angegebenen Spalten übereinstimmen müssen die **Sortierreihenfolge** Eigenschaft der **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="e6a0f-118">Das folgende Codebeispiel zeigt die **finden** für aufgerufene Methode eine **DataView** mit einer einzelnen Spalte Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",   
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 <span data-ttu-id="e6a0f-119">Wenn Ihre **Sortierreihenfolge** -Eigenschaft mehrere Spalten angibt, müssen Sie ein Objektarray mit den Suchwerten für jede Spalte in der vom angegebenen Reihenfolge übergeben die **sortieren** -Eigenschaft wie im folgenden Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="e6a0f-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =   
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),   
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6a0f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6a0f-120">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="e6a0f-121">DataViews</span><span class="sxs-lookup"><span data-stu-id="e6a0f-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="e6a0f-122">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e6a0f-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
