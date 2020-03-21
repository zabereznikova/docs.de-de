---
title: Suchen von Zeilen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: cfd4587f0dde7687ecf88bf6b31c44b90a2287ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151142"
---
# <a name="finding-rows"></a>Suchen von Zeilen
Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden. Die Groß-/Kleinschreibung von Suchwerten in den **Such-** und **FindRows-Methoden** wird durch die **CaseSensitive-Eigenschaft** des zugrunde liegenden <xref:System.Data.DataTable>bestimmt. Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.  
  
 Die **Find-Methode** gibt eine ganze Zahl <xref:System.Data.DataRowView> mit dem Index des zurück, der den Suchkriterien entspricht. Wenn mehr als eine Zeile den Suchkriterien entspricht, wird nur der Index der ersten übereinstimmenden **DataRowView** zurückgegeben. Wenn keine Übereinstimmungen gefunden werden, gibt **Find** -1 zurück.  
  
 Um Suchergebnisse zurückzugeben, die mehreren Zeilen entsprechen, verwenden Sie die **FindRows-Methode.** **FindRows** funktioniert genau wie die **Find-Methode,** mit der Ausnahme, dass ein **DataRowView-Array** zurückgegeben wird, das auf alle übereinstimmenden Zeilen in **DataView**verweist. Wenn keine Übereinstimmungen gefunden werden, ist das **DataRowView-Array** leer.  
  
 Um die **Methoden Suchen** oder FindRows zu **verwenden,** müssen Sie eine Sortierreihenfolge angeben, indem Sie **ApplyDefaultSort** auf **true** oder mithilfe der **Sort-Eigenschaft** festlegen. Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.  
  
 Die **Methoden Suchen** und **FindRows** verwenden ein Array von Werten als Eingabe, deren Länge mit der Anzahl der Spalten in der Sortierreihenfolge übereinstimmt. Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden. Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben. Beachten Sie, dass für eine Sortierung für mehrere Spalten die Werte im Objektarray mit der Reihenfolge der Spalten übereinstimmen müssen, die in der **Sort-Eigenschaft** der **DataView**angegeben sind.  
  
 Das folgende Codebeispiel **Find** zeigt die Find-Methode, die für eine **DataView** mit einer einzelnen Spaltensortierreihenfolge aufgerufen wird.  
  
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
  
 Wenn Ihre **Sort-Eigenschaft** mehrere Spalten angibt, müssen Sie ein Objektarray mit den Suchwerten für jede Spalte in der reihenfolge übergeben, die von der **Sort-Eigenschaft** angegeben wird, wie im folgenden Codebeispiel.  
  
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
