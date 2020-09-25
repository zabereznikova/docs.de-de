---
title: Suchen von Zeilen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: dc0661e29e6d3ee5aa3f54179e8abf265cd67d58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186977"
---
# <a name="finding-rows"></a>Suchen von Zeilen

Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden. Die Unterscheidung nach Groß-/Kleinschreibung von Suchwerten in den Methoden **Find** und **FindRows** wird durch die **CaseSensitive** -Eigenschaft des zugrunde liegenden bestimmt <xref:System.Data.DataTable> . Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.  
  
 Die **Find** -Methode gibt eine ganze Zahl mit dem Index von zurück, der mit <xref:System.Data.DataRowView> den Suchkriterien übereinstimmt. Wenn mehr als eine Zeile mit den Suchkriterien übereinstimmt, wird nur der Index der ersten übereinstimmenden **DataRowView** zurückgegeben. Wenn keine Übereinstimmungen gefunden werden, gibt **Find** -1 zurück.  
  
 Verwenden Sie die **FindRows** -Methode, um Suchergebnisse zurückzugeben, die mehreren Zeilen entsprechen. **FindRows** funktioniert genauso wie die **Find** -Methode, mit der Ausnahme, dass Sie ein **DataRowView** -Array zurückgibt, das auf alle übereinstimmenden Zeilen in der **DataView**verweist. Wenn keine Übereinstimmungen gefunden werden, ist das **DataRowView** -Array leer.  
  
 Wenn Sie die **Find** -Methode oder die **FindRows** -Methode verwenden möchten, müssen Sie eine Sortierreihenfolge angeben, indem Sie **ApplyDefaultSort** auf **true** festlegen oder die **Sort** -Eigenschaft verwenden. Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.  
  
 Die **Find** -Methode und die **FindRows** -Methode nehmen ein Array von Werten als Eingabe an, deren Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht. Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden. Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben. Beachten Sie, dass die Werte im Objekt Array für eine Sortierung in mehreren Spalten mit der Reihenfolge der Spalten identisch sein müssen, die in der **Sort** -Eigenschaft von **DataView**angegeben sind.  
  
 Das folgende Codebeispiel zeigt, wie die **Find** -Methode für eine **DataView** mit einer einzelnen Spalten Sortierreihenfolge aufgerufen wird.  
  
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
  
 Wenn die **Sort** -Eigenschaft mehrere Spalten angibt, müssen Sie ein Objekt Array mit den Suchwerten für jede Spalte in der von der **Sort** -Eigenschaft angegebenen Reihenfolge übergeben, wie im folgenden Codebeispiel gezeigt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- ["DataViews"](dataviews.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
