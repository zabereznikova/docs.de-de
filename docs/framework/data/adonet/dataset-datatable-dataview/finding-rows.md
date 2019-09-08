---
title: Suchen von Zeilen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: ad10557a55b498fe004bff6ce89801e975e7138b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786321"
---
# <a name="finding-rows"></a><span data-ttu-id="105c9-102">Suchen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="105c9-102">Finding Rows</span></span>
<span data-ttu-id="105c9-103">Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="105c9-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="105c9-104">Die Unterscheidung nach Groß-/Kleinschreibung von Suchwerten in den Methoden **Find** und **FindRows** wird durch die **CaseSensitive** -Eigenschaft des zugrunde liegenden <xref:System.Data.DataTable>bestimmt.</span><span class="sxs-lookup"><span data-stu-id="105c9-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="105c9-105">Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="105c9-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="105c9-106">Die **Find** -Methode gibt eine ganze Zahl mit dem Index <xref:System.Data.DataRowView> von zurück, der mit den Suchkriterien übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="105c9-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="105c9-107">Wenn mehr als eine Zeile mit den Suchkriterien übereinstimmt, wird nur der Index der ersten übereinstimmenden **DataRowView** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="105c9-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="105c9-108">Wenn keine Übereinstimmungen gefunden werden, gibt **Find** -1 zurück.</span><span class="sxs-lookup"><span data-stu-id="105c9-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="105c9-109">Verwenden Sie die **FindRows** -Methode, um Suchergebnisse zurückzugeben, die mehreren Zeilen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="105c9-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="105c9-110">**FindRows** funktioniert genauso wie die **Find** -Methode, mit der Ausnahme, dass Sie ein **DataRowView** -Array zurückgibt, das auf alle übereinstimmenden Zeilen in der **DataView**verweist.</span><span class="sxs-lookup"><span data-stu-id="105c9-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="105c9-111">Wenn keine Übereinstimmungen gefunden werden, ist das **DataRowView** -Array leer.</span><span class="sxs-lookup"><span data-stu-id="105c9-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="105c9-112">Wenn Sie die **Find** -Methode oder die **FindRows** -Methode verwenden möchten, müssen Sie eine Sortierreihenfolge angeben, indem Sie **ApplyDefaultSort** auf **true** festlegen oder die **Sort** -Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="105c9-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="105c9-113">Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="105c9-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="105c9-114">Die **Find** -Methode und die **FindRows** -Methode nehmen ein Array von Werten als Eingabe an, deren Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht.</span><span class="sxs-lookup"><span data-stu-id="105c9-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="105c9-115">Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="105c9-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="105c9-116">Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben.</span><span class="sxs-lookup"><span data-stu-id="105c9-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="105c9-117">Beachten Sie, dass die Werte im Objekt Array für eine Sortierung in mehreren Spalten mit der Reihenfolge der Spalten identisch sein müssen, die in der **Sort** -Eigenschaft von **DataView**angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="105c9-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="105c9-118">Das folgende Codebeispiel zeigt, wie die **Find** -Methode für eine **DataView** mit einer einzelnen Spalten Sortierreihenfolge aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="105c9-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="105c9-119">Wenn die **Sort** -Eigenschaft mehrere Spalten angibt, müssen Sie ein Objekt Array mit den Suchwerten für jede Spalte in der von der **Sort** -Eigenschaft angegebenen Reihenfolge übergeben, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="105c9-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="105c9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="105c9-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="105c9-121">DataViews</span><span class="sxs-lookup"><span data-stu-id="105c9-121">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="105c9-122">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="105c9-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
