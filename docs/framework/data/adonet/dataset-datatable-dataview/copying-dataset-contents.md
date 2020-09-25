---
title: Kopieren von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: 1cadcacab6084bbf3caaf61d98b78fe3067d92f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202369"
---
# <a name="copying-dataset-contents"></a>Kopieren von DataSet-Inhalten

Sie können eine Kopie von erstellen, <xref:System.Data.DataSet> damit Sie mit Daten arbeiten können, ohne dass sich dies auf die ursprünglichen Daten auswirkt, oder mit einer Teilmenge der Daten aus einem **DataSet**arbeiten. Beim Kopieren eines **DataSets**können Sie folgende Aktionen ausführen:  
  
- Erstellen Sie eine exakte Kopie des **DataSets**, einschließlich Schema, Daten, Zeilen Zustandsinformationen und Zeilen Versionen.  
  
- Erstellen Sie ein **DataSet** , das das Schema eines vorhandenen **DataSets**enthält, aber nur Zeilen, die geändert wurden. Sie können alle geänderten Zeilen oder einen bestimmten **DataRowState**-Wert zurückgeben. Weitere Informationen zu Zeilen Zuständen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).  
  
- Kopieren Sie das Schema oder die relationale Struktur des **DataSets** nur, ohne Zeilen zu kopieren. Zeilen können mit <xref:System.Data.DataTable> in eine vorhandene <xref:System.Data.DataTable.ImportRow%2A> importiert werden.  
  
 Verwenden Sie die- **DataSet** <xref:System.Data.DataSet.Copy%2A> Methode des **DataSets**, um eine exakte Kopie des Datasets zu erstellen, das sowohl das Schema als auch die Daten enthält. Im folgenden Codebeispiel wird gezeigt, wie eine exakte Kopie des **DataSets**erstellt wird.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Verwenden **Modified**Sie die-Methode des Datasets, um eine Kopie eines **DataSets** zu erstellen, das Schema und nur die Daten enthält, die **hinzugefügte**, geänderte oder **Gelöschte** Zeilen darstellen <xref:System.Data.DataSet.GetChanges%2A> . **DataSet** Sie können **GetChanges** auch verwenden, um nur Zeilen mit einem angegebenen Zeilen Status zurückzugeben, indem Sie beim Aufrufen von **GetChanges**einen **DataRowState** -Wert übergeben. Im folgenden Codebeispiel wird gezeigt, wie ein **DataRowState** beim Aufrufen von **GetChanges**übergeben wird.  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 Um eine Kopie eines **DataSets** zu erstellen, das nur das Schema enthält, verwenden Sie die- <xref:System.Data.DataSet.Clone%2A> Methode des **DataSets**. Sie können dem geklonten **DataSet** auch vorhandene Zeilen mithilfe der **ImportRow** -Methode der **Daten**Tabelle hinzufügen. **ImportRow** fügt der angegebenen Tabelle Informationen zu Daten, Zeilen Status und Zeilen Version hinzu. Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.  
  
 Im folgenden Codebeispiel wird ein Klon eines **DataSets** erstellt, und anschließend werden die Zeilen aus dem ursprünglichen **DataSet** der **Customers** -Tabelle im **DataSet** -Klon für Kunden hinzugefügt, wobei die **CountryRegion** -Spalte den Wert "Germany" hat.  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
