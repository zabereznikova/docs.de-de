---
title: "Anzeigen von Daten in einer &#39;DataTable&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Anzeigen von Daten in einer &#39;DataTable&#39;
Mithilfe der **Rows**\-Auflistung und der **Columns**\-Auflistung der **DataTable** können Sie auf die Inhalte einer <xref:System.Data.DataTable> zugreifen.  Sie können auch die <xref:System.Data.DataTable.Select%2A>\-Methode verwenden, um Teilmengen der Daten in einer **DataTable** gemäß bestimmten Kriterien einschließlich Suchkriterien, Sortierreihenfolge und Zeilenstatus zurückzugeben.  Außerdem können Sie die <xref:System.Data.DataRowCollection.Find%2A>\-Methode der **DataRowCollection** verwenden, wenn Sie mithilfe eines Primärschlüsselwerts nach einer bestimmten Zeile suchen.  
  
 Die **Select**\-Methode des **DataTable**\-Objekts gibt eine Gruppe von <xref:System.Data.DataRow>\-Objekten zurück, die den angegebenen Kriterien entsprechen.  **Select** verwendet optionale Argumente eines Filterausdrucks, eines Sortierausdrucks und von **DataViewRowState**.  Der Filterausdruck gibt anhand von **DataColumn**\-Werten \(z. B. `LastName = 'Smith'`\) an, welche Zeilen zurückgegeben werden sollen.  Der Sortierausdruck folgt den Standard\-SQL\-Konventionen für die Anordnung von Spalten, z. B. `LastName ASC, FirstName ASC`.  Informationen zu Regeln für das Schreiben von Ausdrücken finden Sie in der Beschreibung der <xref:System.Data.DataColumn.Expression%2A>\-Eigenschaft der **DataColumn**\-Klasse.  
  
> [!TIP]
>  Wenn Sie die **Select**\-Methode einer **DataTable** mehrmals aufrufen möchten, können Sie eine Leistungssteigerung erzielen, indem Sie zuerst eine <xref:System.Data.DataView> für die **DataTable** erstellen.  Durch das Erstellen der **DataView** werden die Zeilen der Tabelle indiziert.  Die **Select**\-Methode nutzt dann diesen Index, wodurch die Zeit zum Generieren des Abfrageergebnisses deutlich verkürzt wird.  Weitere Informationen zum Erstellen einer **DataView** für eine **DataTable** finden Sie unter [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 Die **Select**\-Methode bestimmt anhand eines <xref:System.Data.DataViewRowState>, welche Version der Zeilen angezeigt oder bearbeitet werden soll.  In der folgenden Tabelle werden die möglichen **DataViewRowState**\-Enumerationswerte aufgeführt.  
  
|"DataViewRowState"\-Wert|Beschreibung|  
|------------------------------|------------------|  
|**CurrentRows**|Aktuelle Zeilen, einschließlich nicht geänderter, hinzugefügter und geänderter Zeilen.|  
|**Deleted**|Eine gelöschte Zeile.|  
|**ModifiedCurrent**|Eine aktuelle Version, die eine geänderte Version der ursprünglichen Daten darstellt.  \(Siehe **ModifiedOriginal**.\)|  
|**ModifiedOriginal**|Die ursprüngliche Version aller geänderten Zeilen.  Die aktuelle Version kann über **ModifiedCurrent** abgerufen werden.|  
|**Added**|Eine neue Zeile.|  
|**Keine**|Keine|  
|**OriginalRows**|Ursprüngliche Zeilen, einschließlich nicht geänderter und gelöschter Zeilen.|  
|**Unchanged**|Eine nicht geänderte Zeile.|  
  
 Im folgenden Beispiel wird das **DataSet**\-Objekt gefiltert, sodass nur Zeilen angezeigt werden, deren **DataViewRowState** auf **CurrentRows** festgelegt ist.  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 Mithilfe der **Select**\-Methode können Zeilen mit abweichenden **RowState**\-Werten oder Feldwerten zurückgegeben werden.  Im folgenden Beispiel wird ein **DataRow**\-Array zurückgegeben, das auf alle gelöschten Zeilen verweist, und es wird ein anderes **DataRow**\-Array zurückgegeben, das auf alle Zeilen \(geordnet nach **CustLName**\) verweist, in denen die **CustID**\-Spalte größer als 5 ist.  Weitere Informationen zum Anzeigen von Informationen in der Zeile **Deleted** finden Sie unter [Zeilenstatus und Zeilenversion](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## Siehe auch  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataViewRowState>   
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Zeilenstatus und Zeilenversion](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)