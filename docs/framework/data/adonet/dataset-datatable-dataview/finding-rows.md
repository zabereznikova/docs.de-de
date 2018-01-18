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
# <a name="finding-rows"></a>Suchen von Zeilen
Mithilfe der <xref:System.Data.DataView.Find%2A>-Methode und der <xref:System.Data.DataView.FindRows%2A>-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden. Die Groß-/Kleinschreibung der Suche nach Werten in der **suchen** und **FindRows** Methoden richtet sich nach der **CaseSensitive** Eigenschaft des zugrunde liegenden <xref:System.Data.DataTable>. Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.  
  
 Die **suchen** Methode gibt eine ganze Zahl mit dem Index für die <xref:System.Data.DataRowView> , die mit die Suchkriterien übereinstimmt. Wenn mehr als eine Zeile mit die Suchkriterien entsprechen, die nur der Index der ersten übereinstimmenden entspricht **DataRowView** zurückgegeben wird. Wenn keine Übereinstimmungen gefunden werden, **suchen** gibt-1 zurück.  
  
 Um Suchergebnisse zurückzugeben, die mehrere Zeilen entsprechen, verwenden die **FindRows** Methode. **FindRows** funktioniert wie die **suchen** Methode, mit der Ausnahme zurückgegeben, eine **DataRowView** Array, das alle übereinstimmenden Zeilen in verweist auf die **"DataView"**. Wenn keine Übereinstimmungen gefunden werden, die **DataRowView** Array leer sein wird.  
  
 Verwenden der **suchen** oder **FindRows** Methoden müssen Sie eine Sortierung angeben bestellen Sie hierfür entweder **ApplyDefaultSort** auf **"true"** oder mithilfe der **Sortieren** Eigenschaft. Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.  
  
 Die **suchen** und **FindRows** Methoden akzeptieren ein Array von Werten als Eingabe, dessen Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht. Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden. Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben. Beachten Sie, dass für eine Sortierung für mehrere Spalten die Werte im Objektarray die Reihenfolge der Spalten im angegebenen entsprechen müssen die **sortieren** Eigenschaft von der **"DataView"**.  
  
 Das folgende Codebeispiel zeigt die **suchen** für aufgerufene Methode einen **"DataView"** mit einer einzelnen Spalte Sortierreihenfolge.  
  
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
  
 Wenn Ihre **sortieren** -Eigenschaft mehrere Spalten angibt, müssen Sie ein Objektarray mit den Suchwerten für jede Spalte in der Reihenfolge, angegeben durch Übergeben der **sortieren** -Eigenschaft wie im folgenden Codebeispiel wird.  
  
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
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
