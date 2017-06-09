---
title: "Suchen nach Zeilen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Suchen nach Zeilen
Mithilfe der <xref:System.Data.DataView.Find%2A>\-Methode und der <xref:System.Data.DataView.FindRows%2A>\-Methode von <xref:System.Data.DataView> kann nach Zeilen anhand deren Sortierschlüsselwerten gesucht werden.  In der **Find**\-Methode und der **FindRows**\-Methode wird die Berücksichtigung der Groß\- und Kleinschreibung in Suchwerten durch die **CaseSensitive**\-Eigenschaft der zugrunde liegenden <xref:System.Data.DataTable> festgelegt.  Suchwerte müssen vollständig mit den vorhandenen Sortierschlüsselwerten übereinstimmen, um ein Ergebnis zurückzugeben.  
  
 Die **Find**\-Methode gibt eine ganze Zahl mit dem Index der <xref:System.Data.DataRowView> zurück, die den Suchkriterien entspricht.  Wenn mehr als eine Zeile mit den Suchkriterien übereinstimmt, wird nur der Index der ersten übereinstimmenden **DataRowView** zurückgegeben.  Wenn keine Übereinstimmungen gefunden werden, gibt **Find** den Wert \-1 zurück.  
  
 Mit der **FindRows**\-Methode können Sie zu den Suchergebnissen zurückkehren, die mit mehreren Zeilen übereinstimmen.  **FindRows** funktioniert wie die **Find**\-Methode, außer dass sie ein **DataRowView**\-Array zurückgibt, das auf alle übereinstimmenden Zeilen in der **DataView** verweist.  Wenn keine Übereinstimmungen gefunden werden, ist das **DataRowView**\-Array leer.  
  
 Zum Verwenden der **Find**\-Methode oder der **FindRows**\-Methode muss eine Sortierreihenfolge festgelegt werden. Dies ist durch Festlegen von **ApplyDefaultSort** auf **true** oder mithilfe der **Sort**\-Eigenschaft möglich.  Wenn keine Sortierreihenfolge angegeben wurde, wird eine Ausnahme ausgelöst.  
  
 Die **Find**\-Methode und die **FindRows**\-Methode akzeptieren ein Array von Werten als Eingabe, dessen Länge der Anzahl der Spalten in der Sortierreihenfolge entspricht.  Wenn eine einzelne Spalte sortiert wird, kann ein einzelner Wert übergeben werden.  Wenn eine Sortierreihenfolge mehrere Spalten enthält, wird ein Objektarray übergeben.  Beachten Sie, dass bei einem Sortiervorgang für mehrere Spalten die Werte im Objektarray mit der in der **Sort**\-Eigenschaft von **DataView** angegebenen Reihenfolge übereinstimmen muss.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie die **Find**\-Methode für eine **DataView** mit einer Sortierreihenfolge für eine einzelne Spalte aufgerufen wird.  
  
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
  
 Wenn die **Sort**\-Eigenschaft mehrere Spalten angibt, muss ein Objektarray mit den Suchwerten für jede Spalte in der von der **Sort**\-Eigenschaft angegebenen Sortierreihenfolge übergeben werden. Dies wird im folgenden Codebeispiel veranschaulicht.  
  
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
  
## Siehe auch  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)