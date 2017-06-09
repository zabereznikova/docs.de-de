---
title: "Kopieren von DataSet-Inhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Kopieren von DataSet-Inhalten
Sie können eine Kopie von <xref:System.Data.DataSet> erstellen. So können Sie mit den Daten arbeiten, ohne dass die ursprünglichen Daten beeinflusst werden, oder Sie können mit einer Teilmenge der Daten aus einem **DataSet** arbeiten.  Beim Kopieren eines **DataSet** verfügen Sie über folgende Optionen:  
  
-   Sie können eine exakte Kopie des **DataSet** erstellen, einschließlich Schema, Daten, Informationen zum Zeilenstatus und Zeilenversionen.  
  
-   Erstellen Sie ein **DataSet**, in dem das Schema eines vorhandenen **DataSet** enthalten ist. Es sollen aber nur Zeilen vorhanden sein, die bereits geändert wurden.  Sie können alle Zeilen zurückgeben, die geändert wurden, oder Sie geben einen bestimmten **DataRowState** an.  Weitere Informationen zum Zeilenstatus finden Sie unter [Zeilenstatus und Zeilenversion](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
-   Sie kopieren nur das Schema oder die relationale Struktur des **DataSet**, ohne die darin enthaltenen Zeilen zu kopieren.  Zeilen können mit <xref:System.Data.DataTable.ImportRow%2A> in eine vorhandene <xref:System.Data.DataTable> importiert werden.  
  
 Verwenden Sie die <xref:System.Data.DataSet.Copy%2A>\-Methode des **DataSet** zum Erstellen einer exakten Kopie des **DataSet**, die sowohl das Schema als auch die Daten enthält.  Das folgende Codebeispiel veranschaulicht die Erstellung einer exakten Kopie des **DataSet**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Um eine Kopie eines **DataSet** zu erstellen, die das Schema und nur Daten der Zeilen mit dem Status **Added**, **Modified** oder **Deleted** enthält, verwenden Sie die <xref:System.Data.DataSet.GetChanges%2A>\-Methode des **DataSet**.  Sie können mit **GetChanges** auch nur Zeilen mit einem bestimmten Zeilenstatus zurückgeben, indem Sie beim Aufrufen von **GetChanges** einen **DataRowState**\-Wert übergeben.  Im folgenden Codebeispiel wird gezeigt, wie beim Aufrufen von **GetChanges** ein  **DataRowState**\-Wert übergeben wird.  
  
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
  
 Verwenden Sie die <xref:System.Data.DataSet.Clone%2A>\-Methode des **DataSet** zum Erstellen einer Kopie eines **DataSet**, die nur das Schema enthält.  Sie können dem geklonten **DataSet** mithilfe der **ImportRow**\-Methode der **DataTable** auch vorhandene Zeilen hinzufügen.  **ImportRow** fügt der angegebenen Tabelle Daten, den Zeilenstatus sowie Versionsinformationen hinzu.  Spaltenwerte werden nur hinzugefügt, wenn der Spaltenname übereinstimmt und der Datentyp kompatibel ist.  
  
 Im folgenden Codebeispiel wird zunächst ein Klon eines **DataSet** erstellt. Anschließend werden die Zeilen aus dem ursprünglichen **DataSet** der **Customers**\-Tabelle im **DataSet**\-Klon für Kunden hinzugefügt, deren **CountryRegion**\-Spalte den Wert "Germany" hat.  
  
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
  
## Siehe auch  
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)