---
title: Kopieren von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: b85fb6ebf56b110330be121c87d2492b0cfac536
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401943"
---
# <a name="copying-dataset-contents"></a>Kopieren von DataSet-Inhalten
Sie können eine Kopie erstellen eine <xref:System.Data.DataSet> , damit Sie ohne Auswirkungen auf die ursprünglichen Daten mit Daten arbeiten können, oder Arbeiten mit einer Teilmenge der Daten aus einer **DataSet**. Beim Kopieren einer **DataSet**, können Sie:  
  
-   Erstellen Sie eine genaue Kopie der **DataSet**, einschließlich Schema, Daten, Informationen zum Zeilenstatus und Zeilenversionen.  
  
-   Erstellen Sie eine **DataSet** , enthält das Schema einer vorhandenen **DataSet**, aber nur die Zeilen, die geändert wurden. Sie können alle Zeilen zurückgeben, die geändert wurden, oder geben Sie einen bestimmten **DataRowState**. Weitere Informationen zum Zeilenstatus finden Sie unter [Zeilenstatus und Zeilenversionen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Kopieren Sie das Schema oder die relationale Struktur von den **DataSet** , ohne dass alle Zeilen kopiert. Zeilen können mit <xref:System.Data.DataTable> in eine vorhandene <xref:System.Data.DataTable.ImportRow%2A> importiert werden.  
  
 Erstellen Sie eine genaue Kopie der **DataSet** , die sowohl Schema-als auch Daten enthält, verwenden Sie die <xref:System.Data.DataSet.Copy%2A> -Methode der der **DataSet**. Im folgenden Codebeispiel wird veranschaulicht, wie erstellen Sie eine genaue Kopie der **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Erstellen Sie eine Kopie des eine **DataSet** , umfasst, Schema und nur die Daten darstellt **Added**, **"geändert"**, oder **gelöschte** Zeilen: Verwenden Sie die <xref:System.Data.DataSet.GetChanges%2A> Methode der **DataSet**. Können Sie auch **GetChanges** zurückzugebenden nur Zeilen mit einem bestimmten Zeilenstatus durch Übergeben einer **DataRowState** Wert beim Aufruf von **GetChanges**. Im folgenden Codebeispiel wird veranschaulicht, wie zum Übergeben einer **DataRowState** beim Aufrufen von **GetChanges**.  
  
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
  
 Erstellen Sie eine Kopie einer **DataSet** , nur die Schemas enthält, verwenden Sie die <xref:System.Data.DataSet.Clone%2A> -Methode der der **DataSet**. Sie können auch vorhandene Zeilen hinzufügen, auf die geklonte **DataSet** mithilfe der **ImportRow** Methode der **DataTable**. **ImportRow** Daten, die Zeile (Zustand) und die Versionsinformationen für die Zeile auf die angegebene Tabelle hinzugefügt. Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.  
  
 Das folgende Codebeispiel erstellt einen Klon des eine **DataSet** und fügt dann die Zeilen aus der ursprünglichen **DataSet** auf die **Kunden** -Tabelle in der **DataSet**  -Klon für Kunden, in denen die **CountryRegion** Spalte hat den Wert "Germany".  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
