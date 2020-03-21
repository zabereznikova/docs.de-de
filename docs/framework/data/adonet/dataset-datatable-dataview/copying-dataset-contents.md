---
title: Kopieren von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151363"
---
# <a name="copying-dataset-contents"></a>Kopieren von DataSet-Inhalten
Sie können eine Kopie <xref:System.Data.DataSet> eines erstellen, sodass Sie mit Daten arbeiten können, ohne die ursprünglichen Daten zu beeinflussen, oder mit einer Teilmenge der Daten aus einem **DataSet**arbeiten. Beim Kopieren eines **DataSets**können Sie:  
  
- Erstellen Sie eine exakte Kopie des **DataSet**, einschließlich des Schemas, der Daten, der Zeilenstatusinformationen und der Zeilenversionen.  
  
- Erstellen Sie ein **DataSet,** das das Schema eines vorhandenen **DataSets**enthält, jedoch nur Zeilen, die geändert wurden. Sie können alle geänderten Zeilen zurückgeben oder einen bestimmten **DataRowState**angeben. Weitere Informationen zu Zeilenzuständen finden Sie unter [Zeilenzustände und Zeilenversionen](row-states-and-row-versions.md).  
  
- Kopieren Sie nur das Schema oder die relationale Struktur des **DataSets,** ohne Zeilen zu kopieren. Zeilen können mit <xref:System.Data.DataTable> in eine vorhandene <xref:System.Data.DataTable.ImportRow%2A> importiert werden.  
  
 Um eine exakte Kopie des **DataSets** zu erstellen, <xref:System.Data.DataSet.Copy%2A> das sowohl Schema als auch Daten enthält, verwenden Sie die Methode des **DataSet**. Das folgende Codebeispiel zeigt, wie Sie eine exakte Kopie des **DataSet**erstellen.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Verwenden Sie die Methode des **DataSet,** um eine Kopie eines **DataSets** zu <xref:System.Data.DataSet.GetChanges%2A> erstellen, das schemas und nur die Daten enthält, die **Added**, **Modified**oder **Deleted** rows darstellen. Verwenden Sie die Methode des DataSet . Sie können **GetChanges** auch verwenden, um nur Zeilen mit einem angegebenen Zeilenstatus zurückzugeben, indem Sie beim Aufrufen von **GetChanges**einen **DataRowState-Wert** übergeben. Das folgende Codebeispiel zeigt, wie ein **DataRowState** beim Aufrufen von **GetChanges**übergeben wird.  
  
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
  
 Um eine Kopie eines **DataSets** zu erstellen, <xref:System.Data.DataSet.Clone%2A> die nur Schema enthält, verwenden Sie die Methode des **DataSet**. Sie können dem geklonten **DataSet** auch vorhandene Zeilen hinzufügen, indem Sie die **ImportRow-Methode** der **DataTable**verwenden. **ImportRow** fügt der angegebenen Tabelle Daten-, Zeilenstatus- und Zeilenversionsinformationen hinzu. Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.  
  
 Im folgenden Codebeispiel wird ein Klon eines **DataSets** erstellt und dann die Zeilen aus dem ursprünglichen **DataSet** zur **Tabelle Customers** im **DataSet-Klon** für Kunden hinzugefügt, bei denen die **Spalte CountryRegion** den Wert "Deutschland" hat.  
  
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
