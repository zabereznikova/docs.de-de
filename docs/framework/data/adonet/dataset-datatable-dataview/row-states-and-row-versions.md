---
title: "Zeilenstatus und Zeilenversion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Zeilenstatus und Zeilenversion
ADO.NET verwaltet Zeilen in Tabellen mithilfe des Zeilenstatus und der Zeilenversion.  Ein Zeilenstatus gibt den Status einer Zeile an. In Zeilenversionen werden die Werte, die in einer Zeile gespeichert werden, während der Bearbeitung verwaltet. Zu diesen Werten zählen z. B. die Werte **current**, **original** und **default**.  Wenn Sie beispielsweise eine Spalte in einer Zeile geändert haben, weist die Zeile den Zeilenstatus `Modified` und die folgenden beiden Zeilenversionen auf: `Current` mit den aktuellen Zeilenwerten und `Original` mit den Zeilenwerten vor den Änderungen der Spalte.  
  
 Jedes <xref:System.Data.DataRow>\-Objekt hat eine <xref:System.Data.DataRow.RowState%2A>\-Eigenschaft, über die Sie den aktuellen Status der Zeile überprüfen können.  Die folgende Tabelle enthält eine kurze Beschreibung aller `RowState`\-Enumerationswerte.  
  
|"RowState"\-Wert|Beschreibung|  
|----------------------|------------------|  
|<xref:System.Data.DataRowState>|Seit dem letzten Aufruf von `AcceptChanges` oder seit der Erstellung der Zeile durch `DataAdapter.Fill` wurden keine Änderungen ausgeführt.|  
|<xref:System.Data.DataRowState>|Die Zeile wurde der Tabelle hinzugefügt, `AcceptChanges` wurde aber nicht aufgerufen.|  
|<xref:System.Data.DataRowState>|Ein Element der Zeile wurde geändert.|  
|<xref:System.Data.DataRowState>|Die Zeile wurde aus einer Tabelle gelöscht, und `AcceptChanges` wurde nicht aufgerufen.|  
|<xref:System.Data.DataRowState>|Die Zeile ist nicht Teil einer `DataRowCollection`.  Der `RowState` einer neu erstellten Zeile wird auf `Detached` festgelegt.  Nach dem Hinzufügen der neuen `DataRow` zur `DataRowCollection` durch Aufrufen der `Add`\-Methode wird der Wert der `RowState`\-Eigenschaft auf `Added` festgelegt.<br /><br /> `Detached` wird auch für eine Zeile festgelegt, die mit der `Remove`\-Methode bzw. mit der `Delete`\-Methode, gefolgt von der `AcceptChanges`\-Methode, aus einer `DataRowCollection` entfernt wurde.|  
  
 Wenn `AcceptChanges` für einen <xref:System.Data.DataSet>, eine <xref:System.Data.DataTable> oder eine <xref:System.Data.DataRow> aufgerufen wird, werden alle Zeilen mit dem Zeilenstatus `Deleted` entfernt.  Die verbleibenden Zeilen erhalten den Zeilenstatus `Unchanged`, und die Werte in der Zeilenversion `Original` werden mit den Werten der Zeilenversion `Current` überschrieben.  Wenn `RejectChanges` aufgerufen wird, werden alle Zeilen mit dem Zeilenstatus `Added` entfernt.  Die verbleibenden Zeilen erhalten den Zeilenstatus `Unchanged`, und die Werte in der Zeilenversion `Current` werden mit den Werten der Zeilenversion `Original` überschrieben.  
  
 Sie können die verschiedenen Zeilenversionen einer Zeile anzeigen, indem Sie einen <xref:System.Data.DataRowVersion>\-Parameter mit dem Spaltenverweis übergeben. Dies wird im folgenden Beispiel dargestellt.  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 Die folgende Tabelle enthält eine kurze Beschreibung aller `DataRowVersion`\-Enumerationswerte.  
  
|"DataRowVersion"\-Wert|Beschreibung|  
|----------------------------|------------------|  
|<xref:System.Data.DataRowVersion>|Die aktuellen Werte der Zeile.  Diese Zeilenversion ist für Zeilen, deren `RowState` auf `Deleted` festgelegt ist, nicht vorhanden.|  
|<xref:System.Data.DataRowVersion>|Die Standardzeilenversion einer bestimmten Zeile.  Die Standardzeilenversion für eine Zeile mit dem Status `Added`, `Modified` oder `Unchanged` lautet `Current`.  Die Standardzeilenversion für eine Zeile mit dem Status `Deleted` lautet `Original`.  Die Standardzeilenversion für eine Zeile mit dem Status `Detached` lautet `Proposed`.|  
|<xref:System.Data.DataRowVersion>|Die ursprünglichen Werte der Zeile.  Diese Zeilenversion ist für Zeilen, deren `RowState` auf `Added` festgelegt ist, nicht vorhanden.|  
|<xref:System.Data.DataRowVersion>|Die vorgeschlagenen Werte für die Zeile.  Diese Zeilenversion ist während der Bearbeitung einer Zeile vorhanden oder wird für Zeilen verwendet, die nicht Teil einer `DataRowCollection` sind.|  
  
 Sie können überprüfen, ob eine `DataRow` eine bestimmte Zeilenversion aufweist, indem Sie die <xref:System.Data.DataRow.HasVersion%2A>\-Methode aufrufen und eine `DataRowVersion` als Argument übergeben.  So gibt z. B. `DataRow.HasVersion(DataRowVersion.Original)` für neu hinzugefügte Zeilen vor dem Aufrufen von `AcceptChanges` den Wert `false` zurück.  
  
 Im folgenden Codebeispiel werden die Werte in allen gelöschten Zeilen einer Tabelle angezeigt.  `Deleted`\-Zeilen haben keine `Current`\-Zeilenversion. Deshalb müssen Sie beim Zugriff auf die Spaltenwerte `DataRowVersion.Original` übergeben.  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## Siehe auch  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [DataAdapter und DataReader](../../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)