---
title: Suchen von Zeilen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 72af4b049153ce647cc1ceb2d40c3b17cc7ed988
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206550"
---
# <a name="finding-rows"></a>Suchen von Zeilen
Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden. Die Groß-/Kleinschreibung der Suche Werte in der **finden** und **FindRows** Methoden richtet sich nach der **CaseSensitive** Eigenschaft des zugrunde liegenden <xref:System.Data.DataTable>. Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.  
  
 Die **finden** Methode gibt eine ganze Zahl, durch den Index des dem <xref:System.Data.DataRowView> , die den Suchkriterien entspricht. Wenn mehr als eine Zeile mit die Suchkriterien entsprechen, nur der Index der ersten übereinstimmenden entspricht **DataRowView** zurückgegeben wird. Wenn keine Übereinstimmungen gefunden werden, **finden** gibt-1 zurück.  
  
 Verwenden, um Ergebnisse zurückzugeben, die mehrere Zeilen entsprechen den **FindRows** Methode. **FindRows** funktioniert wie die **finden** -Methode, mit dem Unterschied, dass die It gibt eine **DataRowView** Array, das alle übereinstimmenden Zeilen in verweist auf die **DataView**. Wenn keine Übereinstimmungen gefunden werden, die **DataRowView** Array leer sein wird.  
  
 Verwenden der **finden** oder **FindRows** Methoden müssen Sie eine Sortierung angeben bestellen, entweder durch Festlegen **ApplyDefaultSort** zu **"true"** oder mithilfe der **Sortierreihenfolge** Eigenschaft. Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.  
  
 Die **finden** und **FindRows** Methoden akzeptieren ein Array von Werten als Eingabe, dessen Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht. Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden. Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben. Beachten Sie, dass für eine Sortierung für mehrere Spalten die Werte im Objektarray die Reihenfolge der im angegebenen Spalten übereinstimmen müssen die **Sortierreihenfolge** Eigenschaft der **"DataView"**.  
  
 Das folgende Codebeispiel zeigt die **finden** für aufgerufene Methode eine **DataView** mit einer einzelnen Spalte Sortierreihenfolge.  
  
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
  
 Wenn Ihre **Sortierreihenfolge** -Eigenschaft mehrere Spalten angibt, müssen Sie ein Objektarray mit den Suchwerten für jede Spalte in der vom angegebenen Reihenfolge übergeben die **sortieren** -Eigenschaft wie im folgenden Codebeispiel wird.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
