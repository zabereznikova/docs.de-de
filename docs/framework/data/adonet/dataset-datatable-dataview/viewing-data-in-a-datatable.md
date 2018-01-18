---
title: Anzeigen von Daten in einer "DataTable"
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
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2576c95ad7739d28e2ca822fd13fb6f176900814
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="viewing-data-in-a-datatable"></a>Anzeigen von Daten in einer "DataTable"
Sie erreichen den Inhalt des eine <xref:System.Data.DataTable> mithilfe der **Zeilen** und **Spalten** Sammlungen von der **DataTable**. Sie können auch die <xref:System.Data.DataTable.Select%2A> -Methode zum Zurückgeben von Teilmengen der Daten in einer **DataTable** gemäß bestimmten Kriterien einschließlich Suchkriterien, Sortierreihenfolge und Zeilenstatus. Darüber hinaus können Sie die <xref:System.Data.DataRowCollection.Find%2A> Methode der **DataRowCollection** bei der Suche nach einer bestimmten Zeile einen primären Schlüsselwert verwenden.  
  
 Die **wählen** Methode der **DataTable** Objekt gibt eine Menge von <xref:System.Data.DataRow> Objekte, die den angegebenen Kriterien entsprechen. **Wählen Sie** verwendet optionale Argumente eines Filterausdrucks, Sortierausdrucks und **"DataViewRowState"**. Der Filterausdruck gibt, welche Zeilen basierend auf zurückzugebenden **DataColumn** Werte, z. B. `LastName = 'Smith'`. Der Sortierausdruck folgt den Standard-SQL-Konventionen für die Anordnung von Spalten, z. B. `LastName ASC, FirstName ASC`. Regeln zum Schreiben von Ausdrücken finden Sie unter der <xref:System.Data.DataColumn.Expression%2A> Eigenschaft von der **DataColumn** Klasse.  
  
> [!TIP]
>  Wenn Sie eine Anzahl von Aufrufen zum Ausführen der **wählen** Methode eine **DataTable**, können Sie die Leistung erhöhen, indem Sie zunächst eine <xref:System.Data.DataView> für die **DataTable**. Erstellen der **"DataView"** die Zeilen der Tabelle indiziert. Die **wählen** Methode anschließend Hintergrundverarbeitungsmodus, die indiziert werden, erheblich reduziert die Zeit, um das Abfrageergebnis zu erzeugen. Weitere Informationen zum Erstellen einer **"DataView"** für eine **DataTable**, finden Sie unter ["DataViews"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 Die **wählen** Methode bestimmt, welche Version der Zeilen, die angezeigt oder bearbeitet anhand einer <xref:System.Data.DataViewRowState>. Die folgende Tabelle beschreibt die möglichen **"DataViewRowState"** Enumerationswerte.  
  
|"DataViewRowState"-Wert|Beschreibung|  
|----------------------------|-----------------|  
|**CurrentRows**|Aktuelle Zeilen, einschließlich nicht geänderter, hinzugefügter und geänderter Zeilen.|  
|**Gelöscht**|Eine gelöschte Zeile.|  
|**ModifiedCurrent**|Eine aktuelle Version, die eine geänderte Version der ursprünglichen Daten darstellt. (Siehe **ModifiedOriginal**.)|  
|**ModifiedOriginal**|Die ursprüngliche Version aller geänderten Zeilen. Die aktuelle Version ist verfügbar mit **ModifiedCurrent**.|  
|**Hinzugefügt**|Eine neue Zeile.|  
|**Keine**|Keine|  
|**OriginalRows**|Ursprüngliche Zeilen, einschließlich nicht geänderter und gelöschter Zeilen.|  
|**Unverändert**|Eine nicht geänderte Zeile.|  
  
 Im folgenden Beispiel die **DataSet** Objekt gefiltert, sodass nur Zeilen, deren Arbeit mit **"DataViewRowState"** festgelegt ist, um **CurrentRows**.  
  
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
  
 Die **wählen** Methode kann verwendet werden, um Zeilen mit abweichenden zurückgeben **RowState** -Werten oder Feldwerten. Das folgende Beispiel gibt eine **DataRow** Array, das alle Zeilen verweist, wurde gelöscht, und eine andere **DataRow** Array, das alle Zeilen verweist, geordnet nach **CustLName**, wobei die **CustID** Spalte ist größer als 5. Informationen zum Anzeigen der Informationen in den **gelöschte** Zeile, finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
