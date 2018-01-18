---
title: Suchen von Zeilen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 43703ead9d38ea1cf02539f12479e9228d7eacd4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="finding-rows"></a><span data-ttu-id="737df-102">Suchen von Zeilen</span><span class="sxs-lookup"><span data-stu-id="737df-102">Finding Rows</span></span>
<span data-ttu-id="737df-103">Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="737df-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="737df-104">Die Groß-/Kleinschreibung der Suche nach Werten in der **suchen** und **FindRows** Methoden richtet sich nach der **CaseSensitive** Eigenschaft des zugrunde liegenden <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="737df-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="737df-105">Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="737df-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="737df-106">Die **suchen** Methode gibt eine ganze Zahl mit dem Index für die <xref:System.Data.DataRowView> , die mit die Suchkriterien übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="737df-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="737df-107">Wenn mehr als eine Zeile mit die Suchkriterien entsprechen, die nur der Index der ersten übereinstimmenden entspricht **DataRowView** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="737df-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="737df-108">Wenn keine Übereinstimmungen gefunden werden, **suchen** gibt-1 zurück.</span><span class="sxs-lookup"><span data-stu-id="737df-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="737df-109">Um Suchergebnisse zurückzugeben, die mehrere Zeilen entsprechen, verwenden die **FindRows** Methode.</span><span class="sxs-lookup"><span data-stu-id="737df-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="737df-110">**FindRows** funktioniert wie die **suchen** Methode, mit der Ausnahme zurückgegeben, eine **DataRowView** Array, das alle übereinstimmenden Zeilen in verweist auf die **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="737df-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="737df-111">Wenn keine Übereinstimmungen gefunden werden, die **DataRowView** Array leer sein wird.</span><span class="sxs-lookup"><span data-stu-id="737df-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="737df-112">Verwenden der **suchen** oder **FindRows** Methoden müssen Sie eine Sortierung angeben bestellen Sie hierfür entweder **ApplyDefaultSort** auf **"true"** oder mithilfe der **Sortieren** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="737df-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="737df-113">Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="737df-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="737df-114">Die **suchen** und **FindRows** Methoden akzeptieren ein Array von Werten als Eingabe, dessen Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht.</span><span class="sxs-lookup"><span data-stu-id="737df-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="737df-115">Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="737df-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="737df-116">Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben.</span><span class="sxs-lookup"><span data-stu-id="737df-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="737df-117">Beachten Sie, dass für eine Sortierung für mehrere Spalten die Werte im Objektarray die Reihenfolge der Spalten im angegebenen entsprechen müssen die **sortieren** Eigenschaft von der **"DataView"**.</span><span class="sxs-lookup"><span data-stu-id="737df-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="737df-118">Das folgende Codebeispiel zeigt die **suchen** für aufgerufene Methode einen **"DataView"** mit einer einzelnen Spalte Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="737df-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="737df-119">Wenn Ihre **sortieren** -Eigenschaft mehrere Spalten angibt, müssen Sie ein Objektarray mit den Suchwerten für jede Spalte in der Reihenfolge, angegeben durch Übergeben der **sortieren** -Eigenschaft wie im folgenden Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="737df-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="737df-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="737df-120">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="737df-121">DataViews</span><span class="sxs-lookup"><span data-stu-id="737df-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="737df-122">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="737df-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
